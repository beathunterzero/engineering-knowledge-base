## Imagen

- Es una **plantilla inmutable**.
- Contiene el sistema base + dependencias + configuración.
- No cambia nunca.

Ejemplos:
- `ubuntu`
- `debian`
- `python:3.12`
- `nginx`

## Contenedor

- Es una **instancia en ejecución** de una imagen.
- Puede tener cambios temporales.
- Puede detenerse, reiniciarse o eliminarse.

## Diferencia clave

|Imagen|Contenedor|
|---|---|
|Plantilla|Instancia|
|No cambia|Cambia|
|No ejecuta procesos|Ejecuta procesos|
|Se almacena|Se ejecuta|

## Por qué `docker run` crea contenedores nuevos

Cada vez que haces:

```bash
docker run hello-world
```

Docker:
1. Toma la imagen
2. Crea un contenedor nuevo
3. Ejecuta el proceso
4. El contenedor termina
5. Queda detenido

Por eso se acumulan contenedores.

## Contenedores persistentes vs no persistentes

### No persistente (hello-world)

- Se ejecuta una vez
- Imprime un mensaje
- Se apaga
- No se puede reiniciar

### Persistente (ejemplo: Debian)

```bash
docker run -it --name debianlab debian bash
```

Puedes:

```bash
docker stop debianlab
docker start -ai debianlab
```

## Qué es el Docker Engine

Es el motor que ejecuta contenedores.

Incluye:
- containerd
- runc
- networking
- almacenamiento

## Qué son `docker-desktop` y `docker-desktop-data` en WSL

- **docker-desktop** → entorno donde corre el engine
- **docker-desktop-data** → almacenamiento de imágenes y contenedores

Nunca debes modificarlos manualmente.

*****************
## También puedes ver:
[[Flujo de trabajo diario en Docker]]