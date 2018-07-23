# Client Actions

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


# Client Action Result

Any side effect that the Client Action wants to create must be done using the **result** object.

- To say something to the user as text: ```result.text('a message')```
- To show an image to the user: ```result.image('https://example.com/image.jpg')```
- To show a video to the user: ```result.video('https://example.com/video.mp4')```
- To send a file to the user: ```result.image('https://example.com/myfile.doc')```
- To send audio to the user: ```result.audio('https://example.com/audio.mp3')```

It is also possible to show a text with actions buttons:

```javascript
result.buttonsBuilder()
  .text('select an option')
  .addURLButton('click me', 'https://www.google.com') // a button that will open a page
  .addLocationButton() // ask the user for its location using GPSs
  .quickReplies() // marks the button so it's showed as pills
  .addPhoneButton('call me', '+11233212312')
  .addButton('click me', 'rule with name XX') // when user clicks it will fire the rule named XX
  .send(); // send must by always called to finalize
```

## Go to anothe rule

This handy method makes possible to execute a rule when the Client Action ends. This is helpful when after saying something to the user or change some session or user state, you want to fire a rule to continue the conversational flow. 

```javascript
result.gotoRule('a rule name');
```


## Client Action end mark

```result.done()``` should be called to mark that the Client Action was finished. 

**It's is important to call _result.done()_ method in every flow that the code has in order to finish the execution**

_The following code shows a well implemented Client Action with _done()_ method called in every flow:


```javascript
rp({uri: 'https://script.google.com/macros/s/AKfycbyd5AcbAnWi2Yn0xhFRbyzS4qMq1VucMVgVvhul5XqS9HkAyJY/exec?tz=Asia/Tokyo Japan', json: true})
    .then(json=> {
        // saying the time
        result.text('The time in Tokyo is ' + json.fulldate);

        // do not forget to end the execution
        result.done();
    })
    .catch(error => {
        result.text('Problems: ' + error + '|' + JSON.stringify(error));
        result.done();
    });
    
// even though the code ends here, the Client Action will run until result.done() was reached
```

# Input Example

```json
{
  "context": {
    "userData": {
      "CHAT_PLATFORM_ID": "webchat",
      "CHAT_CHANNEL_ID": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "PLATFORM_CONTACT_ID": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "LAST_MODIFICATION": "2018-07-23T03:43:51.243Z",
      "HAS_TALKED": true,
      "_id_": "O0IUBYCHJYSA4PNB0QH7",
      "LAST_SEEN": "2018-07-23T03:43:52.279Z",
      "variables": {
        "svar": "sdas"
      },
      "tags": [
        "testtest2"
      ]
    },
    
    "message": {
      "BUSINESS_ID": "YPDXTZKM8Y3NXLXVQYAN",
      "CREATION_TIME": "2018-07-23T03:43:52.281Z",
      "FROM_NAME": "Usuario",
      "CUSTOMER_ID": "O0IUBYCHJYSA4PNB0QH7",
      "_id_": "LBIJGWZN4SJADFT2HUD2",
      "FROM": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "OBJECT_TYPE": "Message",
      "SESSION_CREATION_TIME": "2018-07-23T03:43:52.281Z",
      "AUDIOS_URLS": [],
      "MESSAGE": "test",
      "CHAT_PLATFORM_ID": "webchat",
      "CHAT_CHANNEL_ID": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "LAST_MODIFICATION": "2018-07-23T03:43:52.281Z",
      "TO": "me",
      "TAGS": {}
    },
    
    "params": {}
  }
}
```
