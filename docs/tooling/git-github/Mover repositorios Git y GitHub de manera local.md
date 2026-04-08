## Mover la carpeta físicamente

Git no depende de rutas absolutas, así que puedes mover la carpeta completa del repositorio a cualquier ubicación.
### **Pasos**

1. Cierra cualquier editor o terminal que esté usando la carpeta.
2. Mueve la carpeta completa (incluyendo `.git`) al nuevo directorio.
3. Abre una terminal en la nueva ubicación.

## Verificar que Git reconoce el repositorio

En la nueva ruta, ejecuta:

```code
git status
```

Debes ver algo como:

```code
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

Si aparece, Git reconoce correctamente el repositorio.

## Confirmar que el remoto sigue apuntando a GitHub

Ejecuta:

```code
git remote -v
```

Debes ver las URLs de tu repositorio en GitHub tanto para `fetch` como para `push`.

Ejemplo:

```code
origin  https://github.com/usuario/repositorio.git (fetch)
origin  https://github.com/usuario/repositorio.git (push)
```

Si esto aparece, la conexión remota está intacta.

## Probar sincronización con GitHub

### Pull

```code
git pull
```

Si dice _Already up to date_, todo está bien.

### Push (opcional pero recomendado)

Crea un archivo temporal para probar:

```code
echo "test" > test.txt
git add .
git commit -m "Prueba después de mover el repositorio"
git push
```

Si sube sin errores, el repositorio está 100% funcional.

Luego puedes eliminar el archivo:

```code
rm test.txt
git add .
git commit -m "Eliminando archivo de prueba"
git push
```

*********
## También puedes ver:
