# Git y GitHub para un Tecnólogo ADSO Junior Competitivo

## Descripción

Este documento contiene los conocimientos fundamentales y profesionales que debe manejar un **Tecnólogo en Análisis y Desarrollo de Software (ADSO) con perfil Junior Competitivo** en el uso de **Git y GitHub**.

El objetivo no es memorizar comandos, sino comprender el flujo de trabajo profesional utilizado por equipos reales de desarrollo de software.

Un desarrollador Junior competitivo debe ser capaz de:

* Gestionar versiones del código.
* Trabajar con ramas locales y remotas.
* Sincronizar cambios con GitHub.
* Descargar y trabajar con ramas remotas.
* Colaborar con otros desarrolladores.
* Mantener repositorios organizados.
* Resolver conflictos.
* Aplicar buenas prácticas de desarrollo.

---

# 📚 Índice

1. Fundamentos de Git y GitHub
2. Configuración inicial
3. Creación y administración de repositorios
4. Flujo profesional de trabajo
5. Manejo de ramas
6. Ramas remotas y sincronización
7. Estrategia profesional de ramas
8. Merge y conflictos
9. Trabajo con GitHub
10. Pull Requests
11. Issues
12. Archivo `.gitignore`
13. README profesional
14. Historial y recuperación
15. Deshacer cambios
16. Buenas prácticas
17. Git avanzado
18. Aplicación en proyectos ADSO
19. Evaluación del nivel Junior
20. Flujo profesional completo

---

# 1. Fundamentos de Git y GitHub

## ¿Qué es Git?

Git es un **sistema de control de versiones distribuido** que permite:

* Registrar cambios realizados en el código.
* Recuperar versiones anteriores.
* Trabajar en equipo.
* Mantener un historial del proyecto.
* Comparar modificaciones.
* Trabajar con ramas.
* Integrar diferentes versiones del código.

### Definición profesional

> Git permite gestionar el historial del código fuente mediante commits y ramas, facilitando la colaboración, trazabilidad y control de versiones durante el desarrollo de software.

---

# Git vs GitHub

| Git                                       | GitHub                                                |
| ----------------------------------------- | ----------------------------------------------------- |
| Sistema de control de versiones           | Plataforma para alojar y colaborar sobre repositorios |
| Funciona localmente                       | Servicio remoto en la nube                            |
| Maneja commits y ramas                    | Aloja repositorios remotos                            |
| Puede funcionar sin Internet              | Facilita la colaboración en línea                     |
| Permite trabajar con repositorios locales | Permite Pull Requests, Issues, revisiones, etc.       |

### Concepto sencillo

```text
Git = Controla las versiones del código

GitHub = Aloja y permite colaborar con el código
```

---

# 2. Configuración inicial de Git

## Configurar usuario

```bash
git config --global user.name "Nombre"
```

```bash
git config --global user.email "correo@example.com"
```

Consultar configuración:

```bash
git config --list
```

Consultar una configuración específica:

```bash
git config user.name
```

```bash
git config user.email
```

Eliminar configuración:

```bash
git config --global --unset user.name
```

```bash
git config --global --unset user.email
```

También se debe conocer:

* Tokens de GitHub.
* SSH Keys.
* Autenticación segura.
* Configuración de credenciales.

---

# 3. Crear y administrar repositorios

## Inicializar un repositorio

```bash
git init
```

Convierte una carpeta normal en un repositorio Git.

Después:

```bash
git status
```

---

## Clonar un repositorio

```bash
git clone URL
```

Ejemplo:

```bash
git clone https://github.com/usuario/proyecto.git
```

Esto:

* Descarga el código.
* Descarga el historial.
* Configura el repositorio local.
* Crea normalmente el remoto `origin`.

Verificar el remoto:

```bash
git remote -v
```

---

# 4. Flujo profesional de trabajo

El flujo básico es:

```text
Modificar código
       ↓
git status
       ↓
git add
       ↓
git commit
       ↓
git push
       ↓
GitHub
```

---

## Revisar cambios

```bash
git status
```

Permite identificar:

* Archivos nuevos.
* Archivos modificados.
* Archivos eliminados.
* Archivos preparados para commit.

---

## Agregar cambios

Todos los cambios:

```bash
git add .
```

Archivo específico:

```bash
git add archivo.py
```

---

## Crear commits profesionales

```bash
git commit -m "feat: crear endpoint usuarios"
```

Tipos recomendados:

```text
feat      Nueva funcionalidad
fix       Corrección de errores
docs      Documentación
test      Pruebas
refactor  Mejoras internas del código
chore     Tareas de mantenimiento
```

Ejemplos:

```bash
git commit -m "feat: agregar login"
```

```bash
git commit -m "fix: corregir conexión BD"
```

```bash
git commit -m "docs: actualizar README"
```

---

# 5. Manejo de ramas

Las ramas permiten desarrollar funcionalidades sin afectar directamente la versión estable.

## Ver ramas locales

```bash
git branch
```

Ejemplo:

```text
* main
  develop
  feature/login
```

El `*` indica la rama actual.

---

## Crear una rama

```bash
git branch feature/login
```

---

## Crear y cambiar a una rama

Forma moderna:

```bash
git switch -c feature/login
```

También existe la forma clásica:

```bash
git checkout -b feature/login
```

---

## Cambiar de rama

Forma moderna:

```bash
git switch main
```

Forma clásica:

```bash
git checkout main
```

---

## Eliminar una rama local

```bash
git branch -d feature/login
```

Si Git no permite eliminarla porque tiene cambios no fusionados:

```bash
git branch -D feature/login
```

⚠️ `-D` fuerza la eliminación, por lo que debe utilizarse con cuidado.

---

# 6. Ramas remotas y sincronización

Esta parte es **fundamental cuando se trabaja en equipo**.

Una rama puede existir:

```text
LOCAL
feature/login
```

o remotamente:

```text
REMOTA
origin/feature/login
```

---

## Ver ramas remotas

```bash
git branch -r
```

Ejemplo:

```text
origin/main
origin/develop
origin/feature/login
origin/feature/usuarios
```

`origin` normalmente representa el repositorio remoto principal.

---

## Ver todas las ramas

Para ver ramas locales y remotas:

```bash
git branch -a
```

Ejemplo:

```text
* main
  develop
  feature/login
  remotes/origin/main
  remotes/origin/develop
  remotes/origin/feature/login
```

---

# Actualizar información del repositorio remoto

## `git fetch`

```bash
git fetch
```

Descarga información nueva del repositorio remoto **sin integrar automáticamente los cambios en tu rama actual**.

---

## `git fetch --all`

```bash
git fetch --all
```

Actualiza la información de **todos los repositorios remotos configurados**.

Después:

```bash
git branch -r
```

Puedes consultar las ramas remotas disponibles.

---

# 📥 Bajar una rama remota a local

Supongamos que después de:

```bash
git fetch --all
```

aparece:

```text
origin/feature/login
```

Existen varias formas de crear la rama local.

---

## Método moderno recomendado

```bash
git switch --track origin/feature/login
```

Git crea la rama local:

```text
feature/login
```

y la conecta con:

```text
origin/feature/login
```

---

## Método clásico

```bash
git checkout --track origin/feature/login
```

También crea la rama local y establece el seguimiento de la rama remota.

---

## Método explícito

```bash
git checkout -b feature/login origin/feature/login
```

Aquí indicamos explícitamente:

```text
Crear rama local:
feature/login

Basada en:
origin/feature/login
```

---

## Verificar la conexión

Después puedes ejecutar:

```bash
git branch -vv
```

Ejemplo:

```text
* feature/login  a123abc [origin/feature/login] crear login
  main           b456def [origin/main] actualizar README
```

Esto permite comprobar qué rama remota está siguiendo cada rama local.

---

# 🔄 Flujo completo para bajar una rama remota

Este proceso es importante memorizarlo:

```bash
git status
```

```bash
git fetch --all
```

```bash
git branch -r
```

Si aparece:

```text
origin/feature/login
```

entonces:

```bash
git switch --track origin/feature/login
```

Finalmente:

```bash
git branch
```

Resultado:

```text
* feature/login
  main
```

---

## Flujo visual

```text
                    GITHUB
                       │
                       │
                git fetch --all
                       │
                       ↓
              RAMAS REMOTAS
                       │
                git branch -r
                       │
                       ↓
           origin/feature/login
                       │
                       │
        git switch --track origin/feature/login
                       │
                       ↓
              RAMA LOCAL
              feature/login
```

---

# `fetch` vs `pull`

| Comando           | Función                                              |
| ----------------- | ---------------------------------------------------- |
| `git fetch`       | Descarga información del remoto sin integrar cambios |
| `git fetch --all` | Actualiza información de todos los remotos           |
| `git pull`        | Descarga cambios y los integra en la rama actual     |

### Ejemplo

```bash
git fetch --all
```

Después puedes revisar:

```bash
git branch -r
```

Y decidir qué hacer con los cambios.

En cambio:

```bash
git pull
```

realiza la descarga y posteriormente intenta integrar los cambios en la rama actual.

---

# 7. Estrategia profesional de ramas

Una estructura habitual puede ser:

```text
main
 │
develop
 │
 ├── feature/login
 ├── feature/usuarios
 ├── feature/mascotas
 └── feature/citas
```

## Main

Contiene código estable o preparado para producción.

## Develop

Puede utilizarse como rama de integración para nuevas funcionalidades, dependiendo de la estrategia del equipo.

## Feature

Contiene desarrollos específicos.

Ejemplos:

```text
feature/login
feature/usuarios
feature/mascotas
feature/citas
```

---

# 8. Merge y conflictos

## Unir una rama

Por ejemplo, estando en `develop`:

```bash
git switch develop
```

Después:

```bash
git merge feature/login
```

Esto integra los cambios de:

```text
feature/login
```

en:

```text
develop
```

---

# Conflictos

Cuando dos desarrolladores modifican partes incompatibles del mismo código puede producirse un conflicto.

Git puede mostrar:

```text
<<<<<<< HEAD
Mi código
=======
Código del compañero
>>>>>>> feature/login
```

Proceso para resolverlo:

1. Revisar el conflicto.
2. Determinar qué código debe conservarse.
3. Modificar el archivo.
4. Eliminar los marcadores de conflicto.
5. Guardar el archivo.
6. Ejecutar `git add`.
7. Crear el commit correspondiente.

Ejemplo:

```bash
git add archivo.py
```

Después:

```bash
git commit -m "fix: resolver conflicto en autenticación"
```

---

# 9. Trabajo con GitHub

## Conectar repositorio remoto

```bash
git remote add origin URL
```

Ejemplo:

```bash
git remote add origin https://github.com/usuario/proyecto.git
```

---

## Ver repositorios remotos

```bash
git remote -v
```

Ejemplo:

```text
origin  https://github.com/usuario/proyecto.git (fetch)
origin  https://github.com/usuario/proyecto.git (push)
```

---

# Subir código

Primera vez:

```bash
git push -u origin main
```

Después:

```bash
git push
```

Si estás trabajando en una rama:

```bash
git push -u origin feature/login
```

Después de configurar el seguimiento:

```bash
git push
```

---

# Descargar cambios

```bash
git pull
```

También puedes especificar:

```bash
git pull origin main
```

---

# Obtener información sin integrar

```bash
git fetch
```

Todos los remotos:

```bash
git fetch --all
```

Después puedes revisar:

```bash
git branch -r
```

---

# 10. Pull Request

Un **Pull Request (PR)** permite solicitar que los cambios realizados en una rama sean revisados antes de integrarse a otra rama.

Flujo:

```text
Crear rama
     ↓
Desarrollar
     ↓
git add
     ↓
git commit
     ↓
git push
     ↓
Pull Request
     ↓
Code Review
     ↓
Aprobación
     ↓
Merge
```

Beneficios:

* Revisión de código.
* Control de calidad.
* Detección de errores.
* Trabajo colaborativo.
* Historial de cambios.
* Integración controlada.

---

# 11. GitHub Issues

Los Issues permiten organizar tareas y problemas.

Usos:

* Reportar errores.
* Crear funcionalidades.
* Registrar tareas.
* Organizar trabajo.

Ejemplo:

```text
Issue #15

Título:
Crear módulo de autenticación

Estado:
En desarrollo
```

Una rama puede relacionarse con un Issue:

```text
Issue #15
     ↓
feature/autenticacion
```

---

# 12. Archivo `.gitignore`

El `.gitignore` evita que determinados archivos sean incluidos en el repositorio.

## Python

```gitignore
.env
venv/
__pycache__/
*.pyc
```

## Node.js

```gitignore
node_modules/
.env
```

Nunca subir:

* Contraseñas.
* Tokens.
* Claves privadas.
* Variables de entorno reales.
* Datos sensibles.
* Archivos temporales.
* Dependencias que se puedan instalar mediante un gestor de paquetes.

---

# 13. README profesional

Todo proyecto debería tener una documentación básica.

Ejemplo:

```text
PROYECTO/
│
├── README.md
├── .gitignore
├── src/
├── requirements.txt
└── documentación/
```

El `README.md` debería incluir:

* Nombre del proyecto.
* Descripción.
* Objetivo.
* Tecnologías utilizadas.
* Requisitos.
* Instalación.
* Configuración.
* Ejecución.
* Estructura del proyecto.
* Ejemplos de uso.
* Autores.
* Licencia, cuando corresponda.

---

# 14. Historial y recuperación

## Ver historial

```bash
git log
```

Vista resumida:

```bash
git log --oneline
```

Más información visual:

```bash
git log --oneline --graph --all
```

---

# Comparar cambios

```bash
git diff
```

Comparar cambios preparados para commit:

```bash
git diff --staged
```

Comparar ramas:

```bash
git diff main..develop
```

---

# 15. Deshacer cambios

## Quitar un archivo del staging

```bash
git restore --staged archivo
```

El archivo **no se elimina**, simplemente deja de estar preparado para el commit.

---

## Descartar cambios de un archivo

```bash
git restore archivo
```

⚠️ Esto puede eliminar cambios locales que todavía no hayan sido guardados en un commit.

---

## Modificar el último commit

```bash
git commit --amend
```

Puede utilizarse para corregir el mensaje o agregar cambios al último commit.

---

# 16. Buenas prácticas profesionales

Un Junior competitivo debe:

* Crear ramas por funcionalidad.
* Evitar trabajar directamente sobre `main`.
* Realizar commits pequeños y claros.
* Utilizar mensajes descriptivos.
* Revisar `git status` frecuentemente.
* Revisar los cambios antes de hacer commit.
* Mantener actualizado el repositorio local.
* Utilizar Pull Requests cuando el flujo del equipo lo requiera.
* Resolver conflictos correctamente.
* Documentar los proyectos.
* Utilizar `.gitignore`.
* Nunca subir credenciales.
* No hacer `git push --force` sin conocer sus consecuencias.
* Mantener ramas organizadas.

---

# 17. Git avanzado

## Git Stash

Permite guardar temporalmente cambios que todavía no quieres convertir en commit.

Guardar:

```bash
git stash
```

Ver los cambios guardados:

```bash
git stash list
```

Recuperar:

```bash
git stash pop
```

---

# Git Rebase

Permite reorganizar commits y actualizar una rama tomando como base otra.

Ejemplo:

```bash
git switch feature/login
```

```bash
git rebase main
```

Se debe utilizar con cuidado cuando la rama ya ha sido compartida con otros desarrolladores.

---

# Git Tags

Permiten identificar versiones específicas.

Crear:

```bash
git tag v1.0.0
```

Ver tags:

```bash
git tag
```

Subir un tag:

```bash
git push origin v1.0.0
```

También se puede utilizar:

```bash
git push origin --tags
```

---

# Git Reset

Permite mover el estado de la rama a otro commit.

Ejemplo:

```bash
git reset --soft HEAD~1
```

Existen diferentes modos:

```text
--soft
--mixed
--hard
```

⚠️ `--hard` puede eliminar cambios locales. Debe utilizarse con cuidado.

---

# Git Remote

Ver remotos:

```bash
git remote -v
```

Agregar remoto:

```bash
git remote add origin URL
```

Cambiar la URL:

```bash
git remote set-url origin URL
```

---

# 18. Aplicación en proyectos ADSO

## Backend FastAPI

Ejemplo:

```text
backend/
│
├── app/
│   ├── routers/
│   ├── models/
│   ├── schemas/
│   └── main.py
│
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

---

# Frontend

```text
frontend/
│
├── src/
├── public/
├── package.json
├── .gitignore
└── README.md
```

No se debe subir:

```text
node_modules/
.env
```

---

# Bases de datos

No se deberían subir datos reales o sensibles:

```text
datos_clientes.sql
```

Puede ser apropiado subir scripts de estructura y datos de prueba, según el proyecto:

```text
schema.sql
seed.sql
```

Por ejemplo:

```text
database/
├── schema.sql
└── seed.sql
```

---

# Ejemplo aplicado a Huellitas Saludables

Una estructura profesional podría ser:

```text
HUELLITAS_SALUDABLES/
│
├── backend/
│   ├── src/
│   ├── requirements.txt
│   ├── .env.example
│   └── README.md
│
├── frontend/
│   ├── src/
│   ├── package.json
│   └── README.md
│
├── database/
│   ├── schema.sql
│   └── seed.sql
│
├── .gitignore
└── README.md
```

Posibles ramas:

```text
main
develop
│
├── feature/autenticacion
├── feature/usuarios
├── feature/mascotas
├── feature/citas
└── feature/historia-clinica
```

---

# 19. Evaluación del nivel Junior

## 🟢 Junior básico

Debe manejar:

```text
git init
git clone
git status
git add
git commit
git push
git pull
git branch
```

---

# 🟡 Junior competitivo

Debe dominar:

```text
git init
git clone
git status
git add
git commit
git push
git pull

git branch
git branch -r
git branch -a

git switch
git checkout

git fetch
git fetch --all

git merge
git diff

Pull Requests
Issues
README
.gitignore

Resolución de conflictos
Trabajo colaborativo
Buenas prácticas
```

Además, debe saber **descargar una rama remota y convertirla en una rama local**:

```bash
git fetch --all
git branch -r
git switch --track origin/nombre-rama
```

O mediante la forma clásica:

```bash
git checkout -b nombre-rama origin/nombre-rama
```

---

# 🔴 Junior sobresaliente

Además debe conocer:

```text
Git Flow
Rebase
Stash
Tags
Reset
SSH
GitHub Actions básico
Code Review
Convenciones de commits
Protección de ramas
```

También debe comprender cuándo **no** utilizar determinadas operaciones, especialmente:

```bash
git reset --hard
git push --force
```

---

# 20. Flujo profesional completo

Este es uno de los flujos que un Junior ADSO debería poder ejecutar sin depender constantemente de otra persona.

## 1. Clonar el proyecto

```bash
git clone URL
```

## 2. Entrar al proyecto

```bash
cd proyecto
```

## 3. Revisar estado

```bash
git status
```

## 4. Actualizar información remota

```bash
git fetch --all
```

## 5. Ver ramas disponibles

```bash
git branch -a
```

o:

```bash
git branch -r
```

## 6. Descargar una rama remota a local

```bash
git switch --track origin/develop
```

O:

```bash
git checkout -b develop origin/develop
```

## 7. Crear una rama para la funcionalidad

```bash
git switch -c feature/citas
```

## 8. Desarrollar

Modificar el código y realizar pruebas.

## 9. Revisar cambios

```bash
git status
```

```bash
git diff
```

## 10. Preparar cambios

```bash
git add .
```

## 11. Crear commit

```bash
git commit -m "feat: agregar gestión de citas"
```

## 12. Subir rama

```bash
git push -u origin feature/citas
```

## 13. Crear Pull Request

```text
feature/citas
       ↓
Pull Request
       ↓
Code Review
       ↓
Aprobación
       ↓
Merge
       ↓
develop
```

## 14. Actualizar nuevamente el repositorio local

Después de que otros desarrolladores hagan cambios:

```bash
git fetch --all
```

Revisar:

```bash
git branch -r
```

Y actualizar la rama correspondiente mediante `pull`, `merge` o `rebase`, según el flujo establecido por el equipo.

---

# 🎯 Flujo que debes dominar de memoria

```text
                    GITHUB
                       │
                       ↓
                git fetch --all
                       │
                       ↓
               git branch -r
                       │
                       ↓
           ¿Qué rama necesito?
                       │
                       ↓
       git switch --track origin/rama
                       │
                       ↓
                 RAMA LOCAL
                       │
                       ↓
                 Desarrollar
                       │
                       ↓
                  git status
                       │
                       ↓
                    git add
                       │
                       ↓
                   git commit
                       │
                       ↓
                    git push
                       │
                       ↓
                PULL REQUEST
                       │
                       ↓
                  CODE REVIEW
                       │
                       ↓
                     MERGE
```

---

# ✅ Conclusión

Un Tecnólogo ADSO con perfil **Junior Competitivo** no debe limitarse a conocer `git add`, `git commit` y `git push`.

Debe comprender el ciclo completo:

```text
Repositorio local
       ↕
Ramas locales
       ↕
Ramas remotas
       ↕
GitHub
       ↕
Pull Requests
       ↕
Code Review
       ↕
Merge
```

Especialmente debe saber diferenciar:

```bash
git branch
```

**Ramas locales**

```bash
git branch -r
```

**Ramas remotas**

```bash
git branch -a
```

**Todas las ramas**

```bash
git fetch --all
```

**Actualizar información de los remotos**

```bash
git switch --track origin/rama
```

**Crear una rama local siguiendo una rama remota**

y la forma clásica:

```bash
git checkout -b rama origin/rama
```

**Crear explícitamente una rama local basada en una rama remota.**

> **Git no es solamente guardar código; es una herramienta para controlar versiones, colaborar, revisar cambios, mantener trazabilidad y construir software de manera profesional.**
