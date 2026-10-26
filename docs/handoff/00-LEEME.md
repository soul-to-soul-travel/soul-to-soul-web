# Sitio web Soul to Soul Travel — paquete para el desarrollador

Versión del paquete: 2026-10-26.

Empieza aquí. Este documento dice qué hay en cada carpeta, en qué orden leerlo y qué manda cuando dos fuentes no coinciden.

## Qué vas a construir

El nuevo sitio de Soul to Soul Travel: viajes privados por Colombia para viajeros internacionales (EE. UU., Canadá y Europa). Es bilingüe (EN/ES) desde el lanzamiento, en Next.js 15 + Sanity + Vercel.

| # | Página | Estado | Carpeta |
|---|---|---|---|
| 1 | Home | [DISEÑADA] con cambios decididos | `03-paginas/01-home` |
| 2 | About Us | [DISEÑADA] | `03-paginas/02-about` |
| 3 | Página de viaje — Coffee Region (Kabai). **Es la plantilla de todos los viajes** | [DISEÑADA] | `03-paginas/03-plantilla-viaje-coffee-region` |
| 4 | Why Colombia | [DISEÑADA] — faltan medios | `03-paginas/04-why-colombia` |
| 5 | Inspiration (blog) + migración del blog actual | [SIN DISEÑO] — brief | `03-paginas/05-inspiration-blog` |
| 6 | Destinations | [SIN DISEÑO] — brief | `03-paginas/06-destinations` |
| 7 | Página de viaje — Bogotá (Bacatá) | Usa la plantilla 3 | `03-paginas/07-viaje-bogota` |
| 8 | Letter from the founders | [SIN DISEÑO] [SIN COPY] — brief | `03-paginas/08-letter-from-the-founders` |
| 9 | Legales: Privacy, Terms, Cookies | [SIN DISEÑO] [SIN TEXTO] — brief | `03-paginas/09-legales` |
| 10 | Quiz de arquetipos de viajero (destino de todos los CTA) | [EN ALCANCE] — concepto por cerrar con el equipo | `03-paginas/10-quiz-arquetipos` |

Fuera de la v1: Testimonials (como página propia) y Careers.

## Orden de lectura

1. Este archivo.
2. `PENDIENTES.md` — qué está abierto y a quién le toca.
3. `02-design-system/readme.md` — la marca completa: dirección creativa, voz, paleta, tipografía, layout, iconografía y componentes.
4. `02-design-system/design-decisions.md` — log de decisiones de diseño, con lo que se probó y se descartó.
5. `05-tecnico/stack-e-integraciones.md`.
6. Por cada página: su `NOTAS-*.md` o `BRIEF-*.md`, abrir su `VISTA-*.html` y leer su contenido en `04-contenido/`.

## Carpetas

| Carpeta | Qué hay |
|---|---|
| `01-marca/` | Manual de marca oficial VF 2026 (PDF) · logos SVG listos para usar + masters editables · fuentes (WOFF2 de Milanesa y Better Yesterday; Avenir LT Std solo en OTF) · "Keep Seeking" en SVG |
| `02-design-system/` | Design system completo exportado de Claude Design: `tokens/` (CSS + `tokens.json`), `components/` (16 componentes React de referencia), `templates/website/` (fuente del Home), `guidelines/` (fichas de colores, tipografía, espaciado, marca), `assets/` (logos, símbolos, acuarelas, 22 fotos, texturas, formas orgánicas), `explorations/` (alternativas comparadas antes de cada decisión) |
| `03-paginas/` | Una carpeta por página: `VISTA-*.html` para abrir con doble clic, `fuente/` con el prototipo y `NOTAS`/`BRIEF` con decisiones y pendientes |
| `04-contenido/` | Copy exportado de Notion: Coffee Region (Kabai), Bogotá (Bacatá), plantilla de página de viaje, guía de comunicación, FAQs, contenido de About, arquitectura de información, inventario del blog para migrar. En `04-contenido/es/` está la **traducción preliminar al español** (Home, About, Why Colombia, FAQs, Kabai, Bacatá), marcada [TRADUCCIÓN PRELIMINAR — REVISAR] |
| `05-tecnico/` | Stack e integraciones + el plan de desarrollo exportado de Notion |
| `AGENTS.md` / `CLAUDE.md` | Reglas para Codex / Claude Code. Copiarlos a la raíz del repo |

Medios originales que no se duplicaron aquí (están en carpetas hermanas de esta, dentro de `Raíz/` en el mismo Drive):
- Video del hero: `Home/Hero Video/`
- Fotos del Eje Cafetero: `Viaje Eje C/`
- Fotos de Bogotá: `Bacatá Bogotá Journey/Fotos Bogota/`

## Qué manda cuando algo no coincide

1. Las decisiones del 2026-10-26 en los `NOTAS-*.md` y en `PENDIENTES.md`.
2. `02-design-system/readme.md`, `design-decisions.md` y `tokens/`.
3. Los prototipos (`.dc.html`, `.jsx`).
4. Cualquier página de Notion anterior. La página "Design System" de Notion (mayo–junio) quedó superada por el design system de esta carpeta.

Para el copy: el texto de `04-contenido/` (Notion) vale sobre el texto escrito dentro de los prototipos.

## Sobre los prototipos

Se hicieron en Claude Design. Los archivos `.dc.html` y `.jsx` corren dentro de esa herramienta. Son una **implementación de referencia**: todas las decisiones visuales y de comportamiento están resueltas ahí, pero el sitio se construye de cero en Next.js. No hay que portar el runtime del prototipo (`support.js`, `ds-base.js`, `image-slot.js`, `_ds_bundle.js`, `tweaks-panel.jsx`). Los tokens CSS (`02-design-system/tokens/`) sí se reutilizan tal cual.

Los `VISTA-*.html` son autocontenidos: se abren con doble clic, sin internet.

## Cambios hechos al preparar este paquete

- Se excluyeron del design system los archivos que no son de este sitio y el material de trabajo: `scraps/`, `screenshots/`, `uploads/` y otras plantillas como emails y presentación.
- `CLAUDE.md` del design system se renombró a `design-decisions.md`, para que no choque con el `CLAUDE.md` del repo.
- En el design system se corrigieron dos referencias desactualizadas: el pilar "Craft" pasa a "Firsthand", y el CTA del header "Book a Call" pasa a "Enquire Now".
- El `readme.md` que viene dentro de `03-paginas/02-about/fuente/_ds/` es una copia anterior. Vale el de `02-design-system/`.

## Contacto

Dudas de contenido y marca: Soul / Sebas (Soul to Soul Travel). Toda decisión que cierre un `[PENDIENTE]` se anota en `PENDIENTES.md` con su fecha.
