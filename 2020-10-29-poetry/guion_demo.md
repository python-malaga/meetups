
docker run -t -i --rm -h pypi.local -v /srv/pypi:/srv/pypi:rw -p 8080:80 --name pypi codekoala/pypi 

## poetry 
- Projecto nuevo en poetry poetry new python_malaga
- Explicación de fichero TOML, donde está 
- Ejemplo de búsqueda de fichero python requests poetry search requests
- Poetry add requests
- Enseñar lock file
- Cambiar versión de la libreria por un igual y actualizar con poetry update
- Iniciamos el código
```
import requests

def give_me_a_joke():
        try:
            return requests.get("https://api.chucknorris.io/jokes/random").json().get("value")
        except Exception as ex:
            return "no jokes for now"
```
- construimos  con poetry build



docker run -t -i --rm -h pypi.local -v $(pwd)/srv/pypi:/srv/pypi:rw -p 8080:80 --name pypi codekoala/pypi



### Configuración de repositorio
poetry config repositories.python_malaga https://localhost:8080

### Publicar repositorio
poetry publish -u python_malaga 