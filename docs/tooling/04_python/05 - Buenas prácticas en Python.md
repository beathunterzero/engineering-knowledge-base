## 1. Estándares de estilo (PEP 8)

El código en Python debe ser legible y consistente. Seguir PEP 8 facilita la auditoría, el mantenimiento y la colaboración.

Indentación

- Usar 4 espacios
    
- Evitar tabuladores
    

Nombres

- snake_case para funciones y variables
    
- PascalCase para clases
    

Longitud de línea

- Máximo recomendado: 79 caracteres
    

Modularidad

- Funciones pequeñas
    
- Una sola responsabilidad por función
    

---

## 2. Punto de entrada

Permite evitar ejecución accidental cuando el script se importa como módulo.

```python
def main():
    pass

if __name__ == "__main__":
    main()
```

Ventaja

- Reutilización de código sin ejecución automática
    

---

## 3. Uso de logging

En lugar de print, se recomienda usar logging para control de eventos.

```python
import logging

logging.basicConfig(level=logging.INFO, format='%(levelname)s: %(message)s')

logging.info("Proceso iniciado")
logging.error("Error en procesamiento")
```

Ventajas

- Clasificación por niveles
    
- Posibilidad de redirigir a archivos
    
- Mejor trazabilidad en ejecución
    

---

## 4. Manejo de excepciones

Permite evitar interrupciones inesperadas en ejecución.

```python
try:
    with open("evidencia.log", "r") as file:
        data = file.read()
except FileNotFoundError:
    logging.error("Archivo no encontrado")
except Exception as e:
    logging.error(f"Error inesperado: {e}")
```

---

## 5. Documentación (docstrings)

Cada función debe describir su propósito, parámetros y retorno.

```python
def extraer_ips(texto):
    """
    Extrae direcciones IPv4 de un texto.

    Args:
        texto (str): Texto de entrada

    Returns:
        list: Direcciones IP encontradas
    """
    pass
```

---

## 6. Organización de módulos

Estructura recomendada:

```plaintext
src/
│
├── main.py
├── utils.py
└── core/
    └── parser.py
```

main.py

- Punto de entrada
    

utils.py

- Funciones reutilizables
    

core/

- Lógica principal del sistema
    

---

### Referencias externas

[https://peps.python.org/pep-0008/](https://peps.python.org/pep-0008/)

---

### Documentación relacionada

[[01 - Python para WSL]]