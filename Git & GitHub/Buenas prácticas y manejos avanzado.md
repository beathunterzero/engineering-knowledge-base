## `.gitignore` avanzado

### Archivos que SIEMPRE deben ignorarse

```code
# Python
__pycache__/
*.pyc

# Entornos virtuales
.venv/
env/

# Archivos de entorno
*.env

# Logs
*.log

# Archivos del sistema
.DS_Store
Thumbs.db
```

### `.gitignore` global (usuario)

Configurar un `.gitignore` para todo tu sistema:

```bash
git config --global core.excludesfile ~/.gitignore_global
```

Ejemplo de `.gitignore_global`:

```code
.DS_Store
Thumbs.db
*.log
```

## Reglas de oro de Git

- Nunca subir `.venv`
- Nunca subir contraseñas, claves o tokens
- Siempre revisar `git status` antes de commitear
- Siempre hacer `git pull` antes de `git push`
- Mantener commits pequeños y descriptivos
- No subir archivos personales
- Crear `.gitignore` ANTES del primer commit

## Ignorar archivos nuevos (sin borrarlos)

Ignorar un archivo localmente:

```bash
git update-index --skip-worktree archivo.txt
```

Volver a rastrearlo:

```bash
git update-index --no-skip-worktree archivo.txt
```

## Dejar de rastrear un archivo ya subido

```bash
git rm --cached archivo.txt
```

Luego agregarlo a `.gitignore`.

## Git avanzado (operaciones útiles)

### Ver historial detallado

```bash
git log --oneline --graph --decorate
```

### Revertir un commit

```bash
git revert <hash>
```

### Reset suave (mantiene cambios)

```bash
git reset --soft HEAD~1
```

### Reset duro (borra cambios)

```bash
git reset --hard HEAD~1
```

### Stash (guardar cambios sin commitear)

```bash
git stash
git stash pop
```

*****
## También puedes ver:
