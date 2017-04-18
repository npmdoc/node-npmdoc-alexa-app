# npmdoc-alexa-app

#### api documentation for  [alexa-app (v4.0.0)](https://github.com/alexa-js/alexa-app#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-alexa-app.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-alexa-app) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-alexa-app.svg)](https://travis-ci.org/npmdoc/node-npmdoc-alexa-app)

#### A module to simplify creation of Alexa (Amazon Echo) apps (Skills) using Node.js

[![NPM](https://nodei.co/npm/alexa-app.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/alexa-app)

- [https://npmdoc.github.io/node-npmdoc-alexa-app/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-alexa-app/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-alexa-app/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-alexa-app/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-alexa-app/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-alexa-app/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Matt Kruse",
        "url": "http://mattkruse.com"
    },
    "bugs": {
        "url": "https://github.com/alexa-js/alexa-app/issues"
    },
    "dependencies": {
        "alexa-utterances": "^0.2.0",
        "alexa-verifier-middleware": "^0.2.1",
        "bluebird": "^2.10.2",
        "body-parser": "^1.15.2",
        "lodash.defaults": "^4.2.0",
        "numbered": "^1.0.0"
    },
    "description": "A module to simplify creation of Alexa (Amazon Echo) apps (Skills) using Node.js",
    "devDependencies": {
        "chai": "^3.4.1",
        "chai-as-promised": "^5.3.0",
        "chai-string": "^1.3.0",
        "coveralls": "^2.11.9",
        "danger": "0.6.10",
        "ejs": "^2.5.5",
        "eslint": "^2.9.0",
        "esprima": "^3.1.3",
        "express": "^4.14.0",
        "istanbul": "^0.4.3",
        "mocha": "^2.3.4",
        "sinon": "^1.17.7",
        "sinon-chai": "^2.8.0",
        "supertest": "^2.0.1"
    },
    "directories": {},
    "dist": {
        "shasum": "9b74cc6e86dd6728ca6f1fa4b25a1bb397896283",
        "tarball": "https://registry.npmjs.org/alexa-app/-/alexa-app-4.0.0.tgz"
    },
    "engines": {
        "node": ">=0.12"
    },
    "gitHead": "8147e90ead97b1bf6bcae15d2a7f18c28456b707",
    "homepage": "https://github.com/alexa-js/alexa-app#readme",
    "keywords": [
        "amazon",
        "echo",
        "alexa",
        "skills"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "ajcrites"
        },
        {
            "name": "dblock"
        },
        {
            "name": "mkruse"
        }
    ],
    "name": "alexa-app",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/alexa-js/alexa-app.git"
    },
    "scripts": {
        "coverage": "istanbul cover _mocha -- -R spec",
        "danger": "danger",
        "lint": "eslint index.js;",
        "test": "mocha",
        "test-with-coverage": "./node_modules/istanbul/lib/cli.js cover ./node_modules/mocha/bin/_mocha -- -R spec ./test/*.js"
    },
    "version": "4.0.0"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
