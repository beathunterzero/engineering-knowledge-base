## 1. Definición de OVA y OVF

OVF (Open Virtualization Format)

- Conjunto de archivos que describen una máquina virtual
    
- Incluye configuración, discos y metadatos
    

OVA (Open Virtual Application)

- Archivo único que contiene el paquete OVF
    
- Formato recomendado para portabilidad
    

---

## 2. Exportación de una VM

Permite generar una copia portátil del entorno.

---

### 2.1 Procedimiento

1. Apagar la máquina virtual
    
2. Limpiar el sistema
    

- Eliminar archivos temporales
    
- Vaciar papelera
    

3. Exportar desde VMware
    

- File > Export to OVF
    

4. Seleccionar formato
    

- Elegir OVA para archivo único
    

5. Definir ubicación
    

- Guardar en almacenamiento externo o backup
    

---

## 3. Importación de OVA

Permite desplegar máquinas virtuales preconfiguradas.

---

### 3.1 Procedimiento

1. Abrir archivo
    

- File > Open
    
- Seleccionar archivo OVA
    

2. Aceptar licencias si aplica
    
3. Configurar
    

Nombre

- Aplicar nomenclatura estándar
    

Ruta

- Seleccionar ubicación con suficiente espacio
    

4. Finalizar importación
    

- VMware registrará la VM
    

---

## 4. Consideraciones técnicas

Snapshots

- No se incluyen en exportación OVA
    
- El estado exportado es consolidado
    

Compatibilidad

- Puede haber errores entre versiones de VMware
    

Red

- Seleccionar “I Copied It” para evitar conflictos de MAC
    

---

## 5. Buenas prácticas

Documentación

- Incluir credenciales y configuración en archivo adjunto
    

Integridad

- Verificar funcionamiento tras importación
    

Red

- Confirmar configuración del adaptador
    

Portabilidad

- Utilizar compresión adicional si es necesario para transferencia
    

---

### Referencias externas

[https://docs.vmware.com/en/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-D815858E-A343-417A-8994-67D8919A30E5.html](https://docs.vmware.com/en/VMware-Workstation-Pro/17/com.vmware.ws.using.doc/GUID-D815858E-A343-417A-8994-67D8919A30E5.html)

---

### Documentación relacionada

[[01 - Virtualización (Virtual Machines)]]