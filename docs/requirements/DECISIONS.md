# Registro de decisiones — Distrecon

> Decisiones de producto confirmadas por el propietario. No sustituyen decisiones de Arquitectura.

## Base consolidada

Las decisiones DEC-0001 a DEC-0029 se mantienen en el PDD v0.3.0. Las siguientes amplían esa base.

| ID | Decisión |
|---|---|
| DEC-0030 | Cliente creado manualmente nace activo; verificación de email habilita acceso privado. |
| DEC-0031 | Cliente inactivo tiene área privada de solo lectura; no crea ni modifica pedidos. |
| DEC-0032 | Dueños/superadministrador reciben pedidos nuevos únicamente en el panel interno. |
| DEC-0033 | Cliente modifica opciones solo antes de producción y con pago pendiente; vuelve a revisión. No sustituye archivo sin incidencia. |
| DEC-0034 | Incidencia permite sustitución incluso tras pago; diferencia positiva requiere pago simulado adicional y diferencia negativa genera reembolso simulado manual. |
| DEC-0035 | Cancelación de pedido pagado por cliente, dueño o superadministrador genera reembolso simulado manual. |
| DEC-0036 | Dueño/superadministrador cancela en cualquier estado; motivo y comunicación al cliente son opcionales. |
| DEC-0037 | Todos los cambios de estado notifican al cliente por centro de notificaciones y email. |
| DEC-0038 | Se muestra estimación por plazo/horario; operación puede actualizarla y notificarla. |
| DEC-0039 | Entrega manual sin verificación digital; se permite recogida parcial. |
| DEC-0040 | Servicio requiere publicación explícita, precio y plazo antes de estar disponible por cualquier canal. |
| DEC-0041 | Cada servicio configura opciones propias, obligatoriedad y valores por defecto. |
| DEC-0042 | Precio muestra base imponible, IVA y total; IVA incluido. |
| DEC-0043 | Panel de dueños: estados, incidencias, pendientes de hoy, listos, origen, servicios y repetición. |
| DEC-0044 | Plantilla Printop 1.0.0 sustituye a Pressworks. El propietario confirma compra; compatibilidad/licencia de activos se escalan a Arquitectura. |
| DEC-0045 | Catálogo documental inicial: A5/A4/A3, gramajes 80–160 g según tamaño, B/N/color, caras, orientación, 1/2/4 páginas por cara y acabados básicos. Valores, límites y tarifa iniciales quedan en `docs/business-analysis/CATALOG-INITIAL-DEFAULTS.md` y son configurables. |

## Deuda de producto

| ID | Deuda |
|---|---|
| DTD-001 | Solicitud de presupuesto manual para trabajos especiales, fuera de MVP. |
| DTD-002 | Integración de WhatsApp Business. |

## Preguntas abiertas / escalaciones

| ID | Asunto | Destinatario |
|---|---|---|
| UPD-001 | Matriz concreta de servicios, opciones, límites y tarifas reales. | Propietario + Business Analysis |
| UPD-002 | Validación PDF, antivirus, almacenamiento, backups, borrado y límites. | Arquitectura |
| UPD-003 | Buzón, ingestión segura de correo y emails transaccionales. | Arquitectura |
| UPD-004 | Compatibilidad de Printop, derechos de activos y arquitectura aprobada. | Arquitectura + Propietario |
| UPD-005 | Horario público, fotos y contenido comercial definitivo. | Propietario |
| UPD-006 | Cobro real, reembolsos y cumplimiento cuando se salga del mockup. | Arquitectura + legal/negocio |