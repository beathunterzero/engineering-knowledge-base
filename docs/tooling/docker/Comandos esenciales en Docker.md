## Imágenes

```bash
docker images
docker pull <imagen>
docker rmi <imagen>
```

## Contenedores

```bash
docker ps
docker ps -a
docker run <imagen>
docker stop <id>
docker start <id>
docker rm <id>
docker container prune
```

## Acceder a un contenedor

```bash
docker exec -it <id> bash
```

## Logs

```bash
docker logs <id>
docker logs -f <id>   # seguir logs en tiempo real
```

## Información del sistema

```bash
docker info
docker version
```

## Inspeccionar contenedores

```bash
docker inspect <id>
```

## Copiar archivos

```bash
docker cp archivo.txt <id>:/ruta/
docker cp <id>:/ruta/archivo.txt .
```

**************
## También puedes ver:
[[Buenas prácticas en Docker]]