


# Poetry
- Poetry es una herramienta que facilita la gestión de paquetes y de dependencias y nos ayuda a construir y publicar nuestras propias librerias


- Fué creado en el 2018 por Sébastien Eustace
  
- Los únicos requerimientos que necesita son python 2.7 o python 3.5 y es multiplataforma, podemos usarlo tanto en windows, como en osx y obviamente en linux

- Sus principales características son las siguientes. 
-- Usa Pyproject.toml como fichero de dependencias
-- Usa un fichero lock para bloquear las versiones de las dependencias
-- Permite gestionar entornos virtuales 
-- Nos permite exportación de las librerias y versiones en ficheros como el requirements.txt
-- Nos facilita un autocompletado en la shell
-- Nos da un control de la versión de python con pyenv
-- Y la mas importante, nos permite construir y publicar paquetes de una manera realmente sencilla

- Para instalar poetry podemos usar el propio pip o descargarnos el instalador desde github
- Si necesitamos actualizar poetry no tenemos que volverlo a descargar, simplemente con este comando podemos actualizarlo
- Si vamos a comenzar un proyecto, podemos hacer uso del siguiente comando. Este comando nos generará la siguiente estructura de directorios.
- En caso de que ya tengamos un proyecto iniciado y queramos incorporar poetry al proyecto, simplemente nos situamos en el proyecto y ejecutamos la siguiente instrucción
- Si observamos el fichero toml que nos ha creado previamente, vemos que en el bloque [tool.poetry.dependencies] únicamente tenemos python38 como depenencia 
- Si queremos añadir una dependencia al proyecto, podemos simplemente añadirla al fichero toml y posteriormente instalarla con el comando poetry install, o ejecutar el comando poetry add [dependencia]
- Podemos crear dependencias sólo en los entornos de desarrollo, imaginaos que queremos usar un linter o ejecutar tipado estático o por ejemplo unos tests , para eso ejecutamos el mismo comando que en la transparencia anterior sólo que con el parámetro -D
- En caso de que ejecutemos el comando de poetry init, poetry buscará si existe un entorno virtual en el directorio en el que está, en caso de no existir lo añadirá el con al versión de python que tenga por defecto.
  - Para ejecutar comandos, tenemos dos opciones, el comando run y el shell interactivo
- Por otro lado, otra cosa bastante interesante de poetry son los ficheros lock. poetry lock es un fichero que nos bloquea las versiones mediante el nombre del fichero y su hash correspondiente. Esto nos asegura la versión de la libreria que estamos usando.
  - En caso de que quisieramos actualizar las dependencias del lockfile, podriamos usar el compando poetry update, que nos actualizaría las librerias del fichero lock
  - Es muy muy recomendable subir el fichero lock al repsitorio, así nos aseguramos de que quien vaya a contribuir a nuestro proyecto o libreria usa las mismas versiones que nosotros para ello.
- Si ejecutamos el comando poetry install sin un fichero lock, poetry buscará las últimas versiones de las dependencias que tenemos, en caso de existir, respetará aquellas que se encuentran dentro del fichero.
- Una vez que tenemos nuestra libreria lista, procedemos a la construcción de la misma, al usar la estructura de ficheros pyproject.toml, toda la información ya se encuentra ahí por lo que ejecutando el comando poetry build, nos creará una carpeta "dist" donde incluira todos los builds tanto sdist como wheel.
- El siguiente paso es publicarlo al index con el poetry publish