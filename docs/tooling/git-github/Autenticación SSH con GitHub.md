# ¿Qué es la autenticación SSH?

SSH es un método de autenticación basado en **claves criptográficas**, no contraseñas. Permite conectarte a GitHub sin:

- Escribir usuario
- Escribir token
- Renovar credenciales
- Guardar contraseñas en texto plano

Es el método **más seguro y recomendado** para trabajar con GitHub desde WSL.

## Verificar si ya tienes claves SSH

Antes de generar una nueva clave, revisa si ya existe una:

```bash
ls ~/.ssh
```

Si ves archivos como:

- `id_ed25519`
- `id_ed25519.pub`
- `id_rsa`
- `id_rsa.pub`

entonces ya tienes claves.
Si no existe la carpeta o está vacía, continúa con el siguiente paso. Si aparece:

```code
ls: cannot access '/home/rhodyn/.ssh': No such file or directory
```

Significa que **no tienes claves SSH**, lo cual es perfecto para comenzar desde cero.

## Generar una nueva clave SSH (ed25519)

GitHub recomienda usar **ed25519** (más segura y moderna que RSA).

Ejecuta:

```bash
ssh-keygen -t ed25519 -C "rhodyn.ildefonso.1311@outlook.com"
```

Explicación de parámetros:

- `-t ed25519` → tipo de clave
- `-C` → comentario (tu correo para identificarla)

Cuando pregunte:

```code
Enter file in which to save the key (/home/rhodyn/.ssh/id_ed25519):
```

Presiona **Enter** para usar la ruta por defecto:

Cuando pregunte por passphrase:

```code
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
```

Puedes:
- **Presionar ENTER dos veces** (sin passphrase) → recomendado para WSL
- O escribir una passphrase si quieres más seguridad

Resultado esperado:
- Se crea la carpeta `~/.ssh`
- Se generan:
    - `id_ed25519` (clave privada)
    - `id_ed25519.pub` (clave pública)

Cuando pregunte por passphrase:
- Puedes dejarlo vacío (Enter)
- O poner una contraseña para mayor seguridad

### ¿Qué debes poner cuando te pide la passphrase?

En este paso:

```code
Enter passphrase (empty for no passphrase):
```

Tienes **dos opciones válidas**, y ambas son correctas dependiendo de tu preferencia.

#### Opción 1 — Presionar ENTER (sin passphrase)

**Recomendado para WSL y GitHub si quieres simplicidad.**

Ventajas:
- No te pedirá contraseña cada vez que uses Git
- Es más cómodo para desarrollo diario
- Funciona perfecto con GitHub
- No afecta la seguridad si tu PC está protegida

Desventajas:
- Si alguien accede a tu PC, podría usar tu clave SSH (muy improbable si tu máquina está segura)

**Si quieres comodidad total, presiona ENTER otra vez.**

#### Opción 2 — Escribir una passphrase

**Recomendado si quieres máxima seguridad.**

Ventajas:
- La clave privada queda protegida con contraseña
- Aunque alguien copie tu clave, no podrá usarla

Desventajas:
- Tendrás que escribir la passphrase cada vez que uses Git
- O tendrás que cargarla en el agente SSH manualmente

**Si eliges seguridad extra, escribe una contraseña y presiona ENTER.**

## Agregar la clave privada al agente SSH

El agente SSH mantiene tus claves cargadas en memoria.

Iniciar el agente:

```bash
eval "$(ssh-agent -s)"
```

Agregar tu clave:

```bash
ssh-add ~/.ssh/id_ed25519
```

Debe mostrar:

```code
Identity added: /home/usuario/.ssh/id_ed25519
```

## Obtener la clave pública

La clave pública es la que se sube a GitHub.

Mostrarla:

```bash
cat ~/.ssh/id_ed25519.pub
```

Copia TODO el contenido, incluyendo:

```code
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI...
```

## Registrar la clave en GitHub

1. Ir a GitHub
2. Settings
3. SSH and GPG Keys
4. New SSH Key
5. Título:

```code
  Ubuntu WSL - beathunterzero
```

6. Pegar la clave pública
   - **Key type:** Authentication Key
   - **Key:** pega la clave pública
   - **Add SSH key**
6. Guardar

## Probar la conexión SSH

Ejecuta:

```bash
ssh -T git@github.com
```

Primera vez verás:

```code
The authenticity of host 'github.com' can't be established.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Escribe:

```code
yes
```

Si todo está bien, verás algo como:

```code
Hi Rhodyn! You've successfully authenticated, but GitHub does not provide shell access.
```

Esto confirma que:
- Tu clave SSH funciona
- GitHub te reconoce
- Ya no necesitas tokens
- Puedes hacer `git push` sin contraseñas

## Configurar Git para usar SSH por defecto

Si tu repositorio está usando HTTPS, cámbialo a SSH:
### Ver URL actual:

```bash
git remote -v
```

Si ves algo como:

```code
https://github.com/usuario/repositorio.git
```

#### Asegúrate de estar dentro del proyecto

Antes de ejecutar cualquier comando Git, debes estar dentro de la carpeta del proyecto.

Ejemplo:

```bash
cd ~/projects_ubuntu/carnada
```

#### Si NO estás dentro del proyecto, Git mostrará este error:

```code
fatal: not a git repository (or any of the parent directories): .git
```

Esto significa:
- Estás en una carpeta que NO es un repositorio Git
- No existe un `.git` en ese directorio
- Debes navegar a la carpeta correcta

**Solución:** entrar a la carpeta del proyecto y volver a intentar.

### Verifica la URL remota actual

Dentro del proyecto:

```bash
git remote -v
```

Si ves algo como:

```code
origin  https://github.com/beathunterzero/carnada.git (fetch)
origin  https://github.com/beathunterzero/caranda.git (push)
```

Entonces **sí necesitas migrar a SSH**.

Cámbialo a SSH:

```bash
git remote set-url origin git@github.com:beathunterzero/carnada.git
```

(Usa el nombre real de tu repositorio. Carnada.git es un proyecto personal que estoy usando para este ejemplo)

### Confirmar que la migración fue exitosa

```bash
git remote -v
```

Ahora deberías ver:

```code
origin  git@github.com:beathunterzero/carnada.git (fetch)
origin  git@github.com:beathunterzero/carnada.git (push)
```

Esto confirma que:
- El repositorio ya usa SSH
- Ya no pedirá tokens
- `git push` funcionará usando tu clave SSH

## Clonar repositorios usando SSH

A partir de ahora, usa:

```bash
git clone git@github.com:beathunterzero/carnada.git
```

No pedirá usuario ni token.

## Ventajas de usar SSH sobre tokens

|SSH|Token (PAT)|
|---|---|
|No expira|Expira cada 30–90 días|
|No pide contraseña|Pide token al menos una vez|
|Más seguro|Menos seguro|
|Ideal para WSL|Ideal para scripts|
|No requiere almacenamiento en texto plano|Se guarda en `~/.git-credentials`|

## Buenas prácticas

- Usa una clave SSH por dispositivo
- Nombra tus claves claramente en GitHub
- No compartas tu clave privada
- Haz backup de tu carpeta `~/.ssh` si cambias de PC
- Si pierdes una clave, revócala desde GitHub inmediatamente
******
## También puedes ver:
