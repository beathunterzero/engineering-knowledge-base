## Estructura recomendada

```code
mi_proyecto/
│
├── .venv/               # Entorno virtual (ignorado)
├── src/                 # Código fuente
│   └── main.py
├── docs/                # Documentación
├── requirements.txt
├── .gitignore
└── README.md
```

## Carpetas estándar

### `src/`

- Contiene todo el código fuente.
- Evita colocar scripts sueltos en la raíz.

### `docs/`

- Documentación técnica o notas del proyecto.

### `.venv/`

- Entorno virtual local.
- Siempre ignorado.

## Dónde colocar archivos clave

### `requirements.txt`

En la raíz del proyecto.

### `.gitignore`

También en la raíz.

### Módulos Python

Dentro de `src/`, nunca en la raíz.

## Buenas prácticas de organización

- Un proyecto = un entorno virtual.
- No mezclar código de pruebas con código de producción.
- Mantener `main.py` como punto de entrada.
- Usar nombres descriptivos para módulos.
- Documentar dependencias y comandos en `README.md`.
- Cuando se trata de scripts directos, evitar usar `src/` para limpieza en ejecución del script.
*****
## También puedes ver:
[[Gestión de dependencias en Python]]