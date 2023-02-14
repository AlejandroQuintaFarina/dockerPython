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

