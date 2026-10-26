# Home — notas para el desarrollo

Estado: [DISEÑADA] con cambios decididos el 2026-10-26 que el prototipo todavía NO refleja (ver sección 3).

## 1. Dónde está

| Qué | Ruta en este paquete |
|---|---|
| Vista para abrir en el navegador (doble clic, funciona sin internet) | `03-paginas/01-home/VISTA-home.html` |
| Código fuente del prototipo | `02-design-system/templates/website/Website.dc.html` + `sections.jsx` |
| Componentes que usa | `02-design-system/components/` (Header, JourneySection, Window, Callout, Quote, KeepSeeking, Footer, NewsletterForm…) |
| Video real del hero | Drive: `Raíz/Home/Hero Video/Video Hero Raiz.mp4` (carpeta hermana de este paquete) |
| Recortes, texturas y sombra botánica originales | Drive: `Raíz/Home/Cropped images`, `Raíz/Home/Texturas`, `Raíz/Home/Sombras` |

El prototipo corre dentro de Claude Design (archivos `.dc.html` + JSX en el navegador). Es una **implementación de referencia**: todas las decisiones visuales están resueltas ahí, pero el sitio se construye de cero en Next.js. No copiar el `support.js`, `ds-base.js`, `tweaks-panel.jsx` ni el panel de "Tweaks" — son herramientas del prototipo.

## 2. Orden de secciones (tal como está en `sections.jsx`)

1. Header (sticky; al bajar ~120px colapsa a la píldora Terracotta con el sello)
2. Intro canvas: Hero ("Modern life is good at keeping you busy, distracted, disconnected." → "Our journeys are designed for reconnecting to yourself") + video de Colombia 21:9 + bloque "Who we are" con stats
3. How we travel — tres pilares con símbolos ancestrales
4. Destinations — encabezado + dos `JourneySection` (formato "booking panel"), alternando Coconut y Coffee
5. "Not ready to go home yet?" — carrusel Arc/Fan de extensiones
6. Windows of Colombia — ventanas que se abren al hover; es la puerta al blog (Inspiration)
7. Testimonial — un testimonio editorial grande
8. FAQ — acordeón, la pregunta de seguridad va primera
9. Final CTA (fondo Palm) — "Each journey begins with a conversation."
10. Newsletter — "A slow letter, once a month."
11. Keep Seeking — revelado con spotlight del cursor sobre el páramo
12. Footer (Coffee)

## 3. Cambios decididos que hay que aplicar sobre el prototipo

| # | Cambio | Estado |
|---|---|---|
| 1 | **Viajes principales: Eje Cafetero + Bogotá.** Bogotá reemplaza a Sierra Nevada en el primer `JourneySection` (fondo Coconut, foto a la izquierda). El Eje Cafetero sigue en el segundo (fondo Coffee, espejado). Contenido de Bogotá: `04-contenido/bogota-bacata-contenido-web.md` | [DECIDIDO] — nombre visible ("Bogotá" o "Bacatá") [PENDIENTE] |
| 2 | **Sierra Nevada pasa a "Coming soon"** dentro del carrusel de extensiones (la tarjeta lleva el badge `Coming soon`, ya soportado por `JourneyCard`) | [DECIDIDO] |
| 3 | **Lista del carrusel de extensiones, en este orden:** Sierra Nevada (coming soon), San Andrés, Barichara, Boyacá y, al final, **Oaxaca (México)**, presentada de forma que se entienda que es un adelanto de los viajes a México (por ejemplo, eyebrow "Mexico · Coming soon" o un separador "Beyond Colombia"). Salen Bogotá, Medellín, Cartagena, Ciudad Perdida y Nevado del Ruiz | [DECIDIDO 2026-10-26] |
| 4 | **Precios:** los USD 3.200 / 2.400 del prototipo son de relleno. El precio es un campo del CMS; si está vacío, el bloque de precio no se muestra | [DECIDIDO] |
| 5 | **Pilares:** Balance · Connection · **Firsthand** (no "Craft") | [DECIDIDO] — el código del prototipo ya dice Firsthand |
| 6 | **CTA principal:** "Enquire Now" (header y How we travel) y "Get in Touch" (Final CTA) llevan al **quiz de arquetipos**, que es parte del alcance de este desarrollo (`03-paginas/10-quiz-arquetipos`) | [DECIDIDO 2026-10-26] |
| 7 | **Hero:** se usa la versión del design system, con la frase fija "…reconnecting to yourself" (sin palabra rotativa). Existe una versión anterior con palabra rotativa en el proyecto About; no es la vigente | [DECIDIDO 2026-10-26] |
| 8 | **Video:** el prototipo pone una foto con botón de play. Usar el video real (ver sección 1), autoplay silenciado en loop, sin texto encima, con póster y versión liviana para móvil | [DECIDIDO] |
| 9 | **Stats "5+ años / 200+ viajeros / 25K+ comunidad":** el readme del design system dice "150+ travelers" de Tidur. Confirmar cifras reales antes de publicar | [PENDIENTE] |
| 10 | **Testimonio y FAQs del prototipo son de ejemplo.** Contenido real desde el CMS; FAQs base en `04-contenido/faqs-generales.md` | [DECIDIDO] |
| 11 | **Windows of Colombia:** cada ventana enlaza a un artículo del blog (Inspiration). Los títulos actuales ("A morning in the Sierra", "Bogotá in three meals"…) son de relleno hasta migrar/escribir artículos | [DECIDIDO] |
| 12 | **Bilingüe EN/ES desde el lanzamiento** (next-intl). El copy del prototipo está en inglés; la traducción preliminar al español está en `04-contenido/es/` | [DECIDIDO] — revisión de la traducción: [PENDIENTE] |

## 4. Detalles de implementación que no son obvios en el prototipo

- Ventanas (Window): en móvil no hay hover. Decidir apertura al tap o al entrar en viewport (IntersectionObserver). Respetar `prefers-reduced-motion`.
- Las ilustraciones de acuarela pesan 10–17 MB cada una en `02-design-system/assets/illustrations/`. Generar versiones web (WebP/AVIF, máximo ~1400 px) en el build; nunca servir los PNG originales.
- Botánicas "de costura" (monstera entre Testimonial/FAQ, banano saliendo del Final CTA): ver regla "Botanical illustrations have gravity" en `02-design-system/readme.md`.
- Texturas de fondo: `mix-blend-mode: luminosity` a ~0.35 sobre sección con `isolation: isolate` (ver `02-design-system/design-decisions.md`).
