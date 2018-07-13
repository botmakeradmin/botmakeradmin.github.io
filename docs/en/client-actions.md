# Client Actions specification

Client actions are useful for adding arbitrary code within a conversation in order to solve complex rules or to call external services to adquire realtime information with meaning to the current user conversation.

_Example: you can ask the user to say a color. Then you can call [Google Translation API](https://cloud.google.com/translate/docs/) to make to bot to reply the color in other language_


## How to invoke the code

First you will need to create the Code Action in the Code Actions screen. Remember the name you used when you save it.
Then go to the rule you're interested and in the response screen, in there you only to add an _Action_. Then select Client Action option and finally set the name of the code that you previously saved.

![call code](https://botmakeradmin.github.io/docs/en/callcode.png)


## Code features

Node.js v6.14.0 is supported and a faily common list of libraries are whitelisted:

```javascript
  {
    "@turf/helpers": "^6.1.4", // accessed by "turfHelpers" var
    "@turf/turf": "^5.1.6", // accessed by "turf" var
    "bluebird": "^3.5.1", // accessed by "bluebird" var
    "googleapis": "^32.0.0", // accessed by "google" var
    "js-sha256": "^0.9.0", // accessed by "sha256" var
    "jsonwebtoken": "^8.3.0", // accessed by "jwt" var
    "lodash": "^4.17.10", // accessed by "_" var
    "md5": "^2.2.1", // accessed by "md5" var
    "moment": "^2.22.2", // accessed by "moment" var
    "redis": "^2.8.0",
    "request": "^2.87.0",
    "request-promise": "^4.2.2", // accessed by "rp" var
    "secure-random": "^1.1.1", // accessed by "securedRandom" var
    "xml2js": "^0.4.19", // accessed by "xml2js" var
    "xml2json": "^0.11.2"
  }
```

_In case you need to whilelist another library, write to [architecture@botmaker.com](mailto:architecture@botmaker.com) and the team will put the request in our roadmap_


## Client Action Input

When the code is invoked, all the information we know about the user, conversations and general settings are provided. The following diagram describes the input that a Cloud Function might use.

## Context object

A read-only object that has relevant information that a Code Action might need. It has

- **bot**: settings and other data related to the bot (not the current user or conversation)
- **userData**: all the data related to an user
- **message**: data related to last message from the user
- **params**: optional params that can be passed by a rule

_For example:_

```javascript
const userFirstName = context.userData.FIRST_NAME;
```

## userSession object

Allows to read and write variables that will last for a session from the user. Generally speaking a conversasion session is deleted after 1 hour of inactivity. This is an useful place to store data related the current conversation of the user.
*Keep in mind that values have to be of type string*

- To read a value: ```userSession.get('valueKey')``` => will return a string value or null
- To write a value: ```userSession.set('valueKey', 'value')```

_For example:_

```javascript
if ( !userSession.get('userJustTalked') )
  userSession.set('userJustTalked', 'true');
```


## user object

Allows to read and write variables that will persist in the user forever. This is an useful place to store data related to the user.
**Keep in mind that values have to be of type string**

- To read a value: ```user.get('valueKey')``` => will return a string value or null
- To write a value: ```user.set('valueKey', 'value')```

_For example:_

```javascript
if ( !user.get('neverWasHere') )
  userSession.set('neverWasHere', 'true');
```


## entityLoader object

When a cvs file is saved in the Entities option of the platform, Client Actions can access them. For instance, a store list can be filtered and showed to the user based on his location.

```javascript
entityLoader('entity name', json => {
  // here you got your entity object loaded as JSON
});
```


## connectRedis object

A Redis db instance is available for usage within the Client Actions. You can do

```javascript
const redis = connectRedis();
const myKey = redis.get('key');
```


## Client Action Result

result


 3. a var called 'res' is also provided and supports the methods:
 text(message): says a string the message
 done(): marks the code as finished(). It's mandatory to call this method when the execution's done
 session(varName, varValue): saves the varValue in a varName with scope session (it will be there for a couple of minutes)
 user(varName, varValue): saves the varValue in a varName with scope user (it will be there forever)


una propuesta: que user.get('neverWasHere') ) y  userSession.set('neverWasHere', 'true');

se guarden tambien en variableValues , ademas de escribir en clientActionVars por compatibilidad
con eso estamos como queremos
BTW esta muy linda la doc
