## 1. Rol de pip y entornos virtuales

pip es el gestor de paquetes de Python utilizado para instalar librerías externas.

Para evitar conflictos entre proyectos, se utilizan entornos virtuales (.venv), que aíslan dependencias y versiones de cada proyecto.

---

## 2. Flujo operativo

El entorno virtual no debe manipularse directamente. La interacción se realiza mediante su activación desde la raíz del proyecto.

---

### 2.1 Activación del entorno

```bash
cd ~/mi_proyecto
source .venv/bin/activate
```

Indicador de activación

- El prompt muestra el prefijo (.venv)
    

Una vez activo:

- python y pip apuntan al entorno local
    
- Las instalaciones no afectan al sistema global
    

---

## 3. Gestión de dependencias (requirements.txt)

Archivo que define las dependencias del proyecto.

---

Exportar dependencias actuales

```bash
pip freeze > requirements.txt
```

---

Instalar dependencias

```bash
pip install -r requirements.txt
```

---

Actualizar dependencias

```bash
pip install --upgrade nombre_paquete
pip freeze > requirements.txt
```

---

## 4. Versionado

Formato: MAJOR.MINOR.PATCH

MAJOR

- Cambios incompatibles
    

MINOR

- Nuevas funcionalidades compatibles
    

PATCH

- Correcciones de errores
    

Recomendación

- Usar versiones fijas (ej. paquete==2.31.0)
    
- Evitar versiones abiertas (ej. paquete>=2.0)
    

---

## 5. Recuperación del entorno

Si el entorno presenta errores, se recomienda reconstruirlo.

```bash
rm -rf .venv
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

---

## 6. Buenas prácticas

Aislamiento

- No usar instalaciones globales
    

Uso de privilegios

- Evitar sudo pip install
    

Control de dependencias

- Mantener solo librerías necesarias
    

Documentación

- Especificar versión de Python en README.md
    

---

### Referencias externas

[https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)  
[https://semver.org/](https://semver.org/)

---

### Documentación relacionada

[[01 - Python para WSL]]  
[[04 - Automatización y scripting en Python]]