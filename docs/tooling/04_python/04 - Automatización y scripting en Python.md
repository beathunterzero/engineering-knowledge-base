## 1. Rol de Python en CTI y CTH

Python es uno de los lenguajes principales en ciberseguridad por su capacidad de automatización y su ecosistema de librerías.

En contextos de Cyber Threat Intelligence y Threat Hunting se utiliza para:

- Normalización de datos
    
- Integración con APIs (VirusTotal, AlienVault)
    
- Procesamiento de logs
    
- Automatización de análisis
    

---

## 2. Scripts dinámicos

Un script debe permitir la entrada de parámetros sin modificar el código. Para ello se utiliza argparse.

---

### 2.1 Uso de argparse

```python
import argparse

def main():
    parser = argparse.ArgumentParser(description="Herramienta de ejemplo")
    parser.add_argument("--name", help="Nombre del analista", required=True)
    
    args = parser.parse_args()
    print(f"[*] Iniciando análisis para: {args.name}")

if __name__ == "__main__":
    main()
```

---

## 3. Casos de uso en ciberseguridad

Limpieza de logs

- Filtrado y rotación de archivos
    

Parsers de IoCs

- Extracción de IPs, hashes y dominios
    

Scraping

- Recolección de información de fuentes externas
    

Enriquecimiento

- Consulta de reputación de indicadores
    

---

## 4. Interoperabilidad de entornos

---

### 4.1 Ejecución desde PowerShell

```powershell
python .\src\scripts\analisis_iocs.py --file logs.txt
```

---

### 4.2 Ejecución vía WSL

```powershell
wsl python3 /home/rhodyn/proyectos/cth/parser.py --name beathunterzero
```

---

## 5. Buenas prácticas

Ubicación

- Almacenar scripts en src/scripts/
    

Rutas

- Usar rutas relativas con os o pathlib
    

Parámetros

- Evitar valores fijos en el código
    

Documentación

- Incluir ejemplos de uso en README.md
    

---

### Referencias externas

[https://docs.python.org/3/howto/argparse.html](https://docs.python.org/3/howto/argparse.html)

---

### Documentación relacionada

[[01 - Python para WSL]]  
[[05 - Buenas prácticas en Python]]