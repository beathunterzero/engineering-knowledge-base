# ¿Qué es WSL?

WSL (_Windows Subsystem for Linux_) es una capa de compatibilidad que permite ejecutar distribuciones Linux dentro de Windows **sin máquinas virtuales** y **sin dual boot**.

En términos simples:
- Es Linux corriendo dentro de Windows
- Con acceso directo al hardware
- Con integración total con el sistema de archivos
- Ideal para desarrollo (Python, Git, Docker, Node, etc.)

WSL te permite tener lo mejor de ambos mundos:
- La comodidad de Windows
- La potencia y flexibilidad de Linux

## ¿Qué versión de WSL usar?

### WSL 2 (recomendado)

- Kernel Linux real
- Mejor rendimiento
- Mejor compatibilidad
- Soporte para Docker

### Cómo verificar tu versión:

```powershell
wsl --version
```

## Instalar WSL en Windows

### Instalación rápida (Windows 10/11):

```powershell
wsl --install
```

Esto instala:
- WSL 2
- Ubuntu (por defecto)
- Kernel Linux
- Configuración inicial

### Ver distribuciones disponibles:

```powershell
wsl --list --online
```

## Instalar una distribución Linux

Ejemplo: instalar Ubuntu 22.04

```powershell
wsl --install -d Ubuntu-22.04
```

Otras distribuciones comunes:
- Debian
- Kali Linux
- openSUSE
- Fedora Remix

### Ver distribuciones instaladas:

```powershell
wsl --list --verbose
```

# ## 🟦 5. Primeros pasos dentro de WSL

Cuando abras Ubuntu por primera vez:

- Te pedirá crear un usuario Linux
    
- Ese usuario será tu cuenta principal
    
- Tendrás acceso a `/home/tu_usuario`
    

### Actualizar paquetes:

bash

```
sudo apt update && sudo apt upgrade -y
```

### Instalar herramientas básicas:

bash

```
sudo apt install build-essential git curl wget -y
```

## Integración con Windows

WSL permite acceder a Windows desde Linux y viceversa.
### Desde WSL → Windows:

```bash
cd /mnt/c
cd /mnt/d
```

### Desde Windows → WSL:

En el explorador:

```code
\\wsl$
```

## Mantenimiento de distribuciones

### Ver estado de WSL:

```powershell
wsl --status
```

### Actualizar WSL:

```powershell
wsl --update
```

### Reiniciar WSL:

```powershell
wsl --shutdown
```

### Exportar una distribución (backup):

```powershell
wsl --export Ubuntu ubuntu_backup.tar
```

### Importar una distribución:

```powershell
wsl --import Ubuntu2 D:\WSL\Ubuntu2 ubuntu_backup.tar
```

### Eliminar una distribución:

```powershell
wsl --unregister Ubuntu
```

*****
## Puedes ver también
[[Mantenimiento de distribuciones]]
[[Powershell]]
[[Git]]
[[Estructura de un repositorio]]
[[Token Personal (PAT)]]
[[Autenticación SSH con GitHub]]