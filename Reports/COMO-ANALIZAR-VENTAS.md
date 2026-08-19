# Procedimiento: cómo analizar las ventas de los kits

> Guía para repetir el análisis cada vez que se descarguen reportes nuevos (p. ej. para medir el efecto del cambio de fotos del Kit de 4 piezas). Seguir estos pasos en orden.

## 0. Contexto fijo del proyecto

- **2 variaciones:**
  - **Kit 4 piezas** — SKU `MS-KIT4-BRW`, ASIN `B0GBYV3L65`, retail **$79.99**. *(Listing cuyas fotos se cambiaron el 2026-06-18.)*
  - **Kit 8 piezas** — SKU `MS-KIT8-BRW`, ASIN `B0GBZJVY8B`, retail **$99.99**. *(Control, sin cambios.)*
- **Estructura de carpetas:** los reportes van en `Reports/sales/<fecha>/` (Business Report) y `Reports/orders/<fecha>/` (volcado de pedidos FBA, suele venir paginado en `fba_orders_data.csv`, `(1)`, `(2)`…).
- Los markdown de análisis se generan **a la misma altura** que los CSV que analizan.

## 1. Combinar y deduplicar el volcado de pedidos

- Leer **todos** los `fba_orders_data*.csv` con `encoding='utf-8-sig'` (traen BOM).
- **Deduplicar por nº de pedido** = primer token de la columna `Order details` (las páginas se solapan en los bordes).
- Clasificar cada pedido por kit: `MS-KIT4` → 4pc, `MS-KIT8` → 8pc.
- El Business Report se lee también con `utf-8-sig` (la columna `Date` lleva BOM).

## 2. 🚫 Excluir pedidos de Amazon Vine (NO son ventas reales)

- Vine = unidades gratis a reseñadores. **Siempre se descuentan** de todas las estadísticas.
- **Identificación:** precios redondos **$80.00** (4pc) y **$100.00** (8pc), vs retail $79.99/$99.99.
- El volcado de pedidos **no trae precio**, así que se cruzan con el **Business Report**: los días con Vine muestran ASP **no terminado en `.99`**. Sumar pedidos × precio redondo debe cuadrar con las ventas de esos días.
- **Baseline conocido (captura 2026-06-18):** los 30 Vine fueron **todo febrero 2026** (2/19 + 2/20) = 3×4pc + 27×8pc = $2,940.00, que coincide al céntimo con las ventas de febrero. Verificar de nuevo con cada descarga por si hay Vine más reciente.
- Guardar un CSV limpio (`orders_final_sin_vine.csv`) solo con los pedidos orgánicos.

## 3. Estadísticas a calcular (siempre sobre datos orgánicos, sin Vine)

**Por cada kit, separadas en el tiempo:**
- Promedio **diario / semanal (×7) / mensual (×30)** de pedidos.
- Ventanas: **global**, **últimos 30 / 14 / 7 días**.
- Desglose **mensual** y **semanal** (semana lun–dom) con la **cuota del 4pc** en el mix.
- Marcar la última semana si es **parcial**.

**A nivel de cuenta (Business Report, combina ambos kits):**
- Conversión = `Total Order Items / Sessions - Total`, sesiones, unidades, ventas, ASP.
- Semanal y mensual, **excluyendo febrero/Vine**.
- Recordar: en fechas recientes ~87% del volumen es 4pc, así que la conversión de cuenta refleja sobre todo al listing modificado. *(Lo ideal es descargar el Business Report filtrado por ASIN para aislar el 4pc.)*

## 4. ⚠️ Factores que confunden (señalarlos siempre)

1. **Tendencia previa del 4pc:** su cuota ya subía antes del cambio (40%→87%). Descontarla; no atribuir toda subida a las fotos.
2. **Tráfico variable:** las sesiones cayeron ~a la mitad antes del cambio (31→15/día). Comparar contra ventana equivalente.
3. **Control 8pc débil:** con poco volumen reciente sus variaciones son ruido (sirve para estacionalidad, no como control fino).
4. Comparar siempre **ventanas de igual duración**.

## 5. 🎯 Detectar el efecto de las fotos

La imagen principal actúa **antes del clic** → el efecto se ve primero en **CTR/sesiones**, luego en **conversión**.

Métricas clave y su orden de importancia:
1. **CTR en búsqueda** (impresiones→clics) — señal más directa. **No está en estos ficheros**; descargar **Search Query Performance / Brand Analytics**.
2. **Sesiones / día** — si las fotos mejoran el CTR, el tráfico debería subir.
3. **Conversión (cuenta).**
4. **Pedidos 4pc / día y / semana.**
5. **Cuota 4pc del mix** vs control 8pc.

**Señal sólida** = sesiones **y** conversión suben a la vez y el efecto **persiste varias semanas**.
**Esperar antes de concluir:** ≥ 3–4 semanas y ≥ ~400 sesiones post-cambio.

## 6. Entregables a generar

Por cada captura, dejar en la carpeta correspondiente (`<fecha>/`):
- `orders_final_sin_vine.csv` — pedidos orgánicos limpios.
- Un markdown con: reparto por variación, estadísticas temporales por kit, métricas de detección del efecto y **tabla ANTES vs DESPUÉS** rellenable.
- Mantener coherencia entre el doc de `sales/` (conversión/sesiones) y el de `orders/` (mix por producto).

---

### Valores "ANTES" de referencia (baseline 2026-06-18, ventana 5/18–6/16)

| Métrica | Valor |
|---|---|
| Conversión (cuenta) | 5.88% |
| Sesiones / día | 14.7 |
| Pedidos 4pc / día | 0.80 |
| Pedidos 4pc / semana | 5.6 |
| Cuota 4pc del mix | 87% |
| Pedidos 8pc / día (control) | 0.07 |
| Split orgánico 4pc/8pc (mar–jun) | 52% / 48% (55 / 51 de 106) |

*Documentos base de esa captura: `sales/Jun 18, 2026/baseline-analisis-2026-06-18.md`, `orders/Jun 18, 2026/baseline-orders-2026-06-18.md`, `orders/Jun 18, 2026/estadisticas-temporales-por-kit-2026-06-18.md`.*
