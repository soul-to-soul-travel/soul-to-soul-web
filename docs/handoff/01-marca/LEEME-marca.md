# Marca — dónde está cada cosa

Fecha: 2026-10-26. Todo lo de la marca está en dos carpetas de este paquete: `01-marca/` (identidad) y `02-design-system/assets/` (material visual del sitio). Las rutas son relativas al paquete.

| Qué | Dónde | Notas |
|---|---|---|
| Manual de marca | `01-marca/brandbook/Brandbook-Soul-to-Soul-VF-2026.pdf` | La versión vigente. Manda sobre cualquier otro documento de marca |
| Logos | `01-marca/logos/` (17 SVG) y `01-marca/logos/masters-editables/` (4 masters) | Variantes: logo horizontal, logotype, isotype (palma), vertical y stamp (sello), cada una en coffee, light, coconut o terracotta. Casi los mismos SVG están en `02-design-system/assets/logos/` (18) |
| Tipografías | `01-marca/fuentes/` | Milanesa Serif Light (.otf, .woff, .woff2), Avenir LT Std Book/Roman/Black (.otf), Better Yesterday itálica (.woff, .woff2). Playfair Display viene de Google Fonts. Licencia web por confirmar: pendiente #1 |
| Lettering "Keep Seeking" | `01-marca/keep-seeking/` (3 SVG) | Tagline a mano. No se traduce |
| Colores y tokens | `02-design-system/readme.md` y `02-design-system/tokens/` (CSS y `tokens.json`) | Coffee `#503421`, Light `#F7F4F0`, Coconut `#F0E8D5`, Terracotta `#A35940`, Palm `#D3C381` |
| Fotos seleccionadas | `01-marca/fotos-seleccionadas/` (ver `LEEME-fotos.md` ahí) | 24 de Colombia en general, 46 del Eje Cafetero, 6 de Bogotá, 1 del Home |
| Ilustraciones y acuarelas | `02-design-system/assets/illustrations/` (13 PNG, 126 MB) | Banano, cacao, coco, jaguar, monstera, tortuga y las acuarelas `img-*`. Pesan 1 a 17 MB: siempre generar versión web |
| Texturas | `02-design-system/assets/textures/` (25) | Acuarelas de fondo (`watercolor-01..09`), papel, sombras botánicas (`botanical-shadow`, `leaf-shadow`) y fotos de ventanas (`win*`, `window-estuco-caramelo`) para Windows of Colombia |
| Formas | `02-design-system/assets/shapes/` (23, en `large/` y `simple/`) | Blobs y recortes orgánicos para enmarcar fotos |
| Símbolos | `02-design-system/assets/symbols/` (36 SVG) | Iconos de pilares, viajes y UI |
| Fotos del design system | `02-design-system/assets/photography/` (24) | Las mismas que `fotos-seleccionadas/colombia-general/` |
| Componentes de referencia | `02-design-system/components/` | 16 componentes (Header, JourneySection, Window, KeepSeeking, Footer…) con su `.jsx`, `.d.ts` y `.prompt.md` |
| Originales fuera del paquete | Drive, carpetas hermanas en `Raíz/`: `Home/` (video del hero, texturas, sombras, recortes), `Viaje Eje C/`, `Bacatá Bogotá Journey/` | Solo si falta algo; lo del paquete ya es la selección |

Lo que todavía no existe: fotos reales del equipo y de los anfitriones (pendiente #6), medios de Why Colombia (pendiente #7).
