## Reglas de estilo (PEP8)

- 4 espacios por indentación
- Nombres descriptivos
- Líneas de máximo 79 caracteres
- Funciones pequeñas y claras

## Estructura de módulos

Ejemplo:

```code
src/
│
├── main.py
├── utils.py
└── services/
    └── api.py
```

## Uso de `__main__`

```python
if __name__ == "__main__":
    main()
```

Permite ejecutar el script directamente.

## Logging básico

```python
import logging

logging.basicConfig(level=logging.INFO)
logging.info("Inicio del programa")
```

Evita usar `print()` en proyectos reales.

## Manejo de errores

```python
try:
    funcion()
except Exception as e:
    logging.error(f"Error: {e}")
```

## Documentación mínima

- Cada función debe tener docstring.
- Explicar parámetros y retorno.
- Documentar dependencias externas.

***************
## También puedes ver:
[[Automatización y scripting en Python]]