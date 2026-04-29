## 1. Gestión de alias

En PowerShell, un alias es un nombre alternativo que referencia a un cmdlet, función, ejecutable o script. Su propósito es optimizar la velocidad operativa reduciendo comandos extensos a formas abreviadas.

Comando de asignación:  
Set-Alias

Sintaxis:  
Set-Alias <nombre_alias> <comando_original>

---

### 1.1 Limitación de la sesión

Los alias definidos directamente en la consola son temporales. Se eliminan al cerrar la sesión de PowerShell.

Para persistirlos, deben declararse en el perfil de PowerShell.

---

## 2. El perfil de PowerShell ($PROFILE)

El perfil de PowerShell es un script que se ejecuta automáticamente al iniciar cada sesión. Cumple una función equivalente a .bashrc o .zshrc en sistemas Linux/Unix.

---

### 2.1 Utilidad del perfil

Alias permanentes

- Definición de accesos rápidos para herramientas como Git, Docker o navegación
    

Funciones personalizadas

- Automatización de tareas complejas o repetitivas
    

Variables de entorno

- Configuración de rutas y herramientas
    

Personalización del entorno

- Ajustes del prompt y apariencia de la consola
    

---

## 3. Implementación y configuración

### 3.1 Localización y creación

La ruta del perfil está almacenada en la variable automática $PROFILE.

Flujo de gestión:

```powershell
# Verificar si el archivo existe
Test-Path $PROFILE

# Crear el archivo si no existe
New-Item -Path $PROFILE -ItemType File -Force

# Editar el perfil
notepad $PROFILE
```

---

### 3.2 Ejemplo de configuración

Ejemplo de alias definidos en el perfil:

```powershell
# Navegación
Set-Alias -Name ll -Value Get-ChildItem
Set-Alias -Name .. -Value "cd .."

# Herramientas externas
Set-Alias -Name gs -Value "git status"
Set-Alias -Name d -Value docker
```

---

## 4. Políticas de ejecución

Al cargar el perfil por primera vez, PowerShell puede bloquear la ejecución por restricciones de seguridad.

Error común:  
cannot be loaded because running scripts is disabled on this system

Solución (ejecutar en una consola con privilegios adecuados):

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

---

### Referencias externas

[https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_profiles)  
[https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/set-alias](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/set-alias)

---

### Documentación relacionada

[[01 - Powershell]]  
[[04 - Automatización para Docker en PowerShell]]