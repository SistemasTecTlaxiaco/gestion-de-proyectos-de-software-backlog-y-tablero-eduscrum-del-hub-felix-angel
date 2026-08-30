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

# Revisión de Historias de Usuario — Unión de Productores de Miel de San Juan Ñumi

## 📋 Resumen Ejecutivo

| Hallazgo | Historia afectada | Tipo de problema | Decisión | Estado |
|:--------:|:------------------|:-----------------|:--------:|:------:|
| 1 | HU-P1-005 — Reporte mensual | Redacción / Ambigüedad de rol | ✅ Aceptado | Corregido |
| 2 | HU-P2-004 — Trazabilidad del lote | Alcance / Múltiples actores | ✅ Aceptado | Dividido en 2 historias |
| 3 | HU-P1-005 — Reporte mensual | Criterio de aceptación vago | ✅ Aceptado | Corregido |
| 4 | HU-P1-003 — Control de inventario | Configurabilidad vs. simplicidad | ❌ Rechazado | Deuda técnica registrada |
| 5 | HU-P1-004 — Registro de ventas | Caso límite no cubierto | ✅ Aceptado | Corregido |

**Totales:** 4 aceptados | 1 rechazado | 0 pendientes

---

## 🔍 Hallazgos Detallados

### Hallazgo 1 — Rol escrito con diagonal de género

| Campo | Detalle |
|-------|---------|
| **ID del hallazgo** | H-001 |
| **Historias afectadas** | HU-P1-005 (Reporte mensual), HU-P2-004 (Corte de caja) |
| **Tipo** | Redacción / Ambigüedad |
| **Origen de la observación** | Revisión automática de estilo (IA) |
| **Decisión** | ✅ **Aceptado** |

**Observación:**  
El rol está escrito como `presidente/a` y `tesorero/a`. Usar la diagonal (`/a`) para cubrir género no es un problema de fondo, pero puede leerse como si fueran dos roles distintos posibles, generando ambigüedad sobre quién es el actor real.

**Argumento del equipo:**  
Coincidimos en que el rol debe quedar como un nombre único y sin ambigüedad. Optamos por escribir "presidente de la Unión" y "tesorero del mercado", sin diagonal, porque en ambos casos hay una persona específica ocupando ese cargo.

**Corrección aplicada:** Ver [HU-P1-005 corregida](#hu-p1-005-reporte-mensual) y [HU-P2-004 corregida](#hu-p2-004-corte-de-caja).

---

### Hallazgo 2 — Dos actores mezclados en un mismo "Como"

| Campo | Detalle |
|-------|---------|
| **ID del hallazgo** | H-002 |
| **Historia afectada** | HU-P3-004 — Trazabilidad completa del lote |
| **Tipo** | Alcance / Múltiples actores |
| **Origen de la observación** | Revisión de coherencia de actor (IA) |
| **Decisión** | ✅ **Aceptado** |

**Observación:**  
La historia combina dos roles distintos en un mismo "Como": `comprador o autoridad reguladora`. Cada historia de usuario debe tener un solo actor, porque comprador y autoridad reguladora pueden necesitar información distinta y tener motivaciones diferentes.

**Argumento del equipo:**  
Es un error real de alcance. Dividimos la historia en dos versiones, una por cada rol, de modo que cada una tenga su propio criterio de aceptación específico.

**Corrección aplicada:** Ver [HU-P3-004a y HU-P3-004b corregidas](#hu-p3-004a--004b-trazabilidad-del-lote).

---

### Hallazgo 3 — Criterio de exportación sin formato definido

| Campo | Detalle |
|-------|---------|
| **ID del hallazgo** | H-003 |
| **Historia afectada** | HU-P1-005 — Reporte mensual |
| **Tipo** | Criterio de aceptación no verificable |
| **Origen de la observación** | Revisión de verificabilidad (IA) |
| **Decisión** | ✅ **Aceptado** |

**Observación:**  
El criterio "el reporte puede visualizarse en pantalla o exportarse" es vago porque no especifica en qué formato se exporta ni cómo se verifica que la exportación fue correcta.

**Argumento del equipo:**  
No era verificable tal cual estaba redactado. Se corrigió especificando el formato de exportación (PDF) como condición concreta.

**Corrección aplicada:** Ver [HU-P1-005 corregida](#hu-p1-005-reporte-mensual).

---

### Hallazgo 4 — Umbral de alerta fijo (10 kg)

| Campo | Detalle |
|-------|---------|
| **ID del hallazgo** | H-004 |
| **Historia afectada** | HU-P1-003 — Control de inventario disponible |
| **Tipo** | Configurabilidad vs. simplicidad |
| **Origen de la observación** | Revisión de flexibilidad (IA) |
| **Decisión** | ❌ **Rechazado** |

**Observación:**  
El umbral de alerta de `10 kg` está fijo en el criterio de aceptación. Se sugiere hacerlo configurable para que no dependa de un número arbitrario dentro de la historia.

**Argumento del equipo:**  
Para el alcance de esta evidencia, un umbral fijo es suficiente y más fácil de verificar como criterio de aceptación. Hacerlo configurable queda como mejora futura.

**Registro de deuda técnica:**

| Ítem | ID deuda | Descripción | Prioridad sugerida |
|------|----------|-------------|-------------------|
| Umbral configurable | DT-001 | Hacer configurable el umbral de alerta de inventario bajo (actualmente fijo en 10 kg) | Media |

---

### Hallazgo 5 — Caso de venta mayor al inventario sin cubrir

| Campo | Detalle |
|-------|---------|
| **ID del hallazgo** | H-005 |
| **Historia afectada** | HU-P1-004 — Registro de ventas y clientes |
| **Tipo** | Caso límite no cubierto / Ambigüedad de alcance |
| **Origen de la observación** | Revisión de casos de uso (IA) |
| **Decisión** | ✅ **Aceptado** |

**Observación:**  
No se especifica qué debe pasar si se intenta registrar una venta mayor al inventario disponible, lo cual deja un caso sin cubrir (ambigüedad de alcance).

**Argumento del equipo:**  
Es un escenario real que puede ocurrir en la operación diaria. Se agregó un criterio de aceptación adicional para cubrirlo.

**Corrección aplicada:** Ver [HU-P1-004 corregida](#hu-p1-004-registro-de-ventas-y-clientes).

---

## 📝 Historias Corregidas

### HU-P1-005 — Reporte mensual

| Campo | Detalle |
|-------|---------|
| **Problemática** | P1 — Producción y comercialización |
| **Actor** | Presidente de la Unión de Productores de Miel de San Juan Ñumí |
| **Hallazgos relacionados** | H-001 (rol), H-003 (formato de exportación) |
| **Responsable de corrección** | [Nombre del responsable] |
| **Fecha de validación** | [Pendiente] |

**Antes:**

> Como presidente/a de la Unión de Productores de Miel de San Juan Ñumí, quiero generar un reporte mensual de producción, inventario y ventas, para tomar decisiones informadas sobre la comercialización.
>
> **Criterios:** reporte muestra totales; puede visualizarse en pantalla o exportarse; totales coinciden con registros.

**Después:**

> Como **presidente de la Unión de Productores de Miel de San Juan Ñumí**, quiero generar un reporte mensual de producción, inventario y ventas, para tomar decisiones informadas sobre la comercialización.

**Criterios de aceptación:**

1. El reporte muestra totales de producción, inventario disponible y ventas del mes.
2. El reporte puede exportarse en formato **PDF**.
3. Los totales del reporte coinciden exactamente con los registros individuales de producción y ventas.

---

### HU-P1-004 — Registro de ventas y clientes

| Campo | Detalle |
|-------|---------|
| **Problemática** | P1 — Producción y comercialización |
| **Actor** | Encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí |
| **Hallazgos relacionados** | H-005 (caso límite) |
| **Responsable de corrección** | [Nombre del responsable] |
| **Fecha de validación** | [Pendiente] |

**Antes:**

> Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí, quiero registrar cada venta con los datos del cliente y la cantidad vendida, para llevar control de ingresos y de clientes recurrentes.
>
> *(Sin criterios de aceptación detallados)*

**Después:**

> Como encargado de ventas de la Unión de Productores de Miel de San Juan Ñumí, quiero registrar cada venta con los datos del cliente y la cantidad vendida, para llevar control de ingresos y de clientes recurrentes.

**Criterios de aceptación:**

1. El sistema permite capturar nombre del cliente, cantidad vendida, precio y fecha.
2. El sistema descuenta automáticamente del inventario la cantidad vendida.
3. **Si la cantidad solicitada es mayor al inventario disponible, el sistema rechaza el registro y muestra un aviso.** *(Nuevo — H-005)*
4. Se puede generar un listado de ventas filtrado por cliente y por periodo.

---

### HU-P2-004 — Corte de caja

| Campo | Detalle |
|-------|---------|
| **Problemática** | P2 — Administración del mercado municipal |
| **Actor** | Tesorero del Mercado Municipal de San Juan Ñumi |
| **Hallazgos relacionados** | H-001 (rol) |
| **Responsable de corrección** | Equipo de desarrollo |
| **Fecha de validación** | [Pendiente] |

**Antes:**

> Como tesorero/a del Mercado Municipal de Huajuapan de León, quiero generar un corte de caja con el total cobrado en un periodo, para rendir cuentas claras a la administración municipal.

**Después:**

> Como **tesorero del Mercado Municipal de Huajuapan de León**, quiero generar un corte de caja con el total cobrado en un periodo, para rendir cuentas claras a la administración municipal.

**Criterios de aceptación:**

1. El sistema suma automáticamente todos los pagos registrados en el periodo seleccionado.
2. El corte de caja muestra el total esperado (según locatarios activos) contra el total cobrado real.
3. El corte puede exportarse en formato **PDF** para su entrega.

---

### HU-P3-004a / 004b — Trazabilidad del lote

| Campo | Detalle |
|-------|---------|
| **Problemática** | P3 — Trazabilidad del mezcal artesanal |
| **Hallazgos relacionados** | H-002 (múltiples actores) |
| **Responsable de corrección** | Eguipo de desarrollo |
| **Fecha de validación** | [Pendiente] |

**Antes:**

> Como comprador o autoridad reguladora, quiero consultar la trazabilidad completa de un lote, para verificar el origen y autenticidad del mezcal artesanal.

---

#### HU-P3-004a — Comprador final

> Como **comprador final**, quiero consultar el origen y autenticidad de un lote de mezcal, para tener confianza en el producto que estoy adquiriendo.

**Criterios de aceptación:**

1. El sistema permite buscar un lote por su identificador único.
2. El sistema muestra fecha de producción, comunidad de origen y productor responsable.

---

#### HU-P3-004b — Autoridad reguladora

> Como **autoridad reguladora**, quiero consultar la trazabilidad completa de producción, costos y venta de un lote, para verificar el cumplimiento normativo del proceso artesanal.

**Criterios de aceptación:**

1. El sistema permite buscar un lote por su identificador único.
2. El sistema muestra en una sola vista: insumos usados, costos registrados y datos de venta.
3. La información mostrada coincide exactamente con los registros individuales capturados.

---

## 📊 Lecciones Aprendidas

| Tipo de problema | Cantidad | Patrón detectado |
|:-----------------|:--------:|:-----------------|
| Redacción / Ambigüedad | 1 | Uso de diagonal de género en roles |
| Alcance / Actor mal definido | 1 | Múltiples actores en una sola historia |
| Criterio no verificable | 1 | Falta de formato o condición concreta |
| Caso límite omitido | 1 | Escenarios de error no contemplados |
| Configurabilidad pospuesta | 1 | Umbral fijo aceptado por simplicidad |

### Recomendaciones para futuras historias

1. **Definir el actor antes de redactar**: asegurar que haya una sola persona con un rol claro y sin ambigüedad de género en la redacción.
2. **Verificar criterios con la regla SMART**: cada criterio debe ser Específico, Medible, Alcanzable, Relevante y con Tiempo definido.
3. **Revisar casos límite de forma sistemática**: ¿qué pasa si no hay datos? ¿qué pasa si se excede una cantidad? ¿qué pasa si falla la conexión?
4. **Documentar decisiones de alcance**: cuando se rechace una mejora por simplicidad, registrarla explícitamente como deuda técnica.

---

## ✅ Checklist de Cierre

- [x] Todos los hallazgos revisados por el equipo
- [x] Historias corregidas redactadas con formato estándar
- [x] Deuda técnica registrada (DT-001)
- [ ] Asignar responsables de corrección
- [ ] Validar historias corregidas con stakeholders
- [ ] Actualizar backlog con HU-P3-004a y HU-P3-004b
- [ ] Programar revisión de deuda técnica para siguiente sprint

---


## Conclusiones

La auditoría con IA fue útil sobre todo para detectar dos tipos de problema que el equipo no había notado al redactar las historias originales: roles ambiguos (uso de "/a" y mezcla de dos actores en una sola historia) y criterios de aceptación no verificables (faltaba especificar formato de exportación y el caso de venta mayor al inventario). De los 5 hallazgos, 4 se aceptaron y se aplicaron directamente a las historias; el hallazgo sobre el umbral configurable se rechazó por estar fuera del alcance de esta etapa del proyecto, dejándolo documentado como mejora futura. El resultado es un conjunto de historias con un solo actor por historia y criterios medibles, lo que facilita su verificación en las siguientes iteraciones.
