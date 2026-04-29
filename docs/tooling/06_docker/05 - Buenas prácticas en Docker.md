## 1. Optimización del entorno

El uso eficiente de Docker requiere priorizar rendimiento y control operativo.

---

### 1.1 Uso de CLI sobre interfaz gráfica

Limitaciones de la interfaz gráfica

- Mayor consumo de recursos
    
- Menor visibilidad de errores
    
- Menor velocidad operativa
    

Recomendación

- Utilizar Docker desde la terminal
    
- Operar sobre WSL2
    

---

### 1.2 Uso de WSL2

Ventajas

- Kernel Linux real
    
- Mejor rendimiento de I/O
    
- Integración con herramientas Linux
    

---

## 2. Gestión de recursos

---

### 2.1 Limpieza de entorno

Eliminar imágenes no utilizadas

```bash
docker image prune
```

Eliminar contenedores detenidos

```bash
docker container prune
```

---

### 2.2 Estandarización

Nombrado de contenedores

```bash
docker run -d --name lab_analisis debian
```

Modo interactivo

```bash
docker run -it --name kali_audit kali-rolling /bin/bash
```

---

## 3. Uso en ciberseguridad

---

### 3.1 Aislamiento

Contenedores sin red

```bash
docker run --network none --name sandbox_malware <imagen>
```

Evitar montaje de volúmenes sensibles

---

### 3.2 Entornos efímeros

```bash
docker run --rm -it alpine sh
```

Ventajas

- Entornos limpios
    
- Sin residuos
    

---

### 3.3 Uso de imágenes ligeras

Ejemplos

- alpine
    
- debian-slim
    

Beneficios

- Menor consumo
    
- Mayor velocidad de despliegue
    

---

## 4. Aplicación en OSINT y CTH

Modularidad

- Un contenedor por herramienta
    

Aislamiento

- Evita conflictos de dependencias
    

Reproducibilidad

- Entornos replicables entre analistas
    

---

### Referencias externas

[https://docs.docker.com/develop/develop-images/dockerfile_best-practices/](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)  
[https://learn.microsoft.com/en-us/windows/wsl/compare-versions](https://learn.microsoft.com/en-us/windows/wsl/compare-versions)  
[https://www.cisecurity.org/benchmark/docker](https://www.cisecurity.org/benchmark/docker)

---

### Documentación relacionada

[[01 - Conceptos fundamentales de Docker]]  
[[06 - Docker Compose]]