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

- Não use disparadores com poucas palavras chaves, pois deixará a regra fácil de ser disparada - e devemos deixá-las 

### Disparadores por tempo de inatividade

Quando ativado um disparador por tempo de inatividade, a regra será disparada automaticamente quando o *timer* pré definido ser atingido. O tempo computado será o tempo em que o usuário não enviou nada ao Bot.



<!--stackedit_data:
eyJoaXN0b3J5IjpbNjk3MDIxNTcxLDE1OTU4OTcxMDYsMTQ0Nz
U0NjA5MiwxMjgzMzI5NDU1XX0=
-->