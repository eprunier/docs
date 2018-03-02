<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Package management](#package-management)
  - [NPM](#npm)
  - [Yarn](#yarn)
- [Development](#development)
  - [Functional programming](#functional-programming)
  - [Web](#web)
  - [Mobile](#mobile)
  - [RDBMS](#rdbms)
  - [CLI](#cli)
    - [Args](#args)
    - [Colors](#colors)
    - [Console application dev](#console-application-dev)
  - [XML](#xml)
  - [Crypto](#crypto)
  - [GraphQL](#graphql)
  - [Test](#test)
    - [General](#general)
    - [Web testing](#web-testing)
    - [API testing](#api-testing)
    - [Load testing](#load-testing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Package management

- [NPM](https://npmjs.org)
- [Yarn](https://yarnpkg.com)

## NPM

Using NPM behind a proxy

    npm config set proxy "<proxy_url>"
    npm config set https-proxy "<proxy_url>"

## Yarn

Using Yarn behind a proxy

    yarn config --proxy <proxy_url>
    yarn config --https-proxy <proxy_url>

# Development

## Functional programming

- [Ramda](http://ramdajs.com)
- [Crocks](https://github.com/evilsoft/crocks)

## Web

- [LoopBack](./loopback.md)
- [Express](https://expressjs.com)
- [Hapi](https://hapijs.com)
- [Koa](http://koajs.com)
- [Micro](https://github.com/zeit/micro)

- [Next.js](https://learnnextjs.com)
- [Electrode](http://electrode.io/)

## Mobile

- [Ionic](https://ionicframework.com/)
- [React Native](https://facebook.github.io/react-native/)

Comparisons:

- [Ionic vs. React Native - which framework is better for cross-platform mobile app development?](https://dzone.com/articles/ionic-vs-react-native-which-framework-is-better-fo)
- [Teact Native vs Ionic: a side-by-side comparison](https://www.codementor.io/fmcorz/react-native-vs-ionic-du1087rsw)
- [Ionic vs React Native](https://medium.com/@ankushaggarwal/ionic-vs-react-native-3eb62f8943f8)

## RDBMS

- [Sequelize](http://docs.sequelizejs.com/)

## CLI

### Args

- [yargs](https://www.npmjs.com/package/yargs)
- [minimist](https://www.npmjs.com/package/minimist)
- [commander](https://www.npmjs.com/package/commander)

### Colors

- [Chalk](https://www.npmjs.com/package/chalk)
- [Colors](https://www.npmjs.com/package/colors)

### Console application dev

- [Vorpal](https://www.npmjs.com/package/vorpal)
- [Terminal Kit](https://www.npmjs.com/package/terminal-kit)

## XML

- xmldom
- xml-crypto - XMLDSIG library

## Crypto

- [Forge](https://github.com/digitalbazaar/forge)
- [node-srp](https://github.com/mozilla/node-srp) - Secure remote password

## GraphQL

- [Prisma](https://github.com/graphcool/prisma)

## Test

### General

- [Jest](https://facebook.github.io/jest/)
- [Tape](https://github.com/substack/tape) - Read [Why I use Tape Instead of Mocha & So Should You](https://medium.com/javascript-scene/why-i-use-tape-instead-of-mocha-so-should-you-6aa105d8eaf4) by Eric Elliott
- [Mocha](https://mochajs.org/) + [Chai](http://chaijs.com/)
- [Jasmine](https://jasmine.github.io/)

### Web testing

- [PhantomJS](http://phantomjs.org/)
- [Protractor](http://www.protractortest.org)
- [Test Aramada](http://testarmada.io/)

### API testing

- [SuperTest](https://github.com/visionmedia/supertest)
- [Chai HTTP](https://github.com/chaijs/chai-http)

### Load testing

- [Artillery](https://artillery.io/)
