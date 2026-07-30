# 🚀 Git y GitHub — Guía Profesional para Desarrolladores ADSO

## 📚 Nivel: Junior Sobresaliente

---

## 📌 Descripción

Esta documentación contiene los conocimientos profesionales de **Git y GitHub** que debe dominar un desarrollador con perfil **Tecnólogo en Análisis y Desarrollo de Software (ADSO) Junior Sobresaliente**.

El objetivo es comprender Git no solamente como una herramienta para guardar código, sino como un sistema profesional para:

- Controlar versiones.
- Trabajar en equipos de desarrollo.
- Gestionar cambios de software.
- Mantener calidad del código.
- Automatizar procesos.
- Aplicar buenas prácticas utilizadas en la industria.

---

# 🎯 Objetivos de aprendizaje

Al finalizar esta guía se debe tener la capacidad de:

✅ Administrar repositorios profesionales.  
✅ Trabajar con ramas y estrategias de desarrollo.  
✅ Participar en equipos mediante Pull Requests.  
✅ Resolver conflictos de código.  
✅ Mantener un historial limpio.  
✅ Aplicar estándares profesionales.  
✅ Automatizar procesos básicos mediante GitHub Actions.

---

# 1. Fundamentos avanzados de Git

## ¿Qué es Git?

Git es un sistema de control de versiones distribuido que permite gestionar el ciclo de vida del código fuente.

Sus principales funciones son:

- Registrar cambios.
- Crear puntos de restauración.
- Gestionar versiones.
- Trabajar paralelamente mediante ramas.
- Facilitar colaboración entre desarrolladores.

---

# Git como sistema distribuido

Git trabaja con tres zonas principales:

```
Working Directory
        |
        |
        ↓
Staging Area
        |
        |
        ↓
Repository
```

## Working Directory

Zona donde modificamos archivos.

Ejemplo:

```
app.py
usuarios.py
database.py
```

---

## Staging Area

Zona donde seleccionamos qué cambios serán guardados.

Comando:

```bash
git add .
```

---

## Repository

Lugar donde Git guarda las versiones.

Comando:

```bash
git commit
```

---

# 2. Git vs GitHub

| Git | GitHub |
|-|-|
| Control de versiones | Plataforma colaborativa |
| Funciona localmente | Servicio remoto |
| Maneja commits | Maneja repositorios |
| Maneja ramas | Maneja Pull Requests |

---

# 3. Configuración profesional

## Identidad

```bash
git config --global user.name "Nombre"
```

```bash
git config --global user.email "correo"
```

---

## Configuración segura

Un desarrollador profesional debe conocer:

- Tokens personales.
- SSH Keys.
- Autenticación segura.
- Gestión de credenciales.

---

# 4. Gestión profesional de repositorios

## Crear repositorio

```bash
git init
```

---

## Clonar proyecto

```bash
git clone URL
```

---

## Repositorios remotos

Agregar remoto:

```bash
git remote add origin URL
```

Consultar:

```bash
git remote -v
```

---

# 5. Flujo profesional de commits

Un commit representa un cambio lógico dentro del proyecto.

Ejemplo:

Incorrecto:

```
Cambios varios
```

Correcto:

```
feat: agregar autenticación JWT
fix: corregir conexión con base de datos
docs: actualizar documentación
```

---

# Conventional Commits

Formato:

```
tipo: descripción
```

Tipos:

| Tipo | Uso |
|-|-|
| feat | Nueva funcionalidad |
| fix | Corrección |
| docs | Documentación |
| test | Pruebas |
| refactor | Mejoras internas |
| chore | Configuración |

---

# 6. Estrategia profesional de ramas

Las ramas permiten desarrollar funcionalidades sin afectar la versión estable.

Modelo:

```
main

 |

develop

 |

├── feature/login

├── feature/pagos

├── fix/error-api

└── hotfix/servidor
```

---

# Tipos de ramas

## Main

Código estable.

Uso:

- Producción.
- Versiones finales.

---

## Develop

Integración de nuevas funcionalidades.

---

## Feature

Desarrollo de nuevas características.

Ejemplo:

```bash
git switch -c feature/login
```

---

## Fix

Corrección de errores.

Ejemplo:

```bash
git switch -c fix/error-login
```

---

## Hotfix

Correcciones urgentes en producción.

---

# 7. Git Flow

Git Flow es una estrategia organizada de ramas.

Estructura:

```
main

develop

feature

release

hotfix
```

Permite:

- Separar desarrollo y producción.
- Organizar equipos grandes.
- Mantener estabilidad.

---

# 8. Merge y resolución de conflictos

Un merge une cambios:

```bash
git merge feature/login
```

---

Cuando existen conflictos:

```
<<<<<<< HEAD

Código actual

=======

Código nuevo

>>>>>>> rama
```

Proceso profesional:

1. Analizar cambios.
2. Elegir solución.
3. Probar aplicación.
4. Crear commit.

---

# 9. Git Rebase

Rebase permite reorganizar historial.

Ejemplo:

Antes:

```
A---B---C
     \
      D---E
```

Después:

```
A---B---C---D---E
```

Comando:

```bash
git rebase main
```

Uso profesional:

Antes de crear un Pull Request.

---

# 10. Git Stash

Permite guardar cambios temporalmente.

Ejemplo:

Estoy trabajando:

```
Código incompleto
```

Necesito cambiar de tarea.

Guardar:

```bash
git stash
```

Recuperar:

```bash
git stash pop
```

---

# 11. Versionamiento con Tags

Los tags identifican versiones.

Ejemplo:

```bash
git tag v1.0.0
```

Versiones:

```
v1.0.0
Primera versión estable

v1.1.0
Nueva funcionalidad

v2.0.0
Cambio importante
```

---

# 12. Seguridad con SSH

SSH permite conexión segura con GitHub.

Ejemplo:

HTTPS:

```
https://github.com/user/proyecto
```

SSH:

```
git@github.com:user/proyecto.git
```

Ventajas:

- Mayor seguridad.
- No ingresar credenciales constantemente.
- Autenticación mediante claves.

---

# 13. Pull Request profesional

Un Pull Request debe incluir:

## Título

Ejemplo:

```
Agregar módulo de autenticación
```

## Descripción

Debe explicar:

- Qué se hizo.
- Por qué se hizo.
- Cómo probarlo.

Ejemplo:

```
Cambios:

- Modelo usuario creado.
- Endpoint login agregado.
- Validaciones implementadas.

Pruebas:

- Login correcto.
- Usuario inválido.
```

---

# 14. Code Review

Proceso donde otros desarrolladores revisan código.

Se analiza:

- Calidad.
- Seguridad.
- Legibilidad.
- Arquitectura.
- Errores.

---

# 15. GitHub Issues

Permiten gestionar trabajo.

Usos:

- Bugs.
- Nuevas funcionalidades.
- Mejoras.

Ejemplo:

```
Issue #25

Crear autenticación JWT

Estado:
En desarrollo
```

---

# 16. .gitignore profesional

Evita subir información privada.

Ejemplo:

Python:

```
.env
venv/
__pycache__/
*.pyc
```

Node:

```
node_modules/
.env
```

Nunca subir:

❌ Contraseñas  
❌ Tokens  
❌ Llaves privadas  
❌ Datos reales  

---

# 17. GitHub Actions (CI/CD básico)

GitHub Actions permite automatizar procesos.

Ejemplo:

```
git push

↓

GitHub Actions

↓

Instalar dependencias

↓

Ejecutar pruebas

↓

Validar código
```

Ejemplo:

```yaml
name: Tests

on:
 push:

jobs:

 test:
  runs-on: ubuntu-latest

  steps:

  - uses: actions/checkout@v4

  - name: Ejecutar pruebas
    run: pytest
```

---

# 18. Organización profesional de proyectos

Ejemplo Backend:

```
backend/

├── app/

├── tests/

├── requirements.txt

├── .env.example

├── README.md

└── .gitignore
```

---

# 19. Buenas prácticas de un Junior Sobresaliente

Un desarrollador profesional:

✅ Usa ramas correctamente.  
✅ Mantiene commits pequeños.  
✅ Documenta proyectos.  
✅ Revisa código antes de subirlo.  
✅ Usa Pull Requests.  
✅ Protege información sensible.  
✅ Entiende flujos de trabajo.  
✅ Automatiza procesos repetitivos.  

---

# Evaluación del nivel

## Junior Básico

Conoce:

- init
- add
- commit
- push
- pull
- branch

---

## Junior Competitivo

Domina:

- Ramas.
- Merge.
- Conflictos.
- Pull Requests.
- Issues.
- Buenas prácticas.

---

## Junior Sobresaliente

Además domina:

✅ Git Flow  
✅ Rebase  
✅ Stash  
✅ Tags  
✅ SSH  
✅ Conventional Commits  
✅ Code Review  
✅ GitHub Actions básico  
✅ Organización profesional de repositorios  

---

# Conclusión

Dominar Git y GitHub a nivel Junior Sobresaliente significa entender que el desarrollo profesional no consiste únicamente en escribir código, sino en saber **gestionarlo, colaborar, mantener calidad y trabajar bajo procesos utilizados en la industria del software**.