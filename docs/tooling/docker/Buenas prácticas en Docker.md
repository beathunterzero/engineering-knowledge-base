## No usar Docker Desktop UI

- Consume más RAM
- Consume más CPU
- No aporta nada para tu flujo técnico

## Usar WSL2 como backend

- Más rápido
- Más ligero
- Mejor integración con Linux

## Mantener solo imágenes necesarias

```bash
docker image prune
```

## Limpiar contenedores detenidos regularmente

```bash
docker container prune
```

## Nombrar contenedores siempre

```bash
docker run -it --name debianlab debian bash
```

## Usar `-it` para laboratorios interactivos

```bash
docker run -it kali-rolling bash
```

## Evitar contenedores huérfanos

Siempre detenerlos:

```bash
docker stop <id>
```

## Buenas prácticas para CTI/CTH

### Para análisis de malware:

- Usar contenedores aislados
- No montar volúmenes del host
- No exponer puertos innecesarios

### Para reproducir TTPs:

- Usar imágenes ligeras (alpine, debian)
- Crear contenedores efímeros
- Documentar comandos

### Para OSINT:

- Usar contenedores con herramientas específicas
- Evitar instalar herramientas en el host

************
## También puedes ver:
