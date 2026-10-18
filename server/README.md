# Apañao — Servidor (Node.js + Express)

API REST del backend de **Apañao**, construida con **Node.js + Express** y
conectada a **MongoDB** mediante **Mongoose**. Actúa como intermediaria entre el
frontend en React y la base de datos, gestionando cuentas, despensa, menús y
listas de la compra.

## Tecnologías

- **Node.js + Express.js** — servidor y API REST (CRUD)
- **Mongoose** — modelado y acceso a MongoDB
- **JSON Web Token (JWT)** — autenticación y autorización
- **bcrypt / bcryptjs** — hash de contraseñas
- **Zod** (o express-validator) — validación de datos de la API
- **dotenv** — variables de entorno
- **Helmet + express-rate-limit** — seguridad de la API

## Estructura de archivos prevista

```
server/
├── package.json              # Dependencias y scripts (dev, start)
├── .env                      # Variables de entorno (MongoDB, JWT_SECRET, ...) — no se versiona
├── .env.example             # Plantilla de variables de entorno
├── src/
│   ├── server.js             # Arranque del servidor HTTP (listen)
│   ├── app.js                # Configuración de Express: middlewares, rutas, errores
│   │
│   ├── config/               # Configuración del proyecto
│   │   ├── db.js             # Conexión a MongoDB Atlas con Mongoose
│   │   └── env.js            # Lectura y validación de variables de entorno
│   │
│   ├── models/               # Esquemas y modelos de Mongoose
│   │   ├── User.js           # users: credenciales, perfil, alergias, intolerancias
│   │   ├── Ingredient.js     # ingredients: despensa (cantidad, ubicación, caducidad)
│   │   ├── Recipe.js         # recipes: nombre, ingredientes, instrucciones, alérgenos
│   │   ├── Menu.js           # menus: plan semanal y comidas planificadas
│   │   └── ShoppingList.js   # shopping_lists: productos y estado pendiente/comprado
│   │
│   ├── routes/               # Definición de rutas (prefijo /api/v1)
│   │   ├── index.js          # Router principal que agrupa los recursos
│   │   ├── auth.routes.js    # POST /auth/register · /auth/login · GET /auth/me
│   │   ├── user.routes.js    # GET/PATCH /users/me (perfil y preferencias)
│   │   ├── pantry.routes.js  # CRUD /pantry
│   │   ├── menu.routes.js    # /menus (creación y consulta de menús)
│   │   └── shopping.routes.js# /shopping-lists y POST /shopping-lists/:id/sync
│   │
│   ├── controllers/          # Lógica de cada endpoint (req → respuesta)
│   │   ├── auth.controller.js
│   │   ├── user.controller.js
│   │   ├── pantry.controller.js
│   │   ├── menu.controller.js
│   │   └── shopping.controller.js
│   │
│   ├── services/            # Lógica de negocio
│   │   ├── auth.service.js       # Registro, login y generación de JWT
│   │   ├── pantry.service.js     # Reglas de la despensa
│   │   ├── menu.service.js       # Generación y planificación de menús
│   │   └── shopping.service.js   # Cálculo de faltantes y sincronización
│   │
│   ├── middlewares/         # Middlewares de Express
│   │   ├── auth.middleware.js    # Verifica el token JWT en rutas privadas
│   │   ├── validate.middleware.js# Valida el body/params con Zod
│   │   ├── error.middleware.js   # Manejo centralizado de errores
│   │   └── rateLimit.middleware.js# Limita peticiones en /auth
│   │
│   ├── validators/         # Esquemas de validación (Zod / express-validator)
│   │   ├── auth.schema.js
│   │   ├── ingredient.schema.js
│   │   ├── menu.schema.js
│   │   └── shopping.schema.js
│   │
│   └── utils/              # Utilidades y helpers
│       ├── jwt.js          # Firma y verificación de tokens
│       ├── password.js     # Hasheo y comparación con bcrypt
│       └── ApiError.js     # Clase de error personalizada para la API
└── tests/                  # Pruebas automatizadas de la API
```

## Endpoints principales

La API se organiza por recursos bajo el prefijo `/api/v1`:

| Recurso | Endpoints |
| --- | --- |
| **Autenticación** | `POST /auth/register` · `POST /auth/login` · `GET /auth/me` |
| **Perfil** | `GET /users/me` · `PATCH /users/me` |
| **Despensa** | `GET /pantry` · `POST /pantry` · `PATCH /pantry/:id` · `DELETE /pantry/:id` |
| **Menús** | `GET /menus` · `POST /menus` · `GET /menus/:id` · `PATCH /menus/:id` |
| **Lista de la compra** | `GET /shopping-lists` · `POST /shopping-lists` · `PATCH /shopping-lists/:id` |
| **Sincronización** | `POST /shopping-lists/:id/sync` |

## Scripts previstos

```bash
npm install     # Instala dependencias
npm run dev     # Entorno de desarrollo (nodemon)
npm start       # Arranca el servidor en producción
```