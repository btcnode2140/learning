# Deploy de un mini servidor apache con docker

### Creamos un directorio

```mkdir apache```

### Creamos un archivo Dockerfile

```nano Dockerfile```

con d mayuscula

### Creamos el Dockerfile (sirve para crear la imagen de docker)

### Creamos index.html

### Copiamos el index.html

### Buildeamos la imagen de docker

```docker build -t apache .```

en este comando 'apache' es el nombre que va a tener el contenedor al usar . al final significa que va a usar el archivo Dockerfile que esta en ese mismo directorio

### Corremos la imagen creada

docker run -d -p 80:80 --name apache apache

### Entramos al docker en ejecucion para modificar el html

```docker exec -it apache /bin/bash```

/bin/bash al final es para tener una shell disponible