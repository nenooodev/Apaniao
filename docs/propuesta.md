# Propuesta de proyecto Apañao

**Integrantes:** África Galindo Sánchez, A. Manuel Pérez Gómez, Antonio López Gautier, Aarón Gallardo Canto y Pablo Sanz Aznar | **Fecha:** Octubre 2026

## Índice

* Introducción
* 1. El problema
* 2. Viabilidad técnica
* 3. Objetivos y alcance
* 4. Recursos

## Introducción

**Apañao** nace como una solución web integral diseñada para resolver la fricción logística, el estrés diario y el impacto económico a los que se enfrentan estudiantes, jóvenes en pisos compartidos y personas recién independizadas al gestionar su alimentación. El problema real no es solo cocinar, sino la carga mental continua de decidir qué comer con lo que hay, evitar el desperdicio y ajustar la compra a un presupuesto estricto. Este problema afecta de manera directa a estudiantes universitarios y jóvenes con recursos limitados y poco tiempo.

Nuestra **propuesta de valor** ofrece el asistente práctico que te saca una comida en 10 minutos con lo que ya tienes en casa, te avisa para aprovechar los táperes y te ajusta la compra al céntimo según tu presupuesto real, sin exigir despensas llenas ni ingredientes caros.

El **MVP** se centra en el recorrido esencial corregido tras la retroalimentación: autenticación segura por JWT, catálogo base de recetas (`recipes`), control de inventario de despensa (`ingredients`), planificación de menús semanales (`menus`) y generación automática de listas de la compra inteligentes (`shopping_lists`) comparando el stock disponible. Se descartan las APIs de supermercados no oficiales y se reserva la IA como una característica opcional (*Could Have*).

A nivel tecnológico, empleamos el **stack MERN** (MongoDB Atlas, Express.js, React con Vite y Node.js), desplegando el frontend en Vercel y el backend en Render con un coste operativo de 0 €/mes.

Los **objetivos** principales se centran en desarrollar la funcionalidad core de la app, reducir la carga mental con una interfaz optimizada *mobile-first* en menos de 3 toques, garantizar rendimiento en redes móviles y adaptar las recetas a instrucciones sencillas sin tecnicismos.

El **equipo** está formado por África (Frontend), Antonio (Backend Leader), Aarón (DataBase Manager) y Manu (QA y Despliegue), organizados mediante tableros Kanban en GitHub Projects y flujos estrictos de ramas.

## 1. El problema

### 1.1 La necesidad: El problema real de la vida independiente

Vivir por primera vez fuera de casa (ya sea en un piso de estudiantes o en solitario) viene con un curso intensivo obligatorio: **la gestión de la comida diaria**. El problema de siempre no es solo cocinar, sino la carga mental constante que hay detrás: ¿Qué como hoy, qué hago con lo que tengo por casa, cuánto me va a costar y qué tengo que comprar?

La gran mayoría de las apps de recetas y planificación del mercado pasan por alto la realidad de un piso de estudiantes o de una persona joven recién independizada: o son de pago, o los presupuestos son completamente irreales, o te piden ingredientes imposibles de encontrar o pagar.

### 1.2 ¿A quién afecta?

* **Estudiantes universitarios o de ciclos formativos** que compaginan clases, exámenes, poco tiempo libre y presupuestos muy ajustados.
* **Jóvenes que acaban de independizarse** y se enfrentan por primera vez a la gestión económica y logística de hacer la compra y cocinar cada semana.

### 1.3 Frecuencia

Es un **problema diario y continuo**. Se repite al menos dos veces al día (al mediodía y por la noche), convirtiéndose en una fuente constante de estrés, improvisación y pérdida de tiempo.

### 1.4 Impacto

* **Económico:** Gasto innecesario de dinero en compras impulsivas de última hora y en comida que acaba pudriéndose en la nevera.
* **Emocional y físico:** Frustración constante, malnutrición por recurrir siempre a lo ultraprocesado o fácil, y cansancio mental acumulado por tener que pensar qué comer todos los días.

### 1.5 Evidencias

* El clásico grupo de WhatsApp del piso de estudiantes preguntando: *"¿Quién se hace algo con lo que hay por ahí?"* o *"¿Alguien tiene aceite/sal?"*.
* Neveras tristes con tres ingredientes sueltos que no combinan entre sí y táperes olvidados en el fondo del congelador que acaban tirándose a la basura.
* Según los informes del *Ministerio de Agricultura, Pesca y Alimentación sobre el desperdicio alimentario en los hogares españoles*, un porcentaje abrumador (el 97,5%) se genera en el ámbito doméstico.

### 1.6 User personas

* **Usuario principal:** Estudiantes y jóvenes recién independizados que necesitan ajustar el presupuesto y optimizar recursos con poco tiempo.
* **Usuario secundario:** Personas con una jornada laboral intensa que no les deja tiempo para planificar y requieren automatización y seguridad frente a alérgenos.

### 1.7 Casos de uso

* **“¿Qué como hoy?”:** Consulta los ingredientes disponibles y propone opciones rápidas.
* **“Tengo cuatro cosas en la nevera”:** Propone recetas para aprovechar restos cercanos a caducar.
* **“Tengo que hacer la compra con 25 €”:** Genera listas adaptadas a un límite económico estricto.
* **“Hazme la compra para toda la semana”:** Planifica menús semanales y agrupa la lista de la compra.
* **“Compartimos piso”:** Sincroniza la despensa común entre compañeros.

### 1.8 Análisis de Competencia

* **Noodle (Cookpad):** Buen buscador por ingredientes, pero lastrado por muros de pago agresivos y asunción de despensas caras.
* **SuperCook:** Gran base de datos, pero con interfaz obsoleta y sin contemplar la logística del táper ni el presupuesto de estudiantes.
* **Planifood / Mealime:** Listas automáticas, pero con ingredientes caros e inflexibles ante la improvisación con pocos recursos.

### 1.9 Identificación de Oportunidades

1. **Optimización por Presupuesto Real:** Menús ajustados a un límite exacto con marcas blancas de supermercados locales.
2. **Gestión del Táper y Congelador:** Avisos de descongelación y control de raciones cocinadas.
3. **Modo Despensa Compartida:** Sincronización entre compañeros de piso.
4. **Cero Asunciones Culinarias:** Recetas explicadas sin tecnicismos ni utensilios avanzados.

### 1.10 Matriz Comparativa de Funcionalidades

| Característica / Necesidad | Noodle | SuperCook | Mealime | Apañao |
| --- | --- | --- | --- | --- |
| **Búsqueda por ingredientes sueltos** | Sí *(limitado)* | Sí | Parcial | **Sí (priorizando caducidad)** |
| **Filtro por presupuesto máximo (€)** | No | No | No | **Sí (Límite semanal/compra)** |
| **Control de tápers / congelador** | No | No | No | **Sí (Alertas y registro)** |
| **Despensa compartida (Piso)** | No | No | No | **Sí (Multiusuario)** |
| **Recetas para novatos** | Media | Baja | Media | **Alta (Pasos ultra-simples)** |

### 1.11 Punto de Control: Decision Go / No-Go

> **DECISIÓN: SEGUIR ADELANTE (GO)**
> *Justificación:* Existe un hueco desatendido en la intersección entre ahorro estricto, logística del estudiante y simplicidad de preparación que ninguna app dominante integra de forma conjunta.

### 1.12 Propuesta de Valor

> «Para **estudiantes y jóvenes que viven por su cuenta** y están **frustrados por el estrés diario de no saber qué comer, tirar comida y gastar de más**, a diferencia de las **apps de recetas tradicionales o la improvisación** —que exigen ingredientes caros, asumen despensas llenas y se olvidan de los táperes y pisos compartidos—, **Apañao** es **el asistente práctico que te saca una comida en 10 minutos con lo que ya tienes en casa, te avisa para que no se te quede el táper congelado y te ajusta la compra al céntimo según tu presupuesto real.**»

## 2. Viabilidad técnica

### 2.1 Funcionalidades principales y MoSCoW

* **Must Have:** Registro e inicio de sesión, configuración de perfil, gestión de alérgenos, alta de ingredientes, consulta de despensa, planificación de menús (con catálogo base de recetas), sincronización con la compra y consulta de la lista de la compra.
* **Should Have:** Cierre de sesión, actualización/baja de alimentos, registro y consulta de tápers, descuento de tápers, sugerencias de recetas y traspaso a despensa.
* **Could Have:** Gestión de favoritos, alertas de caducidad e integración opcional de IA.
* **Won't Have:** Compartir inventario en red a gran escala o apps nativas móviles.

### 2.2 Definición del MVP

El MVP se estructura sobre los requisitos *Must Have* corregidos: autenticación segura por JWT, alta de despensa, planificación de menús mediante el catálogo base de recetas (`recipes`) y generación automática de la lista de la compra calculada por diferencias de stock, eliminando dependencias de APIs de supermercados externas.

### 2.3 Análisis de Requisitos Técnicos

* **Frontend:** Desarrollado en React con Vite, React Router, Zustand para estado global, Axios y Tailwind CSS para diseño *mobile-first*.
* **Backend:** API REST desarrollada en Node.js con Express, Mongoose para modelos de MongoDB, JWT para autenticación, bcrypt para contraseñas y validación robusta.
* **Base de Datos:** MongoDB Atlas (Tier M0 gratuito) con colecciones estructuradas (`users`, `ingredients`, `recipes`, `menus`, `shopping_lists`) interrelacionadas mediante referencias `ObjectId` y aislamiento estricto por `userId`.
* **Infraestructura Cloud (Coste 0 €/mes):** Frontend alojado en Vercel (Plan Hobby) y backend en Render (Web Services gratuitos), gestionando los arranques en frío (*cold starts*) mediante avisos visuales en la interfaz.

### 2.4 Análisis de Riesgos y Mitigaciones

* **Riesgo 1 (Falta de experiencia en MERN):** Mitigado mediante mini CRUDs incrementales semanales y programación en pareja (*pair programming*).
* **Riesgo 2 (Dependencia de servicios externos/IA):** Mitigado diseñando una arquitectura desacoplada donde el núcleo funciona de forma autónoma.
* **Riesgo 3 (Cold Starts en Render):** Mitigado incorporando un componente visual amigable de carga en el frontend.

## 3. Objetivos y alcance

### 3.1 Objetivos

* **Objetivo General:** Desarrollar y validar una aplicación web *Mobile-First* basada en el stack MERN que elimine la carga mental de la gestión alimentaria diaria en jóvenes.
* **OE-01 (Funcionalidad Core MERN):** 100% de Historias de Usuario prioritarias completadas y 0 errores bloqueantes probados *end-to-end*.
* **OE-02 (Reducción de Carga Mental UX):** Obtener sugerencias de recetas en < 30 segundos y máximo 3 toques en el 80% de las pruebas móviles.
* **OE-03 (Rendimiento en Red):** Latencia de API < 1,5s y puntuación Lighthouse móvil ≥ 85/100.
* **OE-04 (Adaptación a Principiantes):** 100% de comprensibilidad en las instrucciones de las recetas y utensilios requeridos.

### 3.2 Alcance

* **MVP:** Limitado estrictamente a los módulos *Must Have* (autenticación, despensa, recetas base, menús y lista de compra inteligente).
* **Plataforma:** Enfoque prioritario *Mobile-First* adaptado para dispositivos móviles.
* **Datos:** Datos simulados para pruebas y catálogo inicial con recetas base estructuradas.
* **Exclusiones (Lo que no haremos):** APIs oficiales de supermercados, generación exclusiva por IA de menús, gestión avanzada de tápers multiusuario y apps nativas de iOS/Android.
* **Ampliaciones futuras:** Inclusión de tápers, gestión de alérgenos avanzada, traspaso automático a despensa y asistente de recetas con IA.


## 4. Recursos

### 4.1 Las personas

* **Aarón:** DataBase Manager (Modelado y gestión de MongoDB).
* **Antonio:** Backend Leader (Desarrollo de API REST y Node.js/Express).
* **Manu:** QA y Despliegue (Pruebas, detección de errores y supervisión de despliegues).
* **África:** Frontend Lead (Desarrollo de interfaz de usuario en React y Tailwind CSS).
* **Pablo**: Frontend

### 4.2 La tecnología

* **Stack:** MERN (MongoDB Atlas, Express.js, React, Node.js).
* **Herramientas:** VSCode, Node.js (LTS), Prettier, ESLint, Postman, Git y GitHub Projects (Kanban).

### 4.3 La gestión

* **Control de versiones:** Estrategia estricta con ramas `main`, `develop`, `feature/*`, `fix/*` y `docs/*`, prohibiendo commits directos a `main` y exigiendo Pull Requests revisados.
* **Estructura del repositorio:** Monorepo dividido claramente en las carpetas `/client` (React + Vite) y `/server` (Node.js + Express), además de la documentación centralizada en `/docs`.
