# ⚡ PowerShell — Guía Profesional para Desarrolladores ADSO

## 📚 Nivel: Junior Sobresaliente

---

# 📌 Descripción

Esta documentación contiene los conocimientos avanzados de **PowerShell** que diferencian a un desarrollador ADSO Junior Competitivo de un perfil **Junior Sobresaliente**.

El enfoque está orientado a utilizar PowerShell como una herramienta profesional para:

- Automatización de procesos.
- Creación de scripts reutilizables.
- Administración del entorno de desarrollo.
- Gestión avanzada del sistema operativo.
- Integración con herramientas profesionales.
- Optimización de tareas repetitivas.

---

# 🎯 Objetivos de aprendizaje

Al finalizar esta guía se debe poder:

✅ Crear scripts profesionales en PowerShell.  
✅ Trabajar con funciones y módulos.  
✅ Manejar errores correctamente.  
✅ Procesar información mediante objetos.  
✅ Automatizar procesos de desarrollo.  
✅ Consumir APIs desde PowerShell.  
✅ Administrar configuraciones del sistema.  
✅ Integrar PowerShell con Git y CI/CD.

---

# 1. Comprender PowerShell como lenguaje de programación

Un junior sobresaliente entiende que PowerShell no es solamente una consola.

PowerShell permite:

- Variables.
- Funciones.
- Clases.
- Objetos.
- Manejo de errores.
- Programación orientada a objetos básica.

Ejemplo:

```powershell
function Saludar {

param($nombre)

Write-Host "Hola $nombre"

}

Saludar "Jorge"
```

---

# 2. Trabajo avanzado con objetos

Una diferencia clave:

CMD trabaja con texto.

PowerShell trabaja con objetos.

Ejemplo:

```powershell
Get-Process
```

Devuelve objetos con propiedades:

```
Name
Id
CPU
Memory
```

Consultar propiedades:

```powershell
Get-Process | Get-Member
```

---

# 3. Pipeline avanzado

El pipeline permite encadenar comandos.

Ejemplo:

```powershell
Get-Process | Where-Object CPU -gt 100
```

Proceso:

```
Obtener procesos

↓

Filtrar procesos

↓

Mostrar resultado
```

---

Ejemplo:

```powershell
Get-Service |
Where-Object Status -eq Running
```

Obtiene servicios activos.

---

# 4. Filtrado y procesamiento de información

## Where-Object

Filtrar datos:

```powershell
Get-Process |
Where-Object {$_.Name -like "chrome"}
```

---

## Select-Object

Seleccionar información:

```powershell
Get-Process |
Select-Object Name, CPU
```

---

## Sort-Object

Ordenar:

```powershell
Get-Process |
Sort-Object CPU
```

---

# 5. Exportación de información

Un profesional sabe generar reportes.

## CSV

```powershell
Get-Process |
Export-Csv procesos.csv
```

---

## JSON

```powershell
ConvertTo-Json
```

Útil para:

- APIs.
- Automatización.
- Configuraciones.

---

# 6. Manejo profesional de errores

Un script profesional debe controlar fallos.

Ejemplo:

```powershell
try {

Get-Content archivo.txt

}

catch {

Write-Host "Error encontrado"

}
```

---

Beneficios:

- Evita interrupciones.
- Facilita mantenimiento.
- Mejora calidad del script.

---

# 7. Parámetros en scripts

Un script profesional debe recibir información.

Ejemplo:

```powershell
param(
[string]$nombre
)

Write-Host $nombre
```

Ejecutar:

```powershell
script.ps1 Jorge
```

---

# 8. Creación de funciones reutilizables

Ejemplo:

```powershell
function Crear-Carpeta {

param($nombre)

New-Item $nombre -ItemType Directory

}
```

Ventajas:

- Código reutilizable.
- Mejor organización.
- Fácil mantenimiento.

---

# 9. Módulos de PowerShell

Los módulos permiten agrupar funciones.

Estructura:

```
ModuloProyecto

|

├── funciones.ps1

└── modulo.psm1
```

Importar:

```powershell
Import-Module NombreModulo
```

---

# 10. Gestión de perfiles PowerShell

PowerShell permite personalizar la consola.

Consultar:

```powershell
$PROFILE
```

Crear perfil:

```powershell
New-Item $PROFILE
```

Permite agregar:

- Alias personalizados.
- Funciones.
- Configuraciones.

---

# 11. Automatización de proyectos

Ejemplo:

Crear estructura automáticamente:

```powershell
mkdir Proyecto

cd Proyecto

mkdir src

mkdir tests

New-Item README.md
```

Uso profesional:

- Crear proyectos.
- Preparar ambientes.
- Automatizar configuraciones.

---

# 12. Automatización con Git

PowerShell puede automatizar flujos Git.

Ejemplo:

```powershell
git add .

git commit -m "update"

git push
```

Crear script:

```powershell
deploy.ps1
```

---

# 13. Gestión de entornos de desarrollo

Un junior sobresaliente sabe automatizar:

## Python

Crear entorno:

```powershell
python -m venv venv
```

Instalar dependencias:

```powershell
pip install -r requirements.txt
```

---

## Node.js

Instalar:

```powershell
npm install
```

Ejecutar:

```powershell
npm run dev
```

---

# 14. Trabajo con APIs REST

PowerShell puede consumir servicios web.

Ejemplo:

```powershell
Invoke-RestMethod https://api.com/users
```

Permite:

- Consultar APIs.
- Automatizar pruebas.
- Integrarse con servicios.

---

# 15. Manejo de archivos JSON

Ejemplo:

Leer JSON:

```powershell
Get-Content config.json |
ConvertFrom-Json
```

Convertir:

```powershell
ConvertTo-Json
```

Uso:

- Configuración.
- Automatización.
- APIs.

---

# 16. Administración avanzada del sistema

Un junior sobresaliente conoce:

## Procesos

```powershell
Get-Process
Stop-Process
```

---

## Servicios

```powershell
Get-Service
Restart-Service
```

---

## Registro de Windows

```powershell
Get-ItemProperty
```

---

## Eventos del sistema

```powershell
Get-EventLog
```

---

# 17. Variables de entorno avanzadas

Consultar:

```powershell
Get-ChildItem Env:
```

Modificar:

```powershell
$env:NOMBRE="valor"
```

Importancia:

- Configuración de aplicaciones.
- Rutas.
- Credenciales.
- Entornos.

---

# 18. Seguridad en scripts

Buenas prácticas:

✅ No guardar contraseñas en texto plano.

✅ Usar variables de entorno.

✅ Validar entradas.

✅ Revisar scripts antes de ejecutarlos.

---

Ejemplo:

Evitar:

```powershell
$password="12345"
```

Mejor:

```powershell
$env:PASSWORD
```

---

# 19. Ejecución remota

PowerShell permite administrar equipos remotos.

Concepto:

```
Equipo local

      |

      |

Equipo remoto
```

Herramientas:

```powershell
Enter-PSSession
```

```powershell
Invoke-Command
```

---

# 20. PowerShell y CI/CD

Uso profesional:

```
Código

↓

GitHub

↓

GitHub Actions

↓

PowerShell Script

↓

Automatización
```

Ejemplos:

- Compilar proyectos.
- Ejecutar pruebas.
- Preparar despliegues.

---

# 21. Buenas prácticas profesionales

Un Junior Sobresaliente:

✅ Escribe scripts legibles.  
✅ Usa funciones.  
✅ Documenta código.  
✅ Maneja errores.  
✅ Reutiliza módulos.  
✅ Automatiza tareas repetitivas.  
✅ Usa control de versiones.  
✅ Integra PowerShell con desarrollo.

---

# Evaluación del nivel

## Junior Competitivo

Debe saber:

- Cmdlets.
- Archivos.
- Variables.
- Scripts básicos.
- Automatización simple.

---

# Junior Sobresaliente

Además domina:

✅ Programación en PowerShell.  
✅ Funciones.  
✅ Módulos.  
✅ Pipeline avanzado.  
✅ Manejo de objetos.  
✅ Manejo de errores.  
✅ APIs REST.  
✅ JSON.  
✅ Automatización profesional.  
✅ Integración Git/CD.  
✅ Administración avanzada básica.

---

# Conclusión

Un desarrollador ADSO Junior Sobresaliente utiliza PowerShell como una herramienta de productividad profesional.

No solamente ejecuta comandos: crea automatizaciones, administra entornos, integra herramientas y mejora procesos dentro del ciclo de desarrollo de software.