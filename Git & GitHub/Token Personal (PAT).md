# ¿Qué es un Token Personal (PAT)?

Un **Personal Access Token (PAT)** es una clave generada por GitHub que reemplaza a la contraseña tradicional para operaciones como:

- `git push`
- `git pull`
- `git clone` (si el repo es privado)

GitHub eliminó el uso de contraseñas por seguridad, así que **el token es obligatorio** para autenticarse desde terminales como WSL.

## Cómo generar un Token Personal (PAT) en GitHub

Sigue estos pasos:
### Ir a la configuración de GitHub

Entra a:

```code
GitHub → Settings → Developer Settings → Personal Access Tokens
```

### Elegir el tipo de token

GitHub ofrece dos tipos:

- **Fine-grained token** (más seguro, recomendado)
- **Classic token** (más simple, compatible con todo)

Para WSL, ambos funcionan.

### Crear un nuevo token

Selecciona:

- **Generate new token**

### Asignar permisos mínimos necesarios

Para trabajar con repositorios:

```code
repo
```

Si usas Fine-grained:

- Selecciona el repositorio específico
- Permisos:
    - Read + Write en “Contents”
    - Read + Write en “Metadata”

### Elegir duración

GitHub permite:

- 30 días
- 60 días
- 90 días
- Personalizado

### Generar y copiar el token

GitHub lo mostrará **solo una vez**. Cópialo y guárdalo temporalmente para usarlo en WSL.

## Usar el Token para autenticarse desde WSL

Cuando ejecutes un `git push` por primera vez:

```bash
git push origin main
```

Git pedirá:

```bash
Username: tu_usuario_github
Password: <tu_token_generado>
```

El token funciona como contraseña.

## Guardar el Token para no escribirlo cada vez

Git puede almacenar el token en un archivo local dentro de WSL.

### Configurar el credential helper

```bash
git config --global credential.helper store
```

### Hacer un push para que Git pida el token

```bash
git push
```

### Git guardará el token en:

```code
~/.git-credentials
```

Contenido típico del archivo:

Código

```
https://tu_usuario:tu_token@github.com
```

### ✔️ Advertencia

Este archivo **no está cifrado**. No lo compartas ni lo subas a Git.

## Renovar un token expirado

Cuando el token expire:
1. Repite el proceso de creación
2. Ejecuta:

```bash
git credential reject
```

3. Luego:

```bash
git push
```

Git pedirá el nuevo token y lo guardará.
******
## También puedes ver:
[[Autenticación SSH con GitHub]]