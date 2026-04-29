## 1. Definición de snapshot

Un snapshot es una captura del estado completo de una máquina virtual en un momento específico.

Incluye:

- Estado del disco
    
- Configuración de la VM
    
- Memoria (si la VM está encendida)
    

Permite restaurar la máquina a ese punto exacto.

---

## 2. Casos de uso en ciberseguridad

Estado base

- Snapshot después de instalación limpia
    

Pre-ejecución

- Antes de ejecutar malware o pruebas
    

Comparación

- Antes y después de cambios
    

Puntos de control

- Durante configuraciones complejas
    

---

## 3. Estados del snapshot

VM apagada

Ventajas

- Menor tamaño
    
- Mayor estabilidad
    

Desventajas

- No conserva procesos ni memoria
    

---

VM encendida

Ventajas

- Conserva estado completo del sistema
    

Desventajas

- Mayor consumo de espacio
    
- Proceso más lento
    

---

## 4. Operaciones en VMware

---

### 4.1 Crear snapshot

Ruta

- VM > Snapshot > Take Snapshot
    

Buenas prácticas

- Usar nombres descriptivos
    
- Documentar el estado del sistema
    

---

### 4.2 Revertir snapshot

- Restaura la VM al estado guardado
    
- Elimina cambios posteriores
    

---

### 4.3 Administración

- Uso de Snapshot Manager
    
- Permite navegar entre estados
    
- Eliminar snapshots innecesarios
    

---

## 5. Impacto en almacenamiento

Los snapshots no son copias completas.

Características

- Uso de archivos diferenciales
    
- Incremento de tamaño con cambios
    

Recomendación

- Mantener máximo 2 a 3 snapshots por VM
    
- Evitar acumulación prolongada
    

---

## 6. Buenas prácticas

Snapshot inicial

- Crear estado base limpio
    

Uso controlado

- No mantener estados innecesarios
    

Limpieza

- Eliminar snapshots tras validación de cambios
    

Reversión

- Restaurar después de pruebas o análisis
    

---

### Referencias externas

[https://docs.vmware.com/en/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-60908779-7809-4C4F-941A-98A88E148483.html](https://docs.vmware.com/en/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-60908779-7809-4C4F-941A-98A88E148483.html)

---

### Documentación relacionada

[[01 - Virtualización (Virtual Machines)]]  
[[02 - Creación y configuración de una VM en VMware]]  
[[05 - Exportación e importación de OVAs]]