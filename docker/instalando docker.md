### Hay que agregar mi usuario al grupo sudoers

Nos logeamos como root usando ```su```

```sudo usermod -aG sudo [user]```

Una vez finalizado salimos del usuario root usando ```exit``` y reiniciamos.

---

### Para instalar docker en debian 12 usamos:

```sudo apt install docker```

### Para instalar docker compose

```sudo apt install docker-compose```

### Para instalar docker containerd

```sudo apt install containerd```

---

### Hay que agregar el usuario al grupo docker

```sudo usermode -aG docker [user]```