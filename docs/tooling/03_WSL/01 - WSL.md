## 1. ¿Qué es WSL?

WSL (Windows Subsystem for Linux) es una capa de compatibilidad que permite ejecutar un entorno Linux directamente sobre Windows.

A diferencia de una máquina virtual tradicional, WSL 2 utiliza una arquitectura basada en una micro-VM ligera con un kernel Linux real, lo que permite un alto rendimiento sin necesidad de gestionar recursos de virtualización complejos.

---

### 1.1 Integración de entornos

WSL permite combinar:

Entorno Windows

- Herramientas de productividad y aplicaciones de escritorio
    

Entorno Linux

- Terminal Bash/Zsh
    
- Herramientas de ciberseguridad
    
- Desarrollo y automatización
    
- Uso de contenedores
    

---

## 2. Selección de versión

Para entornos técnicos, se recomienda utilizar WSL 2.

WSL 2

- Kernel Linux real
    
- Mejor rendimiento en sistema de archivos
    
- Compatibilidad con Docker
    

Verificación:

```powershell
wsl --version
wsl -l -v
```

---

## 3. Instalación

El despliegue moderno se realiza desde PowerShell con privilegios de administrador.

```powershell
# Instalación básica
wsl --install

# Listar distribuciones disponibles
wsl --list --online

# Instalar distribución específica
wsl --install -d Ubuntu-22.04
```

---

## 4. Configuración inicial

Después de instalar una distribución, se recomienda preparar el entorno.

```bash
# Actualizar sistema
sudo apt update && sudo apt upgrade -y

# Instalar herramientas básicas
sudo apt install build-essential git curl wget -y
```

---

## 5. Interoperabilidad entre sistemas

WSL permite acceso bidireccional entre sistemas de archivos.

Linux hacia Windows

- Ruta: /mnt/c/Users/
    

Windows hacia Linux

- Ruta de red: \wsl$
    

Exploración gráfica

```bash
explorer.exe .
```

---

## 6. Operaciones de mantenimiento y backup

Auditoría

```powershell
wsl --status
```

Actualización

```powershell
wsl --update
```

Backup

```powershell
wsl --export Ubuntu D:\Backups\ubuntu_cth.tar
```

Restauración

```powershell
wsl --import Ubuntu_Lab D:\WSL\Lab D:\Backups\ubuntu_cth.tar
```

Eliminación

```powershell
wsl --unregister <NombreDistro>
```

---

### Referencias externas

[https://learn.microsoft.com/en-us/windows/wsl/](https://learn.microsoft.com/en-us/windows/wsl/)  
[https://learn.microsoft.com/en-us/windows/wsl/compare-versions](https://learn.microsoft.com/en-us/windows/wsl/compare-versions)

---

### Documentación relacionada

[[02 - Mantenimiento de distribuciones]]