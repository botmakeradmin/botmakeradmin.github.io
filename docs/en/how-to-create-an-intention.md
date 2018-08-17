# How to create an intention?

Hello! Here we'll learn how to create an **Intention**.

![ ](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/en/images/2018-08-17_17-56-48.png)

A Bot is a set of intentions - the intentions allow to define what will be answered by the Bot up a specific request from the user. Your creation is done by two elements.

- Triggers: against which conditions or which user requests the intention should be triggered? They can be:
    - By user expression comprehension;
    - By user inactivity time.

- Answers: when the term is understood, what will the Bot do?

## Triggers

### Triggers by user expression comprehension

The triggers by user expression comprehension can be of two types:

![ ](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/en/images/2018-08-17_17-59-45.png)

**Static phrases**
The Bot will be very restrictive with the comprehension of those phrases, and only little variables are going to be interpreted - global synonyms.

**Phrases with variables**
In this case, words marked as **important words** will elevate the comprehension possibilities of the request. Besides global synonyms, selected variables for each word are going to be sufficient to activate the intention.

**Tips:**
- Don't use triggers with only a few important words, because it'll leave the intention too broad and easy to be triggered. We should keep them in a way that the Bot won't be confused with another solicitation.
- "Play" with the triggers possibilities - note that you can duplicate a trigger, allowing to deactivate some keyword.

### Triggers by inactivity time
When activated a trigger by inactivity time, the intention will be fired automatically as the predefined timer finalizes. The computed time is the time that the user didn't send anything to the Bot.

## Answers

![ ](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/en/images/2018-08-17_18-00-15.png)

When an intention is triggered, the Bot will execute what is defined on the **Answers** screen, in the order that's set up. 

The messages' elements can be:

### Text
Pressing the button "**+Text**," it'll be added a textbox where you can add the text message that you want to be sent. Each box added, will be one box on the chat interface.

### Buttons
Pressing the button "**+Button**," it'll be added a textbox with options. These options will appear on button format to the user.

The buttons can be:
- Open a link;
- Fire an intention;
- Share;
- Call.

Observe the option "**Use quick replies**," this can only be activated when the added buttons are redirecting to intentions. This option will change the button format on Messenger and WebChat, like below:

With quick reply:

Without quick reply

### Carrousel
Pressing the button "**+Carrousel**," it'll be possible to add several images - on Carrousel format - with naming, description and buttons capabilities.

![ }(https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/en/images/2018-08-17_18-02-54.png)

### Actions
Actions permit aggregate simply to the Bot predefined behaviors.

We have a full article about them, which will help you with it's uses. Click here.

### Media
Pressing the button "**+Media**," it'll be possible to add any kind of file to the chat, such as images, audios, videos or general files.

>Remeber: You can always rearrange the order of the content dragging it up and down.






