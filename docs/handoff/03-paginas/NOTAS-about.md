# About Us — notas para el desarrollo

Estado: [DISEÑADA]

## 1. Dónde está

| Qué | Ruta |
|---|---|
| Código fuente del prototipo | `03-paginas/02-about/fuente/About.dc.html` |
| Imágenes que usa | `03-paginas/02-about/fuente/assets/` (incluye `illustrations/orquidea-sin-tallo.png` y `symbols/sunburst-eye.png`, que NO están en el design system general) |
| Design system embebido | `fuente/_ds/` — tokens idénticos a `02-design-system/tokens/` (verificado el 2026-10-26) |

Para verla: abrir el proyecto "About" en Claude Design (pedir acceso a Soul / Sebas) o leer `About.dc.html`, que es HTML legible. No hay exportación standalone de esta página en el paquete.

## 2. Secciones

1. Hero — "Who we are"
2. Our Story — "A trip with no return ticket" + nota de la fundadora (Callout sobre Coffee, firma Aída Henao)
3. The team — "The people behind the journeys": Aída Henao, Sebastián Salazar, María Rincón, Viviana Castañeda
4. The difference — "Why us": Colombian-owned · Women-led · Firsthand · Small groups · Decision Detox
5. Closing CTA — "Each journey begins with a conversation"

Anclas que otras páginas usan: el Home tiene "Meet the team" (→ `/about#team`) y el footer tiene "Our Story" (→ `/about#story`) y "Our Team" (→ `/about#team`).

## 3. Pendientes de esta página

| # | Qué | Estado |
|---|---|---|
| 1 | Fotos reales. El prototipo tiene espacios vacíos (image slots) con la instrucción de qué foto va: pareja de fundadores de espaldas; retratos de Aída, Sebastián, María y Viviana; red de anfitriones (Don José, tejedora, anfitrión de montaña, artista, guía de aves) | [PENDIENTE] — fotos a cargo del equipo |
| 2 | El equipo aparece en dos formatos dentro del prototipo (tarjetas y grilla). Construir uno solo | [PENDIENTE] — cuál de los dos |
| 3 | Versión en español: traducción preliminar en `04-contenido/es/` | [PENDIENTE DE REVISIÓN] |
| 4 | El CTA final lleva al quiz de arquetipos, igual que "Enquire Now" | [DECIDIDO 2026-10-26] |
