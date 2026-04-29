## 1. Instalación base en Ubuntu/Debian

En entornos Linux bajo WSL, Python puede venir preinstalado, pero no siempre incluye herramientas necesarias como pip o soporte completo para entornos virtuales.

Es necesario estandarizar la versión de Python para evitar inconsistencias entre desarrollo y ejecución.

---

### 1.1 Preparación del sistema

```bash
# Actualizar repositorios
sudo apt update

# Instalar Python y pip
sudo apt install python3 python3-pip -y

# Instalar versión específica con soporte completo
sudo apt install python3.12-venv python3.12-full -y
```

Nota técnica

- El paquete python3.12-full incluye módulos adicionales que pueden no estar presentes en instalaciones mínimas
    

---

## 2. Gestión de entornos virtuales

El uso de entornos virtuales es obligatorio para aislar dependencias por proyecto.

---

### 2.1 Creación y activación

```bash
# Crear entorno
python3.12 -m venv .venv

# Activar entorno
source .venv/bin/activate

# Actualizar pip
python -m pip install --upgrade pip
```

---

### 2.2 Método de recuperación

Si el entorno falla o pip no está disponible:

```bash
rm -rf .venv
python3.12 -m venv .venv --without-pip
source .venv/bin/activate
python3 -m ensurepip --upgrade
python -m pip install --upgrade pip
```

---

## 3. Verificación y cierre

Verificación

- python --version (debe mostrar 3.12.x)
    

Salida del entorno

- deactivate
    

---

## 4. Reglas de uso

Versión

- Utilizar python3.12 de forma explícita
    

Estandarización

- El entorno virtual debe llamarse .venv
    

Aislamiento

- No instalar dependencias fuera de un entorno activo
    

Control de versiones

- Incluir .venv en .gitignore
    

Mantenimiento

- Regenerar entornos periódicamente según ciclo definido
    

---

### Referencias externas

[https://ubuntu.com/tutorials/install-python#1-overview](https://ubuntu.com/tutorials/install-python#1-overview)  
[https://docs.python.org/3/library/venv.html](https://docs.python.org/3/library/venv.html)

---

### Documentación relacionada

[[02 - Estructura de proyectos en Python]]  
[[03 - Gestión de dependencias en Python]]  
[[04 - Automatización y scripting en Python]]  
[[05 - Buenas prácticas en Python]]  
[[01 - Powershell]]  
[[01 - WSL]]