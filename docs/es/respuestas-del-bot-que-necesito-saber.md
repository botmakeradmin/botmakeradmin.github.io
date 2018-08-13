# Respuestas del Bot: lo que preciso saber?

Hola! Aquí vamos a aprender cuales son los formatos correctos para cada elemento de conversación para las diferentes plataformas soportadas por BotMaker.

## Textos

- **Facebook Messenger y WebChat**:
	-  Formato UTF-8, con límite de 640 caracteres por caja de texto. Si se excede, el texto será separado en diferentes mensajes.

- **Telegram**:
	-  Formato UFT-8 con límite de 4096 caracteres.
  
- **Twitter**:
	-  Formato UTF-8 con límite desconocido.
  
 - **MercadoLibre**:
	-  Formato UTF-8 con límite de 2000 caracteres.
  
 - **Google Actions**:
	 - Formato UTF-8 con límite de 640 caracteres.

## Botones
- **Facebook Messenger y WebChat**:
	- Texto anterior de los botones en formato UTF-8 con límite de 640 caracteres;
	- Texto de los botones en formato UTF-8 con límite de 20 caracteres. Los botones soportan URLs.
	- ![Sin Respuesta Rápida activada](https://botmakeradmin.github.io/docs/pt/imagens/SemRespostaRapida.jpg)



- **Telegram**:
	- No soportado. Utilizar respuestas rápidas en el lugar.

- **Twitter**:
	- No soportado. Utilizar respuestas rápidas en el lugar.

- **MercadoLibre**:
	- No soportado.

- **Google Actions**:
	- No soportado. Utilizar respuestas rápidas en el lugar.

## Respuestas rápidas (pills)

  - **Facebook Messenger y WebChat**:
	- Texto de los botones en formato UTF-8 con límite de 20 caracteres. Pueden ser usados emojis. Hasta 10 pills.
	- ![Con Respuesta Rápida activada](https://botmakeradmin.github.io/docs/pt/imagens/ComRespostaRapida.jpg)


- **Telegram**:
	- Texto anterior de los botones en formato UTF-8 con límite de 640 caracteres;
	- Texto de los botones en formato UTF-8 con límite de 20 caracteres. Solo soporta hasta una URL.

- **Twitter**:
	- Texto anterior de los botones en formato UTF-8 con límite de 640 caracteres;
	- Texto de los botones en formato UTF-8 con límite de 20 caracteres. 

- **MercadoLibre**:
	- No soportado.

- **Google Actions**:
	- Texto anterior de los botones en formato UTF-8 con límite de 640 caracteres;
	- Texto de los botones en formato UTF-8 com límite de 20 caracteres. Hasta 8 pills.

 ## Carrousel
  - **Facebook Messenger y WebChat**:
	- **Imagen** - formato JPG con aspect ratio de 1.91:1. Tamaño recomendado: 1200x628px.
	- **Título** - texto en formato UTF-8 con límite de 80 caracteres.
	- **Subtítulo** - texto en formato UTF-8 con límite de 80 caracteres.
	- **Botones** - texto en formato UTF-8 con límite de 20 caracteres.

- **Telegram**:
	- No soportado.

- **Twitter**:
	- No soportado.

- **MercadoLibre**:
	- No soportado.

- **Google Actions**:
	- **Imagen** - formato jpg de tamaño 128x232dp.
	- **Título** - texto en formato UTF-8, debe ser único para soportar selección por voz.
	- **Subtítulo** - texto en formato UTF-8, con un máximo de 4 líneas.
	- **Botones** - texto en formato UTF-8 con límite de 20 caracteres.

## Imagenes
  - **Facebook Messenger y WebChat**:
	- Formato JPG, GIF (<75 frames) y PNG (recomendado);
	- El tamaño debe respetar el aspect ratio de 1.91:1 (ejemplo: 1200x628px).

- **Telegram**:
	- Formatos JPG, GIF (<75 frames) y PNG (recomendado);
	- El tamaño máximo es de 5mb.

- **Twitter**:
	- Formatos JPG, GIF (<350 frames), WEBP e PNG (recomendado);
	- El tamaño máximo es de 5mb para imagenes y 15mb para GIFs.

- **MercadoLibre**:
	- No soportado.

- **Google Actions**:
	- Formatos JPG, GIF y PNG de tamaño 128x232dp.

## Audio
  - **Facebook Messenger y WebChat**:
	- Formato MP3, preferiblemente no superiores a 5mb.

- **Telegram**:
	- Formato MP3 no superiores a 20mb.

- **Twitter**:
	- No soportado.

- **MercadoLibre**:
	- No soportado.

- **Google Actions**:
	- Soporte de Speech Synthesis Markup Language ([SSML](https://www.w3.org/TR/speech-synthesis/));
	- Formatos MP3 y OGG, con 24k samples por segundo;
	- Tamaño no superior a 5mb y menor a 120 segundos de duración. 

## Vídeo
  - **Facebook Messenger y WebChat**:
	- Formato MP4, preferiblemente noo superiores a 5mb.

- **Telegram**:
	- Formato MP4 no superiores a 50mb.

- **Twitter**:
	- Especificaciones detalladas [aqui](https://developer.twitter.com/en/docs/media/upload-media/uploading-media/media-best-practices).

- **MercadoLibre**:
	- No soportado.

- **Google Actions**:
	- No soportado.

## Configuración de respuestas
Para resolver las preguntas relacionadas con la configuración de respuestas en una intención, acceda a esta pagina del manual.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAxNTcwNDU4MSw3NDIxMjYyNDgsLTE1Nj
c3Mjg0NjZdfQ==
-->
