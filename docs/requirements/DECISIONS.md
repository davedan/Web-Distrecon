# Registro de decisiones — Distrecon

> Decisiones de producto confirmadas por el propietario. No sustituyen decisiones de Arquitectura.

## Confirmadas

| ID | Decisión |
|---|---|
| DEC-0001 | Plataforma única: web pública, login y zonas privadas dentro del mismo sistema. |
| DEC-0002 | Web pública sin login; login solo abre zona privada según rol. |
| DEC-0003 | Roles exclusivos: superadministrador, dueño y cliente. |
| DEC-0004 | CMS Payload exclusivo de superadministrador; Payload/Turso son restricciones para Arquitectura. |
| DEC-0005 | Idioma inicial español; plantilla Printop 1.0.0 (Wowtheme7) como referencia/adaptación descargada. El propietario confirma que adquirió la licencia; código/HTML declara GPL y CSS, diseño y activos se usarán conforme a esa licencia. ZIP SHA-256: \`70A5E95E401FD5B0D0C8AEA0850B2B10911C300674818491019E49F5C2AAEA8B\`. |
| DEC-0006 | Captación por servicios y verticales reales: particulares, estudiantes, autónomos/empresas, arquitectura/delineación y jurídico. |
| DEC-0007 | Recogida exclusiva en tienda; sin reparto MVP. |
| DEC-0008 | Precio configurable desde catálogo; pago simulado MVP. |
| DEC-0009 | Registro previo obligatorio antes de cargar o pedir por web. |
| DEC-0010 | Registro: email único, contraseña, nombre obligatorio, apellidos opcionales y teléfono obligatorio. |
| DEC-0011 | Verificación obligatoria de email; cliente verificado nace activo. |
| DEC-0012 | Aceptación obligatoria de términos, guardando versión/fecha y enlazando privacidad. |
| DEC-0013 | Cliente edita nombre, apellidos, teléfono y contraseña; no cambia email. Recupera contraseña por correo verificado. |
| DEC-0014 | Email es único. No se duplican fichas; dueño puede vincular pedido a cuenta existente. Solo superadministrador corrige email. |
| DEC-0015 | Dueños y superadministrador hacen CRUD de cuentas de dueños; cada alta se activa con invitación por email. |
| DEC-0016 | Pedidos entran por web, tienda, teléfono y correo. WhatsApp Business queda como deuda. |
| DEC-0017 | Pedidos creados por dueño quedan aprobados por defecto, salvo elección de Pendiente de confirmación. |
| DEC-0018 | Aprobación automática web configurable por dueños/superadministrador; valor inicial desactivado. |
| DEC-0019 | Cliente activo + archivo válido + pago simulado correcto son condición de aprobación automática cuando esté activada. |
| DEC-0020 | Cliente inactivo: alerta separada, activación de cliente y activación explícita de cada pedido; no hay liberación automática. |
| DEC-0021 | Ficha de cliente muestra pedidos, estados y alertas; desde cada pedido se puede activar. |
| DEC-0022 | Incidencia de archivo pausa pedido; cliente sustituye archivo o cancela. Reemplazo elimina binario previo y recalcula precio. |
| DEC-0023 | Archivo se conserva 30 días desde última carga; avisos 15/10/5 por centro de notificaciones y email. |
| DEC-0024 | Al día 30 el archivo se borra y se muestra “Archivo caducado”; el pedido conserva su estado real. |
| DEC-0025 | Historial de pedidos indefinido para cliente, dueños y superadministrador. |
| DEC-0026 | Pedido listo permanece hasta recogida; trabajo físico bajo custodia de Distrecon sin regla automática. |
| DEC-0027 | Horario comercial y plazo de preparación son configurables por dueños; plazo por defecto: 30 minutos. |
| DEC-0028 | Teléfonos públicos: 918 15 06 30 y 918 15 18 24, sin etiquetas. |
| DEC-0029 | Dirección: Av. de Madrid, 18, 28229 Villanueva del Pardillo. Correo: distrecon@distrecon.com. |

## Deuda de producto

| ID | Deuda |
|---|---|
| DTD-001 | Solicitud de presupuesto manual para trabajos especiales; explícitamente fuera de MVP. |
| DTD-002 | Integración de WhatsApp Business para entrada automatizada. |

## Preguntas abiertas / escalaciones

| ID | Asunto | Destinatario |
|---|---|---|
| UPD-001 | Matriz de servicios, opciones, límites y reglas reales de precio. | Propietario + Business Analysis |
| UPD-002 | Validaciones de PDF, antivirus, límites, almacenamiento, backups y borrado seguro. | Arquitectura |
| UPD-003 | Buzón de correo, ingestión segura de adjuntos y emails transaccionales. | Arquitectura |
| UPD-004 | Catálogo de notificaciones de pedido y métricas definitivas del panel de dueños. | Business Analysis |
| UPD-005 | Horario público definitivo, fotografías y contenido comercial. | Propietario |
| UPD-006 | Evidencia de compra/licencia de Printop, derechos de activos y compatibilidad con la arquitectura futura. | Propietario + Arquitectura |
| UPD-007 | Cobro real, reembolsos y obligaciones asociadas cuando salga del mockup. | Arquitectura + legal/negocio |