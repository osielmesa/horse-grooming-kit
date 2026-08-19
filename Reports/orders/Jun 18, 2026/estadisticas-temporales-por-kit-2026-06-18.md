# Estadísticas temporales por kit + detección del efecto de las fotos

**Fecha de captura (corte):** 2026-06-16 (último día con datos) · cambio de fotos del Kit 4 piezas: **2026-06-18**.
**Datos:** 106 pedidos orgánicos (sin Vine), `orders_final_sin_vine.csv` + conversión/sesiones del Business Report (marzo–junio, sin Vine).
**Objetivo:** dejar los promedios por kit (día/semana/mes) y los **valores "ANTES"** de las métricas que delatarán si las fotos nuevas funcionan.

---

## 1. Promedio de ventas por kit

| Periodo | Kit | Pedidos | **/día** | /semana | /mes (×30) |
|---|---|---|---|---|---|
| **Global orgánico** (mar 4 – jun 16, 105 d) | 4 piezas | 55 | **0.52** | 3.67 | 15.7 |
| | 8 piezas | 51 | **0.49** | 3.40 | 14.6 |
| **Últimos 30 días** (5/18 – 6/16) | 4 piezas | 24 | **0.80** | 5.60 | 24.0 |
| | 8 piezas | 2 | **0.07** | 0.47 | 2.0 |
| **Últimos 14 días** (6/3 – 6/16) | 4 piezas | 8 | 0.57 | 4.00 | 17.1 |
| | 8 piezas | 2 | 0.14 | 1.00 | 4.3 |
| **Últimos 7 días** (6/10 – 6/16) | 4 piezas | 6 | 0.86 | 6.00 | 25.7 |
| | 8 piezas | 0 | 0.00 | 0.00 | 0.0 |

> En el global van casi parejos (~0.5/día cada uno), pero en lo reciente **el 4 piezas se dispara y el 8 piezas casi desaparece**.

---

## 2. Mensual por kit (orgánico)

| Mes | 4pc (pedidos / día) | 8pc (pedidos / día) | Cuota 4pc | Conv. cuenta | Sesiones |
|---|---|---|---|---|---|
| 2026-03 (31 d) | 7 / 0.23 | 8 / 0.26 | 47% | 2.28% | 659 |
| 2026-04 (30 d) | 10 / 0.33 | 23 / 0.77 | 30% | 3.80% | 920 |
| 2026-05 (31 d) | 25 / 0.81 | 18 / 0.58 | 58% | 6.81% | 661 |
| 2026-06 (16 d) | 13 / 0.81 | 2 / 0.12 | **87%** | 4.29% | 280 |

*(Conversión y sesiones son a nivel de cuenta —combinan ambos kits—; en junio ~87% es 4 piezas, así que reflejan sobre todo al listing modificado.)*

---

## 3. Semanal por kit (lun–dom)

| Semana | 4pc | 8pc | Total | Cuota 4pc | Conv. cuenta | Sesiones |
|---|---|---|---|---|---|---|
| W11 03/09 | 2 | 3 | 5 | 40% | 4.32% | 162 |
| W12 03/16 | 3 | 2 | 5 | 60% | 1.71% | 175 |
| W13 03/23 | 1 | 1 | 2 | 50% | 1.27% | 158 |
| W14 03/30 | 0 | 8 | 8 | 0% | 3.88% | 206 |
| W15 04/06 | 3 | 2 | 5 | 60% | 3.06% | 196 |
| W16 04/13 | 2 | 5 | 7 | 29% | 3.38% | 237 |
| W17 04/20 | 4 | 8 | 12 | 33% | 4.80% | 229 |
| W18 04/27 | 1 | 6 | 7 | 14% | 4.04% | 223 |
| W19 05/04 | 8 | 7 | 15 | 53% | 6.57% | 198 |
| W20 05/11 | 6 | 7 | 13 | 46% | 6.77% | 192 |
| W21 05/18 | 3 | 0 | 3 | 100% | 4.55% | 66 |
| W22 05/25 | 8 | 0 | 8 | 100% | 11.46% | 96 |
| W23 06/01 | 6 | 2 | 8 | 75% | 3.52% | 142 |
| W24 06/08 | 5 | 0 | 5 | 100% | 5.71% | 105 |
| W25 06/15 *(parcial, 2 d)* | 2 | 0 | 2 | 100% | 3.03% | 33 |

> **La cuota del 4 piezas sube de ~40% (marzo) a ~100% (junio).** Esta tendencia ya existía **antes** del cambio de fotos → es el principal factor a descontar al medir el efecto.

---

## 4. ⚠️ Factores que confunden la medición (leer antes de concluir)

1. **El 4 piezas ya venía subiendo** (cuota 40% → 87% antes del cambio). Una subida posterior NO se puede atribuir entera a las fotos; hay que comparar contra la **tendencia previa** y contra el control.
2. **El tráfico cayó a la mitad:** sesiones de **31.4/día** (30 d previos, 4/18–5/17) a **14.7/día** (últimos 30 d). Si las fotos mejoran el CTR de la imagen principal, las **sesiones deberían recuperarse** — esa es una señal clave a favor de las fotos.
3. **El 8 piezas como control es débil ahora** (casi 0 ventas recientes). Sigue sirviendo para estacionalidad de mercado, pero con poco volumen sus variaciones son ruido.
4. **Última semana (W25) es parcial** (solo 2 días). No la compares como semana completa.

---

## 5. 🎯 Métricas para detectar el efecto de las fotos — VALORES "ANTES"

El cambio afecta sobre todo la **imagen principal** → su efecto se ve primero en **CTR/tráfico** y en **conversión**. Estos son los números base contra los que comparar (ventana de referencia: **últimos 30 días pre-cambio, 5/18–6/16**):

| Métrica | Señal que mide | **Valor ANTES (baseline)** | Qué esperar si las fotos funcionan |
|---|---|---|---|
| **Conversión (cuenta)** | Imagen principal + detalle convencen | **5.88%** (últimos 30 d) · ~5% orgánico medio | Subida sostenida por encima de ~6% |
| **Sesiones / día** | CTR de la imagen principal en búsqueda | **14.7/día** (cayendo desde 31/día) | Recuperación / subida del tráfico |
| **Pedidos 4pc / día** | Resultado neto | **0.80/día** (últimos 30 d) | Subida por encima de la tendencia previa |
| **Pedidos 4pc / semana** | Resultado neto (menos ruido) | **5.6/sem** | > 6–7/sem sostenido |
| **Cuota 4pc del mix** | 4pc vs control 8pc | **87%** (junio) | Se mantiene/sube mientras 8pc estable |
| **CTR en búsqueda** *(no disponible aquí)* | Efecto directo de la foto principal | — | **Descargar el "Search Query Performance" / Brand Analytics** para tenerlo |

> **Métrica #1 = CTR/sesiones.** La imagen principal actúa en los resultados de búsqueda (antes del clic). Si las nuevas fotos son mejores, lo primero que debería moverse son las **impresiones→clics (CTR)** y por tanto las **sesiones**. La conversión es la #2. Como no hay CTR en estos ficheros, **recomiendo descargar el reporte de Search Query Performance** para la próxima medición.

---

## 6. Plantilla de comparación (rellenar "DESPUÉS")

Medir sobre una ventana de **igual duración** (30 días post-cambio: ~6/19–7/18) y comparar:

| Métrica | ANTES (5/18–6/16) | DESPUÉS (___ – ___) | Δ | ¿Mejora? |
|---|---|---|---|---|
| Conversión (cuenta) | 5.88% | | | |
| Sesiones / día | 14.7 | | | |
| Pedidos 4pc / día | 0.80 | | | |
| Pedidos 4pc / semana | 5.6 | | | |
| Cuota 4pc del mix | 87% | | | |
| Pedidos 8pc / día (control) | 0.07 | | | |
| CTR búsqueda (si se obtiene) | — | | | |

**Método para concluir:**
- Esperar **≥ 3–4 semanas** y **≥ 400 sesiones** post-cambio (con ~15 sesiones/día eso son ~27 días).
- Restar la **tendencia previa** del 4 piezas y mirar el **control 8 piezas** y la estacionalidad antes de atribuir mérito a las fotos.
- Señal sólida = **sesiones + conversión suben a la vez** y el efecto persiste varias semanas.

---

*Generado el 2026-06-18 a partir de `orders_final_sin_vine.csv` (106 pedidos orgánicos) y `../../sales/Jun 18, 2026/BusinessReport-6-18-26.csv` (marzo–junio, sin Vine).*
