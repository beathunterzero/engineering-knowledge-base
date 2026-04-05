## Cada vez que reinicies Windows

### En PowerShell:

```powershell
dockerstart --background
```

### En Ubuntu WSL:

```bash
docker ps
```

Si responde, Docker está activo.

### Alternativa automatizada:

```bash
dockerup
```

Aquí ejecuta el servicio de Docker sin abrir `docker-desktop` y automáticamente levanta Ubuntu WSL en el terminal (revisar en [[Alias permanente para Docker]])

## Ejecutar contenedores

```bash
docker run <imagen>
```

Interactivo:

```bash
docker run -it <imagen> bash
```

Con nombre:

```bash
docker run -it --name mi_lab debian bash
```

## Detener contenedores

```bash
docker stop <id>
```

## Reiniciar contenedores

```bash
docker start <id>
```

Interactivo:

```bash
docker start -ai <id>
```

## Eliminar contenedores

```bash
docker rm <id>
```

Eliminar todos los detenidos:

```bash
docker container prune
```

## Ver logs

```bash
docker logs <id>
```

## Ver imágenes

```bash
docker images
```

## Descargar imágenes

```bash
docker pull ubuntu
```

***
## También puedes ver:
[[Alias permanente para Docker]]
[[Comandos esenciales en Docker]]
