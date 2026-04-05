## Instalación de Azure CLI

En Windows:

```powershell
winget install Microsoft.AzureCLI
```

Verificar instalación:

```powershell
az --version
```

## Autenticación

Iniciar sesión:

```powershell
az login
```

Cerrar sesión:

```powershell
az logout
```

Listar suscripciones:

```powershell
az account list --output table
```

Seleccionar suscripción:

```powershell
az account set --subscription "<ID>"
```

## Comandos básicos útiles

### Listar máquinas virtuales

```powershell
az vm list --output table
```

### Listar recursos

```powershell
az resource list --output table
```

### Listar grupos de recursos

```powershell
az group list --output table
```

### Crear un grupo de recursos

```powershell
az group create --name MiGrupo --location eastus
```

## Formatos de salida

Azure CLI permite cambiar el formato:

```powershell
--output table
--output json
--output yaml
```

Ejemplo:

```powershell
az vm list --output json
```

## Alias útiles en PowerShell

```powershell
Set-Alias azlogin "az login"
Set-Alias azvm "az vm list --output table"
Set-Alias azres "az resource list --output table"
```

## Buenas prácticas

- Siempre usar `--output table` para lectura rápida
- Usar `az account set` para evitar errores de suscripción
- No almacenar credenciales en scripts
- Usar `az logout` al terminar en entornos compartidos

********************
## Puedes ver también:
[[AWS CLI]]