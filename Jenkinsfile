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
                        sh "npm run test"
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
                docker "5gsystems/node-sonar-scanner"
            }

            when {
                branch "master"
            }

            steps {
                withSonarQubeEnv("sonar.jmerle.dev") {
                    sh "sonar-scanner"
                }
            }
        }
    }
}
