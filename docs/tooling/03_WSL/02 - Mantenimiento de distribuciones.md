## 1. Introducción al mantenimiento de paquetes

Cada distribución dentro de WSL funciona de forma independiente y utiliza su propio gestor de paquetes.

Mantener el sistema actualizado permite:

- Corregir vulnerabilidades
    
- Mejorar compatibilidad con herramientas (Docker, Python, etc.)
    
- Garantizar estabilidad del entorno
    

---

### 1.1 Comparativa de gestores

Ubuntu / Debian / Kali

- Gestor: APT
    
- Comando base: sudo apt
    

Fedora

- Gestor: DNF
    
- Comando base: sudo dnf
    

openSUSE

- Gestor: Zypper
    
- Comando base: sudo zypper
    

---

## 2. Gestión en distribuciones basadas en Debian (APT)

```bash
# Sincronizar repositorios
sudo apt update

# Actualización completa
sudo apt full-upgrade -y

# Limpieza del sistema
sudo apt autoremove -y
sudo apt clean
```

Instalación de herramientas básicas:

```bash
sudo apt install build-essential git curl wget -y
```

---

## 3. Gestión en Fedora (DNF)

```bash
# Actualización forzada
sudo dnf upgrade --refresh -y

# Limpieza
sudo dnf clean all
```

Herramientas de desarrollo:

```bash
sudo dnf groupinstall "Development Tools" -y
```

---

## 4. Gestión en openSUSE (Zypper)

```bash
# Sincronización
sudo zypper refresh

# Actualización de distribución
sudo zypper dist-upgrade -y
```

Instalación de herramientas base:

```bash
sudo zypper install -t pattern devel_basis
```

---

## 5. Mantenimiento del entorno WSL (host)

---

### 5.1 Gestión del sistema

```powershell
# Detener todas las instancias
wsl --shutdown

# Actualizar kernel
wsl --update

# Ver estado
wsl --status
```

---

## 6. Reglas de higiene técnica

Frecuencia

- Ejecutar mantenimiento de forma periódica (al menos semanal)
    

Ubicación de trabajo

- Evitar trabajar en /mnt/c/
    
- Usar el sistema de archivos Linux (/home/usuario/)
    

Recuperación

- Reinstalar distribuciones en caso de fallos críticos
    

Backup

- Exportar distribuciones configuradas como base reutilizable
    

---

### Referencias externas

[https://learn.microsoft.com/en-us/windows/wsl/wsl-config](https://learn.microsoft.com/en-us/windows/wsl/wsl-config)  
[https://wiki.debian.org/Apt](https://wiki.debian.org/Apt)  
[https://docs.fedoraproject.org/en-US/fedora/rawhide/system-administrators-guide/package-management/DNF/](https://docs.fedoraproject.org/en-US/fedora/rawhide/system-administrators-guide/package-management/DNF/)

---

### Documentación relacionada

[[01 - WSL]]