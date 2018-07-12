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

A seguir, apresentaremos uma lista das principais variáveis disponíveis na plataforma, com uma breve explicação de cada uma.

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

- Variáveis como texto dinâmico dentro de uma resposta:
	- A informação contida em uma variável pode ser utilizada para dar respostas dinâmicas aos usuários, onde a variável será substituída pelo seu conteúdo.

## Ações

As ações permitem agregar ao Bot, de maneira simples, comportamentos pré definidos.

### Principais ações:
A seguir, apresentaremos uma lista das principais ações disponíveis na plataforma, com uma breve explicação de cada uma.

- **Question**: permite fazer perguntas ao usuário e guardar sua resposta como um valor em uma variável;
- **Go to**: permite redirecionar o fluxo a uma regra;
- **Send Email**: permite enviar um email a um usuário;
- **Send to Messenger**: permite adicionar um botão para que o usuário de WebChat conecte suas conta com o Messenger;
- **Add Topic CTA**: sugere botões com regras de mesmo tema;
- **Subscribe/Unsubscribe**: inscreve ou desinscreve o usuário do recebimento de Pushes;
- **Finish**: aborta qualquer fluxo que esteja sendo executado;
- **Mute**: desliga o Bot por 30 minutos;
- **Notify**: marca a conversa como uma mensagem não lida, para que seja visualizada por um operador;
- **Set variable**: permite criar e/ou assignar um determinado valor à uma variável;
- **Clear variable**: limpa uma (ou todas) variáveis;
- **SaveCheckpoint/GotoCheckpoint**: permite guardar e recuperar um checkpoint à uma regra;
- **ClientAction**: permite executar uma ação personalizada, definida na sessão de Código;
- **Callback Url**: permite postar em uma URL;
- **Generate Rule Url**: gera um link que será guardado em uma variável, e quando aberto, dispara a regra definida no Bot.

### Onde utilizar ações?

As ações são configuradas na tela de Respostas, última etapa do desenvolvimento de uma Regra. Veja o exemplo:
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjAwMDAzMTk4LDE0MDAyMzA0NCw0MTY2Mj
g5MDAsLTE5MzAyMzk2NDcsLTczNDgyOTQyOSwtOTM4NjE4Nzgx
LDg3NzUyNTU3N119
-->