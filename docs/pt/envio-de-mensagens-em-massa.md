# Envio de Mensagens em Massa

Olá! Aqui, vamos aprender como enviar mensagens em massa para seus usuários, com possibilidade de segmentação.

A BotMaker permite criar perfis de audiência customizadas para envio de mensagens, útil para:

 - Envio de publicidade; 
 - Anúncio de novidades de produtos e serviços;
 - Pesquisas sobre produtos e serviços; 
 - Anúncio de novas funcionalidades do bot; 
 - Solicitação de preenchimento de formulários;
 - Oferecimento de inscrição a novidades.

## Possibilidades

Podemos usar as seguintes variantes e configurações para o envios de mensagens em massa através da plataforma:

 - Audiências customizadas por atributos (sexo, canal, preferências, etc); 
 - Programação de data e horário para envio da notificação;
 - Suporte para mensagens com elementos de mídia (vídeos, áudios, imagens, GIFs, emojis e arquivos); 
 - Envio de mensagens com Menus de opções para realização de pesquisas ou obtenção de dados em formulário.

## Como usar?

 1. Acessar o Menu "**Audiências**";
 
 ![Acessar Pushes](https://botmakeradmin.github.io/docs/pt/imagens/Audiencias.png)

 2. Nessa seção, você poderá ver as últimas mensagens programas e também poderá criar uma nova;
 
 ![Criar um push](https://botmakeradmin.github.io/docs/pt/imagens/CriarAudiencia.png)
 
> Note que você poderá, através dos botões, observar as métricas de um push, editar um envio, duplicá-lo (para gerar um novo baseado no atual), eliminar o push ou desabilitá-lo (não será enviado quando chegar ao horário programado).
> ![Opções](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/OpcoesPush.png)

3. Para criar um novo Push, clique em "**Criar Novo**", aparecerá uma janela como essa:

![Janela Push](https://botmakeradmin.github.io/docs/pt/imagens/EditarAudiencia.png)

4. Editando um Push: 

- Você pode dar um nome ao Push editando-o no campo "Nova mensagem".

> Ele servirá apenas para identificá-lo na plataforma, não será visível para os que receberem a notificação.

- Em "Audiência" será definido quais usuários receberão a mensagem. Você poderá segmentar seu público adicionando condições, das quais somente usuários que estiverem tageados nelas receberão o push.

> Note que a medida em que você adicionar ou remover condições, o número de usuários que serão alcançados será alterado. Se você desejar enviar o push à todos os usuários, embora não recomendável, devem ser removidas todas as condições.

- Definido seu público, agora, você fará a programação da Data e Horário para a sua mensagem ser disparada.

- E, por fim, você definirá qual será a mensagem a ser enviada! Ela poderá ser: 
	- um texto: ao adicionar um "**+Texto**", será possível digitar uma mensagem de texto.
	
	- uma ação: ao adicionar uma "**+Ação**", será possível disparar uma regra do Bot, roteirizar um Questionário e/ou atribuir variáveis ao usuário;
	-  uma mídia: ao adicionar uma "**+Mídia**", será possível enviar uma imagem, um áudio, um vídeo e/ou um arquivo.

5. Após feita a configuração desejada, clique em **Salvar**, e na data e horário indicados, os usuários da segmentação receberão o Push! 

## Veja um exemplo de um Push configurado:

![Push](https://botmakeradmin.github.io/docs/pt/imagens/Push.png)

Nesse caso, somente usuários que tenham se identificado como clientes atuais da empresa, e que tenham inserido seu endereço de email no chat, receberão a oferta.




<!--stackedit_data:
eyJoaXN0b3J5IjpbNzE1OTg3NzYzLC0xMDIzNTY1NzE1XX0=
-->
