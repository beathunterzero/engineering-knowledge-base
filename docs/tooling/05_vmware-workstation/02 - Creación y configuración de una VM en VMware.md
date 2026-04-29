## 1. Proceso de creación

Para mantener consistencia en el laboratorio, la creación de máquinas virtuales debe seguir un flujo controlado que garantice rendimiento y aislamiento.

---

### 1.1 Configuración de hardware

Se recomienda utilizar la opción Custom (advanced) para control total.

Compatibility

- Usar la versión más reciente disponible
    

Installer Disk Image

- Seleccionar la imagen del sistema operativo
    

Naming

- Aplicar nomenclatura estándar (ej. ENDP-DEB-2604007)
    

Procesadores

- Mínimo 2 núcleos
    
- 4 núcleos para entornos exigentes
    

Memoria

Linux sin entorno gráfico

- 2 GB
    

Windows o entornos gráficos

- 4 GB a 8 GB
    

---

## 2. Configuración de almacenamiento

Disk type

- SCSI o NVMe (recomendado)
    

Capacidad

Sistemas ligeros

- 20 GB a 40 GB
    

Sistemas de análisis

- 80 GB o más
    

Provisioning

- Usar discos divididos en múltiples archivos
    
- Facilita portabilidad y backups
    

---

## 3. Configuración de red

NAT

- Acceso a internet mediante el host
    
- Uso inicial para instalación y actualizaciones
    

Host-Only

- Red aislada entre host y VMs
    
- Recomendado para laboratorios y análisis
    

Bridge

- Conexión directa a la red física
    
- Usar con precaución
    

---

## 4. Post-instalación: VMware Tools

En sistemas Linux:

```bash
sudo apt update
sudo apt install open-vm-tools-desktop -y
sudo reboot
```

Beneficios

- Sincronización de tiempo
    
- Ajuste dinámico de resolución
    
- Integración con el sistema host
    

---

## 5. Validación final

Hostname

- Debe coincidir con el nombre asignado
    

Red

- IP configurada según inventario
    

Snapshot

- Crear estado inicial limpio
    

Credenciales

- Definidas según estándar del laboratorio
    

---

### Referencias externas

[https://docs.vmware.com/en/VMware-Workstation-Pro/index.html](https://docs.vmware.com/en/VMware-Workstation-Pro/index.html)

---

### Documentación relacionada

[[01 - Virtualización (Virtual Machines)]]  
[[03 - Estándar de nomenclatura e inventario de VMs]]  
[[04 - Gestión de snapshots y reversión de estado]]