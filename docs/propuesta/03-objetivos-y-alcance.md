# Fase 3 · Objetivos y Alcance · Apañao

## Introducción

El objetivo de este documento es establecer los objetivos que se persiguen con el desarrollo de Apañao, así como delimitar su alcance para la primera versión del producto (MVP). Para ello, se han definido tanto el objetivo general, como los objetivos específicos, junto a los requisitos y funcionalidades que formarán parte de la versión entregada, diferenciando aquellos que quedan fuera de esta primera iteración.

## 1. Objetivos

### Objetivo general

Desarrollar y validar una aplicación móvil (*Mobile-First*) basada en el stack MERN que elimine la carga mental de la gestión alimentaria diaria en jóvenes e independizados, permitiéndoles transformar sus ingredientes disponibles y presupuestos reducidos en comidas rápidas, económicas y sin desperdicio.

### Objetivos específicos

| ID | Objetivo SMART | Qué se mide | Valor de éxito | Cómo se comprueba |
|---|---|---|---|---|
| **OE-01** | **Funcionalidad Core MERN:** Construir e integrar el buscador de recetas por ingredientes/caducidad, el generador de listas por presupuesto y la despensa compartida para la app móvil antes de la defensa final. | Cobertura de Historias de Usuario prioritarias y registro de errores (*Bug Tracking*). | 100% de Historias de Usuario completadas y 0 errores bloqueantes (*Critical Bugs*). | Prueba de integración *end-to-end* en dispositivos móviles reales por el equipo 10 días antes de la defensa. |
| **OE-02** | **Reducción de Carga Mental (UX Mobile):** Diseñar una interfaz táctil que permita obtener sugerencias de recetas en un máximo de 3 toques o 30 segundos de interacción desde el teléfono. | Tiempo de ejecución (*Time-to-Task*) y número de toques de pantalla desde el inicio hasta la receta. | < 30 segundos y máximo 3 toques en el 80% de las pruebas. | Demo cronometrada con 5 personas reales usando sus propios móviles en los ensayos previos a la defensa. |
| **OE-03** | **Rendimiento en Redes Móviles:** Garantizar una navegación fluida en conexiones de datos (4G/5G) optimizando el backend en Node.js/Express y la interfaz móvil en React. | Tiempo de respuesta de la API (latencia) y puntuación de rendimiento móvil en Google Lighthouse. | Latencia de API < 1,5s y puntuación Lighthouse móvil ≥ 85/100. | Auditorías con Google Lighthouse (perfil Mobile) y pruebas de red simulada 1 semana antes de la defensa. |
| **OE-04** | **Adaptación a Principiantes (Cero Asunciones):** Integrar recetas con lenguaje coloquial, sin tecnicismos, adaptadas a utensilios básicos y con guía explícita para el uso de tápers/congelador. | Grado de comprensión de los pasos e indicaciones por usuarios sin experiencia previa en cocina. | 100% de comprensibilidad en las instrucciones y utensilios requeridos (0 dudas sobre términos técnicos). | Prueba de validación del paso a paso con 3 personas reales sin experiencia culinaria 1 semana antes de la defensa. |

## 2. Alcance

### 2.1. El MVP

El MVP detallado y su análisis de viabilidad se encuentran definidos en el documento [02-viabilidad-tecnica.md](02-viabilidad-tecnica.md).

Hemos tenido en cuenta las correcciones de la A0.4, por lo que hemos **corregido el recorrido del MVP** para garantizar que solo utilice funcionalidades clasificadas estrictamente como **Must Have**, eliminando dependencias externas y requisitos inconsistentes:

- **Inclusión del catálogo de recetas base:** Se incorpora la colección de recetas (`recipes`) a la base de datos desde la primera versión. Sin recetas con ingredientes y cantidades definidas (MVP anterior), es técnicamente imposible calcular las faltas de la despensa.
- **Eliminación de APIs de supermercados:** Se eliminan las integraciones con Mercadona y Carrefour del flujo del MVP (pasan a *Could Have*).
- **Flujo del recorrido corregido:**
    1. **Autenticación:** El usuario se registra e inicia sesión (obteniendo un token de autenticación).
    2. **Poblado de Despensa:** Alta y consulta de ingredientes disponibles.
    3. **Planificación:** Selección de un menú semanal utilizando el catálogo base de recetas de la aplicación (`recipes`).
    4. **Generación de Lista:** El backend compara los ingredientes del menú con el stock actual de la despensa y calcula de forma precisa la lista de la compra pendiente.
    5. **Cierre de sesión:** El usuario cierra su sesión de manera segura.

### 2.2. Plataforma

**Justificación y Enfoque:** Para la primera versión **priorizaremos la experiencia de uso en dispositivos móviles**, ya que es el entorno natural donde el usuario interactuará con la app (en la cocina revisando la despensa o en el supermercado).

### 2.3. Usuarios y datos

- **Volumen de usuarios objetivo:** En la fase de pruebas usaremos un entorno controlado de un mínimo **usuarios simulados**.
- **Naturaleza de los datos:**
    - **Usuarios y Sesiones:** Datos ficticios con correos ficticios para la fase de pruebas.
    - **Recetas:** Catálogo inicial de datos reales (un mínimo de recetas básicas bien estructuradas con ingredientes y cantidades estándar en la base de datos).
    - **Despensa y Lista:** Generados dinámicamente durante las pruebas de uso.

### 2.4. Lo que no haremos

Para asegurar la entrega dentro del calendario y ajustarnos a la capacidad del equipo, las siguientes características **no se realizarán** en esta versión:

1. **Integración con APIs oficiales de Supermercados (Mercadona, Carrefour, etc.):**
    - *Por qué:* No existen APIs oficiales documentadas.
2. **Generación de menús mediante Inteligencia Artificial (LLM/IA):**
    - *Por qué:* Depender de servicios de IA para cada consulta introduce el riesgo de recetas incoherentes y costes por consumo.
3. **Gestión de Tuppers y sobrantes:**
    - *Por qué:* Aunque aporta valor, la aplicación es funcional calculando menús a partir de despensa y recetas. Mantener la lógica de tuppers aumentaría la complejidad sin ser imprescindible para el MVP.
4. **Sincronización de inventario multiusuario o espacios compartidos:**
5. **Aplicación móvil nativa (Android / iOS):**
    - *Por qué:* Tomaría más tiempo del que disponemos. Al priorizar el diseño *Mobile-First* en la web, cubrimos las necesidades del móvil sin duplicar la carga de trabajo.

### 2.5. Ampliaciones futuras

En caso de disponer de más tiempo, las mejoras que serian interesantes abordar serían:

1. **Gestión de Tuppers y Congelador (*Should Have*):** Permitir registrar raciones cocinadas y descontarlas al planificar la semana.
2. **Gestión de Alérgenos y Filtros de Perfil (*Should Have*):** Filtrado automático en el catálogo de recetas según las intolerancias configuradas en el usuario.
3. **Traspaso automático de Lista a Despensa (*Should Have*):** Botón de "Marcar como comprado" para mover productos de la lista directamente al stock de la despensa.
4. **Asistente de Recetas con IA (*Could Have*):** Integración de un servicio de IA para sugerir combinaciones creativas únicamente cuando el catálogo base no devuelva resultados.
5. **Estimación de costes de supermercados (*Could Have*):** Cálculo aproximado del precio total de la lista de la compra.