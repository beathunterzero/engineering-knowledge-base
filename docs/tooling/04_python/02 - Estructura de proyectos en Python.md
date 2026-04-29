## 1. Arquitectura de proyecto estandarizada

Una estructura consistente en proyectos Python facilita la organización, mejora la mantenibilidad y permite la integración con herramientas de automatización y CI/CD.

El siguiente esquema representa una estructura base para proyectos de automatización y seguridad.

---

### 1.1 Esquema de directorios

```text
mi_proyecto/
│
├── .venv/
├── src/
│   ├── __init__.py
│   └── main.py
├── docs/
├── tests/
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 2. Componentes principales

---

### 2.1 Directorio src

Contiene la lógica principal del proyecto.

Ventajas:

- Evita mezclar código con archivos de configuración
    
- Facilita la importación de módulos
    

Nota

- En scripts simples puede omitirse, pero es obligatorio en proyectos escalables
    

---

### 2.2 Entorno virtual (.venv)

Contiene el entorno aislado del proyecto.

Reglas:

- Debe ubicarse en la raíz
    
- No debe incluirse en el control de versiones
    

---

### 2.3 Archivos de configuración

requirements.txt

- Lista de dependencias del proyecto
    

```bash
pip install -r requirements.txt
```

.gitignore

- Debe incluir:
    
    - .venv/
        
    - **pycache**/
        
    - *.env
        

---

## 3. Jerarquía de módulos

Para que Python reconozca los módulos, se utiliza el archivo **init**.py.

Ejemplo de importación:

```python
from src.utils import limpiador_de_logs
```

---

## 4. Buenas prácticas

Aislamiento

- Un entorno virtual por proyecto
    

Punto de entrada

- main.py como orquestador principal
    

Separación

- tests/ separado de src/
    

Documentación

- README.md debe incluir instrucciones claras de uso y configuración
    

---

### Referencias externas

[https://packaging.python.org/en/latest/tutorials/packaging-projects/](https://packaging.python.org/en/latest/tutorials/packaging-projects/)  
[https://docs.python-guide.org/writing/structure/](https://docs.python-guide.org/writing/structure/)

---

### Documentación relacionada

[[01 - Python para WSL]]  
[[03 - Gestión de dependencias en Python]]