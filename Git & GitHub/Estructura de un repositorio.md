# Estructura típica de un repositorio y qué debe contener cada carpeta

La estructura que aparece en tu imagen es un estándar muy usado en proyectos profesionales. Aquí la explicamos en detalle para que quede documentado en tu vault.

```code
/carpeta-principal
├── README.md
├── .gitignore
├── /src
├── /docs
└── /scripts
```

A continuación, el propósito de cada elemento:

## README.md

El archivo más importante del repositorio.

Debe contener:
- Descripción del proyecto
- Objetivo
- Requisitos
- Instalación
- Uso
- Ejemplos
- Créditos o autoría

## .gitignore

Archivo que indica qué NO debe subir Git.

Ejemplos típicos:

- Archivos temporales
- Configuraciones locales
- Cachés
- Archivos generados automáticamente

Por ejemplo:

```code
.venv
.obsidian/workspace
.obsidian/cache/
.DS_Store
Thumbs.db
```

## /src (source)

Carpeta donde vive el **código fuente** del proyecto.

En tu caso, como es documentación técnica, podrías usarla para:

- Scripts de PowerShell
- Scripts de Bash
- Archivos `.ps1`, `.sh`, `.py`, etc.
- Ejemplos de automatización

## /docs

Carpeta para documentación formal.

Esta carpeta puede contener:
- Guías técnicas
- Procedimientos
- Manuales
- Documentación de Git
- Documentación de WSL
- Documentación de Docker
- Documentación de PowerShell

## /scripts

Carpeta para scripts auxiliares.

Ejemplos:

- Scripts de instalación
- Scripts de configuración
- Scripts de automatización
- Scripts para WSL
- Scripts para Git (hooks personalizados)
*****
## Puedes ver también:
[[Buenas prácticas y manejos avanzado]]