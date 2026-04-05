## Instalar dependencias

```bash
pip install nombre_paquete
```

### Dónde ejecutar `pip install nombre_paquete`

#### No se ejecuta dentro de la carpeta `.venv/`

Jamás entras a `.venv/` manualmente. Esa carpeta es interna, Python la gestiona solo.

#### Se ejecuta en la raíz del proyecto

Ejemplo:

```code
mi_proyecto/
│
├── .venv/
├── src/
├── requirements.txt
└── README.md
```

Estando en `mi_proyecto/`, ejecutas:

```bash
pip install nombre_paquete
```

#### Pero SOLO después de activar el entorno virtual

```bash
source .venv/bin/activate
```

Cuando ves esto en tu prompt:

```bash
(.venv) rhodyn@beathunterzero:~/mi_proyecto$
```

significa que **pip está apuntando al pip dentro de .venv**, no al del sistema.

#### ¿Por qué funciona así?

Porque cuando activas el entorno virtual:
- `python` apunta a `.venv/bin/python`
- `pip` apunta a `.venv/bin/pip`
- Las dependencias se instalan dentro de `.venv/lib/...`

No importa desde qué carpeta ejecutes `pip install`, **mientras el entorno esté activado**, pip instalará dentro de `.venv`.

Pero por convención y orden, siempre lo haces desde la raíz del proyecto.

#### Flujo correcto (siempre)

```bash
cd mi_proyecto
source .venv/bin/activate
pip install requests
pip freeze > requirements.txt
```

## Exportar dependencias

```bash
pip freeze > requirements.txt
```

## Instalar dependencias desde requirements

```bash
pip install -r requirements.txt
```

## Actualizar dependencias

```bash
pip install --upgrade nombre_paquete
pip freeze > requirements.txt
```

## Versionado semántico

Ejemplo: `requests==2.31.0`
- **Mayor**: cambios incompatibles
- **Menor**: nuevas funciones
- **Patch**: correcciones

## Regenerar un entorno desde cero

```bash
rm -rf .venv
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Buenas prácticas

- Nunca instalar paquetes globalmente.
- Siempre actualizar requirements después de instalar algo nuevo.
- Mantener dependencias mínimas.
- Evitar versiones flotantes (`requests>=2.0`).

*****
## También puedes ver:
[[Buenas prácticas en Python]]