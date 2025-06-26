# 🐧 Guía rápida: Instalación de Docker en Debian 12

> **Nota:** Todos los comandos deben ejecutarse en una terminal.  
> Reemplaza `[user]` por tu nombre de usuario.

---

## 1. Agregar tu usuario al grupo `sudo`

1. Inicia sesión como root:
   ```sh
   su
   ```
2. Agrega tu usuario al grupo `sudo`:
   ```sh
   usermod -aG sudo [user]
   ```
3. Aplica los cambios de grupo:
   ```sh
   newgrp sudo
   ```
4. Sal del usuario root:
   ```sh
   exit
   ```
5. Refresca la sesión para cargar los nuevos permisos:
   ```sh
   exec su - [user]
   ```
   > Esto reemplaza la sesión actual con una nueva, cargando los permisos de grupo.

---

## 2. Instalación de Docker y herramientas relacionadas

- **Docker:**
  ```sh
  sudo apt install docker
  ```

- **Docker Compose:**
  ```sh
  sudo apt install docker-compose
  ```

- **Containerd:**
  ```sh
  sudo apt install containerd
  ```

---

## 3. Agregar tu usuario al grupo `docker`

1. Agrega tu usuario al grupo `docker`:
   ```sh
   sudo usermod -aG docker [user]
   ```
2. Aplica los cambios de grupo:
   ```sh
   newgrp docker
   ```

---

## 4. Verificación

- Comprueba que perteneces al grupo `docker`:
  ```sh
  groups
  ```
- O verifica directamente en el archivo de grupos:
  ```sh
  cat /etc/group | grep docker
  ```

---

> **¡Listo!** Ya puedes usar Docker sin necesidad de `sudo` en cada comando.

