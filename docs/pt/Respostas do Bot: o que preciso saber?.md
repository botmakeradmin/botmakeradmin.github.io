# Respostas do Bot: o que preciso saber?

Olá! Aqui vamos aprender quais são os formatos corretos para cada elemento de conversação para as diferentes plataformas suportadas pela BotMaker.

## Textos

- **Facebook Messenger e WebChat**:
	-  Formato UTF-8, com limite de 640 caracteres por caixa de texto. Se excedido, o texto será separado em diversas mensagens.

- **Telegram**:
	-  Formato UFT-8 com limite de 4096 caracteres.
  
- **Twitter**:
	-  Formato UTF-8 com limite desconhecido.
  
 - **MercadoLivre**:
	-  Formato UTF-8 com limite de 2000 caracteres.
  
 - **Google Actions**:
	 - Formato UTF-8 com limite de 640 caracteres.

## Botões
- **Facebook Messenger e WebChat**:
	- Texto anterior aos botões em formato UTF-8 com limite de 640 caracteres;
	- Texto dos botões em formato UTF-8 com limite de 20 caracteres. Os botões suportam URLs.

- **Telegram**:
	- Não suportado. Utilizar respostas rápidas no lugar.

- **Twitter**:
	- Não suportado. Utilizar respostas rápidas no lugar.

- **MercadoLivre**:
	- Não suportado.

- **Google Actions**:
	- Não suportado. Utilizar respostas rápidas no lugar.

## Respostas rápidas (pills)

  - **Facebook Messenger e WebChat**:
	- Texto dos botões em formato UTF-8 com limite de 20 caracteres. Podem ser usados emojis. Até 10 pills.

- **Telegram**:
	- Texto anterior aos botões em formato UTF-8 com limite de 640 caracteres;
	- Texto dos botões em formato UTF-8 com limite de 20 caracteres. Só suporta até uma URL.

- **Twitter**:
	- Texto anterior aos botões em formato UTF-8 com limite de 640 caracteres;
	- Texto dos botões em formato UTF-8 com limite de 20 caracteres. 

- **MercadoLivre**:
	- Não suportado.

- **Google Actions**:
	- Texto anterior aos botões em formato UTF-8 com limite de 640 caracteres;
	- Texto dos botões em formato UTF-8 com limite de 20 caracteres. Até 8 pills.

 ## Carrossel
  - **Facebook Messenger e WebChat**:
	- **Imagem** - formato JPG com aspect ratio de 1.91:1. Tamanho recomendado: 1200x628px.
	- **Título** - texto em formato UTF-8 com limite de 80 caracteres.
	- **Subtítulo** - texto em formato UTF-8 com limite de 80 caracteres.
	- **Botões** - texto em formato UTF-8 com limite de 20 caracteres.

- **Telegram**:
	- Não suportado.

- **Twitter**:
	- Não suportado.

- **MercadoLivre**:
	- Não suportado.

- **Google Actions**:
	- **Imagem** - formato jpg de tamanho 128x232dp.
	- **Título** - texto em formato UTF-8, deve ser único para suportar seleção por voz.
	- **Subtítulo** - texto em formato UTF-8, com no máximo 4 linhas.
	- **Botões** - texto em formato UTF-8 com limite de 20 caracteres.

## Imagens
  - **Facebook Messenger e WebChat**:
	- Formato JPG, GIF (<75 frames) e PNG (recomendado).
	- O tamanho deve respeitar o aspect ratio de 1.91:1 (exemplo: 1200x628px).

- **Telegram**:
	- Formatos JPG, GIF (<75 frames) e PNG (recomendado).
	- O tamanho máximo é de 5mb.

- **Twitter**:
	- Formatos JPG, GIF (<350 frames), WEBP e PNG (recomendado).
	- O tamanho máximo é de 5mb para imagens e 15mb para GIFs.

- **MercadoLivre**:
	- Não suportado.

- **Google Actions**:
	- Formatos JPG, GIF e PNG de tamanho 128x232dp.

## Áudio
  - **Facebook Messenger e WebChat**:
	- Formato JPG, GIF (<75 frames) e PNG (recomendado).
	- O tamanho deve respeitar o aspect ratio de 1.91:1 (exemplo: 1200x628px).

- **Telegram**:
	- Formatos JPG, GIF (<75 frames) e PNG (recomendado).
	- O tamanho máximo é de 5mb.

- **Twitter**:
	- Formatos JPG, GIF (<350 frames), WEBP e PNG (recomendado).
	- O tamanho máximo é de 5mb para imagens e 15mb para GIFs.

- **MercadoLivre**:
	- Não suportado.

- **Google Actions**:
	- Formatos JPG, GIF e PNG de tamanho 128x232dp.
 


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMwNTgzMTYwOCwtMTU2NzcyODQ2Nl19
-->