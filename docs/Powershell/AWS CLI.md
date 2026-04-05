## Instalación de AWS CLI

En Windows:

```powershell
winget install Amazon.AWSCLI
```

Verificar instalación:

```powershell
aws --version
```

## Configuración inicial

Configurar credenciales:

```powershell
aws configure
```

Solicita:
- Access Key
- Secret Key
- Región
- Formato de salida

Ver credenciales configuradas:

```powershell
Get-Content ~/.aws/credentials
```

## Comandos básicos útiles

### Listar buckets S3

```powershell
aws s3 ls
```

### Listar instancias EC2

```powershell
aws ec2 describe-instances --output table
```

### Listar usuarios IAM

```powershell
aws iam list-users --output table
```

### Subir archivo a S3

```powershell
aws s3 cp archivo.txt s3://mi-bucket/
```

## Formatos de salida

```powershell
--output table
--output json
--output text
```

Ejemplo:

```powershell
aws ec2 describe-instances --output json
```

## Alias útiles en PowerShell

```powershell
Set-Alias awsec2 "aws ec2 describe-instances --output table"
Set-Alias awss3 "aws s3 ls"
Set-Alias awsiam "aws iam list-users --output table"
```

## Buenas prácticas

- Nunca guardar claves en repositorios
- Usar roles en vez de claves cuando sea posible
- Rotar claves periódicamente
- Usar MFA para cuentas sensibles
- Evitar permisos `AdministratorAccess`

*****
## También puedes ver:
[[Azure CLI]]