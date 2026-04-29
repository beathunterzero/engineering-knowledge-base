## 1. Gestión de imágenes

Las imágenes son plantillas utilizadas para crear contenedores.

Listado de imágenes

```bash
docker images
```

Descarga de imagen

```bash
docker pull <imagen>
```

Eliminación de imagen

```bash
docker rmi <imagen>
```

---

## 2. Gestión de contenedores

---

### 2.1 Estado de contenedores

```bash
docker ps
docker ps -a
```

---

### 2.2 Ejecución

```bash
docker run <opciones> <imagen>
```

Opciones comunes

- -d → ejecución en segundo plano
    
- -p → mapeo de puertos
    

---

### 2.3 Control de estado

```bash
docker stop <id>
docker start <id>
```

---

### 2.4 Eliminación

```bash
docker rm <id>
docker container prune
```

---

## 3. Interacción con contenedores

---

### 3.1 Acceso interactivo

```bash
docker exec -it <id> bash
```

Nota

- Usar sh en contenedores minimalistas
    

---

### 3.2 Logs

```bash
docker logs <id>
docker logs -f <id>
```

---

### 3.3 Transferencia de archivos

```bash
docker cp <archivo_local> <id>:<ruta_destino>
docker cp <id>:<ruta_archivo> <destino_local>
```

---

## 4. Inspección del sistema

---

### 4.1 Información detallada

```bash
docker inspect <id>
```

---

### 4.2 Estado del entorno

```bash
docker info
```

---

### 4.3 Versión

```bash
docker version
```

---

### Referencias externas

[https://docs.docker.com/engine/reference/commandline/cli/](https://docs.docker.com/engine/reference/commandline/cli/)  
[https://docs.docker.com/get-started/docker_cheatsheet.pdf](https://docs.docker.com/get-started/docker_cheatsheet.pdf)  
[https://www.digitalocean.com/community/tutorials/how-to-use-docker-exec-to-run-commands-in-a-docker-container](https://www.digitalocean.com/community/tutorials/how-to-use-docker-exec-to-run-commands-in-a-docker-container)

---

### Documentación relacionada

[[01 - Conceptos fundamentales de Docker]]