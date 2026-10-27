# Pulido de diseño — qué conservar y qué unificar

Fecha: 2026-10-26. Audiencia: el desarrollador. Es parte del alcance del desarrollo, no un extra.

## Cómo leer este documento

- Los prototipos resuelven la idea de cada página, pero no están pulidos: cada uno aplica los tokens del design system a su manera (márgenes, tamaños de letra, radios, botones, cantidad de elementos decorativos). El trabajo es construir el sitio con **una sola regla por cada cosa** y aplicarla igual en todas las páginas.
- **Orden de trabajo: primero el Home, completo y pulido.** Se revisa en conjunto con el equipo y de esa revisión salen las reglas (espaciado, escala tipográfica, retícula, uso de ilustraciones) que después se aplican al resto de páginas. No construir las demás páginas antes de esa revisión.
- **Conservar lo que funciona.** Al equipo le importan estos cuatro elementos y se quedan: el hero del Home que se convierte en el sello de Soul to Soul al hacer scroll; la sección Keep Seeking en el páramo con la luz que ilumina; las ventanas de Windows of Colombia que se abren; y las ilustraciones y acuarelas. El pulido los limpia, no los quita (ver sección 4).
- **Editar, no sumar.** En varias vistas hay demasiados elementos a la vez (texturas, sombras botánicas, ilustraciones, viñetas). La regla general es una pieza decorativa por vista, anclada a un borde, nunca sobre texto ni sobre foto.
- Las cifras de abajo salen de un análisis automático del CSS/JSX de los prototipos y de capturas a 1440 y 390 px, hecho el 2026-10-26 [VERIFICADO salvo donde dice INFERIDO]. Sirven como evidencia, no como lista cerrada: si al construir aparece otra inconsistencia, se resuelve con el mismo criterio.

## 1. Resumen

1. Las cuatro páginas comparten tokens y componentes, pero cada una los aplica distinto: el eyebrow aparece en 7 variantes, el h2 en 9 tamaños y el radio en 8 valores.
2. Home es la más fiel al sistema en escritorio y la más rota en móvil: a 390 px el documento mide 751 px y 97 elementos desbordan [VERIFICADO].
3. Coffee Region tiene el ritmo más disciplinado (104 px en 23 de 27 bordes) pero inventa un tamaño de botón, radios de 24/16 px y controles de carrusel propios.
4. Why Colombia es un wireframe (0 fotos, 13 placeholders, sin Header/Footer, fuentes sin embeber) con 5 colores fuera de paleta y la paleta pastel usada fuera de Window.
5. About se aparta en tipografía (peso 300, tracking negativo, cuerpos 15.5/16.5/17.5 px) y en formas (arcos de 210 px, blobs).

## 2. Hallazgos cuantitativos (valores distintos por página)

| Métrica | Home | Coffee | Why | About |
|---|---|---|---|---|
| Padding vertical de sección | 7: 0/20/70/80/100/104/110 | 3: 0/20/92/104 | 4, todos token | 3 clamps propios (104/116/132 a 1440) |
| Contenedor / medidas de texto | 1280 y 1080 / 9 en px | 1280 y 1440 (header) / 8 en px | 1 token / 11 en ch-rem | 1280 y 780 / 7 en ch |
| font-size declarados (computados) | 11 (22) | 21 (23) | 11 (10) | 18 |
| Tamaños h2 / h3 | 3 / 4 | 5 / 1 | 1 / 1 | 2 / 3 |
| Estilos de eyebrow (uppercase) | 1 (DS) | 5 | 2 | 2, peso 400 |
| letter-spacing | token | 0.2/0.18/0.14em | token | 0.2/−0.01/−0.02em |
| border-radius | 3 | 4 (24 ×13, 16 ×6) | 2 token | 5 (arco 210, blobs) |
| Sombras no permitidas | pill-stamp 0 8 24; marco Window 0 16 36 ×6; 1 text-shadow | 0 | 0 | 0 |
| Colores fuera de tokens | 3 (gradiente verde bajo vídeo) | 0 | 5 pardos + pastel en 9 notas | 1 (rgba 133,66,45) |
| Peso display | 400 | 400 | 400 | 300 ×18 |
| Botones | DS md ×7; 3 flechas 40 px a mano | DS ×8, 6 forzados a 18/36 px; 6 flechas 46 px a mano | 9 terciarios, 0 primarios | md ×1, sm ×1 |
| Fotos / decorativos | ≈24 / 11 (4 texturas, 2 ilustr., 4 símbolos) | 23 / 25 (18 viñetas palma) | 0 / 0 | 15 slots / 4 |
| Móvil 390 | roto (751 px, 97 desbordes) | apila; header recortado; precio US$4,140 vs US$3,800 | correcto | [INFERIDO] h1 y subtítulo `nowrap` |

Cruces: eyebrow en 7 variantes; flechas 40 px/hover coffee (Home) vs 46 px/hover terracota + contador (Coffee); acordeón "+" vs chevron; símbolos de pilares 88 vs 54 px; padding-top del hero 110/20/24/132; Header a 1280 (Home, About), 1440 (Coffee) o texto plano (Why).

## 3. Recomendaciones de pulido (priorizadas)

1. **Ritmo vertical único:** solo `--section-pad-y` (104 / 84 móvil) y 0 en bandas full-bleed. Home usa 7 valores, About 3 clamps propios. Un solo padding de hero para las cuatro páginas.
2. **Dos etiquetas, nada más:** eyebrow = componente `Eyebrow` (11 px/0.2em/600/terracota); metadato ("When", "Day 1", contador) = 11 px/0.2em/400/coffee-55. Coffee tiene 5 variantes, About 2 con peso 400.
3. **Escala tipográfica cerrada:** h1 `--text-hero`; h2 `--text-section` (52) y una secundaria (40); h3 26; cuerpo 16/17; captions 13. Coffee tiene 5 h2, Home 4 h3, About fracciones de px.
4. **Display siempre 400 y tracking 0.01em.** About usa 300 y −0.02/−0.01em.
5. **Radios del sistema:** tarjetas y fotos 2–4 px (hub 8), pill 999, 24 solo en el vídeo hero. Coffee: 13 elementos a 24 y 6 a 16. About: o el arco 210 px entra al DS como único retrato, o se usa el blob simple del DS.
6. **Elevación plana:** quitar la sombra del pill-stamp, el text-shadow del caption del vídeo (usar scrim) y la sombra exterior del marco de Window; la excepción cubre solo las sombras internas de las contraventanas.
7. **Colores:** gradiente verde bajo el vídeo → coconut; radiales de About → terracota con alfa; notas de Why → coconut/palm/light (pastel solo en Window).
8. **Botones solo md y sm del DS:** eliminar `.cta-lg` y `.cta-lg-tertiary` (7 usos con `!important` en Coffee). Si se necesita un CTA grande, añadir `size="lg"` al componente. Why necesita un primario.
9. **Un solo carrusel:** flechas 40 px, hover coffee→light, puntos debajo. Coffee usa 46 px, hover terracota y contador; Testimonial de Home pone las flechas a los lados.
10. **Un solo acordeón:** mismo glifo, pregunta 19 px, fila 24 px. Hoy "+" 19 px (Home) vs chevron 21/23 px (Coffee).
11. **Responsive real:** Home necesita el breakpoint 900 del DS (apilado, Header colapsable, stats sin `nowrap`, JourneySection apilada, textura limitada a 100 vw). About: quitar `nowrap` del h1 y subtítulo, anclar la orquídea al texto y no a `left:573px`.
12. **Header al mismo contenedor (1280)** en todas; en Coffee queda 80 px más afuera que el contenido.
13. **Dosificar decoración:** una pieza de respaldo por vista. Home apila textura + sombra botánica + foto en las 3 primeras pantallas; Coffee usa 18 iconos de palma como viñetas (usar "—" como Home) y deja la palma en una columna vacía.
14. **Limpiar duplicados y placeholders:** newsletter dos veces en Home (sección + footer), "Keep Seeking" tres veces, precio distinto en Coffee, 4 "Draft copy · to approve" y 3 testimonios placeholder visibles.

## 4. Qué conservar

**(a) Hero → sello al hacer scroll.** Funciona y es reconocible (es el Header el que colapsa al pill terracota a >120 px; Coffee lo sustituye por una barra fija distinta). Limpieza: quitar la sombra, morfar en vez de intercambiar nodos (hoy es un swap), dejar ~70 px de aire arriba de cada sección (a 25 % el pill tapa el eyebrow "How we travel") y usar el mismo pill en las cuatro páginas.

**(b) Keep Seeking con luz en el páramo.** Buena idea y accesible (sin JS o con reduced-motion se ve iluminado). Hoy la luz lee como un disco de borde duro (máscara sólida hasta 42 %, corte a 72 %) sobre una foto casi negra, y en táctil no hay cursor: queda oscuro. Suavizar la caída del degradado, subir la exposición base a ~25 %, en `(hover: none)` mover la luz sola o renderizar iluminado, y quitar la tercera repetición de "Keep Seeking" en el footer.

**(c) Windows of Colombia.** El elemento más propio de la marca; conservar. Ajustes: abrir también con tap/focus (hoy solo `:hover`, nunca abre en móvil), quitar la sombra exterior del marco y dejar las internas, retirar o hacer funcional el hint "hover to open" (es un tell tipo scroll-cue), y que "No. 07" mapee notas reales o desaparezca.

**(d) Ilustraciones y acuarelas.** Funcionan ancladas (banano saliendo del CTA Palm, monstera en la costura Testimonial/FAQ). Fallan flotando: palma de Coffee en una columna vacía, orquídea de About clavada a 573 px sobre el h1, sol-ojo recoloreado con `filter` (usar el asset tintado). Regla: una ilustración por vista, anclada a un borde, nunca sobre texto ni foto, máximo dos texturas por página (Home tiene cuatro).
