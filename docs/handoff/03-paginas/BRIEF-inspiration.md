# Inspiration (blog) — brief

Estado: [SIN DISEÑO] — entra en la v1. Se construye con componentes que ya existen en el design system.

"Inspiration" (menú principal) y "Journal" (footer) son **la misma sección**. Usar un solo nombre en navegación: Inspiration. El enlace "Journal" del footer apunta a la misma ruta.

## Concepto

La sección "Windows of Colombia" del Home es la puerta de entrada: cada ventana es un artículo. Al abrirse, la ventana revela la foto del artículo. El blog extiende esa misma idea.

## Páginas

**1. Listado (`/inspiration`, `/es/inspiracion`)**
- Encabezado con `SectionHeading`.
- Artículos presentados con el componente `Window` (`02-design-system/components/windows/`): cuatro variantes pastel, textura `02-design-system/assets/textures/win2-37.jpg`, apertura de 1.200 ms.
- Regla del design system: la paleta pastel se usa SOLO en las ventanas.
- Regla "N items = N cells": la grilla tiene exactamente tantas celdas como artículos.
- Filtros por región o tema: no en la v1.

**2. Artículo (`/inspiration/[slug]`)**
- Plantilla editorial: foto principal (puede ir enmascarada en una forma orgánica simple, ver `readme.md` → organic shapes), eyebrow con región o tema, título, fecha y tiempo de lectura.
- Cuerpo en texto enriquecido desde Sanity, con bloques: párrafo, imagen a todo el ancho, galería, cita destacada (`Callout` variante quote) y nota a mano (fuente Better Yesterday, con moderación).
- Al final: tarjeta hacia el viaje relacionado (`JourneyCard`) y formulario de newsletter (`NewsletterForm`).
- Fondo Light para lectura larga (regla de ritmo Coconut ↔ Light).

## Migración del blog actual

- Inventario de artículos: `04-contenido/inventario-blog-migracion.md`.
- **No se migran** los artículos sobre Asia.
- Los artículos en español se traducen al inglés. Como el sitio es bilingüe, cada artículo migrado queda en EN y ES.
- Redirecciones 301 desde las URLs viejas de `travelsoultosoul.com/blog/...` hacia las nuevas.
- Exportar las imágenes originales en la mejor resolución disponible, no las que sirve el sitio actual.

## Pendientes

- [PENDIENTE] Artículos nuevos para las ventanas del Home: los títulos actuales del prototipo son de relleno.
- [PENDIENTE] Quién traduce los artículos ES → EN.
