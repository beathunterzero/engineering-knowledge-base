## 1. ¿Qué es una máquina virtual?

Una máquina virtual (VM) es un entorno computacional que emula un sistema completo con CPU, memoria, red y almacenamiento, ejecutándose sobre un sistema físico.

Permite ejecutar sistemas operativos independientes sin afectar el sistema principal.

---

## 2. El hipervisor

El hipervisor es el software encargado de crear y gestionar máquinas virtuales.

Tipos:

Tipo 1 (bare-metal)

- Se ejecuta directamente sobre el hardware
    
- Ejemplos: ESXi, Proxmox
    

Tipo 2 (hosted)

- Se ejecuta sobre un sistema operativo
    
- Ejemplo: VMware Workstation
    

---

## 3. Arquitectura básica

Host

- Sistema físico que provee recursos
    

Guest

- Máquina virtual que utiliza recursos del host
    

Encapsulación

- La VM se almacena como archivos dentro de una carpeta
    
- Permite copiar, mover o respaldar entornos completos
    

---

## 4. Componentes virtuales

vCPU

- Núcleos asignados desde el procesador físico
    

vRAM

- Memoria asignada al sistema virtual
    

vDisk

- Archivo que simula un disco duro
    

vNIC

- Interfaz de red virtual
    

---

## 5. Ventajas en ciberseguridad

Aislamiento

- Permite ejecutar código sin afectar el sistema principal
    

Reproducibilidad

- Posibilidad de reiniciar entornos rápidamente
    

Simulación

- Ejecución de múltiples sistemas para pruebas
    

Portabilidad

- Exportación de máquinas virtuales como archivos reutilizables
    

---

## 6. Diferencia con contenedores

Máquina virtual

- Virtualiza hardware
    
- Incluye sistema operativo completo
    
- Mayor aislamiento
    

Contenedores (Docker)

- Comparten el kernel
    
- Mayor eficiencia
    
- Menor aislamiento
    

---

### Referencias externas

[https://www.vmware.com/topics/glossary/content/virtual-machine.html](https://www.vmware.com/topics/glossary/content/virtual-machine.html)

---

### Documentación relacionada

[[02 - Creación y configuración de una VM en VMware]]  
[[03 - Estándar de nomenclatura e inventario de VMs]]  
[[04 - Gestión de snapshots y reversión de estado]]  
[[05 - Exportación e importación de OVAs]]  
[[01 - Powershell]]  
[[01 - WSL]]  
[[01 - Conceptos fundamentales de Docker]]