## 1. Definición y propósito

Azure CLI es una herramienta de línea de comandos multiplataforma diseñada para interactuar con servicios de Microsoft Azure y administrar recursos en la nube.

Para perfiles de Incident Response y Cloud Security, permite:

- Auditoría de configuraciones de red
    
- Gestión de identidades y recursos
    
- Automatización de tareas operativas y respuesta ante incidentes
    

---

## 2. Instalación y verificación (Windows)

El método recomendado en Windows es el uso de winget.

```powershell
# Instalación
winget install Microsoft.AzureCLI

# Verificación
az --version
```

---

## 3. Flujo de autenticación y contexto

Azure CLI utiliza autenticación basada en navegador por defecto.

Login:  
az login

Logout:  
az logout

Se recomienda cerrar sesión en entornos compartidos para evitar exposición de tokens.

---

### 3.1 Gestión de suscripciones

En entornos con múltiples suscripciones, es necesario validar el contexto activo antes de ejecutar comandos.

```powershell
# Listar suscripciones
az account list --output table

# Seleccionar suscripción
az account set --subscription "<ID-de-Suscripción>"
```

---

## 4. Comandos de gestión y auditoría

Consultas frecuentes sobre infraestructura:

VM  
az vm list

- Inventario de máquinas virtuales
    

Resources  
az resource list

- Vista global de recursos
    

Groups  
az group list

- Listado de grupos de recursos
    

Creación  
az group create

- Creación de grupos de recursos
    

---

### 4.1 Formatos de salida (--output)

table

- Recomendado para inspección visual
    

json

- Útil para automatización e integración
    

yaml

- Adecuado para configuraciones estructuradas
    

---

## 5. Optimización mediante alias en PowerShell

Ejemplo de alias para agilizar operaciones:

```powershell
Set-Alias azlogin "az login"
Set-Alias azvm "az vm list --output table"
Set-Alias azres "az resource list --output table"
```

---

## 6. Buenas prácticas de seguridad

Validación de contexto

- Verificar suscripción activa con az account show antes de ejecutar cambios
    

Higiene de sesión

- Ejecutar az logout en entornos compartidos
    

Gestión de secretos

- Evitar exponer credenciales en historial o scripts
    

Consistencia en salida

- Usar --output table para reducir errores de interpretación
    

---

### Referencias externas

[https://learn.microsoft.com/en-us/cli/azure/get-started-with-azure-cli](https://learn.microsoft.com/en-us/cli/azure/get-started-with-azure-cli)  
[https://learn.microsoft.com/en-us/cli/azure/reference-index](https://learn.microsoft.com/en-us/cli/azure/reference-index)

---

### Documentación relacionada

[[01 - Powershell]]  
[[03 - AWS CLI]]