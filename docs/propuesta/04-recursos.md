# Fase 4 · Recursos · Apañao

## Introducción

En esta fase se definen los recursos necesarios para el desarrollo de Apañao. Para ello, se especificarán las personas que integran el equipo, junto a sus roles y responsabilidades por módulo. Además, se detallarán los recursos tecnológicos, las herramientas de desarrollo, la estructura de ramas, la organización de carpetas y la metodología de comunicación que se empleará a lo largo del proyecto.

## 1. Las personas

### Roles técnicos

| Persona | Rol | De qué responde |
| --- | --- | --- |
| Aarón | DataBase Manager | Gestión y modelado de la base de datos MongoDB, así como el correcto uso de las bases de datos relacionales y no relacionales. |
| Antonio | Backend Leader | Coordinación y desarrollo de la lógica del servidor y la API REST (Node.js y Express). Cuenta con apoyo de África. |
| Manu | QA y Despliegue | Realización de pruebas, detección de errores, verificación de requisitos y supervisión del despliegue. Cuenta con apoyo de Aarón. |
| África | Frontend | Desarrollo de la interfaz de usuario y diseño (React). Cuenta con apoyo de Pablo Sanz (Proyecto Intermodular). |

### Responsables por módulo

| Módulo | Requisitos (RF) | Responsable | Apoyo |
| --- | --- | --- | --- |
| Autenticación | RF-01 (Registro), RF-02 (Inicio de sesión) y RF-03 (Cierre de sesión) | Antonio (Backend) | África (Frontend) |
| Perfil y Alérgenos | RF-04 (Configuración de perfil), RF-05 (Gestión de alérgenos) | Antonio (Backend) | África (Frontend) |
| Despensa | RF-06 (Alta de ingredientes), RF-07 (Actualización), RF-08 (Baja) y RF-09 (Consulta) | Aarón (DataBase Manager) | Antonio (Backend) |
| Menús y Recetas | RF-10 (Planificación de menús), RF-11 (Sugerencia de recetas), RF-18 (Menús semanales) y RF-19 (Descuento de tupper) | Antonio (Backend) | África (Frontend) |
| Lista de la compra | RF-09b (Sincronización con la compra), RF-10b (Consulta y edición) y RF-11b (Traspaso a despensa) | Antonio (Backend) | Manu (QA) |
| Tuppers | RF-15 (Registro de tuppers), RF-16 (Alertas de descongelación), RF-17 (Consulta de tuppers) y RF-19 (Descuento de tupper) | Aarón (DataBase Manager) | Antonio (Backend) |
| Alertas y Favoritos | RF-12 (Alertas de caducidad), RF-08b (Gestión de favoritos) | Aarón (DataBase Manager) | Manu (QA) |

### Comunicación (enlace al contrato)

La comunicación del equipo se regirá por lo establecido en el [Contrato del equipo](../CONTRATO.md).

## 2. La tecnología

### Stack, servicios y APIs (enlace a la fase 2)

Para el desarrollo de esta aplicación se utilizará el stack MERN, junto a los servicios y APIs que se han analizado en la [Fase 2 - Viabilidad técnica](./02-viabilidad-tecnica.md). 

- **Stack:** MERN ([MongoDB](./02-viabilidad-tecnica.md#3-base-de-datos-mongodb), [Express.js y Node.js](./02-viabilidad-tecnica.md#2-backend-nodejs--express) y [React](./02-viabilidad-tecnica.md#1-frontend-react)) 
- **Autenticación:** Sistema propio basado en correo electrónico, contraseña y [JWT](./02-viabilidad-tecnica.md#autenticación-y-gestión-del-sistema-de-cuentas).
- **Base de datos:** [MongoDB Atlas](./02-viabilidad-tecnica.md#3-base-de-datos-mongodb) (Free Tier).
- **Servicios de despliegue:** [Vercel](./02-viabilidad-tecnica.md#1-frontend-react-1) para el frontend y [Render](./02-viabilidad-tecnica.md#2-backend-nodejs--express-api) (o Railway/Koyeb) para el backend ([infraestructura cloud](./02-viabilidad-tecnica.md#4-infraestructura-y-despliegue-cloud-stack-mern)).
- **APIs externas:** Se hará uso de las APIs de supermercados necesarias para el MVP, priorizando aquellas con disponibilidad para el desarrollo (contempladas en [la mitigación del riesgo 3](./02-viabilidad-tecnica.md#riesgo-3-falta-de-información)). Para la generación de recetas, se empleará un [modelo híbrido](./02-viabilidad-tecnica.md#riesgo-4-recetas) (catálogo propio en base de datos, con apoyo puntual de IA).

Para más detalles sobre la arquitectura, los endpoints y las colecciones, se puede consultar el documento completo: [02-viabilidad-tecnica.md](./02-viabilidad-tecnica.md).

### Herramientas de desarrollo

| Para qué | Herramienta | Notas |
| --- | --- | --- |
| Editor de código | [Visual Studio Code (VSCode)](https://code.visualstudio.com/) | Extensiones recomendadas: ESLint, Prettier, MongoDB for VS Code y Tailwind CSS IntelliSense. |
| Entorno de ejecución | [Node.js (LTS)](https://nodejs.org/) | Se recomienda el uso de `.nvmrc` para estandarizar la versión entre el equipo. |
| Formateo de código | [Prettier](https://prettier.io/) | Mediante un `.prettierrc` común en la raíz y un `.prettierignore` para excluir `node_modules/`, `dist/` y archivos generados. |
| Calidad de código | [ESLint](https://eslint.org/) | Integrado con el editor y con los flujos de trabajo. |
| Gestión de estilos | [Tailwind CSS](https://tailwindcss.com/) e [Iconos Lucide](https://lucide.dev/) | Para el desarrollo del frontend de forma ágil y mobile-first. |
| Pruebas de API (manual) | [Postman](https://www.postman.com/) | Colección compartida para los endpoints (`/api/v1/...`), con guardado del token JWT para las rutas privadas. |
| Testing automatizado - Frontend | [Vitest](https://vitest.dev/) | Pruebas unitarias de componentes, hooks y utilidades. |
| Testing automatizado - Backend | [Jest](https://jestjs.io/) + [Supertest](https://github.com/ladjs/supertest) | Pruebas de integración de la API REST. |
| Control de versiones | [Git](https://git-scm.com/) y [GitHub](https://github.com/) | Para la gestión del repositorio, Pull Requests y revisión de código. |
| Gestión de tareas | [GitHub Projects](https://github.com/users/nenooodev/projects/4) | Tablero Kanban para la asignación y seguimiento de tareas. |

## 3. La gestión

### Tablero

Para la organización del trabajo, se utilizará un tablero Kanban en [GitHub Projects](https://github.com/users/nenooodev/projects/4). Cada tarea se asignará a un único integrante, siguiendo la regla de "rama por funcionalidad" y prohibiendo cambios directos sobre `main`.

### Ramas

Se seguirá la siguiente estrategia de ramas, acorde a lo establecido en el contrato del equipo:

- **`main`**: Rama estable. Solo recibirá cambios a través de Pull Requests revisados y aprobados.
- **`develop`**: Rama de integración. En ella se unirán las ramas de funcionalidad antes de su paso a `main`.
- **`feature/*`**: Ramas creadas para cada nueva funcionalidad (ej.: `feature/auth-login`, `feature/pantry-crud`, `feature/shopping-sync`). Estas ramas partirán de `develop` y, una vez finalizadas y validadas, se fusionarán a esta mediante un Pull Request.
- **`fix/*`**: Ramas para la corrección de errores detectados durante las pruebas o en despliegue.
- **`docs/*`**: Ramas para la actualización o creación de documentación.

### Estructura de carpetas

Dado que se utilizará el stack MERN, la estructura de carpetas prevista para el repositorio monorepo se alinea con la definida en los README del cliente y del servidor:

```text
apaniao/
├── .github/                  # Workflows, plantillas de PR e issues
├── client/                   # Aplicación frontend (React + Vite + Tailwind CSS)
│   ├── index.html            # Punto de entrada HTML de Vite
│   ├── package.json          # Dependencias y scripts
│   ├── vite.config.js        # Configuración de Vite
│   ├── tailwind.config.js    # Configuración de Tailwind CSS
│   ├── postcss.config.js     # Integración de PostCSS/Tailwind
│   ├── .env                  # Variables de entorno (no versionado)
│   └── src/
│       ├── main.jsx          # Punto de entrada de React
│       ├── App.jsx           # Componente raíz
│       ├── api/              # Instancia Axios y peticiones a la API
│       │   ├── axios.js
│       │   ├── auth.js
│       │   ├── pantry.js
│       │   ├── menus.js
│       │   └── shoppingList.js
│       ├── store/            # Estado global (Zustand/Context)
│       │   ├── authStore.js
│       │   ├── pantryStore.js
│       │   └── shoppingStore.js
│       ├── hooks/            # Hooks reutilizables
│       │   ├── useAuth.js
│       │   └── useQueries.js
│       ├── context/          # Contextos de React
│       │   └── AuthContext.jsx
│       ├── components/       # Componentes reutilizables
│       │   ├── layout/
│       │   ├── ui/
│       │   ├── Loader.jsx
│       │   └── ProtectedRoute.jsx
│       ├── features/         # Módulos por funcionalidad
│       │   ├── auth/
│       │   ├── profile/
│       │   ├── pantry/
│       │   ├── menus/
│       │   ├── recipes/
│       │   ├── shopping/
│       │   └── tuppers/
│       ├── pages/            # Páginas asociadas a rutas
│       │   ├── Home.jsx
│       │   ├── Login.jsx
│       │   ├── Register.jsx
│       │   ├── Profile.jsx
│       │   ├── Pantry.jsx
│       │   ├── MenuPlanner.jsx
│       │   ├── ShoppingList.jsx
│       │   └── NotFound.jsx
│       ├── routes/           # Definición centralizada de rutas
│       │   └── AppRoutes.jsx
│       ├── utils/            # Utilidades y helpers
│       │   ├── validators.js
│       │   └── constants.js
│       └── styles/
│           └── index.css
├── server/                   # Aplicación backend (Node.js + Express)
│   ├── package.json          # Dependencias y scripts
│   ├── .env                  # Variables de entorno (no versionado)
│   ├── .env.example          # Plantilla de variables de entorno
│   └── src/
│       ├── server.js         # Arranque del servidor
│       ├── app.js            # Configuración de Express
│       ├── config/           # Configuración
│       │   ├── db.js
│       │   └── env.js
│       ├── models/           # Modelos de Mongoose
│       │   ├── User.js
│       │   ├── Ingredient.js
│       │   ├── Recipe.js
│       │   ├── Menu.js
│       │   └── ShoppingList.js
│       ├── routes/           # Rutas de la API (/api/v1)
│       │   ├── index.js
│       │   ├── auth.routes.js
│       │   ├── user.routes.js
│       │   ├── pantry.routes.js
│       │   ├── menu.routes.js
│       │   └── shopping.routes.js
│       ├── controllers/      # Controladores
│       │   ├── auth.controller.js
│       │   ├── user.controller.js
│       │   ├── pantry.controller.js
│       │   ├── menu.controller.js
│       │   └── shopping.controller.js
│       ├── services/         # Lógica de negocio
│       │   ├── auth.service.js
│       │   ├── pantry.service.js
│       │   ├── menu.service.js
│       │   └── shopping.service.js
│       ├── middlewares/      # Middlewares
│       │   ├── auth.middleware.js
│       │   ├── validate.middleware.js
│       │   ├── error.middleware.js
│       │   └── rateLimit.middleware.js
│       ├── validators/       # Esquemas de validación
│       │   ├── auth.schema.js
│       │   ├── ingredient.schema.js
│       │   ├── menu.schema.js
│       │   └── shopping.schema.js
│       ├── utils/            # Utilidades
│       │   ├── jwt.js
│       │   ├── password.js
│       │   └── ApiError.js
│       └── tests/            # Pruebas automatizadas
├── docs/                     # Documentación del proyecto
├── .prettierrc
├── .prettierignore
├── .nvmrc
└── README.md
```