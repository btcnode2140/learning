# Estas Instrucciones fueron hechas sobre Debian 12

### Agregar mi usuario al grupo sudoers

Nos logeamos como root usando ```su```

```sudo usermod -aG sudo [user]```

Luego para aplicar los cambios usamos

```newgrp sudo```

Una vez finalizado salimos del usuario root usando ```exit```

Para forzar la actualizacion de la sesion actual usamos

exec su - [user]

Esto reemplaza la sesion actual con una nueva cargando los nuevos permisos de grupo.

---

### Para instalar docker en usamos:

```sudo apt install docker```

### Para instalar docker compose

```sudo apt install docker-compose```

### Para instalar docker containerd

```sudo apt install containerd```

---

### Hay que agregar el usuario al grupo docker

```sudo usermode -aG docker [user]```

```newgrp docker```

Ahora si ponemos el comando: ```groups``` deberiamos ver que pertenecemos al grupo docker.

Tambien podemos verificarlo usando ```cat /etc/group | grep docker```