# Stack e integraciones

Resumen de lo decidido al 2026-10-26. La historia completa de las decisiones está en `stack-tecnico-y-plan-de-desarrollo.md` (exportado de Notion). Si ese documento contradice esta tabla, vale la tabla.

| Capa | Herramienta | Estado |
|---|---|---|
| Framework | Next.js 15 (App Router) + TypeScript | [DECIDIDO] |
| Estilos | Tailwind CSS, mapeando los tokens CSS del design system | [DECIDIDO] |
| Idiomas | next-intl, **EN + ES desde el lanzamiento** | [DECIDIDO] |
| CMS | Sanity: viajes, extensiones, artículos del blog, testimonios, FAQs | [DECIDIDO] |
| Imágenes | Sanity assets o Cloudinary | [PENDIENTE] |
| Hosting | Vercel (cuenta Team) | [DECIDIDO] |
| Repositorio | GitHub, organización de la empresa (ya existe) | [DECIDIDO] — nombre del repo y accesos [PENDIENTE] |
| Newsletter | Brevo | [DECIDIDO] |
| Email transaccional | Resend | [DECIDIDO] |
| Contacto / enquiry | Quiz de arquetipos (futuro) → contacto | [PENDIENTE] — destino del lanzamiento |
| Analítica | PostHog + Vercel Analytics + Meta Pixel, detrás del consentimiento de cookies | [DECIDIDO] |
| Animación | `motion/react` (nunca `framer-motion`); GSAP/ScrollTrigger solo si hace falta | [DECIDIDO] |

## Contenido que vive en el CMS (no hardcodeado)

- Viajes y extensiones: estado live / coming-soon, precio opcional, galería, highlights.
- Artículos del blog (Inspiration).
- Testimonios: máximo 3 líneas, con atribución completa.
- FAQs: la de seguridad siempre va primera.
- Textos legales y la Letter from the founders.

## SEO y migración

- Redirecciones 301 desde el sitio actual (`travelsoultosoul.com`). Ver `04-contenido/inventario-blog-migracion.md`.
- `hreflang` EN/ES, sitemap y metadatos por página. El nombre interno "Raíz" no aparece en ningún metadato.
