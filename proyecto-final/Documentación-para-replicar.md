## prerrequisitos
<ul>
  <li>Python 3.9 o superior</li>
  <li>bash con git</li>
  
</ul>

## instrucciones 

### descarga el repositorio en tu equipo
para esto se puede descargar el .zip de repositorio o usar  `git clone` con el cliente ssh del repositorio: `git@github.com:Ingenieria-de-Software-2021-ITAM/CAMPEONES-2021.git`

### crea un  virtual enviorment en python y configuralo
situate en la carpeta `/web` y crea un nuevo venv (virtual enviormente) de python. Las instrucciones pueden cambiar dependiendo del sistema operativo y versión de pip.
Se pueden ver más instrucciones aqui https://docs.python.org/3/library/venv.html

Una vez creado, activate usando `source (nombre que se le dio al venv)/bin/activate` en linux o `source (nombre que se le dio al venv)/Scripts/Activate` en Windows usando bash.

Actualiza la versión de PIP <br>
`pip install --upgrade pip`

instala los paquetes necesarios para el proyecto usando el `requirements.txt` provisto en la carpeta /web . Para hacer esto, una vez con el venv activado y pip actualizado, 
puedes ejectuar el siguiente comando:
<br>
`pip install -r requirements.txt`


### inicia la página
depués corre el archivo run. Situate en la carpeta /web y, una vez activado el venv con los paquetes instalados en requirements.txt, usa el siguiente comando:
<br>
`python run.py`
