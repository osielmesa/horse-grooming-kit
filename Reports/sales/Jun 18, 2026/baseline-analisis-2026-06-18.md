# Baseline de Ventas — Snapshot pre-cambio de imágenes

**Fecha de captura:** 2026-06-18
**Motivo:** Antes de reemplazar las imágenes del **Kit de 4 piezas** por versiones más profesionales. Este documento es la línea base "ANTES". Dentro de unas semanas se descarga un reporte nuevo y se compara contra estos números para medir si el cambio de imágenes dio resultado.

**Qué se cambió:** Solo las imágenes del listing del **Kit de 4 piezas** (`MS-KIT4-BRW`, ASIN `B0GBYV3L65`).
El **Kit de 8 piezas** (`MS-KIT8-BRW`, ASIN `B0GBZJVY8B`) **no** se tocó → sirve como control de referencia.

> ⚠️ **Métricas a vigilar para juzgar el cambio** (en orden de importancia):
> 1. **Tasa de conversión** (Order Item Session %) — es lo que más afecta la imagen principal.
> 2. **Sesiones / tráfico** — la imagen principal afecta el CTR en los resultados de búsqueda.
> 3. **Unidades y velocidad de venta** (unidades/día).
> 4. **Precio medio de venta (ASP).**

---

## ⚠️ Notas sobre los datos (leer antes de comparar)

- **🚫 Vine excluido:** los **30 pedidos de febrero** son del programa Amazon Vine (no son ventas reales; precios redondos $80.00/$100.00 vs retail $79.99/$99.99) y se descuentan del análisis. Aportaban $2,940.00 / 30 unidades. Detalle y prueba en `../../orders/Jun 18, 2026/baseline-orders-2026-06-18.md`.
- **`BusinessReport-6-18-26.csv`** es a **nivel de cuenta** (una fila por día, sin separar por ASIN). No se puede dividir mecánicamente conversión/sesiones por producto. **Combina los dos kits.** Según el volcado de pedidos orgánico (sin Vine), el reparto es **51.9% Kit de 4 piezas / 48.1% Kit de 8 piezas** — casi parejo —, y en las últimas semanas el 4 piezas domina (junio: 87% de los pedidos).
- El reparto por producto sale del **volcado completo de pedidos** (136 únicos → 106 orgánicos tras quitar Vine) en el documento de `orders/`.
- **Para una comparación A/B limpia en el futuro:** descargar el **Business Report filtrado por ASIN** (uno para cada kit) y volver a excluir Vine. Así se compara la conversión del 4 piezas de forma aislada.

---

## Resumen del listing modificado — Kit de 4 Piezas (VARIACIÓN PRINCIPAL)

| Dato | Valor |
|---|---|
| SKU / ASIN | `MS-KIT4-BRW` / `B0GBYV3L65` |
| Nombre | Masiel Spark Premium Horse Brushes Set (4 Pieces) |
| Precio inferido (reciente) | **$79.99** |
| Pedidos orgánicos (mar – jun, sin Vine) | **55 de 106 (51.9%)** |
| Cuota de pedidos en junio | **87%** (13 de 15) — en fuerte crecimiento |
| Envío (orgánico) | 51 Expedited / 4 Standard |
| Estado | **Imágenes cambiadas el 2026-06-18** ← evento medido |

## Resumen del listing de control — Kit de 8 Piezas

| Dato | Valor |
|---|---|
| SKU / ASIN | `MS-KIT8-BRW` / `B0GBZJVY8B` |
| Nombre | Masiel Spark Premium Horse Grooming Kit (8 Pieces) |
| Precio inferido | **$99.99** |
| Pedidos orgánicos (mar – jun, sin Vine) | **51 de 106 (48.1%)** |
| Cuota de pedidos en junio | **13%** (2 de 15) — en descenso |
| Envío (orgánico) | 44 Expedited / 5 Standard / 2 NextDay |
| Estado | Sin cambios (control) |

> Precios inferidos a partir de los ASP del Business Report ($79.99 y $99.99 son los dos puntos dominantes). El archivo de pedidos no incluye precio.

---

## Rendimiento a nivel de cuenta (Business Report) — la base de comparación

> Estas cifras combinan ambos kits (orgánico: 52% 4 piezas / 48% 8 piezas). En junio el mix ya es ~87% 4 piezas, así que los datos recientes reflejan sobre todo al listing modificado. **La fila "Base orgánica" es la referencia válida** (excluye los 30 pedidos de Vine de febrero).

| Periodo | Ventas | Unidades | Sesiones | **Conversión** | ASP | Días con venta |
|---|---|---|---|---|---|---|
| Histórico bruto (1 ene – 16 jun) *(incluye 30 uds Vine)* | $12,698.91 | 140 | 2,691 | 5.09% | $90.71 | 66 / 167 |
| ✅ **Base orgánica (1 mar – 16 jun, sin Vine)** | $9,758.91 | 110 | 2,520 | **4.25%** | $88.72 | — |
| **Últimos 30 días (18 may – 16 jun)** | $2,199.73 | 27 | 442 | **5.88%** | $81.47 | 18 / 30 |
| **Junio hasta la fecha (1–16 jun)** | $999.88 | 12 | 280 | **4.29%** | $83.32 | 11 / 16 |

**B2B (incluido en lo anterior):** $799.91 en ventas / 9 unidades / 111 sesiones (histórico).

### Indicadores diarios recientes (para comparar "manzanas con manzanas")
| Métrica | Últimos 30 días | Junio a la fecha |
|---|---|---|
| Sesiones / día | ~14.7 | ~17.5 |
| Unidades / día | ~0.90 | ~0.75 |
| Conversión | 5.88% | 4.29% |
| ASP | $81.47 | $83.32 |

---

## Tendencia mensual (cuenta completa)

| Mes | Ventas | Unidades | Sesiones | Conversión | ASP |
|---|---|---|---|---|---|
| 2026-01 | $0.00 | 0 | 1 | 0.00% | — |
| 2026-02 | $2,940.00 | 30 | 170 | 🚫 Vine (excluir) | $98.00 |
| 2026-03 | $1,359.85 | 15 | 659 | 2.28% | $90.66 |
| 2026-04 | $3,199.66 | 35 | 920 | 3.80% | $91.42 |
| 2026-05 | $4,199.52 | 48 | 661 | 6.81% | $87.49 |
| 2026-06 (parcial, 16 días) | $999.88 | 12 | 280 | 4.29% | $83.32 |

**Lecturas:**
- El ASP baja de forma sostenida (~$91 → ~$83) porque el mix orgánico se desplaza del 8 piezas ($99.99) al 4 piezas ($79.99): en junio ya domina el 4 piezas (ASP ~$83). El ASP de febrero ($98) corresponde a Vine, no a ventas reales.
- Marzo–abril concentran las sesiones (tráfico) pero con conversión baja (2–4%); mayo convierte mejor (6.81%) con menos tráfico.
- **Conversión de referencia esperable: ~4–6%.** Ese es el rango contra el que medir el efecto de las nuevas imágenes.

---

## Cómo comparar dentro de unas semanas

1. Descargar un nuevo `BusinessReport` (idealmente **filtrado por ASIN `B0GBYV3L65`**) y un nuevo `fba_orders_data`.
2. Comparar, sobre una ventana de igual duración (p. ej. 30 días post-cambio vs. estos **últimos 30 días**: conversión **5.88%**, ~0.90 uds/día, ~14.7 sesiones/día):
   - **Conversión** (señal #1 del cambio de imagen principal).
   - **Sesiones/día** (CTR en búsqueda).
   - **Unidades/día** y **ventas**.
3. Usar el **Kit de 8 piezas como control**: si su conversión también sube en el mismo periodo, parte de la mejora se debe a estacionalidad/mercado, no solo a las imágenes.
4. Dejar pasar **al menos 3–4 semanas** y/o ~400+ sesiones post-cambio antes de concluir (con ~15 sesiones/día, menos muestra no es estadísticamente fiable).

---

*Generado el 2026-06-18 a partir de `BusinessReport-6-18-26.csv` (1 ene–16 jun). El desglose por variación procede del volcado completo de pedidos (136 únicos → 106 orgánicos sin Vine) en `../../orders/Jun 18, 2026/baseline-orders-2026-06-18.md`. Los 30 pedidos de febrero (Vine) están excluidos del análisis.*
