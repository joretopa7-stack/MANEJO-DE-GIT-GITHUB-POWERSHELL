# ⚡ PowerShell — Guía Profesional para Desarrolladores ADSO

## 📚 Nivel: Junior Competitivo

---

# 📌 Descripción

Esta documentación contiene los conocimientos fundamentales de **PowerShell** que debe manejar un desarrollador con perfil **Tecnólogo en Análisis y Desarrollo de Software (ADSO) Junior Competitivo**.

El objetivo es aprender PowerShell como herramienta complementaria para:

- Administrar entornos de desarrollo.
- Automatizar tareas repetitivas.
- Gestionar archivos y procesos.
- Trabajar eficientemente con sistemas Windows.
- Mejorar la productividad como desarrollador.

---

# 🎯 Objetivos de aprendizaje

Al finalizar esta guía se debe poder:

✅ Utilizar PowerShell desde la terminal.  
✅ Comprender comandos y estructura de PowerShell.  
✅ Administrar archivos y carpetas.  
✅ Manejar variables y scripts básicos.  
✅ Automatizar tareas comunes.  
✅ Gestionar procesos del sistema.  
✅ Trabajar con herramientas de desarrollo.  
✅ Crear scripts simples de automatización.

---

# 1. Fundamentos de PowerShell

## ¿Qué es PowerShell?

PowerShell es una terminal y lenguaje de scripting desarrollado por Microsoft que permite administrar sistemas y automatizar tareas mediante comandos.

A diferencia de CMD, PowerShell trabaja con **objetos**, no solamente con texto.

---

## PowerShell vs CMD

| CMD | PowerShell |
|-|-|
| Terminal tradicional | Shell avanzada |
| Trabaja principalmente con texto | Trabaja con objetos |
| Menos capacidad de automatización | Alto nivel de scripting |
| Comandos limitados | Gran cantidad de herramientas |

---

# 2. Concepto de Cmdlets

Los comandos de PowerShell se llaman **Cmdlets**.

Su estructura normalmente es:

```
Verbo-Sustantivo
```

Ejemplos:

```powershell
Get-Process
```

Obtener procesos.

```powershell
Get-Service
```

Obtener servicios.

```powershell
Set-Location
```

Cambiar ubicación.

---

# 3. Navegación por el sistema

Un desarrollador debe manejar rutas y directorios.

## Ver ubicación actual

```powershell
Get-Location
```

---

## Cambiar carpeta

```powershell
Set-Location carpeta
```

Alias:

```powershell
cd carpeta
```

---

## Listar archivos

```powershell
Get-ChildItem
```

Alias:

```powershell
ls
```

---

## Crear carpeta

```powershell
New-Item -ItemType Directory nombre
```

---

## Crear archivo

```powershell
New-Item archivo.txt
```

---

## Copiar archivos

```powershell
Copy-Item archivo.txt destino
```

---

## Mover archivos

```powershell
Move-Item archivo.txt destino
```

---

## Eliminar archivos

```powershell
Remove-Item archivo.txt
```

---

# 4. Ayuda y documentación

Un profesional sabe buscar información.

Consultar ayuda:

```powershell
Get-Help comando
```

Ejemplo:

```powershell
Get-Help Get-Process
```

Actualizar ayuda:

```powershell
Update-Help
```

Buscar comandos:

```powershell
Get-Command
```

---

# 5. Variables

Las variables almacenan información.

Crear variable:

```powershell
$nombre="Jorge"
```

Mostrar:

```powershell
$nombre
```

Ejemplo:

```powershell
$proyecto="API FastAPI"
```

---

# 6. Tipos de datos básicos

PowerShell maneja:

- Texto.
- Números.
- Fechas.
- Arrays.
- Objetos.

Ejemplo:

```powershell
$edad=18
```

Array:

```powershell
$lenguajes=@("Python","Java","JavaScript")
```

---

# 7. Operadores

## Matemáticos

```powershell
+
-
*
/
```

Ejemplo:

```powershell
5 + 5
```

---

## Comparación

```powershell
-eq
-ne
-gt
-lt
```

Ejemplo:

```powershell
5 -eq 5
```

Resultado:

```
True
```

---

# 8. Condicionales

Permiten tomar decisiones.

Ejemplo:

```powershell
$edad=18

if($edad -ge 18){

Write-Host "Mayor de edad"

}
else{

Write-Host "Menor de edad"

}
```

---

# 9. Bucles

Automatizar procesos repetitivos.

## For

```powershell
for($i=1;$i -le 5;$i++){

Write-Host $i

}
```

---

## Foreach

```powershell
$programas=@("VSCode","Git","Python")

foreach($programa in $programas){

Write-Host $programa

}
```

---

# 10. Scripts PowerShell

Los scripts tienen extensión:

```
.ps1
```

Ejemplo:

```
backup.ps1
```

Ejecutar:

```powershell
.\backup.ps1
```

---

# 11. Seguridad de ejecución

Consultar política:

```powershell
Get-ExecutionPolicy
```

Cambiar política:

```powershell
Set-ExecutionPolicy
```

Conceptos:

- Restricted.
- RemoteSigned.
- Unrestricted.

---

# 12. Procesos del sistema

Consultar procesos:

```powershell
Get-Process
```

Buscar uno:

```powershell
Get-Process chrome
```

Finalizar proceso:

```powershell
Stop-Process
```

---

# 13. Servicios de Windows

Consultar servicios:

```powershell
Get-Service
```

Iniciar:

```powershell
Start-Service
```

Detener:

```powershell
Stop-Service
```

---

# 14. Variables de entorno

Consultar:

```powershell
Get-ChildItem Env:
```

Ejemplo:

```
PATH
JAVA_HOME
USERPROFILE
```

Importante para:

- Java.
- Python.
- Node.js.
- Bases de datos.

---

# 15. Gestión de software

Un Junior debe conocer gestores de paquetes.

Ejemplo:

## Winget

Buscar:

```powershell
winget search nombre
```

Instalar:

```powershell
winget install nombre
```

Actualizar:

```powershell
winget upgrade
```

---

# 16. PowerShell para desarrollo

Aplicaciones prácticas:

## Git

Ejemplo:

```powershell
git status
git add .
git commit
git push
```

---

## Python

Crear entorno:

```powershell
python -m venv venv
```

Activar:

```powershell
.\venv\Scripts\activate
```

---

## Node.js

Instalar dependencias:

```powershell
npm install
```

Ejecutar proyecto:

```powershell
npm run dev
```

---

# 17. Red básica

Consultar información:

```powershell
ipconfig
```

Probar conexión:

```powershell
Test-Connection google.com
```

Consultar puertos:

```powershell
netstat
```

---

# 18. Automatización básica

Ejemplo:

Crear estructura de proyecto:

```powershell
mkdir proyecto

cd proyecto

mkdir src

mkdir tests
```

PowerShell permite automatizar creación de proyectos y configuraciones.

---

# 19. Buenas prácticas

Un Junior competitivo debe:

✅ Entender comandos principales.  
✅ Saber leer errores.  
✅ Utilizar ayuda integrada.  
✅ Crear scripts simples.  
✅ Automatizar tareas repetitivas.  
✅ Mantener scripts organizados.  
✅ No ejecutar comandos desconocidos sin revisar.  
✅ Usar PowerShell para mejorar productividad.

---

# Evaluación del nivel

## Junior básico

Debe saber:

- Navegación.
- Archivos.
- Comandos básicos.
- Ejecutar scripts.

---

## Junior competitivo

Debe dominar:

✅ Cmdlets principales.  
✅ Variables.  
✅ Condicionales.  
✅ Bucles.  
✅ Scripts básicos.  
✅ Procesos.  
✅ Servicios.  
✅ Variables de entorno.  
✅ Automatización básica.  
✅ Uso con herramientas de desarrollo.

---

## Junior sobresaliente

Además:

✅ Scripts avanzados.  
✅ Manejo de módulos.  
✅ Administración remota.  
✅ Integración CI/CD.  
✅ Automatización avanzada.  
✅ Administración avanzada de Windows.

---

# Conclusión

Un desarrollador ADSO que domina PowerShell a nivel Junior Competitivo tiene una ventaja porque puede interactuar mejor con el sistema operativo, automatizar tareas y administrar su entorno de desarrollo de manera más profesional.

PowerShell no reemplaza la programación; la complementa permitiendo trabajar de forma más eficiente.