# Auditoría con IA — Historias de usuario

## Herramienta utilizada
Claude (Anthropic)

## Prompt utilizado

Actúa como un experto en Scrum/eduScrum revisando historias de usuario.
Audita las siguientes historias de usuario y para cada una indica:
1. Si el formato "Como / Quiero / Para" está completo y bien usado.
2. Si el rol usado es específico y real, o es genérico/ambiguo.
3. Si los criterios de aceptación son verificables (medibles, concretos) o son vagos.
4. Si existe ambigüedad de alcance (si se puede interpretar de más de una forma).
5. Sugiere una versión corregida de la historia si encuentras problemas.

Historias a auditar: [las 13 historias de las problemáticas 1 - Miel, 2 - Mercado y 3 - Mezcal]

## Hallazgos de la IA

### Hallazgo 1 — Rol escrito con diagonal de género
**Historia afectada:** Historia 5 - Problemática 1 (Reporte mensual) y Historia 4 - Problemática 2 (Corte de caja)

**Observación de la IA:** El rol está escrito como "presidente/a" y "tesorero/a". Usar la diagonal ("/a") para cubrir género no es un problema de fondo, pero puede leerse como si fueran dos roles distintos posibles, generando ambigüedad sobre quién es el actor real.

**Decisión del equipo:** Aceptado

**Argumento:** Coincidimos en que el rol debe quedar como un nombre único y sin ambigüedad. Optamos por escribir "presidente de la Unión" y "tesorero del mercado", sin diagonal, porque en ambos casos hay una persona específica ocupando ese cargo.

### Hallazgo 2 — Dos actores mezclados en un mismo "Como"
**Historia afectada:** Historia 4 - Problemática 3 (Trazabilidad completa del lote)

**Observación de la IA:** La historia combina dos roles distintos en un mismo "Como": "comprador o autoridad reguladora". Cada historia de usuario debe tener un solo actor, porque comprador y autoridad reguladora pueden necesitar información distinta y tener motivaciones diferentes.

**Decisión del equipo:** Aceptado

**Argumento:** Es un error real de alcance. Dividimos la historia en dos versiones, una por cada rol, de modo que cada una tenga su propio criterio de aceptación específico.

### Hallazgo 3 — Criterio de exportación sin formato definido
**Historia afectada:** Historia 5 - Problemática 1 (Reporte mensual)

**Observación de la IA:** El criterio "el reporte puede visualizarse en pantalla o exportarse" es vago porque no especifica en qué formato se exporta ni cómo se verifica que la exportación fue correcta.

**Decisión del equipo:** Aceptado

**Argumento:** No era verificable tal cual estaba redactado. Se corrigió especificando el formato de exportación (PDF) como condición concreta.

### Hallazgo 4 — Umbral de alerta fijo (10 kg)
**Historia afectada:** Historia 3 - Problemática 1 (Control de inventario disponible)

**Observación de la IA:** El umbral de alerta de "10 kg" está fijo en el criterio de aceptación; sugiere hacerlo configurable para que no dependa de un número arbitrario dentro de la historia.

**Decisión del equipo:** Rechazado

**Argumento:** Para el alcance de esta evidencia, un umbral fijo es suficiente y más fácil de verificar como criterio de aceptación. Hacerlo configurable queda como mejora futura, no como requisito de esta etapa.

### Hallazgo 5 — Caso de venta mayor al inventario sin cubrir
**Historia afectada:** Historia 4 - Problemática 1 (Registro de ventas y clientes)

**Observación de la IA:** No se especifica qué debe pasar si se intenta registrar una venta mayor al inventario disponible, lo cual deja un caso sin cubrir (ambigüedad de alcance).

**Decisión del equipo:** Aceptado

**Argumento:** Es un escenario real que puede ocurrir en la operación diaria. Se agregó un criterio de aceptación adicional para cubrirlo.

## Historias corregidas

### Problemática 1, Historia 5 — Reporte mensual

**Antes:**
> Como presidente/a de la Unión de Productores de Miel de San Juan Ñumí,
> quiero generar un reporte mensual de producción, inventario y ventas,
> para tomar decisiones informadas sobre la comercialización.
>
> Criterios: reporte muestra totales; puede visualizarse en pantalla o exportarse; totales coinciden con registros.

**Después:**
> Como presidente de la Unión de Productores de Miel de San Juan Ñumí,
> quiero generar un reporte mensual de producción, inventario y ventas,
> para tomar decisiones informadas sobre la comercialización.

**Criterios de aceptación:**
- El reporte muestra totales de producción, inventario disponible y ventas del mes.
- El reporte puede exportarse en formato PDF.
- Los totales del reporte coinciden exactamente con los registros individuales de producción y ventas.

---

### Problemática 1, Historia 4 — Registro de ventas y clientes

**Antes:**
> Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí,
> quiero registrar cada venta con los datos del cliente y la cantidad vendida,
> para llevar control de ingresos y de clientes recurrentes.

**Después:**
> Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí,
> quiero registrar cada venta con los datos del cliente y la cantidad vendida,
> para llevar control de ingresos y de clientes recurrentes.

**Criterios de aceptación:**
- El sistema permite capturar nombre del cliente, cantidad vendida, precio y fecha.
- El sistema descuenta automáticamente del inventario la cantidad vendida.
- Si la cantidad solicitada es mayor al inventario disponible, el sistema rechaza el registro y muestra un aviso.
- Se puede generar un listado de ventas filtrado por cliente y por periodo.

---

### Problemática 2, Historia 4 — Corte de caja

**Antes:**
> Como tesorero/a del Mercado Municipal de Huajuapan de León,
> quiero generar un corte de caja con el total cobrado en un periodo,
> para rendir cuentas claras a la administración municipal.

**Después:**
> Como tesorero del Mercado Municipal de Huajuapan de León,
> quiero generar un corte de caja con el total cobrado en un periodo,
> para rendir cuentas claras a la administración municipal.

**Criterios de aceptación:**
- El sistema suma automáticamente todos los pagos registrados en el periodo seleccionado.
- El corte de caja muestra el total esperado (según locatarios activos) contra el total cobrado real.
- El corte puede exportarse en formato PDF para su entrega.

---

### Problemática 3, Historia 4 — Trazabilidad completa del lote

**Antes:**
> Como comprador o autoridad reguladora,
> quiero consultar la trazabilidad completa de un lote,
> para verificar el origen y autenticidad del mezcal artesanal.

**Después (dividida en dos historias):**

**Historia 4a — Comprador final**
> Como comprador final,
> quiero consultar el origen y autenticidad de un lote de mezcal,
> para tener confianza en el producto que estoy adquiriendo.

**Criterios de aceptación:**
- El sistema permite buscar un lote por su identificador único.
- El sistema muestra fecha de producción, comunidad de origen y productor responsable.

**Historia 4b — Autoridad reguladora**
> Como autoridad reguladora,
> quiero consultar la trazabilidad completa de producción, costos y venta de un lote,
> para verificar el cumplimiento normativo del proceso artesanal.

**Criterios de aceptación:**
- El sistema permite buscar un lote por su identificador único.
- El sistema muestra en una sola vista: insumos usados, costos registrados y datos de venta.
- La información mostrada coincide exactamente con los registros individuales capturados.

## Conclusiones

La auditoría con IA fue útil sobre todo para detectar dos tipos de problema que el equipo no había notado al redactar las historias originales: roles ambiguos (uso de "/a" y mezcla de dos actores en una sola historia) y criterios de aceptación no verificables (faltaba especificar formato de exportación y el caso de venta mayor al inventario). De los 5 hallazgos, 4 se aceptaron y se aplicaron directamente a las historias; el hallazgo sobre el umbral configurable se rechazó por estar fuera del alcance de esta etapa del proyecto, dejándolo documentado como mejora futura. El resultado es un conjunto de historias con un solo actor por historia y criterios medibles, lo que facilita su verificación en las siguientes iteraciones.
