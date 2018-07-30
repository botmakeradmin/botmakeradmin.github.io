# Ações de Cliente

![Seção](https://botmakeradmin.github.io/docs/pt/imagens/Sec%CC%A7a%CC%83oCliente.png)

Olá! Aqui vamos aprender como desenvolver códigos dentro da plataforma Botmaker.

As ações de cliente são uteis para o desenvolvimento de regras mais complexas ou então quando for desejado adiconar códigos arbitrários em uma conversa. É uma excelente alternativa para conectar serviços externos para adquirir informações relevantes em tempo real na conversa com o usuário.

_Por exemplo:_
> Você pode socilitar ao usuário que ele diga uma cor. Após enviada, você pode conectar a [Google Translating API](https://cloud.google.com/translate/docs/) para fazer o bot responder a mesma cor em outra língua.

## Como disparar um código

Primeiramente, você terá de criar uma Ação de Cliente na tela de **Códigos**. Veja abaixo: 

![Criar](https://botmakeradmin.github.io/docs/pt/imagens/CriarClient.png)

> Dê um nome à ação (não se esqueça dele), e clique em **Salvar**.

Na regra em que a ação deverá ser disparada, clique em "**+Ação**", escolha "**Client Actiom**" e selecione o código a ser executado:

![Salvar](https://botmakeradmin.github.io/docs/pt/imagens/ClientSave.png)

## Features de código

Suportamos Node.js v6.14.0, juntamente à lista de *libraries* abaixo:

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

> No caso de você desejar usar outra *library*, escreva-nos um email para [architecture@botmaker.com](mailto:architecture@botmaker.com), e nosso time irá acatar a solicitação!

## Input da Ação de Cliente

Quando o código for disparado, toda informação que tivermos do usuário, conversas e configurações gerais serão fornecidas. O json abaixo descreve o input que uma *Cloud Function* poderá usar.

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

## O objeto *context*

Um objeto somente-leitura que tem informações relevantes que uma ação de código possa requer. Ela fornece:

- **userData**: toda informação referente a um usuário, incluíndo tags e variáveis - se houver;
- **message**: informação referente à última mensagem do usuário;
- **params**: params opcionais que podem ser enviados por uma regra.

_Por exemplo:_

```javascript
const userFirstName = context.userData.FIRST_NAME;
```

## O objeto *userSession*

Esse objeto permite ler e escrever variáveis que irão durar uma sessão do usuário. É um local muito útil para guardar dados relacionados à atual conversa.

> Generalizando, uma sessão é expirada após 1 hora de inatividade do usuário. 

> Tenha em mente que os valores terão de ser do tipo de *string*

- Para ler um valor: ```userSession.get('valueKey')``` => retornará uma string com valor ou nula
- Para escrever um valor: ```userSession.set('valueKey', 'value')```

_Por exemplo:_

```javascript
if ( !userSession.get('userJustTalked') )
  userSession.set('userJustTalked', 'true');
```
_após 1 hora de inatividade, userJustTalked será nulo novamente_

## O objeto _user_
Esse objeto permite ler e escrever variáveis que persistirão ao usuário para sempre. É um local muito útil para guardar dados relacionados ao usuário.

> Tenha em mente que os valores terão de ser do tipo de *string*

- Para ler um valor: ```user.get('valueKey')``` => retornará uma string com valor ou nula
- Para escrever um valor: ```user.set('valueKey', 'value')```

_Por exemplo:_

```javascript
if ( !user.get('neverWasHere') )
  user.set('neverWasHere', 'true');
```
_o valor neverWasHere será true para sempre, ou até quando outra ação de cliente configurar um valor diferente_

## O objeto _entityLoader_

Quando for feito upload de um arquivo _cvs_ no menu "**Registros**" da plataforma, as Ações de Cliente terão acesso a ele. Uma lista guardada poderá ser filtrada. ---  For instance a store list can be filtered and showed to the user based on hes location: ---

```javascript
entityLoader('entity name', json => {
  // here you got your entity object loaded as json
});
```

## O objeto _conncetRedis_

Uma instância _db instance_ está disponível para ser utilizada com Ações de Clientes. Você pode:

```javascript
const redis = connectRedis();
const myKey = redis.get('key');
```

_Suporte completo à redis é fornecido. Dê uma olhada no node oficial: [redis library](https://github.com/NodeRedis/node_redis)._

___

# Resultado de uma Ação de Cliente
Qualquer resultado adicional que uma Ação de Cliente queira criar, precisa ser feito usando o objeto *result*.

- Para dizer algo ao usuário usando texto: ```result.text('a message')```
- Para mostrar uma imagem ao usuário: ```result.image('https://example.com/image.jpg')```
- Para mostrar um vídeo ao usuário: ```result.video('https://example.com/video.mp4')```
- Para enviar um arquivo ao usuário: ```result.image('https://example.com/myfile.doc')```
- Para enviar um áudio ao usuário: ```result.audio('https://example.com/audio.mp3')```

Também é possível enviar ao usuário um texto com botões de ação.

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

## Ir à outra regra

É possível executar uma regra, após finalizada a Ação de Cliente, de forma muito fácil. É útil pois, depois de dizer algo ao usuário, alterar algum dado ou modificar o estado dele, você desejará continuar o fluxo da conversa disparando alguma regra.


```javascript
result.gotoRule('a rule name');
```

## Término de Ação de Cliente

```result.done()``` deverá ser executado quando a Ação de Cliente for finalizada.

**É muito importante chamar _result.done()_ em todo fluxo que exista uma Ação de Cliente, de modo a finalizar a execução do mesmo**

O seguinte código mostra uma Ação de Cliente bem implementada, com o método done() chamado em todo o fluxo.

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



