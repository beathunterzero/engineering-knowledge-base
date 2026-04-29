## 1. Definición y propósito

Docker Compose permite definir y gestionar aplicaciones que utilizan múltiples contenedores.

Se basa en un archivo declarativo que describe servicios, redes y volúmenes.

Archivo utilizado

- docker-compose.yml
    

---

## 2. Estructura del archivo

version

- Define la versión del formato
    

services

- Contiene la definición de los contenedores
    

image / build

- Imagen a usar o proceso de construcción
    

ports

- Mapeo de puertos
    

volumes

- Persistencia de datos
    

depends_on

- Orden de inicio de servicios
    

restart

- Política de reinicio
    

---

## 3. Gestión del ciclo de vida

---

### 3.1 Despliegue

```bash
docker compose up
docker compose up -d
docker compose up --build
```

---

### 3.2 Estado

```bash
docker compose ps
```

---

### 3.3 Reinicio

```bash
docker compose restart
docker compose restart <servicio>
```

---

## 4. Detención y limpieza

```bash
docker compose stop
docker compose down
docker compose down -v
docker compose down --rmi all
```

---

## 5. Diagnóstico

Logs

```bash
docker compose logs -f
docker compose logs -f <servicio>
```

Ejecución de comandos

```bash
docker compose exec <servicio> bash
```

---

## 6. Networking y persistencia

Red

- Compose crea una red interna automáticamente
    
- Los servicios se comunican por nombre
    

Volúmenes

- Permiten persistencia de datos
    
- Se definen en el archivo principal
    

---

## 7. Políticas de reinicio

no

- Sin reinicio automático
    

always

- Reinicio continuo
    

on-failure

- Reinicio ante error
    

unless-stopped

- Reinicio excepto detención manual
    

---

### Referencias externas

[https://docs.docker.com/compose/compose-file/](https://docs.docker.com/compose/compose-file/)  
[https://docs.docker.com/compose/reference/](https://docs.docker.com/compose/reference/)  
[https://yaml.org/](https://yaml.org/)

---

### Documentación relacionada

[[01 - Conceptos fundamentales de Docker]]  
[[05 - Buenas prácticas en Docker]]