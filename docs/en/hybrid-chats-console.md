# Hybrid Chats Console

Hello! Here we'll learn how to operate the Hybrid Chats console.

This section is where we find all the conversations in real time. Here's where  Operators profile users work. It's divided into three columns, from left to right:

1. Conversations List;
2. Conversations Detail;
3. Additional Info and Tags.

# 1. Conversations list

![List](https://botmakeradmin.github.io/docs/en/images/Captura%20de%20Tela%202018-08-17%20a%CC%80s%2015.26.06.png)

Placed on the left column, it's the area where all conversations with the Bot are listed by chronological order, from most recent to most dated.

When you enter on a conversation, the central column will update showing the Conversation Detail.

## Identification

Inside each chat summary, it's possible to see the user ID and the last sent/receive message.

![WebChat](https://camo.githubusercontent.com/0d0e8e15464639a4a4cd22937e364e7b9c49a3bd/68747470733a2f2f626f746d616b657261646d696e2e6769746875622e696f2f646f63732f65732f696d6167656e65732f4964656e74696669636163696f6e4553502e706e67)

![Mess](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-26-53.png)

- **Profile picture:** Always and when the user is chatting through a fixed channel (Messenger, Twitter, Telegram, WhatsApp), it'll be possible to visualize his profile picture.
    - If you can't visualize it, the user is chatting from a WebChat (where he's anonymous), and it'll only be shown a generic image. 

- **Username:** Always and when the user is chatting through a fixed channel (Messenger, Twitter, Telegram, WhatsApp), it'll be possible to visualize his name and surname.
    -  If you can't visualize it, the user is chatting from a WebChat (where he's anonymous), and it'll be only showed a unique code to individualize this chat.

- **Channel**: It's possible to observe on the conversation an indicative icon of which channel the user is using to chat with the Bot.
    - They can be Messenger, WhatsApp, Telegram, Twitter DM, Microsoft Teams, Skype, Google Assistant or Google Chrome (when it's a WebChat).
    - In case of WebChats conversations, the Chrome icon will appear with a mark. The mark is green if the user's still online, and red if he's already disconnected.
    - ![Channel](https://camo.githubusercontent.com/33da8e6c46cfd8730d2139886b69e6e274d20404/68747470733a2f2f626f746d616b657261646d696e2e6769746875622e696f2f646f63732f70742f696d6167656e732f69636f6e65732e706e67)

- **Country:** On every WebChat conversation, the platform will indicate from which country the user is contacting you. This data is obtained from the user's IP address.

- **Date:** It's possible to see on the conversation the date of the last received/sent message. If not shown, it'll appear how long since the last message.

- **Taken chat:** When an operator takes a conversation, it'll be marked with a locker next to the operator's initials.

## Search

Above the chats, it's found a search bar. From it, you can search for a chat typing the user's name or by typing a message from the conversation. 

![Search](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-29-34.png)

Also, it's possible to filter chats by desired tags.

![Filters](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-30-13.png)

# 2. Conversations Detail

![Detail](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-31-29.png)

Placed on the central column, it's the are where you visualize the conversation history from each user.

From the moment that the Bot understands all user's requests and answers them, the conversation can be fully automatized.

Also, the platform was drawn for a hybrid operation (Bot+Human), and that's why it's found all the necessary elements for human service.

## Textbox

![Box](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-31-99.png)

At the bottom of Conversations Detail, it's found the textbox, where operators are capable of executing the following functions:

- Write your messages manually and intervene in the conversation;
- Send images, videos, and files;
- Record voice messages (requires microphone);
- Send GIFs and emojis.

In addition, when the cursor is on the textbox, the operator can click "**Enter**" to open the Bot's Actions Menu.

![Enter](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-32-19.png)

>On it, the operator can search for an intention loaded in the Bot to send it as an answer for a not-comprehended request. While doing it, not only the user will receive the answers, but also the Bot will be being trained for future similar cases - so he can answer without an operator help.

## Header's options

![ ](https://camo.githubusercontent.com/12e5ac3771d9fdf3e8cbd31a82074a070c9e3f15/68747470733a2f2f626f746d616b657261646d696e2e6769746875622e696f2f646f63732f65732f696d6167656e65732f6f70636f6573636861744553502e706e67)

![ ](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-33-15.png)

Besides the points described before, also some options can be executed through the header on Conversations Detail.

### Take chat
By selecting this option, the operator will be self-assigning to a conversation, in a way to avoid that other operators can answer that individually chat at the moment. 

>A blocked chat will not be able to receive other operators intervention before unblocked. This can be done by clicking on "Release chat."

### Assign user to another operator
By selecting this option, it'll be possible to assign a conversation to a specifical operator, whose will better understand the solicitation theme, for ex. It can be blocked and unblocked just as explained before.

### Mark as unread
By selecting this option, the conversation will be marked as "**Unread**."

### Mark as SPAM
By selecting this option, the user will be blocked for seven days. It's recommended on cases which the user is molesting the Bot/Operator by sending nonsense questions.

>A blocked user can still send messages, but the Bot will no longer answer him. Also, the Operators won't be notified about this chat.

## Deactivate bot on the conversation

![ ](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-33-43.png)

The Bot can be deactivated by an operator (on a conversation, individually) selecting the option above.

It's recommended using this function always when an operator needs to interfere manually, in a way to avoid that the Bot answers the questions.

As the operator's finished answering the user's requests, he can reactivate the Bot by clicking on the same option.

>In case that he forgets, the Bot reactivation will be done automatically within 30 minutes.

# 3. Additional Info and Tags

The third and last column is localized at the right area of Hybrid Chats Console. There, it's shown all saved information - provided by the user - and the conversation themes discussed on the chat.

## Additional Info

![ ](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-34-12.png)

It's where all information stored historically by the Bot, through user interaction, is shown. It can be stored, for example:

- Name and surname;
- Birthday;
- Email;
- Address;
- Channel;
- Used URL;
- Any other information that the Bot requested to the user.

From the conversation reading, it's possible to obtain new information, which can be stored manually clicking on the "**Edit**" button. Select the variable and write the info.

![ ](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-34-37.png)

## Tags

![ ](https://botmakeradmin.github.io/docs/en/images/2018-08-17_15-36-35.png)

The tags are the conversation themes which the user, historically, talked about. They are added automatically, always and when it's about topics that the Bot comprehends.

In cases when Operators need to tag themes not comprehended by the Bot, on a specifical chat, it can be done manually clicking on "**Edit**" button.

