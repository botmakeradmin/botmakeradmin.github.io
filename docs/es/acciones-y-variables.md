# Acciones y Variables

Hola! Aqui vamos a aprender a usar variables y acciones de la plataforma Botmaker.

## Variables
Una variable es un nombre simbólico que es utilizado para guardar un valor. 

> Por ejemplo, la variable **${nombre}**, pueden ser valores: "Gabriel", "Julio", "Fernando", etc.

Son utilizadas para:
- Dirigir el flujo de una conversación;
- Guardar informaciones de un usuario;
- Crear intenciones con condiciones;
- Emisión de informes.

Algunas variables acompañan la plataforma como patrón, y la información que ellas contienen se completan de forma automática. Sin mayor esfuerzo, también se puede crear nuevas variables de forma manual.

### Principales variables:

A continuación, presentamos una lista de las principales variables disponibles en la plataforma, con una breve explicación de cada una.

- **isOpenNow**: con valores **true** ó **false**, indica si el Bot responderá en horario de atención o no;
- **operatorsConnectedQty**: cantidad de operadores conectados;
- **chatPlatform**: plataforma en la que está ocurriendo la conversación, puede ser "messenger", "webchat", "skype", etc;
- **isWebChatMobile**: si el usuario está conversando a través de un WebChat mobile;
- **isSubscribe**: con valores **true** ó **false**, indica si el usuario está inscripto para recibir pushes;
- **lastSeen**: última vez que el usuario vió;
- **lastUserSentence**: último mensaje del usuario;
- **lastBotSentence**: última mensaje del Bot;
- **ruleCountInSession**: cuantas veces fué disparada una intención en la sesión;
- **thisWasLastIntentToRun**: ésta fué la última intención ejecutada.

Además, también son encontradas las variables definidas en el Bot y en las Tags (temas) de usuario (verdadero/falso).

### Dónde utilizar variables?

Las variables son muy útiles al momento de definir cuando se debe disparar una Intención, que respuesta se debe dar en tal contexto o para filtrar informes.

- Variables como condición de disparo:
	- Al aplicar una condición a un Disparador, la intención solamente será disparada cuando es ejecutado el disparador y la condición se cumpla. 

![Variable de Disparo](https://botmakeradmin.github.io/docs/es/imagenes/Captura%20de%20Tela%202018-08-13%20a%CC%80s%2015.17.10.png)
	
- Variables como condición de respuestas:
	- Pueden ser utilizadas para, frente a diferentes condiciones, dar diferentes respuestas para la misma intención del usuario.

![Variable de Respuesta](https://botmakeradmin.github.io/docs/es/imagenes/Captura%20de%20Tela%202018-08-13%20a%CC%80s%2015.15.24.png)

- Variables como texto dinámico dentro de una respuesta:
	- La información contenida en una variable puede ser utilizada para dar respuestas dinámicas a los usuarios, donde la variable será substituída por su contenido.

![Variable de Texto](https://botmakeradmin.github.io/docs/es/imagenes/Captura%20de%20Tela%202018-08-13%20a%CC%80s%2015.16.19.png)

## Acciones

Las acciones permiten agregar al Bot, de manera simple, comportamientos predefinidos.

### Principales acciones:
A continuación, presentamos una lista de las principales acciones disponibles en la plataforma, con una breve explicación de cada una.

- **Question**: permite hacer preguntas al usuario y guardar su respuesta como un valor en una variable;
- **Go to**: permite redireccionar el flujo a una intención;
- **Send Email**: permite enviar un email a un usuario;
- **Send to Messenger**: permite agregar un botón para que el usuario de WebChat conecte su cuenta con Messenger;
- **Add Topic CTA**: sugiere botones con intenciones del mismo tema;
- **Subscribe/Unsubscribe**: inscribe o desinscribe al usuario de la recepción de Pushes;
- **Finish**: aborta cualquier flujo que esté siendo ejecutado;
- **Mute**: apaga el Bot por 30 minutos;
- **Notify**: marca la conversación como un mensaje no leído, para que sea visualizado por un operador;
- **Set variable**: permite crear y/o asignar un determinado valor a una variable;
- **Clear variable**: limpia una o todas las variables;
- **SaveCheckpoint/GotoCheckpoint**: permite guardar y recuperar un checkpoint a una intención;
- **ClientAction**: permite ejecutar una acción personalizada, definida en la sesión de Código;
- **Callback Url**: permite cargar una URL;
- **Generate Rule Url**: genera un link que será guardado en una variable, y cuando abre, dispara una intención definida en el Bot.

### Donde utilizar acciones?

Las acciones son configuradas en la pantalla de Respuestas, última etapa de desarrollo de una intención. Mire el ejemplo:

![Acciones](https://botmakeradmin.github.io/docs/es/imagenes/Captura%20de%20Tela%202018-08-13%20a%CC%80s%2015.14.13.png)
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjAwMDAzMTk4LDE0MDAyMzA0NCw0MTY2Mj
g5MDAsLTE5MzAyMzk2NDcsLTczNDgyOTQyOSwtOTM4NjE4Nzgx
LDg3NzUyNTU3N119
-->
