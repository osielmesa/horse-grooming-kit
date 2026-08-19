# Baseline de Pedidos (volcado completo, sin Vine) — Snapshot pre-cambio de imágenes

**Fecha de captura:** 2026-06-18
**Fuente:** Volcado completo de pedidos FBA (`fba_orders_data.csv` + `(1)` + `(2)`), combinados y deduplicados por nº de pedido.
**Cobertura bruta:** 2026-02-19 → 2026-06-16 · **136 pedidos únicos**.
**Cobertura limpia (la usada para estadísticas):** 2026-03-04 → 2026-06-16 · **106 pedidos orgánicos** (tras descontar 30 pedidos de Vine).
**CSV limpio:** [`orders_final_sin_vine.csv`](orders_final_sin_vine.csv) — los 106 pedidos orgánicos, sin Vine.

**Motivo:** Línea base "ANTES" del cambio de imágenes del **Kit de 4 piezas** (`MS-KIT4-BRW`, ASIN `B0GBYV3L65`), realizado el 2026-06-18. El **Kit de 8 piezas** (`MS-KIT8-BRW`, ASIN `B0GBZJVY8B`) no se tocó → control. Complementa a `../../sales/Jun 18, 2026/baseline-analisis-2026-06-18.md`.

---

## 🚫 Pedidos de Vine excluidos (30 pedidos)

Los pedidos del programa **Amazon Vine** no son ventas reales (productos entregados a reseñadores) y se descuentan de todas las estadísticas. Se identifican por precio exacto **$80.00** (4 piezas) y **$100.00** (8 piezas), en vez del precio retail $79.99 / $99.99.

El volcado de pedidos no trae columna de precio, pero los 30 Vine quedan **identificados con total certeza**: son **los 30 pedidos de febrero** (días 2/19 y 2/20). Prueba cruzada con el Business Report:

| | 4 piezas ($80) | 8 piezas ($100) | Total | Ingreso |
|---|---|---|---|---|
| Vine (febrero) | 3 | 27 | **30** | 3×80 + 27×100 = **$2,940.00** |

→ Coincide **al céntimo** con las ventas de febrero del Business Report ($2,940.00), y febrero es el **único** mes con precios redondos (todos los demás meses son `.99` retail). Por eso febrero parecía un "outlier": era la ráfaga de Vine del lanzamiento, no ventas orgánicas.

---

## Reparto por variación (orgánico, sin Vine)

| Variación | Pedidos | Cuota | Ingreso estimado* |
|---|---|---|---|
| **Kit 4 piezas** (`MS-KIT4-BRW`) — *listing modificado* | **55** | **51.9%** | ~$4,399 |
| **Kit 8 piezas** (`MS-KIT8-BRW`) — *control* | **51** | **48.1%** | ~$5,099 |
| **Total orgánico** | **106** | 100% | ~$9,499 |

\* Estimado con precios retail **4pc = $79.99** y **8pc = $99.99**. Aproximación (no incluye multi-unidad ni B2B). El total estimado (~$9,499) cuadra bien con las ventas orgánicas del Business Report (marzo–junio: $9,758.91).

> **Dato clave:** una vez quitado Vine, los dos kits venden casi lo mismo (52% / 48%). El "liderazgo histórico" del 8 piezas era un espejismo de Vine (27 de los 30 pedidos Vine eran 8 piezas).

---

## ⭐ Tendencia mensual por variación (orgánico)

| Mes | Total | 4pc | 8pc | Cuota 4pc |
|---|---|---|---|---|
| 2026-02 | — | — | — | *(30 pedidos Vine, excluidos)* |
| 2026-03 | 15 | 7 | 8 | 47% |
| 2026-04 | 33 | 10 | 23 | 30% |
| 2026-05 | 43 | 25 | 18 | 58% |
| 2026-06 (16 días) | 15 | 13 | 2 | **87%** |

**Lectura:** hay una **inversión clara del mix** en ventas reales. El 8 piezas dominó en marzo–abril, pero el 4 piezas viene creciendo con fuerza y en junio ya es el **87% de los pedidos**. Es contexto crítico para el test de imágenes: el 4 piezas **ya tenía momentum antes** del cambio, así que parte de cualquier subida puede deberse a esa tendencia. **El control (8 piezas) ayuda a separar ambos efectos.**

---

## Ventanas recientes (para comparar "después") — todas orgánicas

| Ventana | Pedidos | 4pc | 8pc |
|---|---|---|---|
| Últimos 30 días (18 may – 16 jun) | 26 | 24 | 2 |
| Junio a la fecha (1 – 16 jun) | 15 | 13 | 2 |

Las ventanas recientes no se ven afectadas por Vine (todo Vine fue en febrero).
Ritmo orgánico: **1.01 pedidos/día** (106 en 105 días).

---

## Preferencia de envío por variación (orgánico)

| Variación | Expedited | Standard | NextDay |
|---|---|---|---|
| Kit 4 piezas | 51 | 4 | 0 |
| Kit 8 piezas | 44 | 5 | 2 |
| **Total** | **95** | **9** | **2** |

~90% elige **Expedited** en ambos productos.

---

## Cómo comparar dentro de unas semanas

1. Volver a descargar el volcado completo de pedidos, combinar/deduplicar y **excluir Vine** igual que aquí (precios redondos $80/$100).
2. Comparar, sobre una ventana de igual duración, **pedidos/día del 4 piezas** y su **cuota del mix** contra estos números (últimos 30 días: **24 pedidos de 4pc**; cuota junio **87%**).
3. **Usar el 8 piezas como control:** la señal más limpia del efecto de las imágenes es *cómo cambia la proporción 4pc:8pc* y la conversión del 4 piezas (baseline de `sales/`), no el conteo bruto del 4 piezas (que ya venía subiendo).
4. Esperar 3–4 semanas / muestra suficiente antes de concluir.

---

*Generado el 2026-06-18 a partir de 3 ficheros `fba_orders_data*.csv` (paginados): 136 pedidos únicos tras deduplicar, 106 orgánicos tras descontar 30 de Vine. CSV limpio: `orders_final_sin_vine.csv`.*
