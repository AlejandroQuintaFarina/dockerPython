# Docker + Python

---

# Creamos un contenedor sencillo de python

```docker run -it --rm --name my-running-script -v "$PWD":/usr/src/myapp -w /usr/src/myapp python:3 python your-daemon-or-script.py```

`docker` el comando base 

`run` crear el contenedor

`-it` dos opciones que me valen para interactuar con la terminal del contendor

`--rm` borra el cotenedor cuando finaliza la acción

`-v` define el mapeo del volumen a continuación

- `"$PWD"` el directorio donde estamos
- `/usr/src/myapp` el directorio dentro del contenedor

`-w` el directorio de trabajo (_workdir_)

`python:3` la imagen que se creará en el contenedor

`python script.py` es el comando para ejecutar dentro del contenedor

# Imagen Docker
Imagen personalizada con libreria externa

---

Para crear una imagen usamos el fichero Dockerfile

Para construirla usamos el comando:

`$ docker build -t youtubeimagen:latest .`

Antes tenemos que descargar la imagen base, en nuestro caso la de python:3

`$ docker pull python:3`

Una vez creada la imagen podemos usarla para lanzar el contenedor

`$ docker run --rm -it youtubeimagen`

---

## Dependencias
Usamos la instrucción [`pyreqs`](https://pypi.org/project/pipreqs/) para crear el fichero `requirements.txt`. Este fichero contendrá todas las librerias que use nuestro script.

`$ pipreqs --force`

En el Dockerfile podemos incluir la instalación de las librerias:

`COPY requirements.txt ./`
`RUN pip install --no-cache-dir -r requirements.txt`


