# 🚀 Git y GitHub para un Tecnólogo ADSO Junior Competitivo

## 📌 Descripción

Este documento contiene los conocimientos fundamentales y profesionales que debe manejar un **Tecnólogo en Análisis y Desarrollo de Software (ADSO) con perfil Junior Competitivo** en el uso de **Git y GitHub**.

El objetivo no es memorizar comandos, sino comprender el flujo de trabajo profesional utilizado por equipos reales de desarrollo de software.

Un desarrollador Junior competitivo debe ser capaz de:

- Gestionar versiones del código.
- Trabajar con ramas.
- Colaborar con otros desarrolladores.
- Mantener repositorios organizados.
- Aplicar buenas prácticas de desarrollo.

---

# 📚 Índice

1. Fundamentos de Git y GitHub
2. Configuración inicial
3. Creación y administración de repositorios
4. Flujo profesional de trabajo
5. Manejo de ramas
6. Estrategia profesional de ramas
7. Merge y conflictos
8. Trabajo con GitHub
9. Pull Requests
10. Issues
11. Archivo .gitignore
12. README profesional
13. Historial y recuperación
14. Deshacer cambios
15. Buenas prácticas
16. Git avanzado
17. Aplicación en proyectos ADSO
18. Evaluación del nivel Junior

---

# 1. Fundamentos de Git y GitHub

## ¿Qué es Git?

Git es un sistema de control de versiones distribuido que permite:

- Registrar cambios realizados en el código.
- Recuperar versiones anteriores.
- Trabajar en equipo.
- Mantener historial del proyecto.
- Comparar modificaciones.

Ejemplo de definición profesional:

> Git permite gestionar el historial del código fuente mediante versiones y ramas, facilitando la colaboración entre desarrolladores.

---

# Git vs GitHub

| Git | GitHub |
|---|---|
| Sistema de control de versiones | Plataforma de alojamiento de código |
| Funciona localmente | Servicio en la nube |
| Maneja commits y ramas | Maneja repositorios remotos, PR e Issues |
| No necesita internet | Facilita colaboración |

Ejemplo:

```
Git = Controla versiones del código

GitHub = Lugar donde compartes y colaboras
```

---

# 2. Configuración inicial de Git

## Configurar usuario

```bash
git config --global user.name "Nombre"
```

```bash
git config --global user.email "correo"
```

Consultar configuración:

```bash
git config --list
```

Eliminar configuración:

```bash
git config --global --unset user.name
```

```bash
git config --global --unset user.email
```

También se debe conocer:

- Tokens de GitHub.
- SSH Keys.
- Autenticación segura.

---

# 3. Crear y administrar repositorios

## Inicializar repositorio

```bash
git init
```

Convierte una carpeta normal en un repositorio Git.

---

## Clonar repositorio

```bash
git clone URL
```

Ejemplo:

```bash
git clone https://github.com/usuario/proyecto.git
```

Esto:

- Descarga el código.
- Descarga historial.
- Crea conexión con GitHub.

---

# 4. Flujo profesional de trabajo

Flujo básico:

```
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

- Archivos nuevos.
- Archivos modificados.
- Archivos preparados.

---

## Agregar cambios

Todos:

```bash
git add .
```

Archivo específico:

```bash
git add archivo.py
```

---

## Crear commits profesionales

Ejemplo:

```bash
git commit -m "feat: crear endpoint usuarios"
```

Tipos recomendados:

```
feat     Nueva funcionalidad

fix      Corrección de errores

docs     Documentación

test     Pruebas

refactor Mejoras internas
```

Ejemplos:

```bash
git commit -m "feat: agregar login"
```

```bash
git commit -m "fix: corregir conexión BD"
```

---

# 5. Manejo de ramas

Las ramas permiten desarrollar funcionalidades sin afectar la versión estable.

## Ver ramas

```bash
git branch
```

---

## Crear rama

```bash
git branch feature/login
```

---

## Crear y cambiar rama

```bash
git switch -c feature/login
```

---

## Cambiar rama

```bash
git switch main
```

---

## Eliminar rama

```bash
git branch -d nombre-rama
```

---

# 6. Estrategia profesional de ramas

Ejemplo:

```
main

 |

develop

 |

├── feature/login

├── feature/usuarios

└── feature/pagos
```

## Main

Contiene código estable.

## Develop

Integra nuevas funcionalidades.

## Feature

Contiene desarrollos específicos.

---

# 7. Merge y conflictos

Unir cambios:

```bash
git merge feature/login
```

Cuando dos personas modifican la misma línea puede aparecer:

```
<<<<<<< HEAD

Mi código

=======

Código compañero

>>>>>>> feature
```

Proceso:

1. Revisar diferencias.
2. Elegir código correcto.
3. Guardar cambios.
4. Crear commit.

---

# 8. Trabajo con GitHub

## Conectar repositorio remoto

```bash
git remote add origin URL
```

Ver conexión:

```bash
git remote -v
```

---

## Subir código

Primera vez:

```bash
git push -u origin main
```

Después:

```bash
git push
```

---

## Descargar cambios

```bash
git pull
```

---

## Obtener información sin mezclar

```bash
git fetch
```

Diferencia:

| Pull | Fetch |
|-|-|
| Descarga y mezcla cambios | Solo descarga información |

---

# 9. Pull Request

Un Pull Request permite solicitar la integración de código.

Flujo:

```
Crear rama

↓

Desarrollar

↓

Commit

↓

Push

↓

Pull Request

↓

Revisión

↓

Merge
```

Beneficios:

- Revisión de código.
- Control de calidad.
- Trabajo colaborativo.

---

# 10. GitHub Issues

Permiten organizar tareas:

Usos:

- Reportar errores.
- Crear funcionalidades.
- Organizar trabajo.

Ejemplo:

```
Issue #15

Crear módulo autenticación

Estado:
En desarrollo
```

---

# 11. Archivo .gitignore

Evita subir archivos innecesarios.

Ejemplo Python:

```
.env
venv/
__pycache__/
*.pyc
```

Ejemplo Node:

```
node_modules/
.env
```

Nunca subir:

- Contraseñas.
- Tokens.
- Claves privadas.
- Datos sensibles.

---

# 12. README profesional

Todo proyecto debe tener:

```
Proyecto

├── README.md
├── .gitignore
├── src/
├── requirements.txt
└── documentación
```

Debe incluir:

- Descripción.
- Tecnologías.
- Instalación.
- Ejecución.
- Ejemplos.

---

# 13. Historial y recuperación

Ver historial:

```bash
git log
```

Vista resumida:

```bash
git log --oneline
```

Comparar cambios:

```bash
git diff
```

---

# 14. Deshacer cambios

Quitar del staging:

```bash
git restore --staged archivo
```

Eliminar cambios:

```bash
git restore archivo
```

Modificar último commit:

```bash
git commit --amend
```

---

# 15. Buenas prácticas profesionales

Un Junior competitivo debe:

✅ Crear ramas por funcionalidad.

✅ Realizar commits pequeños.

✅ Escribir mensajes claros.

✅ Evitar trabajar directamente en main.

✅ Revisar código antes de hacer push.

✅ Documentar proyectos.

✅ Mantener repositorios organizados.

---

# 16. Git avanzado

## Git Stash

Guardar cambios temporalmente:

```bash
git stash
```

Recuperar:

```bash
git stash pop
```

---

## Git Rebase

Reorganizar historial:

```bash
git rebase main
```

---

## Git Tags

Crear versiones:

```bash
git tag v1.0.0
```

---

# 17. Aplicación en proyectos ADSO

## Backend FastAPI

Ejemplo:

```
api/

├── app/

├── requirements.txt

├── .env.example

└── README.md
```

---

## Frontend

```
frontend/

├── src/

├── package.json

├── README.md

└── .gitignore
```

---

## Bases de datos

No subir:

```
datos_clientes.sql
```

Sí subir:

```
estructura_bd.sql
```

---

# 🎯 Evaluación de nivel

## Junior básico

Debe manejar:

- init
- clone
- add
- commit
- push
- pull
- branch


## Junior competitivo

Debe dominar:

- Todo lo anterior.
- Ramas profesionales.
- Merge.
- Resolución de conflictos.
- Pull Requests.
- Issues.
- README.
- .gitignore.
- Trabajo colaborativo.
- Buenas prácticas.


## Junior sobresaliente

Además:

- Git Flow.
- Rebase.
- Stash.
- Tags.
- SSH.
- GitHub Actions básico.

---

# ✅ Conclusión

Un Tecnólogo ADSO que domina estos conceptos tiene la capacidad de integrarse en un equipo profesional de desarrollo, trabajar con metodologías reales y mantener proyectos organizados utilizando herramientas estándar de la industria.

**Git no es solamente guardar código; es una herramienta para colaborar, controlar calidad y construir software profesional.**