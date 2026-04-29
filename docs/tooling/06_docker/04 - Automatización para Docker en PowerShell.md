## 1. Fundamentos de personalización

PowerShell permite optimizar el uso de Docker mediante alias y funciones.

Alias

- Abreviaciones para comandos
    

Funciones

- Bloques reutilizables con lógica integrada
    

---

## 2. Uso de Docker en segundo plano

Docker Desktop puede ejecutarse sin interfaz gráfica.

Parámetro

- --background
    

Beneficio

- Menor consumo de recursos
    

---

## 3. Funciones de automatización

---

### 3.1 Inicio de Docker

```powershell
function Start-DockerDesktop {
    Write-Host "Iniciando Docker Desktop..." -ForegroundColor Cyan
    Start-Process "C:\Program Files\Docker\Docker\Docker Desktop.exe" --background
}
```

---

### 3.2 Detención completa

```powershell
function Stop-DockerDesktop {
    Write-Host "Deteniendo Docker..." -ForegroundColor Yellow

    Stop-Service -Name "com.docker.service" -ErrorAction SilentlyContinue

    Get-Process | Where-Object { $_.Name -like "*Docker*" } |
        Stop-Process -Force -ErrorAction SilentlyContinue

    wsl --terminate docker-desktop >$null 2>$null
    wsl --terminate docker-desktop-data >$null 2>$null

    Write-Host "Docker detenido correctamente." -ForegroundColor Green
}
```

---

### 3.3 Orquestación de entorno

```powershell
function dockerup {
    Write-Host "Levantando entorno..." -ForegroundColor Cyan
    dockerstart
    Start-Sleep -Seconds 3
    wsl -d Ubuntu
}
```

---

## 4. Configuración del perfil

Para persistencia, agregar al archivo $PROFILE.

---

### 4.1 Variables y alias

```powershell
$env:EDITOR = "notepad"

Set-Alias dockerstart Start-DockerDesktop
Set-Alias dockerstop Stop-DockerDesktop
```

---

## 5. Ventajas

Optimización

- Reducción de uso de recursos
    

Control

- Gestión completa del ciclo de vida
    

Integración

- Coordinación con WSL
    

Mantenibilidad

- Código reutilizable
    

---

## 6. Script completo

```powershell
$env:EDITOR = "notepad"

function Start-DockerDesktop {
    Write-Host "Iniciando Docker Desktop..." -ForegroundColor Cyan
    Start-Process "C:\Program Files\Docker\Docker\Docker Desktop.exe" --background
}

function Stop-DockerDesktop {
    Write-Host "Deteniendo Docker..." -ForegroundColor Yellow

    Stop-Service -Name "com.docker.service" -ErrorAction SilentlyContinue

    Get-Process | Where-Object { $_.Name -like "*Docker*" } |
        Stop-Process -Force -ErrorAction SilentlyContinue

    wsl --terminate docker-desktop >$null 2>$null
    wsl --terminate docker-desktop-data >$null 2>$null

    Write-Host "Docker detenido correctamente." -ForegroundColor Green
}

function dockerup {
    Write-Host "Levantando entorno..." -ForegroundColor Cyan
    dockerstart
    Start-Sleep -Seconds 3
    wsl -d Ubuntu
}

Set-Alias dockerstart Start-DockerDesktop
Set-Alias dockerstop Stop-DockerDesktop
```

---

### Referencias externas

[https://docs.docker.com/desktop/settings/windows/](https://docs.docker.com/desktop/settings/windows/)  
[https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_aliases](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_aliases)  
[https://learn.microsoft.com/en-us/windows/wsl/basic-commands](https://learn.microsoft.com/en-us/windows/wsl/basic-commands)

---

### Documentación relacionada

[[01 - Conceptos fundamentales de Docker]]