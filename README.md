# Angular Jenkins Sonar

[![Build Status](https://jenkins.jmerle.dev/buildStatus/icon?job=angular-jenkins-sonar%2Fmaster)](https://jenkins.jmerle.dev/job/angular-jenkins-sonar/job/master/)
[![Quality Gate Status](https://sonar.jmerle.dev/api/project_badges/measure?project=jmerle%3Aangular-jenkins-sonar&metric=alert_status)](https://sonar.jmerle.dev/dashboard?id=jmerle%3Aangular-jenkins-sonar)
[![Coverage](https://sonar.jmerle.dev/api/project_badges/measure?project=jmerle%3Aangular-jenkins-sonar&metric=coverage)](https://sonar.jmerle.dev/dashboard?id=jmerle%3Aangular-jenkins-sonar)
[![Bugs](https://sonar.jmerle.dev/api/project_badges/measure?project=jmerle%3Aangular-jenkins-sonar&metric=bugs)](https://sonar.jmerle.dev/dashboard?id=jmerle%3Aangular-jenkins-sonar)
[![Vulnerabilities](https://sonar.jmerle.dev/api/project_badges/measure?project=jmerle%3Aangular-jenkins-sonar&metric=vulnerabilities)](https://sonar.jmerle.dev/dashboard?id=jmerle%3Aangular-jenkins-sonar)

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.3.8.

This is a little playground to get Angular working with Jenkins as build server and SonarQube for static code analysis with code coverage reporting.

## Changes

Here are the changes that were made to the standard angular-cli project:
- Prettier has been added with some additional tools: `npm i -D husky lint-staged prettier tslint-config-prettier prettier-check`
- The `package.json` file has been updated with new `test:coverage`, `lint`, `lint:fix` and `prettier` commands, and with `husky`, `lint-staged` and `prettier` configuration
- The `tslint.json` file has been updated to extend `tslint-config-prettier`
- The `Jenkinsfile` file has been added with the Jenkins pipeline configuration
- The `.editorconfig` file has been updated with Jenkinsfile configuration
- The `is-ci` package has been added to detect whether we're running in a build environment or not
- The `src/karma.conf.js` and the `e2e/protractor.conf.js` files have been updated to make tests run successfully in a Docker container
- The `karma-sonarqube-reporter` has been added to record test execution data in SonarQube's format
- The `src/karma.conf.js` file has been updated to record test execution data when running tests with coverage reporting
- The `README.md` file has been updated with Jenkins and SonarQube badges
- The `sonar-project.properties` file has been added with Sonar Scanner configuration
- The `src/app/app-routing.module.spec.ts` file has been added to achieve 100% test coverage

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
