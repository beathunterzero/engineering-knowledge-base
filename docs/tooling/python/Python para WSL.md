## Instalación base del sistema

```bash
sudo apt update
sudo apt install python3 python3-pip
sudo apt install python3.12-venv python3.12-full
```

### Notas:
- `python3.12-full` instala librerías estándar extendidas.
- Siempre usa la versión exacta que definiste para tu entorno (3.12).

## Creación del entorno virtual (método recomendado)

```bash
python3.12 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
```

### Reglas:
- El entorno debe llamarse **.venv** siempre.
- Debe estar en la raíz del proyecto.
- Nunca debe subirse al repositorio.

## Creación alternativa (si falla pip o venv)

```bash
rm -rf .venv
python3.12 -m venv .venv --without-pip
source .venv/bin/activate
python3 -m ensurepip --upgrade
python -m pip install --upgrade pip
```

## Verificación

```bash
python --version
pip --version
```

Debe mostrar Python 3.12.x.

## Salir del entorno virtual

```bash
deactivate
```

## Reglas obligatorias para todos los proyectos Python

- Siempre usar `python3.12 -m venv .venv`.
- Nunca usar `python3 -m venv .venv` sin versión explícita.
- Trabajar siempre dentro del entorno virtual.
- Actualizar pip al crear un nuevo entorno.
- Nunca mezclar dependencias del sistema con las del proyecto.
- Hacer una revisión y actualización anual de los venv, próxima revisión en abril del 2027.

****
## También puedes ver:
[[WSL]]
[[Mantenimiento de distribuciones]]
[[Estructura de proyectos en Python]]
