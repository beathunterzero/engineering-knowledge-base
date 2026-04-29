## 1. ¿Qué es PowerShell?

PowerShell es una plataforma de automatización de tareas multiplataforma que incluye un shell de línea de comandos, un lenguaje de scripting y un framework de gestión de configuración.

A diferencia de shells tradicionales como Bash o CMD, que procesan texto plano, PowerShell se basa en el framework .NET y trabaja con objetos. Esto permite una manipulación de datos más estructurada, precisa y reutilizable, especialmente en contextos de administración de sistemas, automatización y análisis.

---

### 1.1 Diferencias críticas de versión

Es importante distinguir entre las dos ramas principales de PowerShell para garantizar compatibilidad en scripts y módulos:

Windows PowerShell

- Versión: 5.1
    
- Base: .NET Framework
    
- Plataforma: Solo Windows
    
- Estado: Mantenimiento (legacy)
    
- Uso recomendado: Compatibilidad con sistemas antiguos
    

PowerShell (Core)

- Versión: 7.x (actual)
    
- Base: .NET 6+ (open source)
    
- Plataforma: Windows, Linux, macOS
    
- Estado: Desarrollo activo
    
- Uso recomendado: DevOps, Cloud, Threat Hunting y entornos multiplataforma
    

---

## 2. Anatomía de los cmdlets

Los comandos nativos de PowerShell se denominan cmdlets. Siguen una convención de nomenclatura basada en la estructura Verbo-Sustantivo, lo que facilita su comprensión y descubrimiento.

Verbos comunes:  
Get (recuperar), Set (establecer), New (crear), Remove (eliminar), Start / Stop

Sustantivos:  
Representan el recurso sobre el que se opera, por ejemplo: Process, Service, Item, Content

Esta estructura permite inferir funcionalidad sin necesidad de memorizar comandos completos.

---

## 3. Comandos esenciales de navegación y gestión

Cmdlets fundamentales para operar en el sistema de archivos:

Get-ChildItem (alias: ls / dir)

- Lista archivos y directorios junto con sus propiedades
    

Set-Location (alias: cd)

- Cambia el directorio de trabajo actual
    

Copy-Item (alias: cp)

- Copia archivos o directorios
    

Remove-Item (alias: rm / del)

- Elimina archivos o directorios (usar -Recurse para eliminar carpetas)
    

Move-Item (alias: mv)

- Mueve o renombra archivos y directorios
    

---

## 4. Herramientas de auto-documentación

PowerShell incluye mecanismos integrados para exploración y aprendizaje de comandos:

Get-Help

- Muestra sintaxis, descripción y parámetros
    
- Ejemplo: Get-Help Get-Process -Examples
    

Get-Command

- Lista comandos disponibles en el sistema
    
- Útil para descubrir funcionalidades de módulos instalados
    

Get-Member (alias: gm)

- Muestra propiedades y métodos de los objetos
    
- Es clave para análisis y comprensión del output
    

Ejemplo:  
Get-Process | Get-Member

---

## 5. El pipeline (|)

En PowerShell, el pipeline transfiere objetos completos entre cmdlets, no solo texto. Esto permite aplicar filtros y transformaciones directamente sobre estructuras de datos sin depender de herramientas externas como sed o awk.

Ejemplo orientado a análisis:  
Get-Process | Where-Object { $_.CPU -gt 100 }

Este comando filtra procesos con alto consumo de CPU utilizando propiedades del objeto.

---

### Referencias Externas

[https://learn.microsoft.com/en-us/powershell/scripting/overview](https://learn.microsoft.com/en-us/powershell/scripting/overview)  
[https://github.com/PowerShell/PowerShell](https://github.com/PowerShell/PowerShell)

---

### Documentación Relacionada

[[02 - Alias en Powershell]]  
[[03 - AWS CLI]]  
[[04 - Azure CLI]]  
[[01 - WSL]]  
[[01 - Git]]