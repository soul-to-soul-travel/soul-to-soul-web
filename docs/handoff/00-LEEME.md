---
proyecto: Sitio web Soul to Soul Travel
version_paquete: 2026-10-26
audiencia: modelos de IA (Claude, Codex, Cursor) y el desarrollador (Manuel, "el paisa")
idioma: español; el copy del sitio está en inglés con traducción preliminar al español
repo: github.com/soul-to-soul-travel/soul-to-soul-web (privado)
version_para_humanos: Google Doc "00 · Léeme — Empieza aquí (para humanos)" en la carpeta del paquete en Drive, https://docs.google.com/document/d/1glbZZLO1QSumFvVTIUdkRYjL_uJAybX4Wt1oCB5VSk4/edit
---

# Paquete de entrega del sitio web — índice para IA

> **Si estás leyendo esto en el repo** (`docs/handoff/`): aquí solo está el texto. Las rutas de este archivo son relativas al paquete del Drive; `03-paginas/` está plana en el repo y los prototipos, assets, fuentes, fotos y el brandbook viven solo en el Drive. Detalle en `LEEME-REPO.md`.

Este archivo es el punto de entrada para un modelo de IA que tenga conectada esta carpeta. Describe qué hay en cada lugar, qué manda cuando hay contradicciones y dónde está la respuesta a cada tipo de pregunta. La versión para leer como persona es el Google Doc de esta misma carpeta.

## 1. Qué es esto en tres líneas

- Especificación completa para construir el nuevo sitio de **Soul to Soul Travel**: viajes privados por Colombia para viajeros internacionales (EE. UU., Canadá y Europa).
- Stack decidido: **Next.js 15 + TypeScript + Tailwind + next-intl (EN/ES) + Sanity + Vercel**.
- Los diseños se hicieron en Claude Design. Aquí están exportados como prototipos de referencia, junto con el design system, el copy y las decisiones.

## 2. Instrucciones para el modelo

1. Antes de responder cualquier pregunta sobre una página, lee su `NOTAS-*.md` o `BRIEF-*.md` en `03-paginas/<página>/`. Ahí están las decisiones más recientes.
2. Cita siempre la ruta del archivo del que sale la respuesta.
3. Si algo está marcado `[PENDIENTE]`, dilo así. No completes el hueco con una suposición.
4. Para preguntas de marca o de diseño visual, la fuente es `02-design-system/readme.md` y después `02-design-system/design-decisions.md`.
5. Para el copy (textos del sitio), la fuente es `04-contenido/`, no el texto escrito dentro de los prototipos.
6. Los archivos `.dc.html`, `.jsx` y `VISTA-*.html` son prototipos que corren dentro de Claude Design. Úsalos para entender layout y comportamiento, nunca como código para copiar tal cual.
7. "Raíz" es un nombre **interno** del proyecto. Nunca aparece en el sitio publicado.
8. Para construir código, sigue además `AGENTS.md` (convenciones fijas).

## 3. Orden de autoridad (qué manda cuando dos fuentes no coinciden)

| Prioridad | Fuente | Ruta |
|---|---|---|
| 1 | Decisiones fechadas 2026-10-26 | `03-paginas/*/NOTAS-*.md`, `PENDIENTES.md` |
| 2 | Design system: reglas y tokens | `02-design-system/readme.md`, `02-design-system/design-decisions.md`, `02-design-system/tokens/` |
| 3 | Copy | `04-contenido/*.md` (EN), `04-contenido/es/*.md` (ES preliminar) |
| 4 | Prototipos | `03-paginas/*/fuente/`, `02-design-system/templates/website/`, `02-design-system/components/` |
| 5 | Notion anterior a octubre de 2026 | No está en el paquete; si se cita, está superado |

## 4. Mapa de carpetas

| Ruta | Qué contiene | Léelo cuando… |
|---|---|---|
| `00-LEEME.md` | Este índice | Siempre primero |
| `AGENTS.md` / `CLAUDE.md` | Reglas de código: stack, convenciones fijas, performance | Vas a escribir código |
| `PENDIENTES.md` | 36 pendientes numerados con dueño (Equipo / Dev); los abiertos también son issues en GitHub | Algo no está claro o falta |
| `01-marca/LEEME-marca.md` | Mapa de la marca: dónde está cada cosa (manual, logos, fuentes, fotos, ilustraciones, texturas, formas, símbolos) | Cualquier pregunta de "dónde está X de la marca" |
| `01-marca/brandbook/` | Manual de marca oficial VF 2026 (PDF) | Dudas de marca que el design system no cubre |
| `01-marca/logos/` | 5 lockups SVG (horizontal, vertical, logotype, isotype, stamp) en `currentColor` y tintes, más `masters-editables/` | Necesitas el logo |
| `01-marca/fuentes/` | Milanesa Serif y Better Yesterday (WOFF2/WOFF/OTF) y Avenir LT Std (solo OTF) | Configurar tipografías. Licencia web [PENDIENTE] (#1) |
| `01-marca/keep-seeking/` | Lettering "Keep Seeking" en SVG | Pre-footer / tagline |
| `01-marca/fotos-seleccionadas/` | Fotos elegidas por el equipo, por carpeta: Colombia general (24), Coffee Region (46), Bogotá (6), Home (1). Ver `LEEME-fotos.md` ahí | Necesitas una foto para cualquier sección. Nunca stock |
| `02-design-system/readme.md` | La marca completa: dirección creativa, voz, paleta, tipografía, layout, iconografía, índice de componentes | Cualquier decisión visual o de tono |
| `02-design-system/design-decisions.md` | Log de decisiones de diseño: qué se probó, qué se revirtió y por qué | Antes de "mejorar" algo ya decidido |
| `02-design-system/tokens/` | Variables CSS (`colors`, `typography`, `spacing`, `radius-motion`, `fonts`, `base`) y `tokens.json` | Configurar Tailwind o el CSS base |
| `02-design-system/components/` | 16 componentes React de referencia (`.jsx`, con tipos en `.d.ts`, ficha `.card.html` y guía `.prompt.md`) | Implementar un componente |
| `02-design-system/guidelines/` | Fichas visuales: colores, tipografía, espaciado, marca, do's & don'ts | Ver una regla en contexto |
| `02-design-system/templates/website/` | Fuente del Home (`Website.dc.html` + `sections.jsx`) | Implementar el Home |
| `02-design-system/explorations/` | Alternativas comparadas antes de cada decisión | Entender por qué se eligió algo |
| `02-design-system/assets/` | Logos, símbolos ancestrales, acuarelas (10–17 MB c/u, optimizar), 24 fotos, texturas, formas orgánicas | Necesitas un asset |
| `03-paginas/` | Una carpeta por página (ver sección 5) | Construir una página |
| `04-contenido/` | Copy exportado de Notion (EN), plantilla de página de viaje, guía de comunicación, FAQs, inventario del blog | Necesitas el texto de una página |
| `04-contenido/es/` | Traducción preliminar al español, marcada [TRADUCCIÓN PRELIMINAR — REVISAR] | Versión ES del sitio |
| `05-tecnico/` | Stack e integraciones; `pulido-de-diseno.md` (qué conservar y qué unificar en los prototipos); plan de desarrollo de Notion; `para-el-repo/` (los archivos que ya están en GitHub) | Infraestructura e integraciones |

## 5. Páginas del sitio

| # | Página | Ruta sugerida | Estado | Notas o brief | Vista (doble clic) | Copy EN | Copy ES |
|---|---|---|---|---|---|---|---|
| 1 | Home | `/` | [DISEÑADA] con cambios del 2026-10-26 | `03-paginas/01-home/NOTAS-home.md` | `03-paginas/01-home/VISTA-home.html` | prototipo | `04-contenido/es/home-es.md` |
| 2 | About Us | `/about` | [DISEÑADA] | `03-paginas/02-about/NOTAS-about.md` | — (fuente: `fuente/About.dc.html`) | `04-contenido/about-who-we-are-contenido.md` | `04-contenido/es/about-es.md` |
| 3 | Página de viaje — Coffee Region. **Plantilla de todos los viajes** | `/journeys/[slug]` | [DISEÑADA] | `03-paginas/03-plantilla-viaje-coffee-region/NOTAS-plantilla-viaje.md` | `…/VISTA-coffee-region.html` | `04-contenido/coffee-region-kabai-contenido-web.md` | `04-contenido/es/coffee-region-kabai-es.md` |
| 4 | Why Colombia | `/why-colombia` | [DISEÑADA], faltan medios | `03-paginas/04-why-colombia/NOTAS-why-colombia.md` | `…/VISTA-why-colombia.html` | prototipo (`fuente/`) | `04-contenido/es/why-colombia-es.md` |
| 5 | Inspiration (blog) + migración | `/inspiration`, `/inspiration/[slug]` | [SIN DISEÑO] — brief | `03-paginas/05-inspiration-blog/BRIEF-inspiration.md` | — | `04-contenido/inventario-blog-migracion.md` | — |
| 6 | Destinations | `/destinations` | [SIN DISEÑO] — brief | `03-paginas/06-destinations/BRIEF-destinations.md` | — | — | — |
| 7 | Viaje Bogotá | `/journeys/[slug]` | Usa la plantilla 3 | `03-paginas/07-viaje-bogota/BRIEF-viaje-bogota.md` | — | `04-contenido/bogota-bacata-contenido-web.md` | `04-contenido/es/bogota-bacata-es.md` |
| 8 | Letter from the founders | `/letter-from-the-founders` | [SIN DISEÑO] [SIN COPY] | `03-paginas/08-letter-from-the-founders/BRIEF-letter-from-the-founders.md` | — | [PENDIENTE] | [PENDIENTE] |
| 9 | Legales: Privacy, Terms, Cookies | `/legal/[slug]` | [SIN DISEÑO] [SIN TEXTO] | `03-paginas/09-legales/BRIEF-legales.md` | — | [PENDIENTE] | [PENDIENTE] |
| 10 | Quiz de arquetipos (destino de todos los CTA) | `/find-your-journey` (nombre [PENDIENTE]) | [EN ALCANCE], concepto por cerrar | `03-paginas/10-quiz-arquetipos/BRIEF-quiz-arquetipos.md` | — | — | — |

Fuera de la v1: Testimonials (como página propia), Careers y Our Team como página aparte.

## 6. Decisiones cerradas (2026-10-26)

- **Home:** se usa la versión del design system, con el hero de frase fija "…reconnecting to *yourself*".
- **Viajes principales del Home:** Bogotá y Coffee Region. Sierra Nevada pasa a "Coming soon".
- **Nombres de los viajes:** se llaman simplemente **Coffee Region** y **Bogotá** (en español: Región Cafetera y Bogotá). Los nombres Kabai y Bacatá quedan retirados: no van en el sitio, en las URLs ni en los metadatos. Los archivos de copy en `04-contenido/` todavía los usan en el título, el hero, la sección que explica la palabra y el SEO; esos pasajes están [POR REESCRIBIR] (pendiente #37 en `PENDIENTES.md`). Mientras tanto, donde el copy diga "Kabai Journey" léase "Coffee Region Journey" y donde diga "Bacatá Journey" léase "Bogotá Journey".
- **Orden de trabajo:** primero el Home, completo y pulido. Se revisa en conjunto y de esa revisión salen las reglas (espaciado, tipografía, retícula, uso de ilustraciones) que se aplican al resto de páginas.
- **Pulido de diseño es parte del alcance.** Los prototipos tienen inconsistencias de márgenes, tamaños de letra y cantidad de elementos decorativos; el desarrollador las unifica conservando lo que funciona (el hero que se convierte en el sello, la luz de Keep Seeking en el páramo, las ventanas que se abren, las ilustraciones). Detalle en `05-tecnico/pulido-de-diseno.md`.
- **Cuentas y herramientas:** toda cuenta nueva (Vercel, Sanity, Resend, Brevo, PostHog, dominio) se crea con el correo del equipo `tech@travelsoultosoul.com` [PENDIENTE: crear ese correo], para que Soul to Soul sea dueña desde el primer día. El desarrollador entra en cada herramienta como miembro con su propio correo, nunca como dueño.
- **Carrusel de extensiones, en orden:** Sierra Nevada (coming soon), San Andrés, Barichara, Boyacá y Oaxaca al final, como adelanto de México.
- **Pilares:** Balance · Connection · **Firsthand** ("Craft" quedó retirado).
- **CTA principal:** "Enquire Now" / "Get in Touch". Lleva al quiz de arquetipos, que construye el desarrollador.
- **Precios:** son un campo del CMS. Los precios de los prototipos son de relleno; si el campo está vacío, no se muestran.
- **Idiomas:** EN + ES desde el lanzamiento.
- **Newsletter:** Brevo.
- **Repo:** GitHub `soul-to-soul-travel/soul-to-soul-web`.
- **Inspiration y Journal** son la misma sección (el blog). Los posts sobre Asia no se migran.
- **Coffee Region es la plantilla** de todas las páginas de viaje. Lo regional entra de forma sutil (fotografía, ilustración, copy), nunca cambiando la paleta.

## 7. Pendientes que bloquean el lanzamiento

Detalle en `PENDIENTES.md`: #1 licencias de fuentes · #3 revisión de la traducción · #4 textos legales · #5 Letter from the founders · #6 fotos del equipo · #7 medios de Why Colombia · #8 cifras · #9 accesos (Vercel, Sanity, Brevo, DNS, PostHog, Meta).

## 8. Glosario

| Término | Significado |
|---|---|
| Raíz | Nombre interno de la línea de viajes por Colombia. **Nunca** se publica |
| Tidur | Viaje insignia anterior por Asia (Singapur, Bali, Camboya), cerrado en 2026 |
| Kabai Journey | Nombre anterior del viaje al Eje Cafetero. Retirado el 2026-10-26: el viaje se llama **Coffee Region**. Aparece todavía en los archivos de copy |
| Bacatá Journey | Nombre anterior del viaje a Bogotá. Retirado el 2026-10-26: el viaje se llama **Bogotá**. Aparece todavía en los archivos de copy |
| Windows of Colombia | Componente firma: ventanas coloniales pastel que se abren al hover. Es la puerta al blog |
| Firsthand | Tercer pilar de "How we travel" (reemplazó a "Craft") |
| Coconut / Light / Coffee / Terracotta / Palm | Los 5 colores de marca: `#F0E8D5` / `#F7F4F0` / `#503421` / `#A35940` / `#D3C381` |
| Hushpitality | Principio visual: calma, silencio, mucho espacio en blanco |
| Keep Seeking | Tagline de la marca. No se traduce |
| Prototipo `.dc.html` | Archivo de Claude Design. Referencia visual, no código de producción |
| `[PENDIENTE]`, `[DECIDIDO]`, `[SIN DISEÑO]`… | Etiquetas de estado usadas en todo el paquete |

## 9. Dónde está la respuesta (preguntas típicas)

| Pregunta | Archivo |
|---|---|
| ¿Qué colores, tipografías o espaciados uso? | `02-design-system/readme.md` + `02-design-system/tokens/` |
| ¿Cómo debe verse o comportarse el botón, el header o el footer? | `02-design-system/components/<grupo>/<Componente>.jsx` y su `.d.ts` / `.prompt.md` |
| ¿Por qué se decidió X y no Y? | `02-design-system/design-decisions.md` y `02-design-system/explorations/` |
| ¿Qué secciones tiene la página Z y qué cambió? | `03-paginas/<Z>/NOTAS-*.md` o `BRIEF-*.md` |
| ¿Cuál es el texto exacto de una sección? | `04-contenido/` (EN) o `04-contenido/es/` (ES) |
| ¿Qué campos tiene una página de viaje en el CMS? | `04-contenido/plantilla-pagina-de-viaje.md` |
| ¿Cómo se escribe para la marca? | `04-contenido/journey-page-communication-guidelines.md` + readme del design system, sección CONTENT FUNDAMENTALS |
| ¿Qué falta o qué está sin decidir? | `PENDIENTES.md` (y los issues del repo) |
| ¿Qué artículos del blog se migran? | `04-contenido/inventario-blog-migracion.md`. El blog actual está en https://www.travelsoultosoul.com/blog (29 artículos; 22 se migran) |
| ¿Dónde están los logos, las fuentes, las fotos, las ilustraciones o las texturas? | `01-marca/LEEME-marca.md` |
| ¿Qué herramientas e integraciones van? | `05-tecnico/stack-e-integraciones.md` |
| ¿Por dónde empiezo y qué hay que pulir del diseño? | `05-tecnico/pulido-de-diseno.md` (primero el Home) |
| ¿Con qué correo se crean las cuentas de las herramientas? | `tech@travelsoultosoul.com` (sección 6 de este archivo) |
| ¿Dónde están las fotos y el video originales? | Fuera de esta carpeta (ver sección 10) |

## 10. Lo que NO está en este paquete

Está en el mismo Drive, en carpetas hermanas dentro de `Raíz/`:
- Video del hero: `Home/Hero Video/`
- Fotos originales del Eje Cafetero: `Viaje Eje C/` (galería, hoteles, extensiones)
- Fotos de Bogotá: `Bacatá Bogotá Journey/Fotos Bogota/`

Los prototipos editables viven en Claude Design (cuenta de Soul to Soul). Lo que está aquí es su exportación.
