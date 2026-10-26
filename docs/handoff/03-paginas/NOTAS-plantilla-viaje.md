# Página de viaje — Coffee Region (Kabai Journey) = PLANTILLA de todos los viajes

Estado: [DISEÑADA]. Esta página es la plantilla de todas las páginas de viaje. Bogotá (Bacatá) se construye con la misma estructura (ver `07-viaje-bogota/BRIEF-viaje-bogota.md`), y las futuras también (Sierra Nevada…).

## 1. Dónde está

| Qué | Ruta |
|---|---|
| Vista para abrir en el navegador (doble clic, funciona sin internet) | `03-paginas/03-plantilla-viaje-coffee-region/VISTA-coffee-region.html` |
| Fuente del prototipo | `fuente/Trip - Coffee Region.dc.html` (también `fuente/Trip - Coffee Region -standalone src-.dc.html` y `fuente/Mobile Preview.dc.html`) |
| Fotos del viaje usadas en el prototipo | `fuente/assets/trip/` (55 archivos, originales de 15–19 MB) |
| Fotos originales y galerías organizadas | Drive: `Raíz/Viaje Eje C/` (Galería, hoteles, extensiones) |
| Copy definitivo sección por sección | `04-contenido/coffee-region-kabai-contenido-web.md` |
| Campos de la plantilla, para modelar en Sanity | `04-contenido/plantilla-pagina-de-viaje.md` |
| Guía de comunicación de las páginas de viaje | `04-contenido/journey-page-communication-guidelines.md` |

## 2. Secciones (orden del prototipo)

01 Hero · 02 Intro · 03 Value props · 03b Panoramic band · 04 Experience highlights · 05 Gallery ("Seven days in pictures") · 06 Itinerary · 06b Divider band · 07 The stays ("Where you stay") · 08 Included · 09 Trip impact · 10 Travel designer ("The people behind these days") · 10b FAQ ("Good to know") · 11a Continue through Colombia (extensiones) · 11 Testimonial ("In their words") · 12a Get the full itinerary ("Not ready to talk yet?") · 12b Final CTA ("Each journey begins with a conversation.")

Cada sección debe ser un bloque del CMS con los campos de `plantilla-pagina-de-viaje.md`. Un viaje puede omitir una sección si no tiene contenido (por ejemplo, testimonios). En ese caso la sección no se muestra; nunca se pone texto de relleno.

## 3. Decisiones y notas

| # | Qué | Estado |
|---|---|---|
| 1 | Si el copy de Notion y el texto del prototipo difieren, **vale Notion** (es más reciente: 2026-10-23) | [DECIDIDO] |
| 2 | Los precios del prototipo ("From US$4,140" en la vista, "USD 4,200 pp" en la fuente) son de relleno. Es un campo del CMS y, si está vacío, no se muestra | [DECIDIDO] |
| 3 | Otros viajes reutilizan la plantilla tal cual. Los elementos regionales entran solo por fotografía, una ilustración o símbolo puntual y el copy, sin tocar la paleta | [DECIDIDO] |
| 4 | "Continue through Colombia" usa la misma fuente de extensiones del Home y de Destinations | [DECIDIDO] |
| 5 | "Get the full itinerary": define qué se entrega (¿PDF por email vía Brevo/Resend?) y cómo se pide el consentimiento de datos (en Notion está en pausa) | [PENDIENTE] |
| 6 | Imágenes: nunca servir los originales de 15–19 MB; generar variantes responsivas | [DECIDIDO] |
| 7 | Huecos de contenido en Notion: el título y el tercer pilar de la sección 03, las leyendas de la galería y los 3 testimonios | [PENDIENTE] — ver `PENDIENTES.md` #23 |
