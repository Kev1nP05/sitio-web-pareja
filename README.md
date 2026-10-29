# Sitio Web Pareja

Sitio web estático desarrollado únicamente con **HTML** para la Práctica N° 2 – *Versionamiento de Aplicaciones* de la asignatura **Fundamentos de Sistemas Web** (NRC 32802), Universidad de las Fuerzas Armadas ESPE, Sede Santo Domingo.

## Objetivo

Aplicar técnicas de versionamiento con Git y GitHub para gestionar los cambios del código fuente, trabajar de forma colaborativa mediante ramas y mantener un historial organizado del proyecto.

## Integrantes

| Integrante | Usuario GitHub | Rama | Funcionalidad |
|---|---|---|---|
| Kevin Párraga | @Kevi1nP05 | `feature-kevin` | Página principal, navegación y formulario de pasatiempos |
| Manfred | @mmarmijos3 | `feature-manfred` | Página "Sobre nosotros" (tabla, listas, glosario y multimedia) |

## Funcionalidades implementadas

- Página de inicio con encabezado, menú de navegación, imagen y descripción del flujo de trabajo.
- Navegación entre las tres páginas del sitio.
- Página **Sobre nosotros** con tabla de integrantes, lista de herramientas, lista de definiciones y mapa embebido.
- Página **Pasatiempos** con lista, imagen y formulario validado (`required`, `type="email"`, `select`, `radio`, `checkbox`, `textarea`).

## Estructura de archivos

```
sitio-web-pareja/
├── index.html
├── sobre-nosotros.html
├── pasatiempos.html
├── README.md
└── img/
    ├── banner.svg
    ├── pasatiempos.svg
    └── equipo.svg
```

## Estructura de ramas

| Rama | Propósito |
|---|---|
| `main` | Producción: versión final aprobada (protegida) |
| `pruebas` | Validación de funcionalidades antes de producción |
| `desarrollo` | Integración de las ramas de funcionalidad |
| `feature-kevin` / `feature-manfred` | Trabajo individual de cada integrante |

Flujo: `feature-*` → `desarrollo` → `pruebas` → `main`

## Comandos utilizados

```bash
git init
git branch -M main
git add .
git commit -m "mensaje"
git remote add origin https://github.com/Kevi1nP05/sitio-web-pareja.git
git push -u origin main
git switch -c <rama>
git push -u origin <rama>
git pull origin <rama>
git merge <rama>
git branch -a
git status
git log --oneline --graph --all
git remote -v
```

## Cómo visualizar el sitio

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/Kevi1nP05/sitio-web-pareja.git
   cd sitio-web-pareja
   ```
2. Abrir `index.html` con doble clic en cualquier navegador, o usar la extensión **Live Server** de Visual Studio Code (clic derecho sobre `index.html` → *Open with Live Server*).

## Protección de la rama `main`

Configurada en **Settings → Branches → Add branch protection rule** (o *Rules → Rulesets*):

- Branch name pattern: `main`
- ✅ Require a pull request before merging
- ✅ Require approvals: **1**
- ✅ Dismiss stale pull request approvals when new commits are pushed
- ✅ Do not allow bypassing the above settings

Verificación: un `git push origin main` directo es rechazado por GitHub; los cambios solo ingresan mediante un Pull Request aprobado por el otro integrante.
