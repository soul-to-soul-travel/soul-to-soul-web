# docs/handoff — cómo leer esta carpeta en el repo

Esta carpeta es una copia **solo de texto** del paquete de entrega del sitio, hecha el 2026-10-26.

## Qué está aquí

- `00-LEEME.md`: documento de entrada.
- `PENDIENTES.md`: los pendientes. Cada uno abierto tiene su issue en GitHub, con las etiquetas `equipo` / `dev`.
- `01-marca/`: solo los dos mapas en texto (`LEEME-marca.md`, `LEEME-fotos.md`); los archivos de marca están en el Drive.
- `02-design-system/`: el readme de marca, el log de decisiones y los tokens (CSS + `tokens.json`).
- `03-paginas/`: las NOTAS y BRIEFs de todas las páginas, juntas en una sola carpeta. En el paquete del Drive cada página tiene su propia subcarpeta.
- `04-contenido/`: el copy en inglés (exportado de Notion), el inventario del blog y `es/` con la traducción preliminar al español.
- `05-tecnico/`: stack e integraciones.

## Qué NO está aquí (está en el Drive)

Paquete completo en el Google Drive de la empresa: `Soul to Soul Travel / 7 - Pagina web y Tecnología / 1 - Página Web / Raíz / 00 - Paquete desarrollador`.

Ahí están:
- Los prototipos (`VISTA-*.html` y `fuente/`).
- Los componentes del design system (`02-design-system/components/`).
- Los assets: logos, símbolos, ilustraciones, fotos, texturas y formas.
- Las fuentes y el brandbook en PDF.

Los originales de fotos y video están en las carpetas hermanas `Home/`, `Viaje Eje C/` y `Bacatá Bogotá Journey/`.

Cuando un documento cita una ruta como `03-paginas/01-home/VISTA-home.html` o `02-design-system/components/...`, esa ruta es relativa al paquete del Drive.

## Regla

Las fotos, los videos y los prototipos no se suben a este repo. Las imágenes del sitio se sirven desde el CMS.
