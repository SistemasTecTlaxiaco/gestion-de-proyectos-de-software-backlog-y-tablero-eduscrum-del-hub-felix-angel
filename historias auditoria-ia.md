# Auditoría con IA — Historias de usuario
## Herramienta utilizada: Claude (Anthropic)

## Prompt utilizado

Actúa como un experto en Scrum/eduScrum revisando historias de usuario.
Audita las siguientes historias de usuario y para cada una indica:
1. Si el formato "Como / Quiero / Para" está completo y bien usado.
2. Si el rol usado es específico y real, o es genérico/ambiguo.
3. Si los criterios de aceptación son verificables (medibles, concretos) o son vagos.
4. Si existe ambigüedad de alcance (si se puede interpretar de más de una forma).
5. Sugiere una versión corregida de la historia si encuentras problemas.



## Hallazgos de la IA

### Hallazgo 1
**Historia afectada:** Historia 5 - Problemática 1 (Reporte mensual) y Historia 4 - Problemática 2 (Corte de caja)
**Observación de la IA:** El rol está escrito como "presidente/a" y "tesorero/a". Usar la diagonal ("/a") para cubrir género no es un problema de fondo, pero puede leerse como si fueran dos roles distintos posibles, generando ambigüedad sobre quién es el actor real.
**Decisión del equipo:** Aceptado
**Argumento:** Tiene razón en que el rol debe quedar como un nombre único y claro. Decidimos usar "presidente de la Unión" y "tesorero del mercado" sin la diagonal, ya que en ambos casos existe una persona específica ocupando ese cargo.

### Hallazgo 2
**Historia afectada:** Historia 4 - Problemática 3 (Trazabilidad completa del lote)
**Observación de la IA:** La historia combina dos roles distintos en un mismo "Como": "comprador o autoridad reguladora". Cada historia de usuario debe tener un solo actor, porque comprador y autoridad reguladora pueden necesitar información distinta y tener motivaciones diferentes.
**Decisión del equipo:** Aceptado
**Argumento:** Es un error real de alcance. Separamos la historia en dos versiones, una por cada rol, para que cada una tenga su propio criterio de aceptación específico.

### Hallazgo 3
**Historia afectada:** Historia 5 - Problemática 1 (Reporte mensual)
**Observación de la IA:** El criterio "el reporte puede visualizarse en pantalla o exportarse" es vago porque no especifica en qué formato se exporta ni cómo se verifica que la exportación fue correcta.
**Decisión del equipo:** Aceptado
**Argumento:** Efectivamente no es verificable tal cual estaba. Se corrigió especificando el formato de exportación (PDF) como condición concreta.

### Hallazgo 4
**Historia afectada:** Historia 3 - Problemática 1 (Control de inventario disponible)
**Observación de la IA:** El umbral de alerta de "10 kg" está fijo en el criterio de aceptación; sugiere hacerlo configurable para que no dependa de un número arbitrario dentro de la historia.
**Decisión del equipo:** Rechazado
**Argumento:** Para efectos de esta evidencia y del alcance del proyecto, un umbral fijo es suficiente y más fácil de verificar como criterio de aceptación. Hacerlo configurable sería una mejora futura, no un requisito de esta etapa.

### Hallazgo 5
**Historia afectada:** Historia 4 - Problemática 1 (Registro de ventas y clientes)
**Observación de la IA:** No se especifica qué debe pasar si se intenta registrar una venta mayor al inventario disponible, lo cual deja un caso sin cubrir (ambigüedad de alcance).
**Decisión del equipo:** Aceptado
**Argumento:** Es un caso real que puede pasar en la operación diaria. Se agregó un criterio de aceptación adicional para cubrir ese escenario.

## Historias corregidas

### Antes (Problemática 1, Historia 5):
Como presidente/a de la Unión de Productores de Miel de San Juan Ñumí,
quiero generar un reporte mensual de producción, inventario y ventas,
para tomar decisiones informadas sobre la comercialización.

Criterios: reporte muestra totales; puede visualizarse en pantalla o exportarse; totales coinciden con registros.

### Después:
Como presidente de la Unión de Productores de Miel de San Juan Ñumí,
quiero generar un reporte mensual de producción, inventario y ventas,
para tomar decisiones informadas sobre la comercialización.

**Criterios de aceptación:**
- El reporte muestra totales de producción, inventario disponible y ventas del mes.
- El reporte puede exportarse en formato PDF.
- Los totales del reporte coinciden exactamente con los registros individuales de producción y ventas.

---

### Antes (Problemática 1, Historia 4):
Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí,
quiero registrar cada venta con los datos del cliente y la cantidad vendida,
para llevar control de ingresos y de clientes recurrentes.

### Después:
Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí,
quiero registrar cada venta con los datos del cliente y la cantidad vendida,
para llevar control de ingresos y de clientes recurrentes.

**Criterios de aceptación:**
- El sistema permite capturar nombre del cliente, cantidad vendida, precio y fecha.
- El sistema descuenta automáticamente del inventario la cantidad vendida.
- Si la cantidad solicitada es mayor al inventario disponible, el sistema rechaza el registro y muestra un aviso.
- Se puede generar un listado de ventas filtrado por cliente y por periodo.

---

### Antes (Problemática 2, Historia 4):
Como tesorero/a del Mercado Municipal de Huajuapan de León,
quiero generar un corte de caja con el total cobrado en un periodo,
para rendir cuentas claras a la administración municipal.

### Después:
Como tesorero del Mercado Municipal de Huajuapan de León,
quiero generar un corte de caja con el total cobrado en un periodo,
para rendir cuentas claras a la administración municipal.

**Criterios de aceptación:**
- El sistema suma automáticamente todos los pagos registrados en el periodo seleccionado.
- El corte de caja muestra el total esperado (según locatarios activos) contra el total cobrado real.
- El corte puede exportarse en formato PDF para su entrega.

---

### Antes (Problemática 3, Historia 4):
Como comprador o autoridad reguladora,
quiero consultar la trazabilidad completa de un lote,
para verificar el origen y autenticidad del mezcal artesanal.

### Después (dividida en dos historias):

**Historia 4a:**
Como comprador final,
quiero consultar el origen y autenticidad de un lote de mezcal,
para tener confianza en el producto que estoy adquiriendo.

**Criterios de aceptación:**
- El sistema permite buscar un lote por su identificador único.
- El sistema muestra fecha de producción, comunidad de origen y productor responsable.

**Historia 4b:**
Como autoridad reguladora,
quiero consultar la trazabilidad completa de producción, costos y venta de un lote,
para verificar el cumplimiento normativo del proceso artesanal.

**Criterios de aceptación:**
- El sistema permite buscar un lote por su identificador único.
- El sistema muestra en una sola vista: insumos usados, costos registrados y datos de venta.
- La información mostrada coincide exactamente con los registros individuales capturados.
