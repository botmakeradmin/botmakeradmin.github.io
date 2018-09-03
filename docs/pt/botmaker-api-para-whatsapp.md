# Botmaker API para WhatsApp

Olá! Aqui vamos aprender como acessar a Botmaker API para WhatsApp.

A Botmaker te oferece acesso oficial para enviar e receber mensagens no WhatsApp para o mais de 1.5 bilhão de usuários ativos ao redor do mundo.

Você poderá começar a enviar mensagens sem a necessidade de programar, através da operação manual ou ativando seu Bot. Também é possível acessar a Botmaker API para conectar seus aplicativos agora mesmo.

**Só leva 15 minutos!**

> Teste agora mesmo aqui ou aqui.

## Considerações iniciais

- O processo de aprovação da sua conta ??WhatsApp Business/Enterprise?? só acontece uma única vez. Quando aprovada, você poderá começar de imediato a utilizar nosso sandbox para desenhar o seu processo de atendimento, seja ele manual ou automático.

- Uma vez integrado à Botmaker, há duas maneiras de iniciar uma conversa com seus usuários:

  1. Os usuários podem começar a conversa com sua marca: para isso, você pode publicar seu número de WhatsApp em anúncios, websites e landing pages, usando a URL de auto ativação: whatsapp://send?phone=seu_número&text=Olá! ou https:wa.me/seu_número/?text=Olá!.
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

- Para aprovar sua conta, nos envie um email a servico@botmaker.com indicando:
  1. Seu **_Business Manager ID_**, obtido em Facebook Business Manager.
  
    - Se ainda não tem um ID, pode criar uma seguindo estes passos.
    
  2. Os **números de telefone** que serão utilizados para sua conta do WhatsApp. No geral, só um número é suficiente, porém, podem ser usados mais para diferenciar idiomas, ambientes ou países, por exemplo.
  
> Podemos te prover números no Brasil e na Argentina.

> Caso queira usar seus números, tenha em mente que somente podem ser utilizados números de telefones fixos. Se nos indicar um número de celular, este não deve ter usado o WhatsApp convencional nos últimos 6 meses.

  3. Informação para o **perfil da conta de WhatsApp**
    - **Foto de perfil** - deve ser uma imagem quadrada, de no mínimo 192x192px. Tenha em mente que o modo de visualização na lista de contatos é circular.
    
    - **Texto descritivo do perfil** - Sobre, Direções, Descrição do comércio, Categoria, Email de contato e URL Web.
    
## Recebendo mensagens dos usuários

As mensages enviadas pelos usuários podem ser vistas intanstaneamente no Console de Operador da Botmaker, onde é possível responder manualmente ou mediante o uso de bots. Sem dificuldade, também é possível notificar um sistema dessas mensagens: se quiser receber cada mensagem, pode configurar um webhook em seus sistemas da seguinte maneira:

- Acesse o Console de Operador da Botmaker e selecione Configurações, Ajustes Internos. Se preferir, acesse diretamente:
- Na área Endpoint de Mensagens, indique seu URL de endpoint. Por exemplo:
  - Seu endpoint deve estar em _http code 200_, ter um certificado válido _https_, estar disponível todo o tempo e responder em menos de 2 segundos.
  
## Enviando mensagens aos usuários

## Alterações no estado das mensagens enviadas

## Sandbox
