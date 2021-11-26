
# Software Requirements Specification

## Introduction
### 1.1 Purpose
Este documento describe los requerimientos de software para la página de sugerencias de proyectos dentro del ITAM.

### 1.2 Document conventions
Cada requerimiento tiene su propia prioridad asignada.

### 1.3 Intended Audience and Reading Suggestions
Este documento esta hecho para los desarrolladores que van a llevar a cabo la implementación del sistema de sugerencias y posteriormente los encargados de mantener la página. 

### 1.4 Product Scope
Esta página busca crear un ambiente de discusión abierto a todos los miembros de la comunidad ITAM para dar sugerencias de proyectos que puedan beneficiar a la universidad y sus integrantes. Creemos que este sistema se alinea con la misión del ITAM en donde aspira a convertirse en una comunidad en su más pleno significado.

# 2. Overall Description

### 2.1 Product Perspective

Este sistema se usará como una expansión al sistema existente en línea del ITAM, para agregar funcionalidad y accesibilidad a todos los usuarios. Además, le permitirá a los miembros de la comunidad el sugerir proyectos desde la perspectiva de quienes los usaran.

### 2.2 Product Functions

Este programa debe cumplir con las funciones que se esperarían de una red social, ya que debe permitir hacer publicaciones y dar "likes" para saber si es una propuesta que la comunidad apruebe colectivamente.

### 2.3 User Classes and Characteristics

Este producto será utilizado por alumnos, profesores y administradores.
Todos los usuarios pueden tener una cuenta, hacer publicaciones y dejar likes.
En un futuro se espera tener comentarios y una forma de compartir propuestas que le gustan a los usuarios para que tengan más alcance.

# 3 External Interface Requirements

## 3.1 User Interfaces
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
  ![new post](https://i.imgur.com/3YJ265I.png
  
## 3.2 Hardware Interfaces
  La aplicación es una página web responsiva, se puede ingresar desde celular u ordenador. Se hostea en una raspberry pi 4 con OS debian 10
  
# 4 System Features

## 4.1 Likes
  Función del sitio para expresar la opinión de la comunidad al respecto de propuestas individuales.

## 4.2 Logins y registros con contraseña encriptada
  Esto permite al sitio tener seguridad gracias a una pared de encriptación necesaria para evitar ataques, hackeos y mantener segura la información sensible dentro de la plataforma.

## 4.3 Perfiles customizables
  Capacidad de tener una foto de perfil para que los demás puedan identificarte, en un futuro se agregarán más opciones de personalización como agregar una bio.
