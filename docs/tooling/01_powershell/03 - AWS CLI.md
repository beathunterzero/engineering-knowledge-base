## 1. Definición y propósito

La AWS CLI es una herramienta de línea de comandos que permite interactuar con servicios de Amazon Web Services desde el shell.

Para perfiles orientados a Cloud Security e Incident Response, es una herramienta clave para:

- Auditorías rápidas de infraestructura
    
- Extracción de evidencias desde logs y servicios
    
- Automatización de tareas sin depender de la consola web
    

---

## 2. Instalación y verificación (Windows)

En entornos Windows, el método recomendado es el uso de winget.

```powershell
# Instalación
winget install Amazon.AWSCLI

# Verificación
aws --version
```

---

## 3. Configuración de identidad

Antes de ejecutar comandos, es necesario asociar la CLI a una identidad de IAM (Identity and Access Management).

---

### 3.1 Inicialización de credenciales

```bash
aws configure
```

Se solicitarán los siguientes parámetros:

- AWS Access Key ID
    
- AWS Secret Access Key
    
- Default region (ej. us-east-1)
    
- Default output format (json o table)
    

---

### 3.2 Almacenamiento local de credenciales

Las credenciales se almacenan en archivos locales en texto plano.

Ubicación:  
~/.aws/credentials

Lectura desde PowerShell:

```powershell
Get-Content ~/.aws/credentials
```

Es importante restringir el acceso a este archivo.

---

## 4. Comandos esenciales de gestión

Operaciones comunes para auditoría y administración:

S3  
aws s3 ls

- Lista buckets disponibles
    

EC2  
aws ec2 describe-instances

- Inventario de instancias y estado
    

IAM  
aws iam list-users

- Lista identidades activas
    

S3 (transferencia)  
aws s3 cp s3:///

- Transferencia de archivos (respaldo o movimiento de evidencias)
    

---

### 4.1 Control de salida (--output)

Permite definir el formato de salida según el caso de uso:

json

- Ideal para automatización y parsing
    

table

- Recomendado para lectura humana
    

text

- Útil para procesamiento en scripts
    

---

## 5. Automatización con alias en PowerShell

Ejemplo de alias para optimizar flujo de trabajo:

```powershell
Set-Alias awsec2 "aws ec2 describe-instances --output table"
Set-Alias awss3 "aws s3 ls"
Set-Alias awsiam "aws iam list-users --output table"
```

---

## 6. Buenas prácticas de seguridad

Principio de menor privilegio

- Evitar el uso de permisos amplios como AdministratorAccess
    

Gestión de secretos

- No almacenar Access Keys en repositorios o archivos expuestos
    

Autenticación fuerte

- Habilitar MFA para accesos CLI
    

Rotación de credenciales

- Cambiar claves periódicamente para reducir riesgo
    

---

### Referencias externas

[https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)  
[https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html)

---

### Documentación relacionada

[[01 - Powershell]]  
[[04 - Azure CLI]]