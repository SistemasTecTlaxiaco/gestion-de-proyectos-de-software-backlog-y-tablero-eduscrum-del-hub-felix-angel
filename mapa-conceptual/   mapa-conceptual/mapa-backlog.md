# Mapa conceptual – Backlog
## Fases del proyecto y ubicación de historias de usuario

## Fase 1: Inicio
- Problemática 1: Falta de control de producción y comercialización de miel (Unión de Productores de Miel de San Juan Ñumí)
- Problemática 2: Falta de control de cobros y locatarios (Mercado Municipal de Huajuapan de León)
- Problemática 3: Falta de trazabilidad en producción de mezcal artesanal (Cooperativa de mezcal, región Mixteca)
- Definición de objetivos del proyecto y organizaciones beneficiadas

## Fase 2: Planificación (Historias de usuario y backlog)
- H1-P1: Registro de productores y colmenas
- H2-P1: Registro de producción por cosecha
- H3-P1: Control de inventario disponible
- H4-P1: Registro de ventas y clientes (corregida)
- H5-P1: Reporte mensual para toma de decisiones (corregida)
- H1-P2: Registro de locatarios
- H2-P2: Registro de pagos de cuota
- H3-P2: Reporte de adeudos
- H4-P2: Corte de caja (corregida)
- H1-P3: Registro de lotes de producción
- H2-P3: Registro de costos de producción
- H3-P3: Registro de ventas a intermediarios y clientes
- H4a-P3: Consulta de trazabilidad para comprador
- H4b-P3: Consulta de trazabilidad para autoridad reguladora
- Auditoría con IA y corrección de historias (ver auditoria-ia.md)

## Fase 3: Ejecución
- Diseño y construcción de base de datos: productores, colmenas, cosechas, inventario, ventas (Problemática 1)
- Diseño y construcción de base de datos: locatarios, pagos, adeudos (Problemática 2)
- Diseño y construcción de base de datos: lotes, costos, ventas, trazabilidad (Problemática 3)
- Desarrollo de módulos de registro, control y reportes para las 3 organizaciones

## Fase 4: Monitoreo y control
- Verificación de que los criterios de aceptación de cada historia se cumplen
- Validación de casos límite agregados en la auditoría (ej. venta mayor al inventario disponible)
- Seguimiento del tablero eduScrum (Issues y Project) para revisar avance real

## Fase 5: Cierre
- Entrega de reportes funcionales a cada organización (Unión de Miel, Mercado, Cooperativa de mezcal)
- Documentación final del proyecto y lecciones aprendidas
- Recomendaciones de mejora continua

## Ajustes decididos

**Historia partida:**
- H4-P3 (Trazabilidad completa del lote) se partió en dos historias: H4a-P3 (para el comprador final) y H4b-P3 (para la autoridad reguladora), porque mezclaba dos roles distintos con necesidades diferentes.

**Historias reescritas:**
- H5-P1 y H4-P2: se ajustó el rol ("presidente/a" → "presidente", "tesorero/a" → "tesorero") y se especificó el formato de exportación (PDF) en sus criterios de aceptación.
- H4-P1: se agregó un criterio de aceptación para cubrir el caso de venta mayor al inventario disponible.

**Qué falta:**
- Falta una historia para el registro de usuarios/permisos del sistema (quién puede editar vs. solo consultar), pendiente de definir en la fase de Planificación.
- Falta una historia de respaldo/exportación general de la base de datos para cada organización, a integrar antes del Cierre.
