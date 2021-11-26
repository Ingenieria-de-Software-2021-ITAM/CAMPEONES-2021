
# Software Requirements Specification

## Introducción
### 1.1 Propósito
Este documento describe los requerimientos de software para la página de sugerencias de proyectos dentro del ITAM.

### 1.2 Convenciones de documentos
Cada requerimiento tiene su propia prioridad asignada.

### 1.3 Audiencia a la que se dirige y sugerencias de lectura
Este documento esta hecho para los desarrolladores que van a llevar a cabo la implementación del sistema de sugerencias y posteriormente los encargados de mantener la página. 

### 1.4 Alcance del producto
Esta página busca crear un ambiente de discusión abierto a todos los miembros de la comunidad ITAM para dar sugerencias de proyectos que puedan beneficiar a la universidad y sus integrantes. Creemos que este sistema se alinea con la misión del ITAM en donde aspira a convertirse en una comunidad en su más pleno significado.

# 2. Descripción general

### 2.1 Perspectiva del producto

Este sistema se usará como una expansión al sistema existente en línea del ITAM, para agregar funcionalidad y accesibilidad a todos los usuarios. Además, le permitirá a los miembros de la comunidad el sugerir proyectos desde la perspectiva de quienes los usaran.

### 2.2 Funciones del producto

Este programa debe cumplir con las funciones que se esperarían de una red social, ya que debe permitir hacer publicaciones y dar "likes" para saber si es una propuesta que la comunidad apruebe colectivamente.

### 2.3 Clases de usuarios y características

Este producto será utilizado por alumnos, profesores y administradores.
Todos los usuarios pueden tener una cuenta, hacer publicaciones y dejar likes.
En un futuro se espera tener comentarios y una forma de compartir propuestas que le gustan a los usuarios para que tengan más alcance.

# 3 Requerimientos para interfaces externas

## 3.1 Interfaces de usuario
Todas las interfaces heredan la misma plantilla principal layout.hml . Existen 4 interfaces

### home
Se deslpiegan los posts de los usuarios (todos) y se ordenan crónologicamente (de más nuevo a más viejo). Los votos solo son visibles a usuarios que hayan iniciado sesión
![interfaz principal](https://i.imgur.com/H1r7wfJ.png)
Cuando se inicia sesión
![interfaz principal con sesión](https://i.imgur.com/G8Er9Oc.png)

### register
página de registros
![register](https://i.imgur.com/v4RqeAQ.png)

### post
página para visualizar un post en especifico
![post](https://i.imgur.com/5zdooUB.png)

### new post
  interfaz para crear un nuevo post con un proyecto
  ![new post](https://i.imgur.com/3YJ265I.png)
  
## 3.2 Interfaces de hardware
  La aplicación es una página web responsiva, se puede ingresar desde celular u ordenador. Se hostea en una raspberry pi 4.
## 3.3 Software Interface
  La aplicación se hostea en un raspberry pi 4 con debian 10 usando python 3.9. Los web requests se procesan usando NGINX, este manda la lógica de python a gunicorn y procesa los archivos estaticos como los .html y los .css . La aplicación se desarrolla usando Flask y diferentes submodulos como flask-sqlalchemy para la conexión y manejo de una base de datos <i>sqlite</i>. 
  
## 3.4 Interfaces de comunicación
  Las conexiones se hacen a través de TCP/HTTP (puerto 80). Se planea encriptar la comunicación vía TLS a futuro (HTTPS) usando un certificado de <i>let's encrypt</i> .
  
# 4 Características del sistema

## 4.1 Likes / votos
  Función del sitio para expresar la opinión de la comunidad al respecto de propuestas individuales.
  
  ### 4.1.1 Description and priority
  
  El usuario puede votar por proyectos que le gusten (parecido a dar un "like" en una red social). Prioridad <b>alta</b> . 
  
  ![UML use case likes](https://i.imgur.com/KS0sUBd.png)
  
  ### 4.1.2 Stimulus/Response Sequences
    
  Stimulus: el usuario encuentra una publicación de un proyecto que le gusta -> (action) presiona un boton de "votar" ->(response) la página registra su voto incrementando un número y cambiando la publicación desde su perspectiva de forma visual, indicando que se votó por ese proyecto.
  
  ### 4.1.3 Functional requirements
  <b>REQ-1</b>: el usuario puede votar por un proyecto publicado en la página. <br>
  <b>REQ-2</b>: el usuario puede quitar su voto por un proyecto publicado en la página por el que haya votado previamente. <br>
  <b>REQ-3</b>: debe haber una diferencia visual entre los poryectos votados y no votados desde la perspectiva del usuario.  <br>
  

## 4.2 Logins y registros con contraseña encriptada
  Esto permite al sitio tener seguridad gracias a una pared de encriptación necesaria para evitar ataques, hackeos y mantener segura la información sensible dentro de la plataforma.
    ### 4.2.1 Description and priority
  
  El usuario puede registrarse con un correo y nombre de usuario. Puede después acceder a la página con sus credenciales (correo y contraseña). Prioridad <b>alta</b> . 
  
  ![UML use case likes](https://i.imgur.com/wqYEQnU.png)
  
  ### 4.2.2 Stimulus/Response Sequences
    
  Stimulus: El usuario le interesa la página y quiere hacer una publicación o votar por un proyecto -> (action) el usuario presiona el voton de registro o inicio de sesión. ->(response) la página le responde con un formulario para recibir los datos. -> (action) el usuario llena y sube el formulario con sus datos.-> (response) la página le muestra una retroalimentacion acerca de si sus datos son correctos o si estos son incorrectos, le dicen cuales son.
  
  ### 4.2.3 Functional requirements
  <b>REQ-1</b>: el usuario puede votar por un proyecto publicado en la página. <br>
  <b>REQ-2</b>: el usuario puede quitar su voto por un proyecto publicado en la página por el que haya votado previamente. <br>
  <b>REQ-3</b>: debe haber una diferencia visual entre los poryectos votados y no votados desde la perspectiva del usuario.  <br>

## 4.3 Perfiles customizables
  Capacidad de tener una foto de perfil para que los demás puedan identificarte, en un futuro se agregarán más opciones de personalización como agregar una bio.

# 5 Requerimientos no funcionales
### 5.1 Requerimientos de rendimiento
Para asegurar una buena experiencia a los usuarios incluso si se tiene un flujo alto de usuarios es importante tener un servidor	que nos permita escalar el proyecto sin ser muy costoso. También es importante manejar los requests de forma eficiente para no tener a los usuarios en espera de forma innecesaria.
### 5.2 Requerimientos de seguridad
El proyecto se apega a los siguientes principios:

 - Confidencialidad: proteger la información de los usuarios es una de las prioridades del equipo, por lo que toda la información personal que no se desea compartir con el público queda detrás de una pared de encriptación garantizando la privacidad.
 - Autenticación: para proteger las cuentas de los usuarios se utiliza un sistema de contraseñas encriptadas, las cuales se pueden cambiar en caso de que se sospeche una brecha en la seguridad o un hackeo de la cuenta.

### 5.3 Atributos de software de calidad
Buscamos proveer un producto de calidad asegurando los siguientes principios:

 - Adaptabilidad: el proyectó deberá ser utilizado tanto en dispositivos móviles como en PC's, además de en Windows, Mac y Linux en distintos navegadores.
 - Mantenibilidad: el código será limpio, legible y fácil de entender, con el fin de simplificar la tarea de mantener el proyecto en un futuro para permitir que evolucione a medida que se necesiten distintas funciones o actualizaciones.
### 5.4 Reglas
Este proyecto opera bajo el estricto principio de la protección de datos, el cuál se logrará a través de las medidas de seguridad que se mencionan previamente. Además, en un futuro se implementara el rol de moderación para usuarios, el cual permitirá filtrar posts que se puedan considerar como ofensivos o inapropiados para la página.
