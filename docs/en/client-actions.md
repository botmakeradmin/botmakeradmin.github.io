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

```javascript
{
  "internal": {
    "name": "testcode1",
    "token": "2PQsPD6pA1QYV_d46F5EQV1QyKCJA272842HDso47bkwvsUnb2r2s0sdl2kcjsnmLkdj2TnzA3vKQYVQYVQZs2Df",
    "chatChannelId": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
    "code": "cmVzdWx0LnRleHQoJ2NhbGxpbmcgYSByZW1vdGUgc2VydmljZS4uJyArIEpTT04uc3RyaW5naWZ5KGNvbnRleHQuYm90KSk7CnJlc3VsdC5kb25lKCk7"
  },
  "context": {
    "bot": {
      "tag333": "",
      "hernan.liendo@gmail.com-1503076675691-current": "",
      "country": "",
      "lastRuleQuestionIdFailed": "",
      "tag456": "",
      "isOpenNow": "true",
      "userHasTalked": "true",
      "userIdOnBusiness": "",
      "businessName": "hernan",
      "messengerReferral": "",
      "lastSlotFillingIntent": "",
      "lastRuleItemId": "1531505954826",
      "thisWasLastIntentToRun": "",
      "t123": "",
      "messageTimeUser": "23:59:47.728",
      "hernan.liendo@gmail.com-1503076675691": "",
      "messageTimeBusiness": "23:59:47.728",
      "isSubscribed": "",
      "channelDisplayName": "hernan",
      "dau": "true",
      "businessAddress": "",
      "webChatHostURL": "https://storage.googleapis.com/m-infra.appspot.com/public/botmaker/webChatTest.html?id=0BBSX05QRF",
      "webChatHostURI": "https://storage.googleapis.com/m-infra.appspot.com/public/botmaker/webChatTest.html?id=0BBSX05QRF",
      "isWebChatMobile": "",
      "dayForUser": "SUNDAY",
      "tes": "",
      "untagnuevo1": "",
      "test": "",
      "webChatHostDomain": "storage.googleapis.com",
      "ipAddress": "",
      "tt123": "",
      "y123": "",
      "firstName": "",
      "lastSeen": "2018-07-23T02:57:47.476Z",
      "webId": "0BBSX05QRF",
      "lastBotSentence": "BotSays.YPDXTZKM8Y3NXLXVQYAN-hernan.liendo@gmail.com-1509367988439",
      "connectionStatus": "",
      "lastUserMessageID": "DIZ45CR462O1GGPEIUDQ",
      "webChatHostReferrer": "https://go.botmaker.com/",
      "messageDate": "2018-07-23T02:59:47.728Z",
      "businessPhone": "",
      "lastName": "",
      "attachments": "",
      "tag555": "",
      "pod": "local",
      "testtest2": "true",
      "gender": "",
      "testtest3": "",
      "agentContext": {
        "openHours": [
          "00:00-23:59",
          "00:00-23:59",
          "00:00-23:59",
          "00:00-23:59",
          "00:00-23:59",
          "00:00-23:59",
          "00:00-23:59"
        ],
        "goodThreshold": 0.9,
        "mercadoPagoClientId": "",
        "customerAssignStrategy": "NONE",
        "wordCloudBlacklist": [],
        "minutesTillResetSession": 60,
        "metricsEmails": [],
        "onlyExpensiveUnderstanding": false,
        "botMuted": false,
        "useWord2Vec": false,
        "privateReplies": [],
        "apiaiAccessToken": "",
        "triggerInactivityRulesForEmptyResponse": false,
        "assignWhenOperatorSpeaks": false,
        "forceIsClosed": false,
        "humanThreshold": 0,
        "useDialogFlow": true,
        "constants": {},
        "fbLoginAppId": "",
        "lang": "ESPANOL",
        "hourGMT": -3,
        "todoPagoToken": "",
        "attentionQueues": [],
        "backgroundColor": "ffffff",
        "variables": {
          "tag333": {
            "map": {
              "type": "tag"
            }
          },
          "tag456": {
            "map": {
              "type": "tag"
            }
          },
          "tag555": {
            "map": {
              "type": "tag"
            }
          },
          "testtest2": {
            "map": {
              "type": "tag"
            }
          },
          "testtest3": {
            "map": {
              "type": "tag"
            }
          },
          "testtest1": {
            "map": {
              "type": "tag"
            }
          },
          "t123": {
            "map": {
              "type": "tag"
            }
          },
          "hernan.liendo@gmail.com-1503076675691": {
            "map": {
              "displayName": "Tema ejemplo",
              "type": "tag"
            }
          },
          "testtag123": {
            "map": {
              "type": "tag"
            }
          },
          "test321": {
            "map": {
              "type": "tag"
            }
          },
          "thetag1": {
            "map": {
              "type": "tag"
            }
          },
          "testtest4": {
            "map": {
              "type": "tag"
            }
          },
          "testtest45": {
            "map": {
              "type": "tag"
            }
          },
          "testvar": {
            "map": {}
          },
          "tes": {
            "map": {
              "type": "tag"
            }
          },
          "test": {
            "map": {
              "type": "tag"
            }
          },
          "untagnuevo1": {
            "map": {
              "type": "tag"
            }
          },
          "testtest1212": {
            "map": {
              "type": "tag"
            }
          },
          "hernan.liendo@gmail.com-1507318785186": {
            "map": {
              "displayName": "Venta de autos",
              "type": "tag"
            }
          },
          "tt123": {
            "map": {
              "type": "tag"
            }
          },
          "ssda": {
            "map": {
              "type": "tag"
            }
          },
          "testtag123123": {
            "map": {
              "type": "tag"
            }
          },
          "y123": {
            "map": {
              "type": "tag"
            }
          },
          "p123": {
            "map": {
              "type": "tag"
            }
          },
          "hernan.liendo@gmail.com-1507318579043": {
            "map": {
              "displayName": "tema 2",
              "type": "tag"
            }
          },
          "svar": {
            "map": {}
          }
        },
        "perfectThreshold": 0.9,
        "muteBotWhenOperatorSpeaks": false,
        "eraseFbUserProfile": false,
        "synonyms": [
          [
            "dada",
            "dadsa"
          ],
          [
            "lo que",
            "cuando"
          ],
          [
            "masa",
            "pizza"
          ],
          [
            "sdsds",
            "que precio"
          ],
          [
            "ansia",
            "descontento",
            "escasez",
            "espejismo",
            "ganas de comer",
            "hambre",
            "ilusionismo",
            "lija"
          ]
        ],
        "triggerInactivityRulesWhenOperatorSpeaks": true,
        "facebookAnalyticsConfiguration": [],
        "todoPagoMerchant": "fsds1214sw",
        "mercadoPagoCurrency": "",
        "mercadoPagoClientSecret": "",
        "metricsHour": 0,
        "restrictedIPs": [],
        "metricsDay": "NEVER",
        "markAsReadBotMessageIfClosed": false,
        "dontMarkAsReadIfHasPendingMessages": false,
        "operatorImpressionsPerSlot": 0,
        "name": "hernan",
        "forceIsOpened": true,
        "advanceSuperSetAdministration": false,
        "googleAnalyticsConfiguration": [
          {
            "trackingId": "UA-73723709-3",
            "source": "BotMaker",
            "eventCategory": "${businessName}"
          }
        ],
        "useContext": false,
        "fontColor": "000000",
        "triggerInactivityRulesForSenderActions": false,
        "operatorSlots": 0
      },
      "testtest1": "",
      "_id_": "YPDXTZKM8Y3NXLXVQYAN",
      "ruleRunInSession": "",
      "locale": "",
      "todayOpenHours": "00:00 a 23:59",
      "random": "0.7438931866269874",
      "hernan.liendo@gmail.com-1507318579043-current": "",
      "testtag123": "",
      "test321": "",
      "thetag1": "",
      "customerId": "O0IUBYCHJYSA4PNB0QH7",
      "testtest4": "",
      "lang": "es",
      "testtest45": "",
      "agentSpoke": "",
      "chatChannelId": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "webChatHostPageTitle": "BotMaker",
      "mau": "true",
      "queueID": "",
      "chatPlatform": "webchat",
      "svar": "sdas",
      "testvar": "",
      "previousUserSentence": "adasd",
      "ruleCountInSession": "0",
      "testtest1212": "",
      "webChatCountry": "",
      "fullName": "null null",
      "operatorsConnectedQty": "0",
      "wau": "true",
      "hernan.liendo@gmail.com-1507318785186": "",
      "ssda": "",
      "testtag123123": "",
      "platformContactId": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "lastRuleBuilder": "YPDXTZKM8Y3NXLXVQYAN-hernan.liendo@gmail.com-1509367988439",
      "p123": "",
      "webChatHostHREF": "https://storage.googleapis.com/m-infra.appspot.com/public/botmaker/webChatTest.html?id=0BBSX05QRF",
      "scheduledRule": "",
      "lastUserSentence": "test",
      "timesOnlineToday": "2",
      "hernan.liendo@gmail.com-1507318579043": "",
      "dayForBusiness": "SUNDAY",
      "faqState-agentContext": {},
      "hasLinkedCustomers": "",
      "operatorID": "",
      "channelWebId": "0BBSX05QRF",
      "lastIntentId": "RuleBuilder:YPDXTZKM8Y3NXLXVQYAN-hernan.liendo@gmail.com-1509367988439"
    },
    "userData": {
      "BUSINESS_ID": "YPDXTZKM8Y3NXLXVQYAN",
      "templateMappings": {
        "tag333": "",
        "hernan.liendo@gmail.com-1503076675691-current": "",
        "country": "",
        "lastRuleQuestionIdFailed": "",
        "tag456": "",
        "isOpenNow": "true",
        "userHasTalked": "true",
        "userIdOnBusiness": "",
        "businessName": "hernan",
        "messengerReferral": "",
        "lastSlotFillingIntent": "",
        "lastRuleItemId": "1531505954826",
        "thisWasLastIntentToRun": "",
        "t123": "",
        "messageTimeUser": "23:59:47.909",
        "hernan.liendo@gmail.com-1503076675691": "",
        "messageTimeBusiness": "23:59:47.91",
        "isSubscribed": "",
        "channelDisplayName": "hernan",
        "dau": "true",
        "businessAddress": "",
        "webChatHostURL": "https://storage.googleapis.com/m-infra.appspot.com/public/botmaker/webChatTest.html?id=0BBSX05QRF",
        "webChatHostURI": "https://storage.googleapis.com/m-infra.appspot.com/public/botmaker/webChatTest.html?id=0BBSX05QRF",
        "isWebChatMobile": "",
        "dayForUser": "SUNDAY",
        "tes": "",
        "untagnuevo1": "",
        "test": "",
        "webChatHostDomain": "storage.googleapis.com",
        "ipAddress": "",
        "tt123": "",
        "y123": "",
        "firstName": "",
        "lastSeen": "2018-07-23T02:57:47.476Z",
        "webId": "0BBSX05QRF",
        "lastBotSentence": "BotSays.YPDXTZKM8Y3NXLXVQYAN-hernan.liendo@gmail.com-1509367988439",
        "connectionStatus": "",
        "lastUserMessageID": "DIZ45CR462O1GGPEIUDQ",
        "webChatHostReferrer": "https://go.botmaker.com/",
        "messageDate": "2018-07-23T02:59:47.909Z",
        "businessPhone": "",
        "lastName": "",
        "attachments": "",
        "tag555": "",
        "pod": "local",
        "testtest2": "true",
        "gender": "",
        "testtest3": "",
        "testtest1": "",
        "ruleRunInSession": "",
        "locale": "",
        "todayOpenHours": "00:00 a 23:59",
        "random": "0.8344078071744329",
        "hernan.liendo@gmail.com-1507318579043-current": "",
        "testtag123": "",
        "test321": "",
        "thetag1": "",
        "customerId": "O0IUBYCHJYSA4PNB0QH7",
        "testtest4": "",
        "lang": "es",
        "testtest45": "",
        "agentSpoke": "",
        "chatChannelId": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
        "webChatHostPageTitle": "BotMaker",
        "mau": "true",
        "queueID": "",
        "chatPlatform": "webchat",
        "svar": "sdas",
        "testvar": "",
        "previousUserSentence": "adasd",
        "ruleCountInSession": "0",
        "testtest1212": "",
        "webChatCountry": "",
        "fullName": "null null",
        "operatorsConnectedQty": "0",
        "wau": "true",
        "hernan.liendo@gmail.com-1507318785186": "",
        "ssda": "",
        "testtag123123": "",
        "platformContactId": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
        "lastRuleBuilder": "YPDXTZKM8Y3NXLXVQYAN-hernan.liendo@gmail.com-1509367988439",
        "p123": "",
        "webChatHostHREF": "https://storage.googleapis.com/m-infra.appspot.com/public/botmaker/webChatTest.html?id=0BBSX05QRF",
        "scheduledRule": "",
        "lastUserSentence": "test",
        "timesOnlineToday": "2",
        "hernan.liendo@gmail.com-1507318579043": "",
        "dayForBusiness": "SUNDAY",
        "hasLinkedCustomers": "",
        "operatorID": "",
        "channelWebId": "0BBSX05QRF",
        "lastIntentId": "RuleBuilder:YPDXTZKM8Y3NXLXVQYAN-hernan.liendo@gmail.com-1509367988439"
      },
      "OPERATOR_LAST_MSG_RECEIVED": "1532314669415",
      "PLATFORM_CONTACT_ID": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "LAST_MESSAGE": "{\"CREATION_TIME\":\"2018-07-22T15:13:26.579Z\",\"INTENT_ID\":\"ANYTHING\",\"CUSTOM_REPRESENTATION\":\"YPDXTZKM8Y3NXLXVQYAN:ANYTHING\",\"literals\":[\"Te responderemos a la brevedad\"],\"FILES_URLS\":[],\"_id_\":\"62SYPIVAKEJYSRW4IBRQ\",\"LAST_USER_MESSAGE_ID\":\"YV50S8V0EU04DQXAS3MH\",\"FROM\":\"me\",\"ITEMS\":[],\"OBJECT_TYPE\":\"Message\",\"type\":\"text\",\"APIAI_RESPONSE\":\"{\\\"success\\\":false}\",\"CHAT_PLATFORM_ID\":\"webchat\",\"MESSAGE\":\"Te responderemos a la brevedad\",\"MESSAGE_TEMPLATE\":\"Te responderemos a la brevedad\",\"VIDEOS_URLS\":[],\"BUSINESS_ID\":\"YPDXTZKM8Y3NXLXVQYAN\",\"RULE_ID\":\"hear(ANYTHING)\",\"FROM_NAME\":\"Bot\",\"CUSTOMER_ID\":\"O0IUBYCHJYSA4PNB0QH7\",\"OPTIONS\":[],\"SESSION_CREATION_TIME\":\"2018-07-22T15:13:23.569Z\",\"AUDIOS_URLS\":[],\"CHAT_CHANNEL_ID\":\"YPDXTZKM8Y3NXLXVQYAN-webchat-null\",\"REPRESENTATION_ID\":\"BotSays.YPDXTZKM8Y3NXLXVQYAN:ANYTHING\",\"RENDERING_INFO\":{},\"LAST_MODIFICATION\":\"2018-07-22T15:13:26.579Z\",\"TO\":\"0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM\",\"IMAGES_URLS\":[]}",
      "_id_": "O0IUBYCHJYSA4PNB0QH7",
      "USER_LAST_MSG_RECEIVED": "1532314399114",
      "OBJECT_TYPE": "Customer",
      "LAST_INBOX_ENTRY_ID": "92657519",
      "CHAT_CHANNEL_ID": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "CHAT_PLATFORM_ID": "webchat",
      "OPERATOR_LAST_MSG_READ": "1532314669415",
      "LAST_MODIFICATION": "2018-07-23T02:57:46.399Z",
      "lastClearChatTime": 0,
      "HAS_TALKED": true,
      "USER_LAST_MSG_READ": "1532314399114",
      "LAST_SEEN": "2018-07-23T02:57:47.476Z",
      "testtest2": "true"
    },
    "message": {
      "BUSINESS_ID": "YPDXTZKM8Y3NXLXVQYAN",
      "CREATION_TIME": "2018-07-23T02:57:47.479Z",
      "FROM_NAME": "Usuario",
      "CUSTOMER_ID": "O0IUBYCHJYSA4PNB0QH7",
      "_id_": "DIZ45CR462O1GGPEIUDQ",
      "FROM": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "OBJECT_TYPE": "Message",
      "SESSION_CREATION_TIME": "2018-07-23T02:57:47.479Z",
      "AUDIOS_URLS": [],
      "MESSAGE": "test",
      "CHAT_PLATFORM_ID": "webchat",
      "CHAT_CHANNEL_ID": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "LAST_MODIFICATION": "2018-07-23T02:57:47.478Z",
      "TO": "me",
      "TAGS": {}
    },
    "params": {}
  },
  "userVariables": {
    "svar": "sdas"
  },
  "session": {}
}
```
