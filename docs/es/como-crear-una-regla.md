# Como crear una intención?

Hola! Aqui vamos a aprender como se crea una **intención**.

Un Bot es un conjunto de intenciones. Las intenciones permiten definir lo que será respondido por el Bot frente a una solicitud específica del usuario. Su creación consta de dos partes:

- **Disparadores**: sobre que condiciones y/o mensajes de usuarios, la intención deberá ser disparada? Pueden ser:

	- Por comprensión de un mensaje del usuario;
	- Por tiempo de inactividad del usuario.

- **Respuesta**: cuando ha entendido el disparador, que hará el Bot?

## Disparadores

### Disparadores por comprensión de frase

Los diparadores por comprensión de una frase pueden ser de dos tipos:
![EstáticoyVariable](https://botmakeradmin.github.io/docs/pt/imagens/Estatico.png)

#### Frases estáticas

El Bot será muy estricto con la comprensión de esas frases, y solamente pequeñas variaciones serán interpretadas - como sinónimos globales.

#### Frases con variables

En ese caso, las palabras marcadas como **"palabras importantes"** aumentarán las posibilidades de comprensión de la solicitud. Además de los sinónimos globales, variaciones seleccionadas de cada palabra, serán suficientes para activar la intención.


**Consejos:**

- No use disparadores con pocas palabras claves, porque dejará la intención muy amplia y fácil de ser disparada - debemos dejarlas de modo que ella no sea confundida con otra solicitud.
- "Juegue" con las posibilidades de los disparadores - observe que puede duplicar un disparador, pudiendo desactivar una palabra importante (cuidado para no dejar una intención amplia!)

### Disparadores por tiempo de inactividad

Cuando se activa un disparador por tiempo de inactividad, la intención será disparada automaticamente cuando el *timer* predefinido sea cumplido. El tiempo computado será el tiempo en que el usuario no haya enviado nada al Bot.

Para utilizar el disparador por tiempo de inactividad, siga el procedimiento del vídeo aqui debajo:

[![](http://img.youtube.com/vi/uROmiorHU-c/0.jpg)](http://www.youtube.com/watch?v=uROmiorHU-c)


## Respuestas

![Respuestas](https://botmakeradmin.github.io/docs/pt/imagens/Respostas.png)

Cuando una intención fué disparada, el Bot ejecutará todo lo que se define en la pantalla de **Respuestas**, en el orden que esten los contenidos.

Los elementos del mensaje pueden ser:

### Texto
Presionando el botón + Texto, podrá ser agregado un texto para el mensaje que desease ser enviado. Cada caja de texto agregado, será una caja de texto en la interfaz del chat.

###  Botones
Presionando el botón + Botones, podrá ser adicionado un texto con opciones, esas opciones aparecerán en formato de botones para el usuário.

Esses botones pueden ser:

- Abrir link
- Disparar una intención (*Fire rule*)
- Compartir
- Llamada (Llamar)

Observe la opción **"Activar respuesta rápida"**, ésta solo podrá ser activada cuando los botones agegados fueran de redireccionamento para intenciones. Esa opción cambiará el formato del botón, en Messenger y en WebChat, como podemos ver abajo:

Con respuesta rápida activada:

![Con Respuesta Rápida activada](https://botmakeradmin.github.io/docs/pt/imagens/ComRespostaRapida.jpg)

Sin respuesta rápida activada:

![Sin Respuesta Rápida activada](https://botmakeradmin.github.io/docs/pt/imagens/SemRespostaRapida.jpg)

### Carrousel
Presionando el botón + Carrousel, será posible agregar diversas imagenes, con posibilidad de agregar nombre, descripción y botones, en formato de Carrousel, como observamos aquí debajo:

![Carrousel](https://botmakeradmin.github.io/docs/pt/imagens/Carrossel.png)

### Acciones
Las acciones permiten agregar al Bot, de manera simple, comportamientos predefinidos.

Tenemos un artículo entero sobre ellas, que te podrá ayudar a aprender sobre su uso! 
[Cliquee aquí para ingresar.](https://botmakeradmin.github.io/docs/pt/A%C3%A7%C3%B5es%20e%20Vari%C3%A1veis.md)

### Media
Presionando el botón + Media, podrá ser agregado cualquier tipo de archivo al chat, como imagenes, vídeos, audios o cualquier otro archivo. 

> Recuerde que puede reajustar la posición del contenido, arrastrando o al cliquear en **Arrastar**, encima de **Eliminar**.


### Vídeo ilustrativo

En el vídeo aqui debajo, podrá ver como agregar textos, botones, media y acciones, en la práctica.

[![](http://img.youtube.com/vi/bzvXxP1gDtA/0.jpg)](http://www.youtube.com/watch?v=bzvXxP1gDtA "")


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MjgzNjYyMiwxMzM2ODMwNDE3LC0yMT
Q0NTMwMzg1LDE1NDU1MjU3MzQsMTU5NTg5NzEwNiwxNDQ3NTQ2
MDkyLDEyODMzMjk0NTVdfQ==
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTkyNzU5NTAxXX0=
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMzM5MTg4MjNdfQ==
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMzNDgxMDk4OF19
-->
