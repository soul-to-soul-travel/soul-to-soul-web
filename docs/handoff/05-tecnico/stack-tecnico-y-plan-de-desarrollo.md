# Stack Técnico y Plan de Desarrollo

- Notion: https://app.notion.com/p/35d1d15d036a81b8adc5ea9002705ccb
- Ruta en Notion: 11 - Página Web & Tecnología
- Última edición en Notion: 2026-06-28
- Exportado de Notion el 2026-10-26

> Nota de exportación: esta página no tiene subpáginas. Es de junio 2026; puede haber decisiones técnicas posteriores que no estén reflejadas aquí. Los enlaces a otras páginas de Notion (notion.so) requieren acceso a Notion.

> Este documento define el **stack técnico, herramientas e infraestructura** para construir la nueva página web de Raíz, junto con el plan de fases de desarrollo. Es el complemento técnico de la [Arquitectura de Información](https://www.notion.so/34a1d15d036a805fb9bfc2d9e977a1cc).

---

# 1. Stack Técnico

## Frontend

| Capa | Herramienta | Por qué |
| --- | --- | --- |
| Framework | **Next.js 15+** (App Router) | SSR para SEO, routing simple, ecosistema maduro, deploy nativo en Vercel. |
| Estilos | **Tailwind CSS** | Velocidad de desarrollo, consistencia, fácil de mantener con Claude Code. |
| Animaciones de componentes | **Framer Motion** | Animaciones React declarativas: entradas, salidas, hover, layout animations. |
| Animaciones de scroll | **GSAP** (+ ScrollTrigger) | Timelines complejos, parallax, scroll-triggered, masks. **Ahora gratis** incluso para uso comercial (cambio de licencia 2024 post-adquisición por Webflow). |
| Scroll suave | **Lenis** | La pieza secreta del look "premium" Awwwards. Scroll con inercia, suave, configurable. |
| Lenguaje | **TypeScript** | Tipos = menos bugs en producción. Claude Code lo maneja muy bien. |

> **Framer Motion vs. GSAP — no es uno o el otro.** Framer Motion para animaciones de componentes React (entrada, salida, hover, layout). GSAP para scroll-triggered y animaciones complejas con timelines. Coexisten sin problema.

## Servicios e integraciones

| Función | Herramienta | Notas |
| --- | --- | --- |
| Newsletter | **Resend** | Moderno, dev-friendly, integración limpia con Next.js. Control total sobre el flow de suscripción y automatizaciones. |
| Booking de llamadas | [**Cal.com**](http://Cal.com) | Open source, embebible, white-label. Se integra visualmente con el diseño del sitio. |
| CMS | **Sanity** | Para Journal/blog y eventualmente destinos. Studio personalizable, structured content, queries con GROQ. |
| Repo | **GitHub** (privado) | Desde el día 1. Branch `main` = producción, `develop` = staging. |
| Deploy | **Vercel** | Deploy automático con cada push. Preview por branch (útil para mostrar progreso). |
| Dominio de staging | [**raiz.tamsa.co**](http://raiz.tamsa.co) | Dominio propio existente, usado como staging mientras se construye. **No indexable** y no usado para pauta o promoción. |
| Idioma del sitio | **Inglés** (V1) | Audiencia americana. Botón de español se evalúa en V2. |

## Estrategia de dominios

**Mientras construimos:**

- `raiz.tamsa.co` → staging permanente (branch `main`)
- `*.raiz.tamsa.co` → preview deploys de Vercel por branch (ej: `feature-hero.raiz.tamsa.co`)

> **Regla crítica:** [tamsa.co](http://tamsa.co) es **dominio de staging, no público**. Bloqueado de indexación (`robots.txt` + `noindex` meta tags). No se usa para pauta de Meta, no se promociona en redes, no se comparte públicamente. La marca Raíz **no** debe conocerse como "[tamsa.co](http://tamsa.co)".

**Para el lanzamiento público (decisión pendiente):**

| Opción | Pro | Contra |
| --- | --- | --- |
| `travelsoultosoul.com/raiz` o `raiz.travelsoultosoul.com` | Capitaliza autoridad/SEO del dominio existente | Dominio raíz sigue con contenido en español de Etidur — confunde |
| Dominio nuevo (ej: `raiz.travel`, `raizcolombia.com`) | Marca limpia, sin asociaciones previas | SEO empieza de cero, costo, definir nombre |
| Migrar `travelsoultosoul.com` completo a Raíz | Dominio limpio y de autoridad, una sola marca | Implica decidir futuro de Etidur y contenido en español |

> Decisión no urgente esta semana, pero **sí antes del lanzamiento público**. Afecta SEO, branding y migración final.

---

# 2. Analytics y Medición

## Stack de analytics

| Herramienta | Función | Costo |
| --- | --- | --- |
| **Vercel Analytics + Speed Insights** | Page views básicos, Core Web Vitals, performance del sitio | Gratis (incluido con Vercel) |
| **PostHog** | Eventos, funnels, heatmaps, session replays, A/B testing | Gratis hasta 1M eventos/mes |
| **Meta Pixel** | Tracking y optimización de ads de Meta | Gratis. Obligatorio cuando empiecen pauta. |

> **Principio:** menos herramientas bien usadas que muchas mal usadas. Estas 3 cubren el 95% de lo que necesitamos sin fragmentar la data.

## Métricas en 4 capas

### Capa 1 — Negocio (las que importan de verdad)

- **Conversiones a newsletter** — suscritos / visitas. Esta es la métrica norte.
- **Conversiones a Book a Call** — llamadas agendadas / visitas. Bajo volumen, alto valor.
- **Tasa de completitud de la mini encuesta** post-suscripción.
- **Costo por suscriptor (CPS)** desde ads de Meta — define si la pauta funciona.

### Capa 2 — Comportamiento (para optimizar)

- **Scroll depth** — ¿llegan a la sección 6 o se van en la 2? Crítico en página larga.
- **Tiempo en página** — ¿leen o pasan?
- **Bounce rate** — si llegan y se van, hero o fuente de tráfico están mal.
- **Click rates en CTAs** — qué CTA performa mejor.
- **Heatmaps + session replays** — ver grabaciones reales de cómo usan el sitio.

### Capa 3 — Adquisición (de dónde viene la gente)

- Tráfico por canal (Meta ads, orgánico, directo, referrals).
- Performance por anuncio (qué creative convierte mejor).
- Demografía básica (país, dispositivo).

### Capa 4 — Técnica (que el sitio no esté roto)

- Core Web Vitals (LCP, FID, CLS).
- Velocidad de carga.
- Errores en producción.

## Eventos mínimos a trackear desde día 1

Definir estos eventos **antes** de instalar PostHog para que la data sea limpia desde el principio:

```
page_view                          (automático)
scroll_depth_25/50/75/100          (% de scroll alcanzado)
cta_click                          (con parámetro: newsletter, book_a_call, destination_card, etc.)
newsletter_form_started            (focus en el input)
newsletter_form_submitted          (conversión)
survey_started                     (mini encuesta post-suscripción)
survey_completed                   (encuesta terminada)
book_call_clicked                  (click en CTA de llamada)
book_call_completed                (vía webhook de Cal.com)
destination_card_clicked           (con nombre del destino)
journal_article_clicked            (con slug del artículo)
```

Con estos eventos se arman **funnels reales** en PostHog: cuántos llegan al hero → cuántos scrollean → cuántos hacen click en algún CTA → cuántos completan la suscripción.

---

# 3. Plan de Desarrollo por Fases

> **Total realista:** 6-8 semanas full-time si las decisiones están bien tomadas antes.

## Fase 0 — Preparación (1 semana)

Antes de tocar código.

- [ ] Benchmarking estructurado de 8-10 sitios Awwwards
- [ ] Mood board y dirección visual aterrizada
- [ ] Definición de tipografías y paleta (basado en rediseño de marketing)
- [ ] Mensaje exacto del hero definido
- [ ] Copy final del home (todas las secciones)
- [ ] Wireframes de baja fidelidad de cada página
- [ ] Sesión de fotos del equipo planeada

## Fase 1 — Foundation (3-5 días)

- [ ] Setup del proyecto Next.js + TypeScript + Tailwind
- [ ] Configuración de GSAP, Framer Motion, Lenis
- [ ] Design system: colores, tipografías, espaciado, componentes base
- [ ] Layout principal (header, footer, container)
- [ ] Routing de las páginas
- [ ] Repo en GitHub + deploy inicial en Vercel

## Fase 2 — Home, sección por sección (1-2 semanas)

Construir cada sección del home en orden:

- [ ] Sección 1 — Hero (estructura, sin animaciones aún)
- [ ] Sección 2 — La historia de Aída (3 bloques A/B/C)
- [ ] Sección 3 — How We Travel (Balance + Conexión)
- [ ] Sección 4 — Colombia + menciones de prensa
- [ ] Sección 5 — Destinations preview
- [ ] Sección 6 — Team
- [ ] Sección 7 — Journal preview
- [ ] Sección 8 — Final CTA
- [ ] Sección 9 — Footer

> **Regla:** primero estructura + estilos, después animaciones. No mezclar las dos pasadas.

## Fase 3 — Animaciones e interacciones (1 semana)

- [ ] Scroll-triggered animations en cada sección
- [ ] Hover states y micro-interacciones
- [ ] Lenis para scroll suave global
- [ ] Cursor personalizado (opcional, evaluar)
- [ ] Transiciones entre páginas

## Fase 4 — Páginas secundarias (1 semana)

- [ ] `/how-we-travel` — filosofía y criterios en profundidad
- [ ] `/destinations` + páginas individuales por destino
- [ ] `/colombia` — contexto y menciones
- [ ] `/about` — equipo extendido + carta de Aída completa
- [ ] `/journal` — listado + plantilla de artículo
- [ ] `/contact` — book a call + formulario + newsletter

## Fase 5 — CMS, integraciones, formularios (3-5 días)

- [ ] Setup de Sanity Studio
- [ ] Schemas en Sanity (Journal articles, Destinations, Team members)
- [ ] Integración Resend (formulario de newsletter + welcome email)
- [ ] Integración [Cal.com](http://Cal.com) (booking embedido o redirect)
- [ ] Mini encuesta post-suscripción
- [ ] PostHog: instalación + eventos definidos
- [ ] Meta Pixel
- [ ] Vercel Analytics + Speed Insights

## Fase 6 — Polish + deploy (3-5 días)

- [ ] SEO: meta tags, Open Graph, sitemap.xml, robots.txt
- [ ] Performance optimization (imágenes, lazy loading, bundle size)
- [ ] Testing en dispositivos reales (mobile, tablet, desktop)
- [ ] Accesibilidad básica (semántica, contraste, navegación por teclado)
- [ ] Política de privacidad y términos
- [ ] Deploy final a producción

---

# 4. Cómo trabajar con Claude

## Claude Code vs. Claude Design

**Claude Code** = la herramienta principal para construir el sitio. Trabaja con el repo real, stack real, archivos reales. Lo que se construye se queda y crece.

[**Claude.ai**](http://Claude.ai) **(artifacts)** = útil para **prototipar secciones específicas** rápido antes de mandarlas al repo. Ejemplo: probar la animación del hero, ver variaciones del menú, jugar con el tono de los criterios. Esos prototipos se pasan después a Claude Code para integrarlos al sitio real.

## Buenas prácticas

- **Commits frecuentes y atómicos.** Una feature = uno o varios commits pequeños. Facilita revertir si algo se rompe.
- **Branches por feature.** No trabajar todo en `main`. `feature/hero-section`, `feature/team-grid`, etc.
- **Preview deploys en Vercel.** Cada branch genera una URL preview — útil para revisar antes de mergear.
- **Una decisión visual grande = primero prototipo en artifacts**, después al repo. Evita re-trabajar 3 veces lo mismo en producción.
- **Documentar decisiones en el repo** (README o `/docs`). Por qué se eligió tal patrón, qué librería para qué.

---

# 5. Decisiones técnicas pendientes

- [ ] Definir si V1 incluye cursor personalizado (estilo Awwwards) o se deja para V2
- [ ] Decidir sistema de gestión de imágenes: Sanity asset library vs. Vercel Blob vs. Cloudinary
- [ ] Decidir si Journal se setea con MDX inicialmente y se migra a Sanity después, o se arranca directo en Sanity
- [ ] Definir estructura de schemas en Sanity antes de crearlos
- [ ] Configurar `raiz.tamsa.co` como dominio de staging en Vercel + bloqueo de indexación (`robots.txt` + `noindex`)
- [ ] Definir si el sitio será 100% client-side animations o si hay SSG/SSR para SEO crítico
- [ ] Auditoría del contenido actual de `travelsoultosoul.com` (páginas, tráfico, backlinks) antes de migrar
- [ ] Definir qué subdominio usar para archivar contenido legacy de Tidur

---

# 6. Material necesario del equipo (rediseño marketing)

Para arrancar el Foundation se necesita:

- [ ] Paleta de colores completa (hex codes)
- [ ] Tipografías definidas (display + body) con links o archivos de las fuentes
- [ ] Logo en formatos editables (SVG idealmente)
- [ ] Set de ilustraciones disponibles del rediseño
- [ ] Iconos disponibles
- [ ] Fotos del equipo (mientras se hace la sesión nueva, fotos de referencia)
- [ ] Banco de fotos/videos de Colombia disponibles

---

# 7. Referencias

- [Arquitectura de Información — Nueva página web](https://www.notion.so/34a1d15d036a805fb9bfc2d9e977a1cc)
- [Versión 2026 v2.0](https://www.notion.so/3481d15d036a81a19b18c1e498259ddf) — criterios de diseño
- [User Persona - Raíz](https://www.notion.so/32d1d15d036a8028b9a2f4df6087f856)
- [American Traveler — Audience Research](https://www.notion.so/3211d15d036a8074b86af1964968b2fd)
- ["I'm biased. Here's why."](https://www.notion.so/32f1d15d036a804584dff0c65c87363a) — carta para Sección 2 del home
