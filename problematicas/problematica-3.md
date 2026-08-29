# Historias de usuario — Problemática 3
## Trazabilidad de producción y ventas de mezcal artesanal
### Cooperativa de productores de mezcal artesanal, región Mixteca de Oaxaca

## Historia 1: Registro de lotes de producción
Como maestro mezcalero de la cooperativa,
quiero registrar cada lote producido con la cantidad de agave utilizado y los litros obtenidos,
para llevar un control real de mi rendimiento por lote.

**Criterios de aceptación:**
- El sistema permite capturar fecha de producción, kilogramos de agave usados y litros de mezcal obtenidos.
- El sistema calcula automáticamente el rendimiento (litros por kilogramo de agave) de cada lote.
- Se puede consultar el historial de lotes producidos por fecha.

## Historia 2: Registro de costos de producción
Como productor de la cooperativa,
quiero registrar los costos de cada lote (agave, leña, mano de obra),
para conocer el costo real de producción por litro.

**Criterios de aceptación:**
- El sistema permite capturar los distintos conceptos de costo asociados a un lote.
- El sistema calcula automáticamente el costo total y el costo por litro de cada lote.
- Se puede comparar el costo por litro entre distintos lotes.

## Historia 3: Registro de ventas a intermediarios y clientes
Como encargado de comercialización de la cooperativa,
quiero registrar cada venta indicando el lote de origen, cliente y precio,
para saber qué lotes ya se vendieron y a qué precio.

**Criterios de aceptación:**
- El sistema permite capturar cliente, lote vendido, cantidad de litros y precio de venta.
- El sistema descuenta automáticamente el inventario disponible del lote correspondiente.
- Se puede consultar el histórico de ventas por cliente o por lote.

## Historia 4: Trazabilidad completa del lote
Como comprador o autoridad reguladora,
quiero consultar la trazabilidad completa de un lote (producción, costos y venta),
para verificar el origen y autenticidad del mezcal artesanal.

**Criterios de aceptación:**
- El sistema permite buscar un lote por su identificador único.
- El sistema muestra en una sola vista: fecha de producción, insumos usados, costos y a quién se vendió.
- La información mostrada coincide exactamente con los registros individuales capturados.
