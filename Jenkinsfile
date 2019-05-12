pipeline {
    agent any

    stages {
        stage("Quality Assurance") {
            agent {
                docker "weboaks/node-karma-protractor-chrome:headless"
            }

            stages {
                stage("Install dependencies") {
                    steps {
                        sh "npm ci"
                    }
                }

                stage("Build") {
                    steps {
                        sh "npm run build"
                    }
                }

                stage("Lint") {
                    steps {
                        sh "npm run lint"
                    }
                }

                stage("Unit tests") {
                    steps {
                        sh "npm run test:coverage"
                        stash name: "code-coverage", includes: "coverage/angular-jenkins-sonar/lcov.info"
                    }
                }

                stage("End-to-end tests") {
                    steps {
                        sh "npm run e2e"
                    }
                }
            }
        }

        stage("Analysis") {
            agent {
                docker {
                    image "noenv/node-sonar-scanner"
                    args "--network web"
                }
            }

            when {
                branch "master"
            }

            steps {
                unstash "code-coverage"

                withSonarQubeEnv("sonar.jmerle.dev") {
                    sh "sonar-scanner -Dsonar.projectVersion=${BUILD_NUMBER}"
                }
            }
        }
    }
}
