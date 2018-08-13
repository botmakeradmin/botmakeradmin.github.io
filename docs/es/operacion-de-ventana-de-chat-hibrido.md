# Operación de Ventana de Chats Híbrida

Hola! Aquí vamos a aprender como operar la Ventana de Chats Híbrida.

En esta sección, es donde encontramos todas las conversaciones en tiempo real, y donde, también, trabajan los usuarios con perfil de Operadores. Se divide en 3 columnas, de izquierda a derecha:

 1. Lista de Conversaciones;
 2. Detalle de Conversaciones;
 3. Información adicional y tags;

# 1. Lista de Conversaciones

![Lista](https://botmakeradmin.github.io/docs/pt/imagens/todoschats.png)
 
Visibles en la columna izquierda, están todas las conversaciones ordenadas cronológicamente, de más reciente a más antigua. 

Al cliquear sobre una conversación, la columna central se actualizará, mostrando en detalle el chat completo. 

## Identificación:

Dentro de cada chat, es posible ver la identificación del usuario y el último mensaje recibido/enviado. La identificación se hace de la siguiente manera:

![ChatWeb](https://botmakeradmin.github.io/docs/pt/imagens/Chatweb.png)

![ChatFace](https://botmakeradmin.github.io/docs/pt/imagens/ChatFace.png)

- **Foto de perfil**: 
Siempre y cuando el usuario está en una conversación a través de un canal fijo (Messenger, Twitter, Telegram, WhatsApp, etc), será posible visualizar su foto de perfil. 

	 - Si no tiene, la conversación se realizó a través de un WebChat (donde el usuario es anonimo), será mostrada una imagen genérica.

- **Nombre de usuario**:
Siempre y cuando el usuario está en una conversación a través de un canal fijo (Messenger, Twitter, Telegram, WhatsApp, etc), será posible visualizar su nombre y sobrenombre.

	 - Si la conversación fué realizada a través de un WebChat (donde el usuario es anonimo), será mostrado un código único para individualizar ese chat.

- **Canal**:
Es posible observar en la conversación un ícono indicativo del canal utilizado por el usuario para comunicarse con el Bot. 

	 - Ellos pueden ser: Messenger, WhatsApp, Telegram, Twitter DM, Google Assistant ou Google Chrome - el último es utilizado cuando la conversación es proveniente de un WebChat.

	 - En el caso de ser una conversación de WebChat, el ícono de Chrome vendrá con una marca verde - si el usuario todavia está conectado - o rojo - si el usuario ya está desconectado.
 
	-	![Icones](https://botmakeradmin.github.io/docs/pt/imagens/icones.png) 

- **País**:
En conversaciones de WebChat, la plataforma indicará el país del usuario, una información obtenida a partir de su dirección IP.

- **Fecha**:
Es posible observar en una conversación la fecha del último mensaje recibido/enviado. Si no se muestra la fecha, será mostrado cuanto tiempo desde el último mensaje.

- **Conversación tomada**:
Cuando una conversación es tomada por un operador, ella será marcada con un candado, junto a las iniciales del operador que la ha tomado.

## Búsqueda:
Sobre los chats, se encuentra una barra de búsqueda. Es posible buscar un chat por el nombre del usuario o por un mensaje contenido en el chat.

![Búsqueda](https://botmakeradmin.github.io/docs/pt/imagens/BuscaChat.png)

También es posible filtrar, para mostrar chats solo las situaciones deseadas:

![Filtro](https://botmakeradmin.github.io/docs/pt/imagens/FiltroCHat.png)

# 2. Detalle de Conversaciones

![Detalle](https://botmakeradmin.github.io/docs/pt/imagens/Detalhe.png)

Encontrado en la columna central de la pantalla, se puede visualizar el historial de conversación completo de cada usuario.

A partir del momento que el Bot entiende las solicitudes de los usuarios y las responde, la conversación puede ser totalmente automática. 

También, la plataforma fué diseñada para una operación híbrida (Bot/Humano), y es por eso que se encuentran todos los elementos necesarios para la operación humana:

## Caja de texto:

![Caja](https://botmakeradmin.github.io/docs/pt/imagens/escreverchat.png)

En la parte inferior se encuentra una caja de texto, donde los operadores pueden ejecutar las siguientes funciones:

 - Escribir manualmente sus mensajes para intervenir en la conversación; 
 - Enviar imagenes, vídeos y archivos; 
 - Grabar mensajes de voz (requiere un micrófono); 
 - Enviar GIFs y emojis.

Adicionalmente, cuando el cursor está en la caja de texto, el operador puede presionar la tecla "**Enter**" para abrir un Menu de acciones del Bot.

![Intenciones](https://botmakeradmin.github.io/docs/pt/imagens/pesquisaregras.png)

> En ella, el operador puede buscar una intención cargada en el Bot para enviarla como respuesta a una pregunta no comprendida del usuario. Al hacer eso, no solo el usuario recibirá la respuesta, sino que también el Bot estará siendo entrenado para futuras ocasiones similares, para responder sin necesitar de la participación de un operador.

## Opciones de Encabezamiento:

![Opciones](https://botmakeradmin.github.io/docs/pt/imagens/opcoeschat.png)

![OpcionesChat](https://botmakeradmin.github.io/docs/pt/imagens/opcoeschata.png)

Además de los puntos descriptos anteriormente, también pueden ser ejecutados diversas acciones a través del encabezamiento del Detalle de Conversación.

### Bloquear chat

Seleccionando esa opción, al Operador le será asignanda una conversación, de manera de evitar que otros operadores puedan responder al usuario en ese momento. 

> Una conversación bloqueada no podrá tener intervención de otro operador antes que sea liberada, cliqueando en "**Liberar chat bloqueado**".

### Asignar usuario a otro operador
Seleccionando esa opción, será posible asignar la conversación a un operador específico, que entienda mejor del tema preguntado, por ejemplo. Se bloqueará y desbloqueará como se describe anteriormente.

### Marcar como no leído
Seleccionando esa opción, la conversación será marcada como "**No Leída**".

### Marcar como SPAM
Seleccionando esa opción, el usuario será bloqueado por 7 días. Se en casosque el usuario esté molestando al Bot/Operador, haciendo preguntas sin sentido. 

> Un usuario bloqueado podrá seguir enviando mensajes, pero el Bot dejará de responderle y los Operadores no serán notificados sobre la conversación.

## Desactivar al Bot en la conversación

![Bloquear](https://botmakeradmin.github.io/docs/pt/imagens/desativarbot.png)

El Bot puede ser desactivado por un operador (en una conversación específicamente), seleccionando la opción de abajo:

Se recomienda utilizar esa funcionalidad siempre que un operador precise intervenir manualmente en una conversación, de manera de evitar que el Bot responda las preguntas.

Una vez que el operador responda a las solicitudes del usuario, o cuando sea pertinente, el puede reactivar el funcionamiento del Bot, cliqueando en el mismo botón. 

> En caso de olvido, la reactivación del Bot se realizará automaticamente despues de 30 minutos.

# 3. Informacióno adicional y Tags
La tercera y última columna esta localizada a la derecha de la pantalla de Chats Híbrida. La misma muestra todas las informaciones guardadas, provenientes del usuario, además de los temas de conversación recorridos durante la conversación.

### Información adicional

![Info add](https://botmakeradmin.github.io/docs/pt/imagens/informacaoadd.png)

Donde están localizadas las informaciones que, historicamente, fueron almacenadas por el Bot a través de la interacción con el usuario. Pueden ser guardadas, por ejemplo: 

- Nombre y sobrenombre; 
- Fecha de nacimiento;
- Email;
- Dirección;
- Canal utilizado;
- URL de interacción;
- Y cualquier otra información que el Bot solicite al usuario.

De la lectura de la conversación, también es posible obtener nuevas informaciones, que pueden ser incorporadas manualmente cliqueando en el botón "**Editar**". Se selecciona la variable y la informacióno a ser guardada.

![Editar info](https://botmakeradmin.github.io/docs/pt/imagens/addinfo.png)

### Etiquetas

![Etiquetas](https://botmakeradmin.github.io/docs/pt/imagens/tags.png)

Las Etiquetas son los temas de conversación de los cuales el usuario ha recorrido historicamente en el chat. Se agregan automáticamente, siempre y cuando se trate de temas de los cuales el Bot entiende.

En casos que los Operadores necesiten etiquetar temas no comprendidos por el Bot, en un Chat específico, el proceso puede ser realizado manualmente cliqueando en el botón "**Modificar**".


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODUyNjMyOCwtMTI4NDMxMTY5NSwtNz
UwMDIxODY1LC0yMjY0OTIzMDcsLTI0MjA0MjIyNiwtMTAxODg3
NjY0NywxMDM1NDc0NDY3LDIxMDQzNDQ0MTMsMTkyMjQzOTk2NC
wtMTMyNjk1OTc0OCwxNjc1NTcxMTg1LC0xNjkwOTQyNjk3LC0x
NzkxODg5MjI2XX0=
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI2NDA4NTY4LC04Njk0MzE0NzUsMjEwOD
AwMDcxNF19
-->
