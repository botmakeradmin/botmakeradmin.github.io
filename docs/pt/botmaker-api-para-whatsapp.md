# Botmaker API para WhatsApp

Olá! Aqui vamos aprender como acessar a Botmaker API para WhatsApp.

A Botmaker te oferece acesso oficial para enviar e receber mensagens no WhatsApp para o mais de 1.5 bilhão de usuários ativos ao redor do mundo.

Você poderá começar a enviar mensagens sem a necessidade de programar, através da operação manual ou ativando seu Bot. Também é possível acessar a Botmaker API para conectar seus aplicativos agora mesmo.

**Só leva 15 minutos!**

> Teste agora mesmo aqui ou aqui.

## Considerações iniciais

- O processo de aprovação da sua conta só acontece uma única vez. Quando aprovada, você poderá começar de imediato a utilizar nosso sandbox para desenhar o seu processo de atendimento, seja ele manual ou automático.

- Uma vez integrado à Botmaker, há duas maneiras de iniciar uma conversa com seus usuários:

  1. Os usuários podem começar a conversa com sua marca: para isso, você pode publicar seu número de WhatsApp em anúncios, websites e landing pages, usando a URL de auto ativação: *whatsapp://send?phone=seu_número&text=Olá!*ou *https:wa.me/seu_número/?text=Olá!*.
  
  2. Você pode iniciar uma conversa com seus usuários (mesmo que não tenham conversado anteriormente com sua empresa): nesse caso, é importante que, previamente, socilite um opt-in em seu website à eles para que você tenha autorização. Pode ser um formulário de registro, um email, etc.
  
- O WhatsApp protege seus usuários contra práticas de SPAM. Eles podem te contactar por qualquer motivo, mas, no caso de que você os contacte, deve ser por uma das razões aprovadas:
  - Atualizações ou alertas de conta;
  - Informação de agendamentos;
  - Finanças pessoais;
  - Novidades de alguma atividade prévia;
  - Novidades em processos de pagamento;
  - Novidades em reservas;
  - Novidades em status de envio;
  - Novidades em trocas e tickets;
  - Novidades de transporte, etc.
  
**Não é permitido enviar mensagens de venda e publicidade.**

- Para aprovar sua conta, nos envie um email a **[servico@botmaker.com](mailto:servico@botmaker.com)** indicando:
  1. Seu **_Business Manager ID_**, obtido em [Facebook Business Manager](https://business.facebook.com/settings/info).
    - Se ainda não tem um ID, pode criar uma seguindo [estes passos](https://www.facebook.com/business/help/1710077379203657).
    
    
  2. Os **números de telefone** que serão utilizados para sua conta do WhatsApp. No geral, só um número é suficiente, porém, podem ser usados mais para diferenciar idiomas, ambientes ou países, por exemplo.
  
> Podemos te prover números no Brasil e na Argentina.

> Caso queira usar seus números, tenha em mente que somente podem ser utilizados números de telefones fixos. Se nos indicar um número de celular, este não deve ter usado o WhatsApp convencional nos últimos 6 meses.

  3. Informação para o **perfil da conta de WhatsApp**
    - **Foto de perfil** - deve ser uma imagem quadrada, de no mínimo 192x192px. Tenha em mente que o modo de visualização na lista de contatos é circular.
    - **Texto descritivo do perfil** - Sobre, Direções, Descrição do comércio, Categoria, Email de contato e URL Web.
    
![Profile picture](https://botmakeradmin.github.io/docs/pt/imagens/profilepicture.png)


## Recebendo mensagens dos usuários

As mensages enviadas pelos usuários podem ser vistas intanstaneamente no [**Console de Operador da Botmaker**](https://go.botmaker.com/), onde é possível responder manualmente ou mediante o uso de bots. Sem dificuldade, também é possível notificar um sistema dessas mensagens: se quiser receber cada mensagem, pode configurar um webhook em seus sistemas da seguinte maneira:

- Acesse o [**Console de Operador da Botmaker**](https://go.botmaker.com/) e selecione Configurações, Ajustes Internos. Se preferir, acesse diretamente: [**https://go.botmaker.com/#/adminconfig**](https://go.botmaker.com/#/adminconfig)
- Na área Endpoint de Mensagens, indique seu URL de endpoint. Por exemplo: [**https://example.com/income**](https://example.com/income)
  - Seu endpoint deve estar em **http code 200**, ter um certificado válido _https_, estar disponível todo o tempo e responder em menos de 10 segundos.
  
![](https://botmakeradmin.github.io/docs/pt/imagens/endpoint-url.png)

- Uma vez ativado, você começará a receber mensagens segundo as políticas do Google PubSub; mensagens assinadas, preservação de mensagens por 7 dias, etc. Veja mais detalhes [aqui](https://cloud.google.com/pubsub/docs/push).
- O exemplo a seguir mostra uma mensagem típica de um usuário:

```json
{
  "CHAT_PLATFORM_ID": "message_platform", // for instance whatsapp 
  "MESSAGE": "Hola!",                     // the user message text
  "CREATION_TIME": "a_date",              // ISO 8601 for message time, for instance 2018-09-03T14:30:24.578Z
  "FROM_NAME": "user_name",               // name of user if possible
  "CUSTOMER_ID": "user_id",               // unique id of user
  "_id_": "message_id",                   // unique id of message
  "FROM": "phone_number",                 // user phone number
  "SESSION_CREATION_TIME": "session_id",  // chat session id
  
  // other less important fields are also inclused in the message
  ...
}
```

- Também suportamos multimídia (mensagens de voz, áudios, documentos, imagens, etc.), por exemplo:

```json
{
   "FROM_NAME": "user_name",               // name of user if possible
   "IMAGES_URLS": [
     "https://botmaker.com/hostedImageByUser.png"
   ],
   ...
}
```

## Enviando mensagens aos usuários
É possível enviar mensagens aos usuários utilizando o Console de Operador, gerando notificações massivamente e programando envios por diferentes estímulos. Também se pode utilizar a API da Botmaker para disparar mensagens programas a partir de um sistema.

Para isso, deve-se:
- Obter um token de acesso à API:
    - Acesse a [Configuração de Canais](https://go.botmaker.com/#/platforms);
    - Selecione **Botmaker API - Credenciais**;
    - Gere um token ou utilize o que já está gerado. Em particular, é importante que salve o **Access Token**.

![GerarToken](https://botmakeradmin.github.io/docs/pt/imagens/Gerar_credenciais.png)

![accesstoken](https://botmakeradmin.github.io/docs/pt/imagens/accesstoken.png)

- Com o acesso ao token, será possível efetuar o chamado HTTP Post ao API rest com um JSON:

```bash
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' --header 'access-token: your_access_token' -d '{"chatPlatform": "whatsapp", "chatChannelNumber": "your_phone", "platformContactId": "user_phone","messageText": "message_to_send"}' 'https://go.botmaker.com/api/v1.0/message/v3'

# your_access_token: ey...
# your_phone: +55135433...
# user_phone: +5512324314..
# message_to_send: Hi!
```

la respuesta va a ser un **http code 200** con un JSON indicando el id del mensaje generado:

```json
{
  "id": "id_del_mensaje"
}
```


- A resposta será um **http code 200** com um JSON indicando o ID da mensagem gerada:

```json
{
  "id": "id_del_mensaje"
}
```

> Cada vez que uma mensagem é enviada ao usuário, será efetuado um check de controle de saldo da sua conta Botmaker. Se a conta estiver prestes a ficar sem saldo, o serviço devolverá um **http code 403 - Forbidden**, indicando que não há saldo para enviar mensagens no JSON de resposta:

```json
{
  "error": {
    "code": 101,
    "message": "Insufficient credit"
  }
}
```

> Cada vez que uma mensagem é enviada ao usuário, será efetuado um check para determinar se a mensagem será rejeitada pelo WhatsApp, já que o usuário não conversou com você na plataforma nas últimas 24 horas. Veja a seção **Templates de Mensagens** para mais informações:

```json
{
  "error": {
    "code": 201,
    "message": "User window is over 24 hours"
  }
}
```

### Templates de mensagens
O WhatsApp permite enviar mensagens aos usuários em até 24 horas depois da última mensagem enviada por ele. Fora desse prazo, as mensagens deverão ser enviadas utilizando o endpoint **intent** e realizando os seguintes passos:

- Acessar Templates de Mensagens no Facebook Business Manager;
- Anotar o **namespace**, **templates** e seus **parâmetros** (se os usam);
- Acessar a [**Configuração de Regras**](https://go.botmaker.com/#/rule);
- Criar uma nova intenção. É importante lembrar o nome dessa intenção para os próximos passos;
- Na aba de **Respostas**, criar uma ação chamada **WhatsApp Template**:

![whatsapptemplate](https://botmakeradmin.github.io/docs/pt/imagens/whatsapptemplate.png)

- Na ação, anotar **namespace**, **templates** e seus **parâmetros**;
- E, finalmente, efetuar a chamada ao endpoint:

```bash
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' --header 'access-token: your_token' -d '{"chatPlatform": "whatsapp", "chatChannelNumber": "your_phone_number", "platformContactId": "user_phone_number", "ruleNameOrId": "rule_name", "params": {"my_template_var":"var_value"}}' 'https://go.botmaker.com/api/v1.0/intent/v2'

# your_token: your access token
# your_phone_number: whatsapp number of yours
# user_phone_number: whatsapp number of user
# rule_name: botmaker rule name
```

### Mensagens multimídia 
A Botmaker permite enviar todas os tipos de mensagens multimídia suportados pelo WhatsApp e outros canais. Para isso, deve-se criar uma mensagem em Regras seguindo a página de **[Como criar respostas]**() em uma intenção.

Também se pode chamar o serviço de ativação de regras desde o seu sistema, por exemplo:

```bash
 curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' --header 'access-token: your_token' -d '{"chatPlatform": "whatsapp", "chatChannelNumber": "your_phone_number", "platformContactId": "user_phone_number", "ruleNameOrId": "rule_name", "params": {"param_key_1":"param_value_1"}}' 'https://go.botmaker.com/api/v1.0/intent/v2'

# your_token: your access token
# your_phone_number: whatsapp number of yours
# user_phone_number: whatsapp number of user
# rule_name: botmaker rule name
```

### Alterações no estado das mensagens enviadas
Posteriormente ao envio de uma mensagem ao usuário, seu endpoint receberá notificações de entrega ou leitura dessa mensagem.

1. **Delivered** indica que a mensagem foi enviada - check duplo do WApp.
2. **Read** indica que a mensagem foi lida pelo usuário de destino - check duplo azul do WApp.

```json
{
  "CHAT_PLATFORM_ID": "message_platform", // for instance whatsapp 
  "CREATION_TIME": "a_date",              // ISO 8601 for message time, for instance 2018-09-03T14:30:24.578Z
  "CUSTOMER_ID": "user_id",               // unique id of user
  "_id_": "message_id",                   // unique id of message
  "FROM": "phone_number",                 // user phone number
  "STATUS": "el_cambio_status"            // message read or delivered
}
```

>Se a opção Confirmação de Leitura for desativada pelo usuário nas configurações de privacidade, essas mensagens não serão recebidas.

### Aplicar formatos à mensagens através da API
É possível aplicar formatos simples à textos de mensagens que serão enviadas aos usuários, por exemplo “Olá, *João*”. Para mais informações, cheque a [**Documentação de Formatos do WhatsApp.**](https://faq.whatsapp.com/en/android/26000002/)

