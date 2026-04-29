## 1. Imagen

Una imagen es una plantilla inmutable utilizada para crear contenedores.

Características

- Solo lectura
    
- Compuesta por capas
    
- No ejecuta procesos
    

Ejemplos

- ubuntu
    
- nginx
    
- python:3.12
    

---

## 2. Contenedor

Un contenedor es una instancia en ejecución de una imagen.

Características

- Ejecutable
    
- Aislado
    
- Temporal
    

Permite iniciar, detener y eliminar procesos de forma independiente.

---

## 3. Diferencia entre imagen y contenedor

Imagen

- Plantilla
    
- Inmutable
    
- No ejecuta procesos
    

Contenedor

- Instancia
    
- Mutable durante ejecución
    
- Ejecuta procesos
    

---

## 4. Ejecución con docker run

Flujo:

1. Verifica si la imagen existe localmente
    
2. Descarga si es necesario
    
3. Crea un contenedor
    
4. Ejecuta el proceso definido
    
5. Cambia a estado detenido al finalizar
    

Cada ejecución crea un contenedor nuevo.

---

## 5. Arquitectura de Docker

Docker Engine gestiona la ejecución de contenedores.

Componentes principales

containerd

- Gestión del ciclo de vida
    

runc

- Ejecución de contenedores
    

Networking

- Comunicación entre contenedores
    

Storage

- Persistencia de datos
    

---

## 6. Docker en WSL

Docker Desktop utiliza distribuciones internas de WSL.

docker-desktop

- Ejecuta el motor Docker
    

docker-desktop-data

- Almacena imágenes y datos
    

Nota

- No modificar manualmente estos entornos
    

---

### Referencias externas

[https://docs.docker.com/get-started/overview/](https://docs.docker.com/get-started/overview/)  
[https://www.docker.com/blog/containerd-vs-runtime/](https://www.docker.com/blog/containerd-vs-runtime/)  
[https://docs.docker.com/desktop/wsl/](https://docs.docker.com/desktop/wsl/)

---

### Documentación relacionada

[[02 - Instalación y configuración con WSL de Docker]]  
[[03 - Comandos esenciales en Docker]]  
[[05 - Buenas prácticas en Docker]]  
[[06 - Docker Compose]]