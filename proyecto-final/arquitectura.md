# arquitectura y justificación

La arquitectura usada en el proyecto fue una arquitectura en capas. 
Ya que la consideramos la más rápida en términos de desarrollo y la idea del proyecto era crear una aplicación sencilla con un sólo proposito.
Ademas la arquitecura en capas va muy de la mano del framework o libreria <i>Flask</i> por su división en diferentes modulos para manejar cosas como
el enrutamiento, stylesheets, db models, web forms, etc. Esto ayuda a separar la lógica de la aplicación en las capas adecuadas para acelerar el desarrollo de la
aplicación ya que reduce la complejidad de implementación. 

## estructura 
![carpeta principal](https://i.imgur.com/GiyAzQZ.png)

Carpeta flaskblog:

![dentro de la carpeta flaskblog que tiene la lógica](https://i.imgur.com/0xvIYBE.png)

### presentation layer
Esta capa esta compuesta por todos los archivos dentro de las carpetas de static y template. Esto es lo que ve el usuario y la información se le pasa desde la bussness layer.
Estos archivos son meramente .css y .html con jinja2

### business layer
Esta capa está conformada por los archivos forms.py y routes.py. Estas capas se ocupan de la lógica de la página, a dónde llevar al cliente cuando use cierto url, qué información, cómo manejarla y qué responder.
Esencialmente es la conexion logica entre el input del usuario y el resultado de la página. Todos los objetos cliente y post los obtiene de los modelos obtenidos por la persistence layer.
Después con un <i>commit</i> la persistence layer se encarga re realizar los cambios.
Además de estos tiene la lógica para inicial la aplicacion de flask en run.py e \_\_init\_\_.py 

### persistence layer
Esta capa está conformada mayormente por models.py ya que le dice a las otras capas cómo comunicarse con la base de datos. Aqui se tienen los objetos post y cliente (además de los "likes" o votos, mas estos son una conexion n-n y no una tabla en sí).

### database layer
en el caso de flask, flask  y sql-alchemy se ocupan de todos los cambios pertinentes a la base de datos
