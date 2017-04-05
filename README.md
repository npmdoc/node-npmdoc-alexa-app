# api documentation for  [alexa-app (v4.0.0)](https://github.com/alexa-js/alexa-app#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-alexa-app.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-alexa-app) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-alexa-app.svg)](https://travis-ci.org/npmdoc/node-npmdoc-alexa-app)
#### A module to simplify creation of Alexa (Amazon Echo) apps (Skills) using Node.js

[![NPM](https://nodei.co/npm/alexa-app.png?downloads=true)](https://www.npmjs.com/package/alexa-app)

[![apidoc](https://npmdoc.github.io/node-npmdoc-alexa-app/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-alexa-app_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-alexa-app/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-alexa-app/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-alexa-app/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Matt Kruse",
        "email": "github@mattkruse.com",
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
            "name": "ajcrites",
            "email": "ajcrites@gmail.com"
        },
        {
            "name": "dblock",
            "email": "dblock@dblock.org"
        },
        {
            "name": "mkruse",
            "email": "github@mattkruse.com"
        }
    ],
    "name": "alexa-app",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module alexa-app](#apidoc.module.alexa-app)
1.  [function <span class="apidocSignatureSpan">alexa-app.</span>app (name)](#apidoc.element.alexa-app.app)
1.  [function <span class="apidocSignatureSpan">alexa-app.</span>request (json)](#apidoc.element.alexa-app.request)
1.  [function <span class="apidocSignatureSpan">alexa-app.</span>response (session)](#apidoc.element.alexa-app.response)
1.  [function <span class="apidocSignatureSpan">alexa-app.</span>session (session)](#apidoc.element.alexa-app.session)
1.  object <span class="apidocSignatureSpan">alexa-app.</span>apps
1.  object <span class="apidocSignatureSpan">alexa-app.</span>to_ssml

#### [module alexa-app.to_ssml](#apidoc.module.alexa-app.to_ssml)
1.  [function <span class="apidocSignatureSpan">alexa-app.to_ssml.</span>cleanse (str)](#apidoc.element.alexa-app.to_ssml.cleanse)
1.  [function <span class="apidocSignatureSpan">alexa-app.to_ssml.</span>fromStr (str, current_ssml)](#apidoc.element.alexa-app.to_ssml.fromStr)



# <a name="apidoc.module.alexa-app"></a>[module alexa-app](#apidoc.module.alexa-app)

#### <a name="apidoc.element.alexa-app.app"></a>[function <span class="apidocSignatureSpan">alexa-app.</span>app (name)](#apidoc.element.alexa-app.app)
- description and source-code
```javascript
app = function (name) {
  if (!(this instanceof alexa.app)) {
    throw new Error("Function must be called with the new keyword");
  }

  var self = this;
  this.name = name;
  this.messages = {
    // when an intent was passed in that the application was not configured to handle
    "NO_INTENT_FOUND": "Sorry, the application didn't know what to do with that intent",
    // when an AudioPlayer event was passed in that the application was not configured to handle
    "NO_AUDIO_PLAYER_EVENT_HANDLER_FOUND": "Sorry, the application didn't know what to do with that AudioPlayer event",
    // when the app was used with 'open' or 'launch' but no launch handler was defined
    "NO_LAUNCH_FUNCTION": "Try telling the application what to do instead of opening it",
    // when a request type was not recognized
    "INVALID_REQUEST_TYPE": "Error: not a valid request",
    // when a request and response don't contain session object
    // https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference#request-body
-parameters
    "NO_SESSION": "This request doesn't support session attributes",
    // if some other exception happens
    "GENERIC_ERROR": "Sorry, the application encountered an error"
  };

  // persist session variables from every request into every response
  this.persistentSession = true;

  // use a minimal set of utterances or the full cartesian product
  this.exhaustiveUtterances = false;

  // a catch-all error handler do nothing by default
  this.error = null;

  // pre/post hooks to be run on every request
  this.pre = function( /*request, response, type*/ ) {};
  this.post = function( /*request, response, type*/ ) {};

  // a mapping of keywords to arrays of possible values, for expansion of sample utterances
  this.dictionary = {};
  this.intents = {};
  this.intent = function(intentName, schema, func) {
    if (typeof schema == "function") {
      func = schema;
      schema = null;
    }
    self.intents[intentName] = {
      "name": intentName,
      "function": func
    };
    if (schema) {
      self.intents[intentName].schema = schema;
    }
  };
  this.audioPlayerEventHandlers = {};
  this.audioPlayer = function(eventName, func) {
    self.audioPlayerEventHandlers[eventName] = {
      "name": eventName,
      "function": func
    };
  };
  this.playbackControllerEventHandlers = {};
  this.playbackController = function(eventName, func) {
    self.playbackControllerEventHandlers[eventName] = {
      "name": eventName,
      "function": func
    };
  };
  this.launchFunc = null;
  this.launch = function(func) {
    self.launchFunc = func;
  };
  this.sessionEndedFunc = null;
  this.sessionEnded = function(func) {
    self.sessionEndedFunc = func;
  };
  this.request = function(request_json) {
    var request = new alexa.request(request_json);
    var response = new alexa.response(request.getSession());
    var postExecuted = false;
    var requestType = request.type();
    var promiseChain = Promise.resolve();

    // attach Promise resolve/reject functions to the response object
    response.send = function(exception) {
      response.prepare();
      var postPromise = Promise.resolve();
      if (typeof self.post == "function" && !postExecuted) {
        postExecuted = true;
        postPromise = Promise.resolve(self.post(request, response, requestType, exception));
      }
      return postPromise.then(function() {
        if (!response.resolved) {
          response.resolved = true;
        }
        return response.response;
      });
    };
    response.fail = function(msg, exception) {
      response.prepare();
      var postPromise = Promise.resolve();
      if (typeof self.post == "function" && !postExecuted) {
        postExecuted = true;
        postPromise = Promise.resolve(self.post(request, response, requestType, exception));
      }
      return postPromise.then(function() {
        if (!response.resolved) {
          response.resolved = true;
          throw msg;
        }
        // propagate successful response if it's already been resolved ...
```
- example usage
```shell
...
### AWS Lambda

Amazon skills that use alexa-app have a built-in 'handler' method to handle calls from AWS Lambda.
You need to make sure that the Handler is set to 'index.handler', which is the default value.

'''javascript
var alexa = require("alexa-app");
var app = new alexa.app("sample");

app.intent("number", {
  "slots": { "number": "AMAZON.NUMBER" },
  "utterances": ["say the number {-|number}"]
},
function(request, response) {
  var number = request.slot("number");
...
```

#### <a name="apidoc.element.alexa-app.request"></a>[function <span class="apidocSignatureSpan">alexa-app.</span>request (json)](#apidoc.element.alexa-app.request)
- description and source-code
```javascript
request = function (json) {
  this.data = json;
  this.slot = function(slotName, defaultValue) {
    try {
      if (this.data.request.intent.slots && slotName in this.data.request.intent.slots) {
        return this.data.request.intent.slots[slotName].value;
      } else {
        return defaultValue;
      }
    } catch (e) {
      console.error("missing intent in request: " + slotName, e);
      return defaultValue;
    }
  };
  this.type = function() {
    if (!(this.data && this.data.request && this.data.request.type)) {
      console.error("missing request type:", this.data);
      return;
    }
    return this.data.request.type;
  };
  this.isAudioPlayer = function() {
    var requestType = this.type();
    return (requestType && 0 === requestType.indexOf("AudioPlayer."));
  };
  this.isPlaybackController = function() {
    var requestType = this.type();
    return (requestType && 0 === requestType.indexOf("PlaybackController."));
  };

  this.userId = null;
  this.applicationId = null;
  this.context = null;

  if (this.data.context) {
    this.userId = this.data.context.System.user.userId;
    this.applicationId = this.data.context.System.application.applicationId;
    this.context = this.data.context;
  }

  var session = new alexa.session(json.session);
  this.hasSession = function() {
    return session.isAvailable();
  };
  this.getSession = function() {
    return session;
  };

  // legacy code below
  // @deprecated
  this.sessionDetails = this.getSession().details;
  // @deprecated
  this.sessionId = this.getSession().sessionId;
  // @deprecated
  this.sessionAttributes = this.getSession().attributes;
  // @deprecated
  this.isSessionNew = this.hasSession() ? this.getSession().isNew() : false;
  // @deprecated
  this.session = function(key) {
    return this.getSession().get(key);
  };
}
```
- example usage
```shell
...
    response.say("You asked for the number " + number);
  }
);

// setup the alexa app and attach it to express before anything else
app.express({ expressApp: express_app });

// now POST calls to /sample in express will be handled by the app.request() function
// GET calls will not be handled

// from here on, you can setup any other express routes or middleware as normal
'''

The express function accepts the following parameters.
...
```

#### <a name="apidoc.element.alexa-app.response"></a>[function <span class="apidocSignatureSpan">alexa-app.</span>response (session)](#apidoc.element.alexa-app.response)
- description and source-code
```javascript
response = function (session) {
  var self = this;
  this.resolved = false;
  this.response = {
    "version": "1.0",
    "response": {
      "directives": [],
      "shouldEndSession": true
    }
  };
  this.say = function(str) {
    if (typeof this.response.response.outputSpeech == "undefined") {
      this.response.response.outputSpeech = {
        "type": "SSML",
        "ssml": SSML.fromStr(str)
      };
    } else {
      // append str to the current outputSpeech, stripping the out speak tag
      this.response.response.outputSpeech.ssml = SSML.fromStr(str, this.response.response.outputSpeech.ssml);
    }
    return this;
  };
  this.clear = function( /*str*/ ) {
    this.response.response.outputSpeech = {
      "type": "SSML",
      "ssml": SSML.fromStr("")
    };
    return this;
  };
  this.reprompt = function(str) {
    if (typeof this.response.response.reprompt == "undefined") {
      this.response.response.reprompt = {
        "outputSpeech": {
          "type": "SSML",
          "ssml": SSML.fromStr(str)
        }
      };
    } else {
      // append str to the current outputSpeech, stripping the out speak tag
      this.response.response.reprompt.outputSpeech.ssml = SSML.fromStr(str, this.response.response.reprompt.outputSpeech.text);
    }
    return this;
  };
  this.card = function(oCard) {
    if (2 == arguments.length) { // backwards compat
      oCard = {
        type: "Simple",
        title: arguments[0],
        content: arguments[1]
      };
    }

    var requiredAttrs = [],
      clenseAttrs = [];

    switch (oCard.type) {
      case 'Simple':
        requiredAttrs.push('content');
        clenseAttrs.push('content');
        break;
      case 'Standard':
        requiredAttrs.push('text');
        clenseAttrs.push('text');
        if (('image' in oCard) && (!('smallImageUrl' in oCard['image']) && !('largeImageUrl' in oCard['image']))) {
          console.error('If card.image is defined, must specify at least smallImageUrl or largeImageUrl');
          return this;
        }
        break;
      default:
        break;
    }

    var hasAllReq = requiredAttrs.every(function(idx) {
      if (!(idx in oCard)) {
        console.error('Card object is missing required attr "' + idx + '"');
        return false;
      }
      return true;
    });

    if (!hasAllReq) {
      return this;
    }

    // remove all SSML to keep the card clean
    clenseAttrs.forEach(function(idx) {
      oCard[idx] = SSML.cleanse(oCard[idx]);
    });

    this.response.response.card = oCard;

    return this;
  };
  this.linkAccount = function() {
    this.response.response.card = {
      "type": "LinkAccount"
    };
    return this;
  };
  this.shouldEndSession = function(bool, reprompt) {
    this.response.response.shouldEndSession = bool;
    if (reprompt) {
      this.reprompt(reprompt);
    }
    return this;
  };
  this.sessionObject = session;
  this.setSessionAttributes = function(attributes) {
    this.response.sessionAttributes = attributes;
  };
  // prepare response object
  this.prepare = function() {
    this.setSessionAttributes(this.sessionObject.getAttributes());
  };
  this.audioPlayerPlay = function(playBehavior, audioItem) {
    var audioPlayerDirective = {
      "type": "AudioPlayer.Play",
      "playBehavior": playBehavior,
      "audioItem": audioItem
    };
    self.response.response.directives.push(audioPlayerDirective);
    return this;
  };
  this.audioPlayerPlayStream = function(playBehavior, stream) {
    var audioItem = {
      "stream": stream
    };
    return this.audioPlayerPlay(playBehavior, audioItem);
  };
  this.audioPlayerStop = function() {
    var audioPlayerDirective = {
      "type": "AudioPlayer.Stop"
    };
    self.response.response.directives.push(audioPlayerDirective);
    return this;
  };
  this.audioPlayerClearQueue = function(clearBehavior) {
    var audioPlayerDirective = {
      "type": "AudioPlayer.ClearQueue",
      "clearBehavior": clearBehavior || "CLEAR_ALL"
    };
    self.response.response.directives.push(audioPlayerDirective);
    return this;
  };

  // legacy code be ...
```
- example usage
```shell
...
  };
  this.sessionEndedFunc = null;
  this.sessionEnded = function(func) {
self.sessionEndedFunc = func;
  };
  this.request = function(request_json) {
var request = new alexa.request(request_json);
var response = new alexa.response(request.getSession());
var postExecuted = false;
var requestType = request.type();
var promiseChain = Promise.resolve();

// attach Promise resolve/reject functions to the response object
response.send = function(exception) {
  response.prepare();
...
```

#### <a name="apidoc.element.alexa-app.session"></a>[function <span class="apidocSignatureSpan">alexa-app.</span>session (session)](#apidoc.element.alexa-app.session)
- description and source-code
```javascript
session = function (session) {
  var isAvailable = (typeof session != "undefined");
  this.isAvailable = function() {
    return isAvailable;
  };
  if (isAvailable) {
    this.isNew = function() {
      return (true === session.new);
    };
    this.get = function(key) {
      // getAttributes deep clones the attributes object, so updates to objects
      // will not affect the session until 'set' is called explicitly
      return this.getAttributes()[key];
    };
    this.set = function(key, value) {
      this.attributes[key] = value;
    };
    this.clear = function(key) {
      if (typeof key == "string" && typeof this.attributes[key] != "undefined") {
        delete this.attributes[key];
      } else {
        this.attributes = {};
      }
    };
    this.details = {
      "new": session.new,
      "sessionId": session.sessionId,
      "userId": session.user.userId,
      "accessToken": session.user.accessToken || null,
      "attributes": session.attributes,
      "application": session.application
    };
    // persist all the session attributes across requests
    // the Alexa API doesn't think session variables should persist for the entire
    // duration of the session, but I do
    this.attributes = session.attributes || {};
    this.sessionId = session.sessionId;
  } else {
    this.isNew = this.get = this.set = this.clear = function() {
      throw "NO_SESSION";
    };
    this.details = {};
    this.attributes = {};
    this.sessionId = null;
  }
  this.getAttributes = function() {
    // deep clone attributes so direct updates to objects are not set in the
    // session unless '.set' is called explicitly
    return JSON.parse(JSON.stringify(this.attributes));
  };
}
```
- example usage
```shell
...

if (this.data.context) {
  this.userId = this.data.context.System.user.userId;
  this.applicationId = this.data.context.System.application.applicationId;
  this.context = this.data.context;
}

var session = new alexa.session(json.session);
this.hasSession = function() {
  return session.isAvailable();
};
this.getSession = function() {
  return session;
};
...
```



# <a name="apidoc.module.alexa-app.to_ssml"></a>[module alexa-app.to_ssml](#apidoc.module.alexa-app.to_ssml)

#### <a name="apidoc.element.alexa-app.to_ssml.cleanse"></a>[function <span class="apidocSignatureSpan">alexa-app.to_ssml.</span>cleanse (str)](#apidoc.element.alexa-app.to_ssml.cleanse)
- description and source-code
```javascript
cleanse = function (str) {
  // <p> is left in place to support intended HTML output
  return str.replace(/<\/?(speak|break|phoneme|audio|say-as|s\b|w\b)[^>]*>/gi, " ")
    .replace(/\s*\n\s*/g, "\n")
    .replace(/  +/g, " ")
    .replace(/ ([.,!?;:])/g, "$1")
    .trim();
}
```
- example usage
```shell
...

  if (!hasAllReq) {
    return this;
  }

  // remove all SSML to keep the card clean
  clenseAttrs.forEach(function(idx) {
    oCard[idx] = SSML.cleanse(oCard[idx]);
  });

  this.response.response.card = oCard;

  return this;
};
this.linkAccount = function() {
...
```

#### <a name="apidoc.element.alexa-app.to_ssml.fromStr"></a>[function <span class="apidocSignatureSpan">alexa-app.to_ssml.</span>fromStr (str, current_ssml)](#apidoc.element.alexa-app.to_ssml.fromStr)
- description and source-code
```javascript
fromStr = function (str, current_ssml) {
  // remove any <speak> tags from the input string, if they exist. There can only be one set of <speak> tags.
  str = str || "";
  str = str.replace(/<speak>/gi, " ").replace(/<\/speak>/gi, " ").trim();

  // and remove them from the concatenated string, if exists
  current_ssml = current_ssml || "";
  current_ssml = current_ssml.replace(/<speak>/gi, " ").replace(/<\/speak>/gi, " ").trim();

  //TODO: Need a library with how to easily construct these statements with appropriate spacing, etc.
  //TODO: make sure all attribute values are surrounded by "..."
  var ssml_str = "<speak>" + current_ssml + (current_ssml === "" ? "" : " ") + str + "</speak>";

  return ssml_str.replace(/  +/, " ");
}
```
- example usage
```shell
...
    "shouldEndSession": true
  }
};
this.say = function(str) {
  if (typeof this.response.response.outputSpeech == "undefined") {
    this.response.response.outputSpeech = {
      "type": "SSML",
      "ssml": SSML.fromStr(str)
    };
  } else {
    // append str to the current outputSpeech, stripping the out speak tag
    this.response.response.outputSpeech.ssml = SSML.fromStr(str, this.response.response.outputSpeech.ssml);
  }
  return this;
};
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
