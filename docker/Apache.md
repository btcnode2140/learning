# 🚀 Deploy de un Mini Servidor Apache con Docker

> **Guía paso a paso para levantar un servidor Apache simple usando Docker.**  
> Ideal para pruebas, desarrollo o aprender los conceptos básicos de Docker.

---

## 1. Crear el directorio de trabajo

```sh
mkdir apache
cd apache
```
> Crea y entra al directorio donde estará tu proyecto.

---

## 2. Crear el archivo `Dockerfile`

```sh
nano Dockerfile
```
> El nombre **debe empezar con D mayúscula**.  
> El `Dockerfile` define cómo se construye la imagen de Docker.

---

## 3. Crear el archivo `index.html`

```sh
nano index.html
```
> Este será el archivo que servirá Apache. Puedes ponerle cualquier contenido de prueba.

---

## 4. Ejemplo básico de `Dockerfile`

```Dockerfile
FROM httpd:2.4
COPY index.html /usr/local/apache2/htdocs/
```
> - Usa la imagen oficial de Apache.
> - Copia tu `index.html` al directorio donde Apache sirve los archivos.

---

## 5. Construir la imagen de Docker

```sh
docker build -t apache .
```
- `apache` es el nombre de la imagen que vas a crear.
- El punto (`.`) indica que el contexto de construcción es el directorio actual (donde está el `Dockerfile`).

---

## 6. Ejecutar el contenedor

```sh
docker run -d -p 80:80 --name apache apache
```
- `-d`: Ejecuta el contenedor en segundo plano (detached).
- `-p 80:80`: Mapea el puerto 80 del host al puerto 80 del contenedor.
- `--name apache`: Nombra el contenedor como "apache".
- El último `apache` es el nombre de la imagen que creaste.

---

## 7. Acceder al servidor

Abre tu navegador y visita:  
[http://localhost](http://localhost)  
> Deberías ver el contenido de tu `index.html`.

---

## 8. Modificar archivos dentro del contenedor (opcional)

Si quieres editar el `index.html` directamente dentro del contenedor:

```sh
docker exec -it apache /bin/bash
```
- Esto te da acceso a una terminal bash dentro del contenedor.
- Puedes editar archivos, instalar utilidades, etc.

---

> **Tip:**  
> Si modificas `index.html` en tu máquina, debes reconstruir la imagen y reiniciar el contenedor para ver los cambios reflejados.

---

**¡Listo!**  
Ahora tienes un mini servidor Apache corriendo en Docker, ideal para experimentar y aprender.