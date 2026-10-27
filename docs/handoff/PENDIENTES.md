# Pendientes y decisiones abiertas

Última actualización: 2026-10-26. Cada pendiente abierto también es un issue en GitHub (`soul-to-soul-travel/soul-to-soul-web`), con las etiquetas `equipo`, `dev`, `bloquea-lanzamiento` y `contenido`. Cada pendiente indica a quién le toca: **Equipo** (Soul to Soul) o **Dev** (el desarrollador). Cuando algo se cierre, se marca [RESUELTO] con la fecha.

## Bloquean el lanzamiento

| # | Pendiente | Le toca | Dónde impacta |
|---|---|---|---|
| 1 | Licencia web de **Milanesa Serif** y **Avenir LT Std**. Hay archivos, pero no está confirmada la licencia para web. Si no la hay, usar los fallbacks ya definidos: Playfair Display e Inter | Equipo | Todo el sitio |
| 2 | [RESUELTO 2026-10-26] El CTA lleva al quiz de arquetipos, que construye el desarrollador | — | — |
| 3 | Revisar la **traducción preliminar al español** (`04-contenido/es/`) | Equipo | Todo el sitio |
| 4 | Textos legales (Privacy, Terms, Cookies), revisados por abogado | Equipo | `09-legales` |
| 5 | Texto de la Letter from the founders (EN/ES) | Equipo | `08-letter-from-the-founders` |
| 6 | Fotos reales del equipo y de la red de anfitriones | Equipo | `03-paginas/02-about` |
| 7 | Videos, fotos y audios de Why Colombia (hoy son marcadores `[VIDEO]`, `[PHOTO]`, `[AUDIO]`) y verificación de las fuentes 2 y 5 | Equipo | `03-paginas/04-why-colombia` |
| 8 | Cifras reales del bloque "Who we are": 5+ años, 200+ viajeros (el design system dice 150+), 25K+ comunidad | Equipo | Home |
| 9 | Accesos para el desarrollador: Vercel, Sanity, Brevo, dominio/DNS, PostHog, Meta. Antes, crear el correo del equipo `tech@travelsoultosoul.com` con el que se abren todas las cuentas (el desarrollador entra como miembro con su propio correo). GitHub [RESUELTO 2026-10-26]: organización `soul-to-soul-travel`, repo privado `soul-to-soul-web`; falta invitar al desarrollador como colaborador del repo | Equipo | Técnico |

## Decisiones de contenido por cerrar

| # | Pendiente | Le toca |
|---|---|---|
| 10 | [RESUELTO 2026-10-26] Hero: versión del design system, frase fija "yourself" | — |
| 11 | [RESUELTO 2026-10-26] Extensiones: Sierra Nevada (coming soon), San Andrés, Barichara, Boyacá y Oaxaca al final como adelanto de México | — |
| 12 | [RESUELTO 2026-10-26] Los viajes se llaman **Coffee Region** y **Bogotá** (ES: Región Cafetera y Bogotá). Kabai y Bacatá quedan retirados. Ver #37 | — |
| 13 | About: el equipo aparece en dos formatos en el prototipo; elegir uno | Equipo |
| 14 | Sierra Nevada "Coming soon": ¿sin enlace o con lista de espera? | Equipo |
| 15 | Artículos nuevos para las ventanas del Home (los títulos del prototipo son de relleno) y quién traduce los del blog actual | Equipo |
| 16 | Concepto del quiz de arquetipos (swipe tipo Tinder): está en el alcance del desarrollador; se cierra en conjunto con el equipo | Dev + Equipo |
| 37 | Reescribir los pasajes del copy que dependían de los nombres Kabai y Bacatá: título y hero, la sección 02 que explica la palabra, el bloque "Nombre del viaje", la URL (`/journeys/kabai-coffee-region` pasa a `/journeys/coffee-region`), meta title y H1. Archivos: `04-contenido/coffee-region-kabai-contenido-web.md`, `04-contenido/bogota-bacata-contenido-web.md` y sus versiones en `es/` | Equipo |

## Encontrados al exportar el contenido de Notion (2026-10-26)

| # | Pendiente | Le toca |
|---|---|---|
| 21 | **Viajes privados o grupos pequeños:** los viajes ahora son privados, pero las FAQs y el borrador de About ("Small groups") siguen diciendo grupos pequeños. El prototipo de About tiene el pilar "Small groups" | Equipo |
| 22 | **FAQs:** dos notas internas que NO se publican ("Internal note, not for the traveler" y la nota de fiebre amarilla/CARDER), falta el link de pago y el documento va firmado "RAÍZ · Soul to Soul Travel", aunque "Raíz" no debe aparecer en público | Equipo — Dev: no publicar esas notas |
| 23 | **Kabai (Eje Cafetero):** falta el título y el tercer pilar en la sección 03; las 11 leyendas de la galería; los 3 testimonios; y la línea de consentimiento de la sección 13 (en pausa). "Perfect for" pasa a "Ideal for" | Equipo |
| 24 | **Bacatá (Bogotá):** no existen las secciones 05 Gallery, 07 Where you stay, 12 In their words ni 13 Not ready to talk yet?; el precio USD 2.300 es tentativo; el tercer pilar tiene tres opciones sin decidir; la versión corta de la nota de Aída no está aprobada | Equipo |
| 25 | **Cifra de viajeros:** "200+" en las páginas de viaje y en el Home, "150+" en Who we are y en el design system | Equipo |
| 26 | **About:** el esqueleto de contenido en Notion está casi todo en [TBD]: intro, historia, biografías y pilares | Equipo |
| 27 | **Blog:** decidir si el bloque de 10 posts de 2020 (bienestar, ley de la atracción) encaja con la marca antes de traducirlo; resolver los 2 posts "por revisar"; descargar las imágenes de Squarespace antes de cerrar la cuenta | Equipo |

## Encontrados al traducir al español (2026-10-26)

Cada archivo de `04-contenido/es/` marca sus dudas con [REVISAR]. Las que afectan también la versión en inglés son estas:

| # | Pendiente | Le toca |
|---|---|---|
| 28 | **Idioma del guía:** el copy dice "English-speaking private guide". ¿En la versión en español se ofrece guía en español? | Equipo |
| 29 | **Acompañamiento:** About dice que "al menos uno de nosotros" acompaña el viaje y que María "camina a tu lado", pero las FAQs dicen que el soporte es remoto | Equipo |
| 30 | **Instagram:** el footer dice @soultosoul y las FAQs dicen travelsoultosoul. ¿Cuál es? | Equipo |
| 31 | **FAQs:** "RAÍZ" aparece 7 veces en copy público (título, firma, kit de viaje…). En la versión en español se reformuló; falta ajustar el inglés | Equipo |
| 32 | **About:** el párrafo de Nusa Penida es texto de relleno; los nombres de la red de anfitriones hay que confirmarlos (mencionan La Guajira, Cartagena y Chocó, que no están en la oferta actual) | Equipo |
| 33 | **Home:** el subtítulo del carrusel de extensiones ("a city to settle into, or a trek…") ya no encaja con la nueva lista (no hay ciudades ni trekking) | Equipo |
| 34 | **Why Colombia:** el par "Mountain, then the ocean" no muestra el mar en ninguno de los dos videos | Equipo |
| 35 | **Bacatá:** la opción A del tercer pilar es "Raíces", demasiado cerca de "Raíz" | Equipo |
| 36 | **Bacatá:** "transporte privado durante todo el viaje" no está costeado para la tarde y las comidas libres | Equipo |

## Técnicos por decidir con el desarrollador

| # | Pendiente | Le toca |
|---|---|---|
| 17 | Fotos: Sanity assets o Cloudinary (el readme del design system menciona Cloudinary, pero no está decidido) | Dev + Equipo |
| 18 | Herramienta del banner de consentimiento de cookies | Dev |
| 19 | Comportamiento de las ventanas en móvil (tap o al entrar en pantalla) | Dev |
| 20 | Pipeline de optimización de imágenes (las ilustraciones originales pesan 10–17 MB) | Dev |
| 38 | Pulido de diseño: unificar espaciado, escala tipográfica, botones, radios e ilustraciones según `05-tecnico/pulido-de-diseno.md`. Primero el Home, revisión conjunta y de ahí las reglas para el resto | Dev |
| 39 | Home en móvil: el prototipo no está adaptado (a 390 px desborda); se construye responsive desde el inicio con el breakpoint del design system | Dev |

## Fuera de la v1 (v2)

- Testimonials (página propia)
- Careers
- Our Team como página aparte (en la v1 vive dentro de About)
