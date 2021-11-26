## 1) Test Plan Identifier

testplat-v0.1

## 2) References

System-requirements.md
arquitectura.md
metodologia.md
propuestaEconomica.xlsx

## 3) Introduction

El presente documento es un plan de calidad para el desarrollo de una aplicacion para proponer proyectos dentro del ITAM.
El objetivo de este plan de calidad es determinar que funcionalidades están listas y cuales incluir a futuro segun la metodologia propuesta al igual como el presupuesto estimado en la propuesta economica.

## 4) Test Items

  <ul>
    <li>Publicación de proyectos</li>
    <li>Personalización de perfiles</li>
    <li>Encriptacion de contraseñas</li>
    <li>Sistema de voto / likes por publicación</li>
  </ul>
  
## 5) Software Risk Issues

<ul>
    <li>contraseñas olvidadas</li>
    <li>regulación de contenido posteado</li>
    <li>procesos asincronos</li>
    
  </ul>

## 6) Features to be Tested

<ul>

<li>  <u>Registro de Cuenta:</u>  <strong>Low.</strong>  El botón se encuentra a la vista del usuario para registrarse. Al dar click al botón, se redirige a una página que pide los datos para el registro de cuenta. Cada uno de los campos es intuitivo y manda un mensaje de registro correcto. </li>
<li>  <u>Login de Cuenta:</u>  <strong>Low.</strong>  El botón se encuentra a la vista del usuario para loggearse. Al dar click, se redirige a la página para ingresar el correo y la contraseña. Si las credenciales son correctas, vuelves a entrar a la página principal con el usuario correcto. </li>
<li>  <u>Publicación de Proyectos:</u>  <strong>Medium.</strong>  El botón para encontrar el proyecto es sencillo a la vista. Al entrar a la sección de publicar el proyecto, puede ser confuzo para el usuario cómo subir la imagen pues no muestra una vista previa </li>

</ul>

## 7) Features not to be Tested

<ul>

<li>  <u>Eliminación de un Post Publicado:</u> Esto será desconocido para el usuario pues no es sencillo encontrar para el usuario. Para realizar esto, deben entrar a sus posts, luego dar click en el título del post, y saldrá la opción de borrarlo. </li>


</ul>

## 8) Approach
Al iniciar el proyecto, se consideró utilizar una librería para poder manejar de manera eficiente y sencilla el manejo de credenciales y creación de posts por cada cuenta. 
El sistema será probado a través de un ciclo completo, es decir, creación de una cuenta, ingreso de la cuenta creada, creación de un proyecto en la página principal, y mediante otros usuarios dar "like" a los proyectos que más les guste.
Por parte del administrador del proyecto, este revisará que se haya creado bien las credenciales y que los proyectos subidos esté bien identificado con el usuario que haya subido este mismo.

## 9) Item Pass/Fail Criteria
Para la implementación de características dentro del proyecto se realizarán pruebas extensivas antes de ser aprobadas para su implementación en el producto abierto al público. Para estas pruebas se utilizaran distintos dispositivos que nos permitan hacer pruebas en muchos ambientes diferentes. Si no se observan diferencias o problemas significativos en alguno de esos ambientes se aprobará la función y se integrará lo antes posible.

## 10) Suspension Criteria and Resumption Requirements
- Los servidores del ITAM están caídos. En esta situación el equipo de desarrollo debe esperar a que el personal del ITAM resuelva el problema para poder verificar la integridad del proyecto y así asegurar una experiencia de calidad. 
- Un error en el código se sube al ambiente de ejecución. En esta situación el equipo de desarrollo revertirá la versión pública a la última estable y se pondrá a buscar arduamente la fuente del error para solucionarlo lo más rápido posible.

## 11) Test Deliverables
<ul>

<li> Ciclos Completos para realizar pruebas </li>
<li> Lista de Incidencias y Errores en la aplicación </li>
<li> Reportes de la funcionalidad de los usuarios de prueba </li>

</ul>

## 12) Remaining Test Tasks
| Tarea | Asignada a | Status | 
|------ | ---------- | ------ |
| Crear la Base de Datos | TM, Dev | Completo |
| Crear los planes de código | TM, PM| Completo |
| Verificar funcionalidad | Dev, Cliente, TM | Pendiente |
| Verificar fidelidad del producto a visión del cliente | Dev, Cliente, TM | Pendiente |

## 13) Environmental Needs
- Tener una Base de Datos de Prueba para probar la inserción de información.
- Logs en cada operación CRUD.
- Manejo de versiones.

## 14) Staffing and Training Needs
Aparte del equipo de desarrollo que incluye a los software developers, al project manager, al dev ops y a los diseñadores, será necesario contratar al personal pertinente que nos permita hacer pruebas regulares sobre el sistema para permitirnos saber si existe algún problema con el sistema cada que se lance una versión o funcionalidad nueva. Además de verificar la compatibilidad de dichas versiones y funcionalidades con los dispositivos que soporta la herramienta.

## 15) Responsibilities
Durante la duración del proyecto cada miembro del equipo será asignado como responsable de una función en la que no esté directamente involucrado con el fin de ayudar a quienes estén trabajando en esa función a tener ojos externos que les permita darse cuenta de errores de forma simple. También, el project manager se encargará de hacer estas pruebas para ayudar aún más a los distintos equipos.

## 16) Schedule

## 17) Planning Risks and Contingencies

## 18) Approvals
