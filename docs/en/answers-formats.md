# Bot's answers formats

Hello! Here we'll learn what are the correct formats for each conversational element for all the platforms supported by BotMaker.

## Texts
- **Facebook Messenger and WebChat**:
	- UTF-8 limited to 640 characters for each textbox. If exceeds, the text will be divided into different messages.

- **Telegram**:
	- UTF-8 limited to 4096 characters.

- **Twitter**:
	- UTF-8. Limit unknown.

- **MercadoLibre**:
	- UTF-8 limited to 2000 characters.

- **Google Actions**:
	- UTF-8 limited to 640 characters.

## Buttons
- **Facebook Messenger y WebChat**:
    - 

- **Telegram**:
    - Not supported. Use pills instead.

- **Twitter**:
    - Not supported. Use pills instead.

- **MercadoLibre**:
    - Not supported.

- **Google Actions**:
    - Not supported. Use pills instead.

## Quick answers (Pills)
- **Facebook Messenger y WebChat**:
    - 

- **Telegram**:
    - 

- **Twitter**:
    - 

- **MercadoLibre**:
    - 

- **Google Actions**:
    - 

## Carrousel
- **Facebook Messenger y WebChat**:
    - 

- **Telegram**:
    - Not supported.

- **Twitter**:
    - Not supported.

- **MercadoLibre**:
    - Not supported.

- **Google Actions**:
    - 

## Images
- **Facebook Messenger y WebChat**:
    - JPG, GIF (<75frames) and PNG (recomended);
	- Respect the ratio 1.91:1 (example: 1200x628px).

- **Telegram**:
    - JPG, GIF (<75frames) and PNG (recomended);
	- Not superior to 5mb.

- **Twitter**:
	- JPG, GIF (<350frames), WEBP and PNG (recomended);
	- Not superior to 5mb to images and 15mb to GIFs.

- **MercadoLibre**:
    - Not supported.

- **Google Actions**:
    - JPG, GIF, and PNG sized 128x232dp.

## Audio
- **Facebook Messenger y WebChat**:
    - MP3, preferably not superior to 5mb.

- **Telegram**:
    - MP3, not superior to 20mb.

- **Twitter**:
    - Not supported.

- **MercadoLibre**:
    - Not supported.

- **Google Actions**:
    - Speech Synthesis Markup Language (SSML) supported;
	- MP3 and OGG, 24k samples per second;
	- Not bigger than 5mb and lower to 120 seconds of duration time.

## Videos
- **Facebook Messenger y WebChat**:
	- MP4, preferably not superior to 5mb.

- **Telegram**:
	- MP4, not superior to 50mb.

- **Twitter**:
	- Especificaciones detalladas aqui.

- **MercadoLibre**:
	- Not supported.

- **Google Actions**:
	- Not supported.

## Setting up answers
To better understand the answers setup on an intention, access [How to create an Intention?].


