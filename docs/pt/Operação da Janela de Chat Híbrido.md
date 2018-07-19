# Operação da Janela de Chats Híbrida

Olá! Aqui vamos aprender como operar a Janela de Chats Híbrida.

Nessa seção, é onde encontramos todas as conversas em tempo real, e onde, também, trabalham os usuários com perfil de Operadores. Ela é dividida em 3 colunas, da esquerda à direita:

 1. Lista de Conversas;
 2. Detalhe de Conversas;
 3. Informação adicional e tags

# 1. Lista de Conversas

![Lista](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/todoschats.png)
 
Visíveis na coluna à esquerda, estão todas as conversas ordenadas cronológicamente, da mais recente à mais antiga. 

Ao clicar sobre uma conversa, a coluna central se atualizará, mostrando em detalhe o chat completo. 

## Identificação:

Dentro de cada chat, é possível ver a identificação do usuário e a última mensagem recebida/enviada. A identificação é feita da seguinte maneira:

![ChatWeb](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/Chatweb.png)

![ChatFace](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/ChatFace.png)

- **Foto de perfil**: 
Sempre e quando o usuário estiver em uma conversa através de um canal fixo (Messenger, Twitter, Telegram, WhatsApp, etc), será possível visualizar sua foto de perfil. 

	 - Se não tiver, a conversa foi realizada através de um WebChat (onde o usuário é anônimo), e será mostrada uma imagem genérica.

- **Nome de usuário**:
Sempre e quando o usuário estiver em uma conversa através de um canal fixo (Messenger, Twitter, Telegram, WhatsApp, etc), será possível visualizar seu nome e sobrenome.

	 - Se a conversa foi realizada através de um WebChat (onde o usuário é anônimo), será mostrado um código único para individualizar esse chat.

- **Canal**:
É possível observar na conversa um ícone indicativo do canal utilizado pelo usuário para se comunicar com o Bot. 

	 - Eles podem ser: Messenger, WhatsApp, Telegram, Twitter DM, Google Assistant ou Google Chrome - o último é utilizado quando a conversa é proveniente de um WebChat.

	 - No caso de ser uma conversa de WebChat, o ícone do Chrome virá com uma marcação verde - se o usuário ainda estiver online - ou vermelha - se ele já está desconectado.
 
	-	![Icones](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/icones.png) 

- **País**:
Em conversas de WebChat, a plataforma indicará o país do usuário, uma informação obtida a partir de seu endereço IP.

- **Data**:
É possível observar na conversa a data da última mensagem recebida/enviada. Se não for mostrada a data, será mostrado quanto tempo desde a última mensagem.

- **Conversa tomada**:
Quando uma conversa for tomada por um operador, ela será marcada com um cadeado, junto às iniciais desse operador que a tomou.

## Pesquisa:
Acima dos chats, encontra-se uma barra de pesquisa. É possível pesquisar um chat pelo nome do usuário ou por uma mensagem contida no chat.

![Pesquisa](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/BuscaChat.png)

Também é possível filtrar, para mostrar chats apenas de situações desejadas:

![Filtro](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/FiltroCHat.png)

# 2. Detalhe de Conversas

![Detalhe](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/Detalhe.png)

Encontrada na coluna central da tela, pode-se visualizar o histórico de conversa completo de cada usuário.

A partir do momento que o Bot entende as solicitações dos usuários e as responde, a conversa pode ser totalmente automática. 

Também, a plataforma foi desenhada para uma operação híbrida (Bot/Humano), e é por isso que encontram-se todos os elementos necessários para a operação humana:

## Caixa de texto:

![Caixa](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/escreverchat.png)

Na parte inferior se encontra uma caixa de texto, onde os operadores podem executar as seguintes funções:

 - Escrever manualmente suas mensagens para intervir na conversa; 
 - Enviar imagens, vídeos e arquivos; 
 - Gravar mensagens de voz (requer um microfone); 
 - Enviar GIFs e emojis.

Adicionalmente, quando o cursos estiver na caixa de texto, o operador pode pressionar a tecla "**Enter**" para abrir um Menu de ações do Bot.

![Regras](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/pesquisaregras.png)

> Nela, o operador pode buscar uma regra carregada no Bot para envia-la como resposta a uma pergunta não compreendida do usuário. Ao fazer isso, não só o usuário receberá a resposta, mas também o Bot estará sendo treinado para futuras ocasiões similares, para responder sem necessitar da participação de um operador.

## Opções do Cabeçalho:

![Opções](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/opcoeschat.png)

![OpçõesChat](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/opcoeschata.png)

Ademais dos pontos descritos anteriormente, também podem ser executadas diversas ações através do cabeçalho do Detalhe de Conversa.

### Bloquear chat

Selecionando essa opção, o Operador estará se assignando a uma conversa, de maneira a evitar que outros operadores possam responder o usuário naquele momento. 

> Uma conversa bloqueada não poderá ter intervenção de outro operador antes que seja liberada, clicando em "**Liberar chat bloqueado**".

### Atribuir usuário a outro operador
Selecionando essa opção, será possível assignar a conversa a um operador específico, que entenda melhor do tema perguntado, por exemplo. Ela será bloqueada e desbloqueada como descrito acima.

### Marcar como não lido
Selecionando essa opção, a conversa será marcada como "**Não Lida**".

### Marcar como SPAM
Selecionando essa opção, o usuário será bloqueado por 7 dias. Ela é recomendada em casos que o usuário esteja molestando o Bot/Operador, fazendo perguntas sem sentido. 

> Um usuário bloqueado poderá seguir enviando mensagens, mas o Bot deixará de respondê-lo e os Operadores não serão notificados sobre a conversa.

## Desligar o Bot na conversa

![Bloquear](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/desativarbot.png)

O Bot pode ser desligado por um operador (em uma conversa, específicamente), selecionando a opção abaixo:

É recomendado utilizar essa funcionalidade sempre que um operador precisar intervir manualmente em uma conversa, de maneira a evitar que o Bot responda as perguntas.

Assim que o Operador responder as solicitações do usuário, ou quando achar pertinente, ele pode reativar o funcionamento do Bot, clicando no mesmo botão. 

> Caso se esqueça, a reativação do Bot será feita automaticamente após 30 minutos.

# 3. Informação adicional e Tags
A terceira e última coluna é localizada à direita da Janela de Chats Híbrida. A mesma mostra todas as informações guardadas, provindas do usuário, além dos temas de conversação percorridos durante conversa.

### Informação adicional

![Info add](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/informacaoadd.png)

Onde estão localizadas as informações que, historicamente, foi armazenada pelo Bot através da interação com o usuário. Podem ser guardados, por exemplo: 

- Nome e sobrenome; 
- Data de nascimento;
- Email;
- Endereço;
- Canal utilizado;
- URL de interação;
- E qualquer outra informação que o Bot solicite ao usuário.

Da leitura da conversa, também é possível obter novas informações, que podem ser incorporadas manualmente clicando no botão "**Editar**". Seleciona-se a varíavel e a informação a ser guardada.

![Editar info](

### Tags
As Tags são os temas de conversação dos quais o usuário historicamente percorreu no chat. Eles são adicionados automáticamente, sempre e quando se trata de temas dos quais Bot entende.

Em casos que os Operadores necessitem tagear temas não compreendidos pelo Bot, em um específico Chat, o processo pode ser realizado manualmente clicando no botão "**Modificar**".


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODUyNjMyOCwtMTI4NDMxMTY5NSwtNz
UwMDIxODY1LC0yMjY0OTIzMDcsLTI0MjA0MjIyNiwtMTAxODg3
NjY0NywxMDM1NDc0NDY3LDIxMDQzNDQ0MTMsMTkyMjQzOTk2NC
wtMTMyNjk1OTc0OCwxNjc1NTcxMTg1LC0xNjkwOTQyNjk3LC0x
NzkxODg5MjI2XX0=
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM4MjUwMzgwNCwtODY5NDMxNDc1LDIxMD
gwMDA3MTRdfQ==
-->