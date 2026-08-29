# Historias de usuario — Problemática 1
## Sistema para el control y comercialización de la producción de miel
### Unión de Productores de Miel de San Juan Ñumí, Oaxaca

## Historia 1: Registro de productores y colmenas
Como responsable de registro de la Unión de Productores de Miel de San Juan Ñumí,
quiero registrar a cada productor junto con sus colmenas asociadas,
para tener un padrón actualizado de quién produce y cuánto.

**Criterios de aceptación:**
- El sistema permite capturar nombre del productor, ubicación y número de colmenas activas.
- Cada productor queda asociado a un identificador único.
- Se puede consultar el listado completo de productores registrados en cualquier momento.

## Historia 2: Registro de producción por cosecha
Como productor de la Unión de Productores de Miel de San Juan Ñumí,
quiero registrar la cantidad de miel cosechada por fecha y por colmena,
para llevar un historial confiable de mi producción.

**Criterios de aceptación:**
- El sistema permite registrar fecha de cosecha, cantidad en kilogramos y colmena de origen.
- El sistema calcula automáticamente el total acumulado de producción por productor.
- Se puede filtrar el historial de cosechas por rango de fechas.

## Historia 3: Control de inventario disponible
Como encargado de inventario de la Unión de Productores de Miel de San Juan Ñumí,
quiero ver en tiempo real cuánta miel disponible hay para vender,
para evitar comprometer ventas que no se puedan cumplir.

**Criterios de aceptación:**
- El inventario se actualiza automáticamente al registrar una cosecha (entrada) o una venta (salida).
- El sistema muestra una alerta cuando el inventario de un lote baja de 10 kg.
- Se puede consultar el inventario total y por lote de cosecha.

## Historia 4: Registro de ventas y clientes
Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí,
quiero registrar cada venta con los datos del cliente y la cantidad vendida,
para llevar control de ingresos y de clientes recurrentes.

**Criterios de aceptación:**
- El sistema permite capturar nombre del cliente, cantidad vendida, precio y fecha.
- El sistema descuenta automáticamente del inventario la cantidad vendida.
- Se puede generar un listado de ventas filtrado por cliente y por periodo.

## Historia 5: Reporte mensual para toma de decisiones
Como presidente/a de la Unión de Productores de Miel de San Juan Ñumí,
quiero generar un reporte mensual de producción, inventario y ventas,
para tomar decisiones informadas sobre la comercialización.

**Criterios de aceptación:**
- El reporte muestra totales de producción, inventario disponible y ventas del mes.
- El reporte puede visualizarse en pantalla o exportarse.
- Los totales del reporte coinciden exactamente con los registros individuales de producción y ventas.
