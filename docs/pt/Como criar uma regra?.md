# Como criar uma regra?

Olá! Aqui vamos aprender como cria-se uma **regra**.

Um Bot é um conjunto de regras - as regras permitem definir o que será respondido pelo Bot diante uma específica solicitação do usuário. Sua criação é feita em duas partes:

- **Disparadores**: sob que condições e/ou mensagens de usuários, a regra deverá ser disparada? Podem ser:

	- Por compreensão de uma mensagem do usuário;
	- Por tempo de inatividade do usuário.

- **Resposta**: quando compreendido o disparador, o que o Bot fará?

## Disparadores

### Disparadores por compreensão de frase

Os diparadores por compreensão de uma frase podem ser de dois tipos:
![EstáticoeVariável](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/Estatico.png)

#### Frases estáticas

O Bot será muito restrito com a compreensão dessas frases, e somente pequenas variações serão interpretadas - como sinônimos globais.

#### Frases com variáveis

Nesse caso, as palavras marcadas como **"palavras importantes"** aumentarão as possibilidades de compreensão da solicitação. Além dos sinônimos globais, variações selecionadas de cada palavra, serão suficientes para ativar a regra.


**Dicas:**

- Não use disparadores com poucas palavras chaves, pois deixará a regra muito ampla e fácil de ser disparada - devemos deixá-las de modo em que ela não seja confundida com outra solicitação.
- "Brinque" com as possibilidades dos disparadores - observe que você pode duplicar um disparador, podendo desativar uma palavra importante (cuidado para não deixar a regra ampla!)

### Disparadores por tempo de inatividade

Quando ativado um disparador por tempo de inatividade, a regra será disparada automaticamente quando o *timer* pré definido ser atingido. O tempo computado será o tempo em que o usuário não enviou nada ao Bot.

Para utilizar o disparador por tempo de inatividade, siga o procedimento do vídeo abaixo:

[![](http://img.youtube.com/vi/uROmiorHU-c/0.jpg)](http://www.youtube.com/watch?v=uROmiorHU-c "")


## Respostas

![Respostas](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/Respostas.png)

Quando uma regra for disparada, o Bot executará tudo o que for definido na tela de **Respostas**, na ordem que estiverem os conteúdos.

Os elementos da mensagem podem ser:

### Texto
Pressionando o botão +Texto, poderá ser adicionado um texto para a mensagem que deseja-se ser enviada. Cada caixa de texto adicionada, será uma caixa de texto na interface do chat.

###  Botões
Pressionando o botão +Botões, poderá ser adicionado um texto com opções, essas opções aparecerão em formato de botões para o usuário.

Esses botões podem ser:

- Abrir link
- Disparar uma regra (*Fire rule*)
- Compartilhar
- Chamada (Chamar)

Observe a opção **"Ativar resposta rápida"**, ele só poderá ser ativado quando os botões adicionados forem de redirecionamento para regras. Essa opção mudará o formato do botão, no Messenger e no WebChat, como podemos ver abaixo:

Com resposta rápida ativada:

![Com Resposta Rápida ativada](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/ComRespostaRapida.jpg)

Sem resposta rápida ativada:

![Sem Resposta Rápida ativada](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/SemRespostaRapida.jpg)

### Carrossel
Pressionando o botão +Carrossel, será possível adicionar diversas imagens, com possibilidade de adicionar nome, descrição e botões, no formato de Carrossel, como observamos abaixo:

![Carrossel](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/imagens/Carrossel.png)

### Ações
As ações permitem agregar ao Bot, de maneira simples, comportamentos pré definidos.

Temos um artigo inteiro sobre elas, que poderá te ajudar a aprender sobre seus usos! 
[Clique aqui para acessar.](https://github.com/botmakeradmin/botmakeradmin.github.io/blob/master/docs/pt/A%C3%A7%C3%B5es%20e%20Vari%C3%A1veis.md)

### Mídia
Pressionando o botão +Mídia, poderá ser adicionado qualquer tipo de arquivo ao chat, como imagens, vídeos, áudios ou qualquer outo arquivo. 

> Lembre-se que você pode reajustar a posição do conteúdo, arrastando-o ao clicar em **Arrastar**, acima de **Excluir**.

### Vídeo ilustrativo

No vídeo abaixo, você verá como adicionar textos, botões, mídias e ações, na prática.

[![](http://img.youtube.com/vi/bzvXxP1gDtA/0.jpg)](http://www.youtube.com/watch?v=bzvXxP1gDtA "")

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MjgzNjYyMiwxMzM2ODMwNDE3LC0yMT
Q0NTMwMzg1LDE1NDU1MjU3MzQsMTU5NTg5NzEwNiwxNDQ3NTQ2
MDkyLDEyODMzMjk0NTVdfQ==
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTkyNzU5NTAxXX0=
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMzM5MTg4MjNdfQ==
-->
