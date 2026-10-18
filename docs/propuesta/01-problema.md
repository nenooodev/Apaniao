# Apañao: Análisis de la Necesidad

## Introducción

Este documento recoge el análisis previo para el desarrollo de **Apañao**, un asistente pensado para hacer llevadera la comida diaria en pisos compartidos o en solitario, sin presupuestos altos ni complicaciones innecesarias.

A lo largo de los siguientes apartados se desglosa el contexto completo del proyecto:
- Empezamos con **el problema real**, a quién lo causa y su impacto diario en el bolsillo y la salud.
- Definimos los **perfiles de usuario** y los **casos de uso** más habituales (desde el típico "no sé qué comer con 4 cosas" hasta cuadrar la compra semanal con 25 €).
- Analizamos **qué ofrece el mercado actual**, detectando dónde fallan las soluciones que existen a día de hoy y qué oportunidades dejan sin tener muy en cuenta.
- Terminamos con la **decisión sobre la viabilidad del proyecto** y nuestra **propuesta de valor**, sintetizando qué hace diferente a **Apañao** frente a cualquier otra herramienta.

## 1. El Problema: ¿Qué nos quita el sueño cada día?

Vivir por primera vez fuera de casa (ya sea en un piso de estudiantes o en solitario) viene con un curso intensivo obligatorio: **la gestión de la comida diaria**.

El problema real no es solo cocinar, sino la carga mental constante que hay detrás:

- **El bucle diario:** Abrir la nevera, ver cuatro ingredientes sueltos y no saber qué inventar sin complicarse la vida.

- **El desfase presupuestario:** Las recetas de internet o aplicaciones de cocina tradicionales asumen despensas llenas de productos caros o tiempos de cocinado que nadie tiene un martes a las 3 de la tarde entre clase y clase.

- **El drama del congelador:** Olvidar sacar el táper de mamá o el guiso congelado a tiempo, lo que obliga a tirar de plan B caro o comida basura.

- **El desperdicio y la tirantez económica:** Comprar sin planificación hace que se caduquen ingredientes y que el dinero de la semana (que suele ir ajustado al milímetro) vuele antes de tiempo.

## 2. ¿A quién afecta?

- **Estudiantes universitarios** que compaginan clases, exámenes y presupuestos muy ajustados.

- **Jóvenes que acaban de independizarse** y disponen de poco tiempo, poca experiencia cocinando y la necesidad de organizarse de forma realista.

## 3. Frecuencia

Es un problema **diario y continuo**. Se repite al menos dos veces al día (al mediodía y por la noche), convirtiéndose en una fuente constante de estrés y improvisación que se traduce en comer mal o gastar de más.

## 4. Impacto

- **Económico:** Gasto innecesario de dinero en compras impulsivas de último minuto y comida que acaba pudriéndose en la basura.

- **Emocional y físico:** Frustración constante, malnutrición por recurrir siempre a lo ultraprocesado o fácil, y cansancio mental acumulado por tener que pensar "qué comer" todos los malditos días.

## 5. Evidencias

- Las típicas fotos de neveras tristes con tres huevos, medio tomate y un trozo de queso seco y demasiado me parece en comparación con mi hueco de la nevera.

- Las conversaciónes que yo nsuelo tener con mis amigas que viven "independizadas" también o personas que he conocido viviendo fuera de casa, hablando de que suelen tener la nevera vacía o que les da pereza pensar que cocinar.

- El desecho recurrente de comida en los pisos compartido porque nadie planeó cómo aprovecharla a tiempo.

## 6. User personas

- Usuario principal: Universitarios y jóvenes recién independizados, por las razones establecidas más arriba.
- Usuario secundario: Personas adultas de clase baja con una jornada laboral intensa que no les deja tiempo para nada más

## 7. Casos de uso

### “¿Qué como hoy?”

**Situación:** Es la hora de comer y no sabes qué preparar. Tienes algunos ingredientes en la nevera, pero no quieres pensar demasiado.

**Apañao:** Consulta lo que tienes disponible y propone varias comidas que puedas hacer con ello, teniendo en cuenta el tiempo disponible, tus preferencias y el presupuesto.

**Resultado:** Pasas de “no sé qué comer” a tener una comida lista sin necesidad de buscar entre cientos de recetas.

---

### “Tengo cuatro cosas en la nevera”

**Situación:** Te quedan huevos, media cebolla, un tomate y un poco de arroz. No quieres tirar comida, pero tampoco sabes qué hacer con ella.

**Apañao:** Detecta qué ingredientes tienes y propone recetas para aprovecharlos, priorizando aquellos que están cerca de caducar.

**Resultado:** Aprovechas mejor la compra y reduces el desperdicio de comida.

---

### “Tengo que hacer la compra con 25 €”

**Situación:** Es principio de mes y tienes un presupuesto limitado para hacer la compra.

**Apañao:** Genera una lista de la compra adaptada al presupuesto, priorizando productos básicos, versátiles y económicos.

**Resultado:** Sabes qué comprar sin llegar a caja preguntándote cómo has gastado tanto.

---

###  “Hazme la compra para toda la semana”

**Situación:** No quieres decidir cada día qué comprar y qué cocinar.

**Apañao:** Planifica varias comidas para la semana y genera automáticamente una lista de la compra agrupada por productos.

**Resultado:** Una sola compra sirve como base para toda la semana y se reduce la improvisación.

---

###  “Mañana tengo clase todo el día”

**Situación:** Sabes que vas a pasar muchas horas fuera de casa y necesitas llevarte comida.

**Apañao:** Tiene en cuenta tu horario y propone comidas fáciles de preparar, transportar y conservar.

**Resultado:** Preparas un táper adecuado sin tener que improvisar la noche anterior.

---

###  “Me voy de viaje y tengo comida que se va a poner mala”

**Situación:** Te vas varios días y tienes alimentos abiertos o próximos a caducar.

**Apañao:** Revisa los alimentos disponibles y propone recetas para aprovecharlos antes de irte.

**Resultado:** Evitas tirar comida y aprovechas al máximo lo que ya has comprado.

---

### “No sé cocinar”

**Situación:** Te independizas por primera vez y apenas sabes preparar más de dos o tres platos.

**Apañao:** Propone recetas sencillas adaptadas a tu nivel y explica cada paso de forma clara, sin asumir conocimientos previos.

**Resultado:** Puedes empezar a cocinar sin sentir que necesitas aprender a cocinar desde cero antes de utilizar la aplicación.

---

### “Tengo poco tiempo”

**Situación:** Llegas a casa tarde y no quieres pasar una hora cocinando.

**Apañao:** Filtra las opciones según el tiempo disponible y propone comidas que puedan prepararse rápidamente con los ingredientes que tienes.

**Resultado:** Comes algo decente sin recurrir siempre a comida preparada o pedir a domicilio.

---

### “He comprado algo y no sé cómo usarlo”

**Situación:** Compraste un ingrediente porque estaba barato, pero ahora no sabes en qué platos utilizarlo.

**Apañao:** Sugiere diferentes comidas en las que puedas utilizarlo y combina las propuestas con otros productos que ya tengas.

**Resultado:** Un ingrediente aislado se convierte en varias comidas posibles.

---

### “Compartimos piso”

**Situación:** Varias personas comparten nevera, despensa y gastos, pero nadie sabe exactamente qué queda ni quién ha comprado qué.

**Apañao:** Permite compartir una despensa y una lista de la compra entre compañeros de piso.

**Resultado:** : Se reducen las compras duplicadas y es más fácil organizar los gastos y la comida común.

### “Tengo comida preparada”

Situación: Has cocinado varias raciones y quieres organizar los táperes de los próximos días.

Apañao: Permite registrar las comidas preparadas y organizarlas según cuándo conviene consumirlas.

Resultado: Sabes qué tienes preparado y reduces el riesgo de olvidarte de comida en la nevera.

### “Quiero comer mejor sin gastar más”

Situación: Quieres mejorar tus hábitos alimenticios, pero no puedes permitirte hacer una compra completamente diferente o comprar productos caros.

Apañao: Propone alternativas utilizando productos económicos y habituales, adaptando las comidas a tus objetivos y presupuesto.

Resultado: Comer mejor no implica necesariamente aumentar el gasto de la compra.

## 8. Análisis de Competencia

Analizamos tres soluciones actuales del mercado que abordan aspectos del problema (recetarios dinámicos, gestión de despensa y planificación de compras/menús), extrayendo sus fortalezas y sus puntos críticos reales según las reseñas negativas de sus usuarios.

### 1. Noodle (antes Cookpad / apps de recetas por ingredientes)
* **Fortalezas:** Excelente interfaz visual, motor de búsqueda por ingredientes disponibles, enfocado en platos rápidos (20 minutos o menos) y hábitos saludables.
* **Debilidades (Reseñas 1★):** Muro de pago (*paywall*) agresivo que bloquea la búsqueda avanzada por ingredientes; asume condimentos o productos secundarios "básicos" que un estudiante no suele tener; no gestiona el presupuesto ni calcula el coste de la compra.

### 2. SuperCook
* **Fortalezas:** Gran base de datos global de recetas; inventario detallado de despensa que cruza cientos de miles de opciones.
* **Debilidades (Reseñas 1★):** Interfaz obsoleta y poco intuitiva; sugiere recetas complejas con técnicas o utensilios poco realistas; no contempla la logística del táper, la comida congelada, los pisos compartidos ni el límite presupuestario semanal.

### 3. Planifood / Mealime
* **Fortalezas:** Automatizan la lista de la compra semanal según un menú planificado; optimizan el tiempo de cocinado.
* **Debilidades (Reseñas 1★):** Sugieren ingredientes caros, exóticos o difíciles de encontrar en supermercados de descuento (como Mercadona, Día o Lidl); inflexibles cuando solo se quiere improvisar con "cuatro cosas"; no abordan la convivencia en pisos compartidos.

---

## 9. Identificación de Oportunidades

El mercado actual ofrece herramientas de recetas o planificadores nutricionales, pero **ninguna resuelve el problema desde la restricción económica y la logística del estudiante**. Las principales oportunidades detectadas son:

1. **Optimización por Presupuesto Real (Supermercado Local):** Diseñar menús ajustados a un límite exacto (ej. 25 €/semana) utilizando precios de marca blanca y productos básicos de supermercados habituales.
2. **Gestión del "Síndrome del Táper y Congelador":** Incluir avisos para descongelar a tiempo y registrar raciones ya cocinadas para evitar compras innecesarias.
3. **Modo "Despensa Compartida":** Módulo colaborativo para sincronizar la nevera común entre compañeros de piso y evitar comprar productos duplicados.
4. **Cero Asunciones Culinarias:** Recetas explicadas sin tecnicismos ("fuego medio-alto", sin necesidad de balanza de precisión o utensilios avanzados).

---

## 10. Matriz Comparativa de Funcionalidades

| Característica / Necesidad | Noodle | SuperCook | Mealime | Apañao |
| :--- | :---: | :---: | :---: | :---: |
| **Búsqueda por ingredientes sueltos** | Sí *(limitado)* | Sí | Parcial | **Sí (priorizando caducidad)** |
| **Filtro por presupuesto máximo (€)** | No | No | No | **Sí (Límite semanal/compra)** |
| **Control de tápers / congelador** | No | No | No | **Sí (Alertas y registro)** |
| **Despensa compartida (Piso)** | No | No | No | **Sí (Multiusuario)** |
| **Recetas para novatos (Poco equipamiento)** | Media | Baja | Media | **Alta (Pasos ultra-simples)** |

---

## 11. Punto de Control: Decision Go / No-Go

> **DECISIÓN: SEGUIR ADELANTE (GO)**

* **Justificación:** La competencia se enfoca en "comer bonito" o "comer sano", pero desatiende la "supervivencia doméstica eficiente". Existe un hueco desatendido en la intersección entre **ahorro estricto + logística del estudiante + simplicidad de preparación**. Ninguna app dominante integra el control de gastos de supermercado con la gestión práctica de táperes y convivencia.

---

## 12. Propuesta de Valor

> «Para **estudiantes y jóvenes que viven por su cuenta** y están **frustrados por el estrés diario de no saber qué comer, tirar comida y gastar de más**, a diferencia de las **apps de recetas tradicionales o la improvisación sobre la marcha** —que exigen ingredientes caros, asumen despensas llenas y se olvidan por completo de los táperes y los pisos compartidos—,
> 
> **Apañao** es **el asistente práctico que te saca una comida en 10 minutos con lo que ya tienes en casa, te avisa para que no se te quede el táper congelado y te ajusta la compra al céntimo según tu presupuesto real.**»

---

### Lo que hace diferente a Apañao:

- **Compras con presupuesto cerrado:** No te pedimos que gastes de más; si tienes 20 € para la semana, la lista se adapta a básicos y marcas blancas.
- **Cocinar con lo que hay:** Prioriza gastar lo que está a punto de ponerse malo en la nevera antes de decirte que compres nada nuevo.
- **Control de táperes:** Te avisa la noche antes para pasar la comida del congelador a la nevera, evitando que acabes pidiendo comida por no tener nada listo.
- **Modo piso compartido:** Despensa y lista común para no comprar cosas repetidas ni tener lios con los compañeros de piso.
- **Cero postureo:** Recetas directas, cortas y pensadas para cuando tienes 10 minutos y pocas ganas de fregar.
