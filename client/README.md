# Apañao — Cliente (React)

Aplicación web del frontend de **Apañao**, una Single Page Application (SPA)
construida con **React + Vite** que consume la API REST del backend en Node.js.

## Tecnologías

- **React** (vía Vite)
- **React Router (v6+)** — navegación y enrutamiento
- **Zustand** (o Context API) — estado global
- **Axios** — cliente HTTP hacia la API
- **TanStack Query (React Query)** — peticiones y caché
- **Tailwind CSS + Lucide React** — estilos e iconos

## Estructura de archivos prevista

```
client/
├── index.html                  # Punto de entrada HTML de Vite
├── package.json                # Dependencias y scripts (dev, build, preview)
├── vite.config.js              # Configuración de Vite
├── tailwind.config.js          # Configuración de Tailwind CSS
├── postcss.config.js           # Integración de PostCSS/Tailwind
├── .env                        # Variables de entorno (URL de la API) — no se versiona
└── src/
    ├── main.jsx                # Punto de entrada: monta React y los providers
    ├── App.jsx                 # Componente raíz y definición de rutas
    │
    ├── api/                    # Capa de comunicación con el backend
    │   ├── axios.js            # Instancia de Axios + interceptores (token JWT, errores)
    │   ├── auth.js             # Peticiones de registro, login y sesión (/auth)
    │   ├── pantry.js           # CRUD de la despensa (/pantry)
    │   ├── menus.js            # Menús semanales (/menus)
    │   └── shoppingList.js     # Lista de la compra y sincronización (/shopping-lists)
    │
    ├── store/                  # Estado global (Zustand / Context)
    │   ├── authStore.js        # Usuario autenticado, token y cierre de sesión
    │   ├── pantryStore.js      # Despensa temporal y filtros
    │   └── shoppingStore.js    # Carrito / lista de la compra activa
    │
    ├── hooks/                  # Hooks reutilizables
    │   ├── useAuth.js          # Acceso y utilidades de autenticación
    │   └── useQueries.js       # Hooks de TanStack Query (caché de recetas, despensa...)
    │
    ├── context/                # Contextos de React (si se usa Context API)
    │   └── AuthContext.jsx     # Proveedor de sesión del usuario
    │
    ├── components/             # Componentes reutilizables
    │   ├── layout/             # Navbar, Sidebar, Footer, Layout general
    │   ├── ui/                 # Botones, inputs, modales, loaders, alertas
    │   ├── Loader.jsx          # Indicador de carga ("Despertando la cocina de Apañao...")
    │   └── ProtectedRoute.jsx  # Envuelve rutas privadas que requieren sesión
    │
    ├── features/               # Módulos por funcionalidad (Must Have del MVP)
    │   ├── auth/               # Registro, inicio y cierre de sesión
    │   ├── profile/            # Configuración de perfil, alergias e intolerancias
    │   ├── pantry/             # Alta y consulta de ingredientes de la despensa
    │   ├── menus/              # Planificación de menús semanales
    │   ├── recipes/            # Sugerencia y detalle de recetas (Should/Could)
    │   ├── shopping/           # Lista de la compra y sincronización
    │   └── tuppers/            # Registro y consulta de tuppers (Should Have)
    │
    ├── pages/                  # Páginas asociadas a cada ruta
    │   ├── Home.jsx            # Pantalla principal
    │   ├── Login.jsx           # Inicio de sesión
    │   ├── Register.jsx        # Registro de usuario
    │   ├── Profile.jsx         # Perfil y preferencias alimentarias
    │   ├── Pantry.jsx          # Despensa virtual
    │   ├── MenuPlanner.jsx     # Planificador de menús
    │   ├── ShoppingList.jsx    # Lista de la compra
    │   └── NotFound.jsx        # Página 404
    │
    ├── routes/                 # Definición centralizada de rutas
    │   └── AppRoutes.jsx
    │
    ├── utils/                  # Utilidades y helpers
    │   ├── validators.js       # Validación de formularios en el cliente
    │   └── constants.js        # Alérgenos, unidades de medida, categorías...
    │
    └── styles/
        └── index.css           # Estilos globales y directivas de Tailwind
```

## Scripts previstos

```bash
npm install     # Instala dependencias
npm run dev     # Entorno de desarrollo (Vite)
npm run build   # Compila para producción
npm run preview # Previsualiza la build de producción
```

> El despliegue del frontend se realizará en **Vercel** (plan gratuito).
