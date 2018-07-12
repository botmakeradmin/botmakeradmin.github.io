# Ações e Variáveis

Olá! Aqui vamos aprender a usar variáveis e ações na plataforma BotMaker.

## Variáveis
Uma variável é um nome simbólico que se é utilizado para guardar um valor. 

> Por exemplo, na variável **${nome}**, podem ser valores: "Gabriel", "Julio", "Fernando", etc.

São utilizadas para:
- Dirigir o fluxo de uma conversa;
- Guardar informações de um usuário;
- Criar regras com condições;
- Emissão de Relatórios.

Algumas variáveis acompanham a plataforma como padrão, e a informação que elas contêm se completam de forma automática. Sem maior esforço, também se pode criar novas variáveis de forma manual.

### Principais variáveis:

As variáveis mais utilizadas são:

- **isOpenNow**: com valores **true** ou **false**, indica se o Bot responderá no horário de atendimento ou não;
- **operatorsConnectedQty**: quantidade de operadores conectados;
- **chatPlatform**: plataforma em que está acontecendo a conversa, pode ser "messenger", "webchat", "skype", etc;
- **isWebChatMobile**: se o usuário está conversando através de um WebChat mobile;
- **isSubscribe**: com valores **true** ou **false**, indica se o usuário está inscrito para receber pushes;
- **lastSeen**: última vez que o usuário visualizou;
- **lastUserSentence**: última mensagem do usuário;
- **lastBotSentence**: última mensagem do Bot;
- **ruleCountInSession**: quantas vezes foi disparada uma regra na sessão;
- **thisWasLastIntentToRun**: esta foi a última regra a ser executada.

Ademais, também são encontradas as variáveis definidas no Bot e as Tags (temas) de usuário (verdadeiro/falso).

### Onde utilizar variáveis?

As variáveis são muito úteis no momento de definir quando se deve disparar uma Regra, qual resposta se deve dar no tal contexto ou então para filtrar Relatórios.

- Variáveis como condição de disparo:
	- Ao aplicar uma condição à um Disparador, a regra somente será disparada quando for executado o disparador e a condição for comprida. 
	
- Variáveis como condição de respostas:
	- Podem ser utilizadas para, diante de diferentes condições, dar diferentes respostas para a mesma intenção do usuário.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NDQ3MjEzMzEsNDE2NjI4OTAwLC0xOT
MwMjM5NjQ3LC03MzQ4Mjk0MjksLTkzODYxODc4MSw4Nzc1MjU1
NzddfQ==
-->