# Envio de Mensajes Masivos

Hola! Aquí, vamos a aprender como enviar mensajes masivos para sus usuarios, con posibilidad de segmentación.

El BotMaker permite crear perfiles de audiencia customizados para envío de mensajes, útil para:

 - Envío de publicidad; 
 - Anuncio de novedades de productos y servicios;
 - Búsquedas sobre productos y servicios; 
 - Anuncio de nuevas funcionalidades del bot; 
 - Solicitud de confección de formularios;
 - Ofrecimiento de inscripción a novedades.

## Posibilidades

Podemos usar las siguientes variantes y configuraciones para los envíos de mensajes en masa a través de la plataforma:

 - Audiencias customizadas por atributos (sexo, canal, preferencias, etc); 
 - Programación de fecha y horario para envío da notificación;
 - Soporte para mensajes con elementos de media (vídeos, audios, imagenes, GIFs, emojis y archivos); 
 - Envío de mensajes con Menues de opciones para realización de busquedas u obtención de datos en formulario.

## Como usar?

 1. Ingrsar al Menu "**Audiencias**";
 
 ![Ingresar Pushes](https://botmakeradmin.github.io/docs/pt/imagens/Audiencias.png)

 2. En esta sección, podrá ver los últimos mensajes programadas y también podrá crear una nueva;
 
 ![Crear un push](https://botmakeradmin.github.io/docs/pt/imagens/CriarAudiencia.png)
 
> Tenga en cuenta que puede, a través de los botones, observar las métricas de un push, editar un envío, duplicarlo (para generar una nueva basado en la actual), eliminar un push o deshabilitarlo (no será enviado cuando llegue al horario programado).
> ![Opciones](https://botmakeradmin.github.io/docs/pt/imagens/OpcsoesPush.png)

3. Para crear un nuevo Push, cliquee en "**Crear Nuevo**", aparecerá una ventana como esta:

![Ventana Push](https://botmakeradmin.github.io/docs/pt/imagens/EditarAudiencia.png)

4. Editando un Push: 

- Puede dar un nombre al Push editandolo en el campo "Nuevo mensaje".

> Esto servirá solo para identificarlo en la plataforma, no será visible para los que reciban la notificación.

- En "Audiencia" será definido cuales usuarios recibirán el mensaje. Podrá segmentar a su público aagregando condiciones, de las cuales solamente los usuarios que estuvieran etiquetados en ellas recibirán el push.

> Note que a medida en que agrega o remueve condiciones, el número de usuarios que serán alcanzados cambiará.    Si desa enviar un push a todos los usuarios, aunque no es recomendable, deben ser eliminadas todas las condiciones.

- Definido su público, ahora, hará la programación de Fecha y Horario para que su mensaje sea disparado.

- Y, por fin, definirá cual será el mensaje a ser enviado! Este podrá ser: 
	- un texto: al agregar un "**+Texto**", será posible digitar un mensaje de texto.
	
	- una acción: al agregar una "**+Acción**", será posible disparar una intención del Bot, enriquecer un Cuestionario y/o atribuir variábles al usuario;
	-  una media: al agregar una "**+Media**", será posible enviar una imagen, un audio, un vídeo y/o un archivo.

5. Después de la confuguración deseada, cliquee en **Guardar**, y en la fecha y horario indicados, los usuarios de la segmentación recibirán el Push! 

## Vea un ejemplo de un Push configurado:

![Push](https://botmakeradmin.github.io/docs/pt/imagens/Push.png)

En este caso, solamente los usuarios que esten identificados como clientes actuales de la empresa, y que tengan ingresado su dirección de email en chat, recibirán la oferta.




<!--stackedit_data:
eyJoaXN0b3J5IjpbNzE1OTg3NzYzLC0xMDIzNTY1NzE1XX0=
-->
