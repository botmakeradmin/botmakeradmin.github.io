
# Acciones de Clientes

![Sección](https://botmakeradmin.github.io/docs/pt/imagens/Sec%CC%A7a%CC%83oCliente.png)

Hola! Aquí vamos a aprender como desarrollar códigos dentro de la plataforma Botmaker.

Las acciones del cliente son utiles para el desarrollo de intenciones mas complejas o cuando se desee agregar códigos arbitrarios en una conversación. Es una excelente alternativa para conectar servicios externos, para adquirir informaciones relevantes en tiempo real en una conversación con un usuario.

_Por ejemplo:_
> Solicitar a un usuario que le diga un color. Después de enviada, puede conectar a [Google Translating API](https://cloud.google.com/translate/docs/) para hacer que el bot responda el mismo color en otro idioma.

## Como disparar un código

Primero, tendrá que crear una Acción de Cliente en la pantalla de **Códigos**. Vea abajo: 

![Crear](https://botmakeradmin.github.io/docs/pt/imagens/CriarClient.png)

> Dé un nombre a la acción (no debe olvidarse de esto), y cliquee en **Guardar**.

En la intención en que la acción deberá ser disparada, cliquee en "**+Acción**", escoja "**Client Action**" y seleccione el código a ser ejecutado:

![Guardar](https://botmakeradmin.github.io/docs/pt/imagens/ClientSave.png)

## Caracteristicas de código

Soporta Node.js v6.14.0, junto a la lista de *libraries* abajo:

```javascript
  {
    "@turf/helpers": "^6.1.4", // accessed by "turfHelpers" var
    "@turf/turf": "^5.1.6", // accessed by "turf" var
    "bluebird": "^3.5.1", // accessed by "bluebird" var
    "googleapis": "^32.0.0", // accessed by "google" var
    "js-sha256": "^0.9.0", // accessed by "sha256" var
    "jsonwebtoken": "^8.3.0", // accessed by "jwt" var
    "lodash": "^4.17.10", // accessed by "_" var
    "md5": "^2.2.1", // accessed by "md5" var
    "moment": "^2.22.2", // accessed by "moment" var
    "redis": "^2.8.0",
    "request": "^2.87.0",
    "request-promise": "^4.2.2", // accessed by "rp" var
    "secure-random": "^1.1.1", // accessed by "securedRandom" var
    "xml2js": "^0.4.19", // accessed by "xml2js" var
    "xml2json": "^0.11.2"
  }
```

> En el caso que desee usar otra *library*, escribanos un email para [architecture@botmaker.com](mailto:architecture@botmaker.com), y nuestro equipo atenderá la solicitud!

## Input de Acción de Cliente

Cuando el código fué disparado, toda información que tenemos del usuario, conversaciones y configuraciones generales serán provistas. La json abajo describe o input que una *Cloud Function* podrá usar.

```javascript
{
  "context": {
    "userData": {
      "CHAT_PLATFORM_ID": "webchat",
      "CHAT_CHANNEL_ID": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "PLATFORM_CONTACT_ID": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "LAST_MODIFICATION": "2018-07-23T03:43:51.243Z",
      "HAS_TALKED": true,
      "_id_": "O0IUBYCHJYSA4PNB0QH7",
      "LAST_SEEN": "2018-07-23T03:43:52.279Z",
      "variables": {
        "svar": "sdas"
      },
      "tags": [
        "testtest2"
      ]
    },
    
    "message": {
      "BUSINESS_ID": "YPDXTZKM8Y3NXLXVQYAN",
      "CREATION_TIME": "2018-07-23T03:43:52.281Z",
      "FROM_NAME": "Usuario",
      "CUSTOMER_ID": "O0IUBYCHJYSA4PNB0QH7",
      "_id_": "LBIJGWZN4SJADFT2HUD2",
      "FROM": "0BBSX05QRF-3318782UBYKNLUIRBM0KL8XMDTM",
      "OBJECT_TYPE": "Message",
      "SESSION_CREATION_TIME": "2018-07-23T03:43:52.281Z",
      "AUDIOS_URLS": [],
      "MESSAGE": "test",
      "CHAT_PLATFORM_ID": "webchat",
      "CHAT_CHANNEL_ID": "YPDXTZKM8Y3NXLXVQYAN-webchat-null",
      "LAST_MODIFICATION": "2018-07-23T03:43:52.281Z",
      "TO": "me",
      "TAGS": {}
    },
    
    "params": {}
  }
}
```

## El objeto *context*

Un objeto solamente-lectura que tiene informacion relevante que una acción de código puede requerir. Esto proporciona:

- **userData**: toda información referente a un usuario, incluyendo tags y variables - si hubiera;
- **message**: información referente al último mensaje del usuario;
- **params**: params opcionales que pueden ser enviados por una intención.

_Por ejemplo:_

```javascript
const userFirstName = context.userData.FIRST_NAME;
```

## El objeto *userSession*

Este objeto permite leer y escribir variables que duran la sesión del usuario. Es muy útil para guardar datos relacionados a la conversación actual.

> Generalizando, una sesión esta expirada despues de 1 hora de inactividad del usuario. 

> Tenga en cuenta que los valores tendrán que ser de tipo *string*

- Para leer un valor: ```userSession.get('valueKey')``` => devolverá una string con un valor o nula
- Para escribir un valor: ```userSession.set('valueKey', 'value')```

_Por ejemplo:_

```javascript
if ( !userSession.get('userJustTalked') )
  userSession.set('userJustTalked', 'true');
```
_Después de 1 hora de inactividad, userJustTalked será nulo nuevamente_

## El objeto _user_
Este objeto permite leer y escribir variables que persistirán en el usuario para siempre. Es muy util para guardar dados relacionados con el usuario.

> Tenga presente que los valores tendrán que ser de tipo *string*

- Para leer un valor: ```user.get('valueKey')``` => devolverá una string con un valor o nula
- Para escribir un valor: ```user.set('valueKey', 'value')```

_Por ejemplo:_

```javascript
if ( !user.get('neverWasHere') )
  user.set('neverWasHere', 'true');
```
_El valor neverWasHere será true para siempre, o hasta cuando otra acción de cliente configure un valor diferente_

## El objeto _entityLoader_

Cuando se haga upload de un archivo _cvs_ no menu "**Registros**" de la plataforma, las Acciones de Cliente tendrán acesso a él. Una lista guardada podrá ser filtrada. ---  For instance a store list can be filtered and showed to the user based on hes location: ---

```javascript
entityLoader('entity name', json => {
  // here you got your entity object loaded as json
});
```

## El objeto _conncetRedis_

Una instancia _db instance_ está disponible para ser utilizada con Acciones de Clientes. Podrá:

```javascript
const redis = connectRedis();
const myKey = redis.get('key');
```

_Soporte completo a redes será proporcionado. De una mirada en el node oficial: [redis library](https://github.com/NodeRedis/node_redis)._

___

# Resultado de una Acción de Cliente
Cualquier resultado adicional que una Acción de Cliente quiera crear, precisa ser realizado usando el objeto *result*.

- Para decir algo a un usuario usando texto: ```result.text('a message')```
- Para mostrar una imagen a un usuario: ```result.image('https://example.com/image.jpg')```
- Para mostrar un video a un usuario: ```result.video('https://example.com/video.mp4')```
- Para enviar un archivo a un usuario: ```result.image('https://example.com/myfile.doc')```
- Para enviar un audio a un usuario: ```result.audio('https://example.com/audio.mp3')```

También es posible enviar a un usuario un texto con botones de acción.

```javascript
result.buttonsBuilder()
  .text('select an option')
  .addURLButton('click me', 'https://www.google.com') // a button that will open a page
  .addLocationButton() // ask the user for its location using GPSs
  .quickReplies() // marks the button so it's showed as pills
  .addPhoneButton('call me', '+11233212312')
  .addButton('click me', 'rule with name XX') // when user clicks it will fire the rule named XX
  .send(); // send must by always called to finalize
```

## Ir a otra intención

Es posible ejecutar una intención, después de finalizada la Acción del Cliente, de forma muy sencilla. Es util porque, despues de decir algo a un usuario, cambiar algún dato o modificar su estado, deseará continuar el flujo de la conversación disparando alguna intención.


```javascript
result.gotoRule('a rule name');
```

## Término de Acción de Cliente

```result.done()``` deberá ser ejecutado cuando una Acción de Cliente se dé por finalizada.

**Es muy importante llamar _result.done()_ en todo flujo que exista una Acción de Cliente, de modo de finalizar la ejecución del mismo**

El siguiente código muestra una Acción de Cliente bien implementada, con el método done() llamado en todo el flujo.

```javascript
rp({uri: 'https://script.google.com/macros/s/AKfycbyd5AcbAnWi2Yn0xhFRbyzS4qMq1VucMVgVvhul5XqS9HkAyJY/exec?tz=Asia/Tokyo Japan', json: true})
    .then(json=> {
        // saying the time
        result.text('The time in Tokyo is ' + json.fulldate);

        // do not forget to end the execution
        result.done();
    })
    .catch(error => {
        result.text('Problems: ' + error + '|' + JSON.stringify(error));
        result.done();
    });
```

