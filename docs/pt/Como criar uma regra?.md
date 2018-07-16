# Como criar uma regra?

Olá! Aqui vamos aprender como cria-se uma **regra**, ou seja, preste bastante atenção!

Um Bot é um conjunto de regras - as regras permitem definir o que será respondido pelo Bot diante uma específica solicitação do usuário. Sua criação é feita em duas partes:

- **Disparadores**: sob que condições e/ou mensagens de usuários, a regra deverá ser disparada? Podem ser:

	- Por compreensão de uma mensagem do usuário;
	- Por tempo de inatividade do usuário.

- **Resposta**: quando compreendido o disparador, o que o Bot fará?

## Disparadores

### Disparadores por compreensão de frase

Os diparadores por compreensão de uma frase podem ser de dois tipos:

#### Frases estáticas

O Bot será muito restrito com a compreensão dessas frases, e somente pequenas variações serão interpretadas - como sinônimos globais.

#### Frases com variáveis

Nesse caso, as palavras marcadas como **"palavras importantes"** aumentarão as possibilidades de compreensão da solicitação. Além dos sinônimos globais, variações selecionadas de cada palavra, serão suficientes para ativar a regra.

**Dicas:**

- Não use disparadores com poucas palavras chaves, pois deixará a regra muito ampla e fácil de ser disparada - devemos deixá-las de modo em que ela não seja confundida com outra solicitação.
- "Brinque" com as possibilidades dos disparadores - observe que você pode duplicar um disparador, podendo desativar uma palavra importante (cuidado para não deixar a regra ampla!)

### Disparadores por tempo de inatividade

Quando ativado um disparador por tempo de inatividade, a regra será disparada automaticamente quando o *timer* pré definido ser atingido. O tempo computado será o tempo em que o usuário não enviou nada ao Bot.

## Respostas

 Quando uma regra for disparada, o Bot executará tudo o que for definido na tela de **Respostas**.

Os elementos da mensagem podem ser:

### Texto
Pressionando o botão +Texto, poderá ser adicionado um texto para a mensagem que deseja-se ser enviada.

[![](http://img.youtube.com/vi/_a3CSq0jIOo/0.jpg)](http://www.youtube.com/watch?v=_a3CSq0jIOo "")

###  Botões
Pressionando o botão +Botões, poderá ser adicionado um texto com opções, essas opções aparecerão em formato de botões para o usuário.

Esses botões podem ser:

- Abrir link

[![](http://img.youtube.com/vi/FUBARvx-tDo/0.jpg)](http://www.youtube.com/watch?v=FUBARvx-tDo "")
- Disparar uma regra (*Fire rule*)

[![](http://img.youtube.com/vi/DN_S3eBYt8c/0.jpg)](http://www.youtube.com/watch?v=DN_S3eBYt8c "")
- Compartilhar
- Chamada (Chamar)

### Carrossel

### Ações

### Mídia
Pressionando o botão +Mídia, poderá ser adicionado qualquer tipo de arquivo ao chat, como imagens, vídeos, áudios ou qualquer outo arquivo. 


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU2MjgzNjYyMiwxMzM2ODMwNDE3LC0yMT
Q0NTMwMzg1LDE1NDU1MjU3MzQsMTU5NTg5NzEwNiwxNDQ3NTQ2
MDkyLDEyODMzMjk0NTVdfQ==
-->
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTkyNzU5NTAxXX0=
-->
