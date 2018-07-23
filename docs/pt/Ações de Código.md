# Ações de Cliente

Olá! Aqui vamos aprender como desenvolver códigos dentro da plataforma Botmaker.

As ações de cliente são uteis para o desenvolvimento de regras mais complexas ou então quando for desejado adiconar códigos arbitrários em uma conversa. É uma excelente alternativa para conectar serviços externos para adquirir informações relevantes em tempo real na conversa com o usuário.

> Por exemplo: você pode socilitar ao usuário que ele diga uma cor. Após enviada, você pode conectar a [*Google Translating API*] (https://cloud.google.com/translate/docs/) para fazer o bot responder a mesma cor em outra língua.

## Como disparar um código

Primeiramente, você terá de criar uma Ação de Código na tela de **Códigos**. Veja abaixo: 
> Dê um nome à ação (não se esqueça dele), e clique em **Salvar**.

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

> Por exemplo:

> ```javascript
const userFirstName = context.userData.FIRST_NAME;
```




