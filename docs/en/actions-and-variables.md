# Actions and Variables

Hello! Here we'll learn how to use variables and actions on Botmaker.

## Variables

A variable is a symbolic name used to save a value.

>For example, on the variable ${name} can be saved values like "Gabriel", "Julio", "Fernando", etc.

They are used for:
- Direct the flow of a conversation
- Save user data
- Create rules with conditions
- Reports emission

Some variables come with the platform by default, and the data contained on them are auto-filled. With no effort, it's possible to create new variables manually. 

### Main variables

Next, we'll show you a list of the most used variables of the platform, with a quick explanation of each one.

- **isOpenNow**: with true or false values, indicates if the Bot will answer on office hours or no.

- **operatorsConnectedQty**: number of connected operators;

- **chatPlatform**: the platform that is hosting the conversation, can be "messenger", "webchat", "skype", etc.

- **isWebChatMobile**: if the user is chatting from a mobile Web chat;

- **isSubscribe**: with true or false values, indicates if the user is subscribed to receive pushes

- **lastSeen**: last time that the user visualized

- **lastUserSentence**: the last sentence said by the user

- **lastBotSentence**: the last sentence said by the bot;

- **ruleCountInSession**: how many times the rule was triggered on the session

- **thisWasLastIntentToRun**: this was the last rule to be executed.

Also, there are found variables that the Bot defined and the Tags (themes)  of the user.

### Where to use variables?

Variables are useful when defining when a rule should be triggered, which answer should be sent on given context, or even to filtrate reports.

- Variables as a trigger condition
    - When adding a condition on a trigger, the rule will be only triggered when it's executed and the condition accomplished. 

- Variables as answers condition 
    - Can be used for, before distinct conditions give different answers for the same user intention.

- Variables as dynamic text in an answer
    - The data contained on a variable can be used to give dynamic answers to users, where the variable will be substituted for its content.

## Actions
Actions allow aggregating to the Bot, easily, predefined behaviors.

### Main actions
Next, we'll show you a list of the main actions present on the platform, with a quick explanation of each one.

- **Question**: allows to ask questions to the user and save his answer as a value on a variable

- **Go to**: allows redirecting the course to a rule 

- **Send email**: allows sending an email to the user

- **Send to Messenger**: adds a button allowing the Web Chat user to connect his account with his Messenger one.

- **Add topic CTA**: suggests buttons with rules from the same theme/topic

- **Subscribe/Unsubscribe**: subscribes or unsubscribes the user from the push deliveries

- **Finish**: aborts any course that's being executed

- **Notify**: marks the conversation as Non-Read, to be visualized by an operator;

- **Set variable**: allows creating and/or assigning a determined value to a variable

- **Clear variable**: Clear one (or all) variables

- **SaveCheckpoint/GotoCheckpoint**: allows saving and resuming a checkpoint from a rule

- **ClientAction**: allows executing a personalized action define on Codes section

- **Callback Url**: allows posting on a URL

- **Generate Rule URL**: generates a link which will be saved on a variable. When opened, triggers the rule defined on the bot.

### Where to use actions?
Actions are set up from the Answers screen, the last step on a rule development. See the example:






 

