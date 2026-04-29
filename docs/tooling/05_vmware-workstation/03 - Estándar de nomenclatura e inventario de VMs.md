## 1. Filosofía de gestión de activos

Las máquinas virtuales deben tratarse como activos estructurados dentro del laboratorio.

Una nomenclatura consistente permite:

- Identificación rápida en logs
    
- Correlación en herramientas de análisis
    
- Gestión ordenada del entorno
    

---

## 2. Estructura de nomenclatura

Formato general:

[ROL]-[SISTEMA]-[ID]

---

### 2.1 Rol del activo

ENDP

- Endpoint de pruebas
    

DFIR

- Análisis forense y respuesta a incidentes
    

PENT

- Evaluación ofensiva
    

SERV

- Servicios de infraestructura
    

---

### 2.2 Sistema operativo

DEB

- Debian
    

FED

- Fedora
    

WIN

- Windows
    

KAL

- Kali Linux
    

KALP

- Kali Purple
    

---

### 2.3 Identificador único

Formato: YYMM###

YY

- Año de creación
    

MM

- Mes de creación
    

- Identificador incremental único
    

Regla

- No reutilizar identificadores
    

---

## 3. Inventario de laboratorio

ENDP-DEB-2604007

- OS: Debian 13
    
- IP: 192.168.197.130
    
- Rol: Endpoint Linux
    

ENDP-FED-2604008

- OS: Fedora 43
    
- IP: 192.168.197.131
    
- Rol: Endpoint Linux
    

DFIR-KALP-2604009

- OS: Kali Purple
    
- IP: 192.168.197.133
    
- Rol: Análisis y SOC
    

PENT-KAL-2604010

- OS: Kali Linux
    
- IP: 192.168.197.134
    
- Rol: Pentesting
    

ENDP-WIN-2604012

- OS: Windows 10
    
- IP: 192.168.197.137
    
- Rol: Endpoint Windows
    

---

## 4. Ciclo de vida

Alta

- Asignar ID único
    
- Registrar información en sistema de gestión
    

Mantenimiento

- Mantener credenciales consistentes en laboratorio
    

Baja

- Registrar motivo de eliminación
    
- No reutilizar el identificador
    

---

## 5. Buenas prácticas de red

Direccionamiento

- Uso de IPs estáticas
    

Consistencia

- Mantener rango definido para visibilidad en herramientas
    

Seguridad

- No reutilizar credenciales del sistema host
    

---

### Referencias externas

[https://kb.vmware.com/s/article/1003736](https://kb.vmware.com/s/article/1003736)

---

### Documentación relacionada

[[01 - Virtualización (Virtual Machines)]]  
[[02 - Creación y configuración de una VM en VMware]]