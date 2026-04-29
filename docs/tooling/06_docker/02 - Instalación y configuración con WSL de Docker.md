## 1. Objetivo del entorno

Configurar Docker para ser utilizado desde Ubuntu en WSL2, evitando el uso constante de la interfaz gráfica de Docker Desktop y reduciendo el consumo de recursos en Windows.

---

## 2. Instalación de Docker Desktop

Durante la instalación, es importante seleccionar opciones que prioricen rendimiento y simplicidad.

---

### 2.1 Parámetros recomendados

Use WSL 2 instead of Hyper-V

- Habilitado
    
- Requerido para usar kernel Linux real
    

Enable WSL Integration

- Habilitado
    
- Permite usar Docker desde Ubuntu
    

Add docker.internal names to hosts

- Habilitado
    
- Mejora conectividad entre host y contenedores
    

Use containerd for pulling images

- Habilitado
    
- Mejora eficiencia en manejo de imágenes
    

Start Docker Desktop when you sign in

- Deshabilitado
    
- Evita consumo automático de recursos
    

Open Docker Dashboard when starts

- Deshabilitado
    
- Evita carga de interfaz gráfica
    

Enable Scout / SBOM

- Deshabilitado
    
- Reduce procesos adicionales
    

---

## 3. Integración con WSL

Pasos:

1. Abrir Docker Desktop
    
2. Ir a Settings → Resources → WSL Integration
    
3. Activar integración con Ubuntu
    
4. Habilitar integración con distribución por defecto
    
5. Cerrar Docker Desktop
    

---

## 4. Verificación en WSL

```bash
docker --version
docker info
docker run --rm hello-world
```

Resultados esperados

- Cliente y servidor disponibles
    
- Ejecución correcta del contenedor de prueba
    

---

## 5. Resolución de problemas

---

### 5.1 Reinicio del entorno

```powershell
dockerstop
wsl --shutdown
dockerstart --background
```

---

### 5.2 Error de conexión al daemon

```bash
sudo usermod -aG docker $USER
```

Acción adicional

- Reiniciar sesión de WSL
    

---

### 5.3 Error de permisos en socket

```bash
sudo chmod 666 /var/run/docker.sock
```

---

## 6. Consideraciones

Uso recomendado

- Ejecutar Docker desde WSL
    

Optimización

- Evitar mantener Docker Desktop abierto
    

Seguridad

- Gestionar correctamente permisos de usuario
    

---

### Referencias externas

[https://docs.docker.com/desktop/wsl/](https://docs.docker.com/desktop/wsl/)  
[https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers)  
[https://ubuntu.com/tutorials/install-and-configure-docker-inside-wsl-2](https://ubuntu.com/tutorials/install-and-configure-docker-inside-wsl-2)

---

### Documentación relacionada

[[01 - Conceptos fundamentales de Docker]]  
[[01 - Git]]  
[[01 - Powershell]]  
[[01 - WSL]]