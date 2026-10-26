# Why Colombia — notas para el desarrollo

Estado: [DISEÑADA] — estructura y copy completos; faltan todos los medios (videos, fotos, audios) y verificar dos fuentes.

## 1. Dónde está

| Qué | Ruta |
|---|---|
| Vista para abrir en el navegador | `03-paginas/04-why-colombia/VISTA-why-colombia.html` |
| Fuente del prototipo (3 partes, escritorio) | `fuente/Main.dc.html` (Hero + "Colombia, as it is"), `fuente/Part2.dc.html` ("Many Colombias"), `fuente/Part3.dc.html` ("What the numbers say" + cierre + fuentes) |
| Mapa del lienzo (orden de las partes y versiones móviles) | `fuente/canvas.json` — el diseño tiene versión móvil de las 3 partes a 390 px |

## 2. Estructura y concepto

La página tiene tres "puertas de entrada" según el tipo de viajero, enlazadas entre sí al final de cada parte ("Not quite you? Try another way in."):
- Parte 1 — *If you notice small things*: escenas cotidianas de Colombia.
- Parte 2 — *If you travel for contrasts*: "Many Colombias" — pares de video lado a lado (frío/calor, montaña/mar, silencio/música, dos desayunos, dos acentos) con un texto centrado encima.
- Parte 3 — *If you like a good fact*: cifras grandes con contador animado (91 ecosistemas, No. 1 en aves/orquídeas/mariposas, 2 costas, 68 lenguas, 1.000+ ritmos, 40+ arepas), cierre "Colombia is alive" y tarjetas hacia los viajes (Bogotá y Coffee Region).

En producción conviene que sea **una sola página** con las tres partes como secciones y anclas (`#part-1`, `#part-2`, `#part-3`); en el prototipo están separadas solo por tamaño del lienzo.

## 3. Pendientes

| # | Qué | Estado |
|---|---|---|
| 1 | Todos los medios están como marcadores `[VIDEO]`, `[PHOTO]` y `[AUDIO]` con la descripción de la toma. Hay que producirlos o conseguirlos. Banco de videos disponible en Drive: `Página Web/Viajes Asia/Hero Video Raíz` | [PENDIENTE] |
| 2 | Fuente 2 (gradiente térmico): confirmar contra IDEAM antes de publicar | [PENDIENTE] |
| 3 | Fuente 5 (dos costas): reemplazar National Geographic por IGAC | [PENDIENTE] |
| 4 | Contador animado: respetar `prefers-reduced-motion` (el prototipo ya lo hace; mantenerlo) | [DECIDIDO] |
| 5 | Audios ("Sumercé", "Ajá"): definir si se reproducen al hover/tap y siempre con control visible; nunca autoplay con sonido | [DECIDIDO] |
| 6 | Versión en español | [PENDIENTE] |

## 4. Ojo al abrir la vista

- El encabezado del prototipo (logo en texto + "Journeys · How we travel · Why Colombia? · Inquire") es provisional. En producción va el `Header` del design system, con el mismo menú del resto del sitio: Why Colombia · Destinations · Inspiration · About Us · EN/ES · Enquire Now.
- En la vista exportada las fuentes de marca no cargan y se ven tipografías del sistema. En producción se usan las del design system (`02-design-system/tokens/fonts.css`).
