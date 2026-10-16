# Fase 3 · Objetivos y alcance · Apañao

## Introducción

En esta fase se definen la meta general y los objetivos específicos del proyecto **Apañao**, así como los criterios de éxito que permitirán medir su cumplimiento técnico y funcional con miras a la defensa final.

---

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
### El MVP          (enlace a la fase 2)
### Plataforma
### Usuarios y datos
### Lo que no haremos
  | Qué | Por qué |
### Ampliaciones futuras   (lista numerada, en orden)
