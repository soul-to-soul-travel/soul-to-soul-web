# Destinations — brief

Estado: [SIN DISEÑO] — entra en la v1. Se arma con componentes existentes.

## Qué muestra

1. Los dos viajes principales: **Eje Cafetero** y **Bogotá**. Cada uno enlaza a su página de viaje (plantilla Coffee Region).
2. **Sierra Nevada** con badge "Coming soon", sin enlace o con enlace a lista de espera [PENDIENTE].
3. Las extensiones (las mismas del carrusel "Not ready to go home yet?" del Home): San Andrés, Barichara y Boyacá, y al final Oaxaca (México) como adelanto de los viajes a México.

## Cómo

- Viajes principales: `JourneySection` (el mismo bloque del Home) o `JourneyCard` en variante `editorial`. Recomendado: `JourneyCard` editorial en grilla, para que no repita el Home.
- Extensiones: `JourneyCard` variante `overlay`, con badge de duración.
- Regla "N items = N cells" en la grilla.

## Modelo en Sanity (sugerido)

Un tipo `journey` con estos campos:
- `type`: flagship | extension
- `status`: live | coming-soon
- `region`
- `days`
- `price` (opcional; si está vacío no se muestra)
- `highlights[]`
- `gallery[]`
- `slug`

La misma fuente alimenta el Home, esta página y las páginas de viaje.
