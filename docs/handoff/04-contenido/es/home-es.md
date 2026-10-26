# Home — copy en español

> [TRADUCCIÓN PRELIMINAR — REVISAR] Traducido por Claude el 2026-10-26 a partir de home-sections.jsx (más Header.jsx y Footer.jsx). Pendiente de revisión del equipo.

## Decisiones aplicadas (2026-10-26)

- [DECISIÓN 2026-10-26] El primer viaje destacado es Bogotá, no Sierra Nevada. El bloque de Sierra Nevada no se traduce (ver sección 05).
- [DECISIÓN 2026-10-26] El carrusel de extensiones queda así, en este orden: Sierra Nevada (Próximamente), San Andrés, Barichara, Boyacá, Oaxaca (México, próximamente). Se quitan Bogotá, Medellín, Cartagena, Ciudad Perdida y Nevado del Ruiz.
- [DECISIÓN 2026-10-26] Los precios del prototipo son de relleno y no se traducen. El precio es un campo del CMS; si está vacío, no se muestra.
- [DECISIÓN 2026-10-26] Los pilares son Balance, Connection y Firsthand → Equilibrio, Conexión, De primera mano.

## Notas de extracción

- Solo se extrajeron los textos visibles, en el orden en que aparecen en pantalla. Los comentarios del código no se traducen.
- Algunos componentes del sistema de diseño (NewsletterForm, JourneySection, Quote, Stat, Window, KeepSeeking) pueden generar textos propios: etiquetas de formulario, botones o rótulos. Esos textos no están en este archivo fuente y no se traducen aquí.
- Panel de ajustes del prototipo (TweaksPanel: "How we travel — heading", "Letter spacing", "Bold question titles", "Texture opacity"…): [NO SE TRADUCE — material interno]. Es una herramienta de diseño y no se publica.

---

## 00 · Header (Header.jsx)

**Logo (alt):** Soul to Soul

**Menú:**
- Por qué Colombia
- Destinos
- Inspiración
- Nosotros
  EN: About Us

**Selector de idioma:** **ES** · EN

**Botón:** Escríbenos

**Header compacto al hacer scroll (alt del sello):** Soul to Soul

---

## 01 · Hero

**Frase de entrada:** La vida moderna es buena para llenarte de prisa, de distracciones, de desconexión.
EN: Modern life is good at keeping you busy, distracted, disconnected.

**Título (H1):** Nuestros viajes están diseñados para reconectar contigo

## 02 · Película de Colombia

**Imagen (alt):** Valle de Cocora, palmas de cera

**Leyenda sobre el video:** Esto existe. Esto te espera.
EN: This exists. This is waiting.

## 03 · Quiénes somos

**Eyebrow:** Quiénes somos

**Título:** Cinco años afuera. Toda una vida *volviendo a casa*.

**Texto:** Durante cinco años hicimos Tidur, un viaje de 14 días por Singapur, Bali y Camboya, con más de 150 viajeros. El oficio que construimos afuera es el que ahora traemos a casa.

**Cifras:**
- 5+ · Años afuera
- 200+ · Viajeros [REVISAR: el texto de arriba dice "más de 150 viajeros" y esta cifra dice 200+; unificar]
- 25K+ · Comunidad

**Botones:** Escríbenos · Conoce al equipo

**Imagen (alt):** Hojas de plátano, palmas de cera y montañas de los Andes colombianos

## 04 · Cómo viajamos (pilares)

**Eyebrow:** Cómo viajamos

**Título:** Cada viaje que diseñamos, primero lo hemos caminado nosotros. No es un eslogan: así hemos viajado siempre, y así construimos hoy cada itinerario en Colombia.

**Subtítulo:** Tres cosas que cuidamos en cada itinerario:

**Pilar 1 — Equilibrio**
El cuerpo se mueve, el alma se aquieta. Entre el movimiento y el descanso, lo icónico y lo escondido.

**Pilar 2 — Conexión**
Con la tierra, con los demás y con esa parte más callada de ti que aparece cuando cesa el ruido.

**Pilar 3 — De primera mano**
Cada rincón, lo caminamos primero. Cada detalle, elegido en persona; nada sale de una lista.

**Botones:** Escríbenos · Lee la historia completa

## 05 · Destinos

**Eyebrow:** A dónde te llevamos

**Título:** Las *rutas* que conocemos de memoria.

**Subtítulo:** Dos viajes insignia, diseñados de principio a fin.

### 05a · Primer viaje destacado

[REEMPLAZADO POR BOGOTÁ — copy en bogota-bacata-es.md]

> [DECISIÓN 2026-10-26] El bloque "Sierra Nevada de Santa Marta" del original (título, teaser, duración, precio, highlights y leyendas de fotos) no se traduce.

### 05b · Eje Cafetero

**Título:** El *Eje* Cafetero

**Teaser:** Bajo las palmas más altas del mundo, los días llevan el ritmo de la cosecha. Recoge café con las familias que cultivan estas montañas verdes y luego camina bajo las palmas de cera de Cocora mientras se levanta la niebla.
EN: Beneath the tallest palms on earth, the days keep the pace of the harvest. Pick with the families who farm these green hills, then walk out under the wax palms of Cocora as the mist lifts.

**Duración:** 5–7 días

**Precio:** [DECISIÓN 2026-10-26: no se muestra]

**Highlights:**
- Días de cosecha en una finca cafetera en producción
- Las palmas de cera del Valle de Cocora
- Una catación: de la cereza madura al tostado
- Mañanas verdes y sin prisa en el Quindío

**Leyendas de las fotos:**
- Valle de Cocora
- Palmas de cera al atardecer
- La cosecha, ya empacada
- Plátano entre el café
- Manos tejiendo

## 06 · Extiende el viaje

**Título:** ¿Todavía no quieres volver a casa?

**Subtítulo:** Extiende el viaje: una ciudad donde quedarte un tiempo, o una caminata que se gana la vista. [REVISAR: la nueva lista de extensiones ya no tiene ciudades grandes ni caminatas; puede que el subtítulo ya no aplique]

**Carrusel (orden decidido el 2026-10-26):**

1. **Sierra Nevada** — Etiqueta: Próximamente — [COPY PENDIENTE]
2. **San Andrés** — [COPY PENDIENTE]
3. **Barichara** — [COPY PENDIENTE]
4. **Boyacá** — [COPY PENDIENTE]
5. **Oaxaca** (México) — Etiqueta: Próximamente — [COPY PENDIENTE]

> [DECISIÓN 2026-10-26] Se quitan del carrusel Bogotá, Medellín, Cartagena, Ciudad Perdida y Nevado del Ruiz. Su copy no se traduce.

**Controles del carrusel (accesibilidad):** Anterior · Siguiente

## 07 · Ventanas de Colombia

**Eyebrow:** Inspiración

**Título:** Ventanas de Colombia.

**Subtítulo:** Abre una ventana. Cada una guarda una nota de campo del camino.

**Ventanas:**
- 07 · Una mañana en la Sierra
- 06 · De la semilla a la taza
- 05 · Una carta, no un folleto
- 03 · Bogotá en tres comidas
- 04 · Aire de sal, noches sin prisa
  EN: Salt air, slow nights
- 01 · La lluvia avanzando sobre la sabana

**Botón de cada ventana:** Lee la nota

**Controles del carrusel (accesibilidad):** Anterior · Siguiente

## 08 · Testimonios

[REVISAR: los nombres y textos parecen de relleno; confirmar que son testimonios reales y si se traducen o se dejan en su idioma original]

**Testimonio 1**
"Nadie nos apuró. Ese fue todo el regalo: alguien más sostenía los hilos con atención de verdad, y por una vez pudimos estar presentes."
— Marian D. · Róterdam, NL · 5 estrellas · Tripadvisor

**Testimonio 2**
"Conocían a los anfitriones, el sendero, el clima: el tipo de detalle que no te da una página web. Nosotros solo llegamos y prestamos atención."
— James & Priya K. · Austin, EE. UU. · 5 estrellas · Tripadvisor

**Testimonio 3**
"Pedí algo honesto, no una vitrina de lo mejor. Lo que recibimos fueron diez días que todavía siento que se me están asentando."
EN: I asked for something honest, not a highlight reel. What we got was ten days that still feel like they're settling into me.
— Lucía M. · Buenos Aires, AR · 5 estrellas · Google

**Controles (accesibilidad):** Testimonio anterior · Testimonio siguiente

## 09 · Preguntas frecuentes

**Título:** Estás en buenas manos. Pregúntanos lo que quieras.

**Subtítulo:** Seguridad, precios, personalización, reembolsos: respuestas directas aquí abajo.

**Indicación:** Toca una pregunta para abrirla.

**Pregunta 1:** ¿Es seguro viajar a Colombia ahora?
**Respuesta:** Primero la respuesta directa, porque es lo que más importa: sí, con el mismo criterio que usarías en cualquier otro lugar. Solo operamos en regiones que conocemos personalmente, nuestros anfitriones viven allí y te diremos con claridad si algo de tu lista no es buena idea.

**Pregunta 2:** ¿Cómo se definen los precios?
**Respuesta:** Cada viaje se cotiza de forma individual: no hay paquetes. Pagas por el diseño, el acompañamiento y los costos reales en el terreno, sin márgenes escondidos.
EN: Every journey is quoted individually — there are no packages. You pay for design, hosting and the real costs on the ground, with nothing marked up invisibly.

**Pregunta 3:** ¿Se puede personalizar el itinerario?
**Respuesta:** De eso se trata. Empezamos con una conversación, no con un catálogo. La ruta se adapta a quien eres y a cómo viajas.

**Pregunta 4:** ¿Cuál es la política de reembolso?
**Respuesta:** Transparente y por escrito antes de que te comprometas. Preferimos perder una reserva que darte una sorpresa después.

**Botón:** Habla con alguien del equipo
EN: Talk with an expert

## 10 · Llamado final

**Frase destacada:** Cada viaje empieza con una conversación.

**Texto:** Sin guion, sin presión. Cuéntanos qué estás buscando y te diremos con honestidad si somos las personas indicadas para diseñarlo.

**Botón:** Hablemos

## 11 · Newsletter

**Título:** Una carta *sin prisa*, una vez al mes.

**Texto:** Una nota de campo, una práctica, un lugar. Sin ruido, sin ventas. Quédate cerca del camino sin prisa.
EN: One field note, one practice, one place. No noise, no selling. Stay close to the slow road.

**Formulario:** [los textos del formulario los genera el componente NewsletterForm; no están en este archivo fuente]

## 12 · Keep Seeking (antes del footer)

**Tagline:** Keep Seeking (no se traduce)

---

## 13 · Footer (Footer.jsx)

**Columna 1 — título:** Quédate cerca del camino sin prisa
EN: Stay close to the slow road
[formulario de newsletter con casilla de consentimiento: textos generados por el componente NewsletterForm, no están en este archivo fuente]

**Columna 2 — Explora**
- Por qué Colombia
- Destinos
- Inspiración
- Bitácora
  EN: Journal

**Columna 3 — Nosotros**
EN: Company
- Qué hacemos
- Nuestra historia
- Nuestro equipo
- Carta de los fundadores
- Testimonios
- Trabaja con nosotros
  EN: Careers

**Columna 4 — Hablemos**
- WhatsApp
- hello@soultosoul.travel
- @soultosoul [REVISAR: el FAQ da la cuenta de Instagram como "travelsoultosoul"; confirmar cuál es la correcta]
- Horario de atención
  Lun–vie · 9:00–18:00 (hora de Colombia, COT)
  EN: Office hours / Mon–Fri · 9–6 COT

**Franja de confianza:**
- RNT · 121733
- Miembro · ANATO
- Tripadvisor · ★★★★★

**Fila inferior:**
- Logo (alt): Soul to Soul
- Privacidad · Términos · Cookies
- © [año] Soul to Soul Travel

**Franja final:** Keep Seeking (no se traduce)
