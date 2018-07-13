# Client Actions specification

Client actions are useful for adding arbitrary code within a conversation in order to solve complex rules or to call external services to adquire realtime information with meaning to the current user conversation.

_Example: you can ask the user to say a color. Then you can call [Google Translation API](https://cloud.google.com/translate/docs/) to make to bot to reply the color in other language_

## How to invoke the code

First you will need to create the Code Action in the Code Actions screen. Remember the name you used when you save it.
Then go to the rule you're interested and in the response screen, in there you only to add an _Action_. Then select Client Action option and finally set the name of the code that you previously saved.

![call code](https://botmakeradmin.github.io/docs/en/callcode.png)



asdas
 ** You can start coding here! - Node.js v6.9.1 is supported. **
 
 1. When you save this code a rule can use it by creating an action of type 'Client Action'
 2. a var called 'req' is available and contains all the data that we have related to an app,
 an user, an user session and the last message that we got from her
 For instance, you can do 'req.user.state.userContext.firstName' to get the first name of the user
 You can navigate the complete req object by clicking the 'Test function' button below
 3. a var called 'res' is also provided and supports the methods:
 text(message): says a string the message
 done(): marks the code as finished(). It's mandatory to call this method when the execution's done
 session(varName, varValue): saves the varValue in a varName with scope session (it will be there for a couple of minutes)
 user(varName, varValue): saves the varValue in a varName with scope user (it will be there forever)
 4. Some pretty known node libraries are in scope for you to use them (please contact us if other libraries whitelisting is required):
 var lodash from https://lodash.com/
 var moment from https://momentjs.com/
 var md5 from https://github.com/pvorb/node-md5
 var secureRandom from https://github.com/jprichardson/secure-random
 var rp from https://github.com/request/request-promise
 
 5. Look around, change and play with the example below:

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
