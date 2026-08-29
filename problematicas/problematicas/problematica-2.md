# Historias de usuario — Problemática 2
## Digitalización de cobros y control de locatarios
### Mercado Municipal de la Heroica Ciudad de Huajuapan de León, Oaxaca

## Historia 1: Registro de locatarios
Como administrador del Mercado Municipal de Huajuapan de León,
quiero registrar a cada locatario con su local, giro comercial y cuota asignada,
para tener un padrón actualizado de todos los comerciantes del mercado.

**Criterios de aceptación:**
- El sistema permite capturar nombre del locatario, número de local, giro y monto de cuota mensual.
- Cada locatario queda asociado a un identificador único.
- Se puede consultar el listado completo de locatarios activos en cualquier momento.

## Historia 2: Registro de pagos de cuota
Como cobrador del Mercado Municipal de Huajuapan de León,
quiero registrar el pago de cuota de cada locatario por mes,
para saber con certeza quién ya pagó y quién está pendiente.

**Criterios de aceptación:**
- El sistema permite registrar fecha de pago, monto y mes que cubre.
- El sistema marca automáticamente como "pendiente" al locatario que no tiene pago registrado en el mes.
- Se puede consultar el historial de pagos de un locatario específico.

## Historia 3: Reporte de adeudos
Como administrador del Mercado Municipal de Huajuapan de León,
quiero ver un listado de locatarios con pagos atrasados,
para dar seguimiento oportuno a los adeudos.

**Criterios de aceptación:**
- El sistema genera un listado de locatarios con uno o más meses sin pago registrado.
- El listado muestra el monto total adeudado por locatario.
- El listado se puede filtrar por mes o por rango de meses.

## Historia 4: Corte de caja
Como tesorero/a del Mercado Municipal de Huajuapan de León,
quiero generar un corte de caja con el total cobrado en un periodo,
para rendir cuentas claras a la administración municipal.

**Criterios de aceptación:**
- El sistema suma automáticamente todos los pagos registrados en el periodo seleccionado.
- El corte de caja muestra el total esperado (según locatarios activos) contra el total cobrado real.
- El corte puede visualizarse o exportarse para su entrega.
