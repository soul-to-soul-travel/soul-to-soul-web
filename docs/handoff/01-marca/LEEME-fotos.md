# Fotos seleccionadas — qué hay y cómo usarlas

Fecha: 2026-10-26. Son las fotos que el equipo ya eligió para el sitio: las que usa el design system y las galerías armadas para los prototipos del Eje Cafetero, Bogotá y el Home. Están tal como se entregaron: distintos tamaños y formatos. Nada de stock: todas son fotos propias o de los aliados.

## Carpetas

| Carpeta | Archivos | Para qué | Notas |
|---|---|---|---|
| `colombia-general/` | 24 | Home, Why Colombia, Destinations y relleno editorial. Son las fotos del design system (`02-design-system/assets/photography/`) | JPG/PNG web, 14 MB en total. Los nombres describen la foto (cocora-valley, frailejones-paramo, guajira-hammocks…) |
| `coffee-region/hero/` | 1 | Hero de la página de viaje Coffee Region | `Hero.jpg` |
| `coffee-region/galeria/` | 12 | Galería general de Coffee Region (sección 05 de la plantilla) | Originales de 0.3 a 16 MB; hay que generar versiones web |
| `coffee-region/full-bleed/` | 3 | Imágenes horizontales a sangre entre secciones | — |
| `coffee-region/hoteles/` | 19 | "Where you stay": hoteles del Eje Cafetero (Sazagua, Pereira y otros) | Mezcla de tamaños; 2 archivos `.HEIC`/`.heic` se convierten a JPG o WebP antes de usar. Los nombres "Edited in Tezza…" son fotos propias editadas; vale la pena renombrarlas al subirlas al CMS |
| `coffee-region/extensiones/` | 9 | Las 4 extensiones del viaje, una subcarpeta por cada una: Hacienda Venecia, Nido del Cóndor, Termales del Ruiz, Viga Vieja | Originales de 11 a 23 MB |
| `coffee-region/ilustraciones/` | 2 | Heliconia y plátano recortados, usados en la página de viaje | PNG con fondo transparente |
| `bogota/` | 6 | Página de viaje Bogotá | AVIF ya optimizados. Son pocas: la plantilla necesita más (pendiente #24) |
| `home/` | 1 | Recorte de Coffee Region usado en el Home | El otro recorte del Home está en `colombia-general/landscape-banana-palms.png` |

## Reglas

- Las fotos se suben al CMS (Sanity) y se sirven desde ahí, nunca desde el repo.
- Generar versiones web de todo lo que pese más de 1 MB (WebP o AVIF, varios anchos). Los originales se quedan aquí.
- Si falta una foto para una sección, se pide al equipo: no se usa stock.
- Las fotos del equipo y de los anfitriones no están todavía (pendiente #6). Los medios de Why Colombia tampoco (pendiente #7).

## De dónde salieron

Carpetas hermanas de este paquete en el Drive, dentro de `Raíz/`: `Viaje Eje C/` (Galería, hoteles, Acommodation, extensions), `Bacatá Bogotá Journey/Fotos Bogota/` y `Home/Cropped images/`. Ahí quedan los originales y el video del hero (`Home/Hero Video/Video Hero Raiz.mp4`).
