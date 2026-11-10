---
artifact:
  id: FR-0001
  type: functional-requirements
  version: 0.1.0
  status: DRAFT
ownership: { discipline: business-analysis, role: business-analyst }
traceability: { upstream: [PDD-0.3.0], downstream: [] }
governance:
  created_at: 2026-11-10
  approval_state: PENDING
blocking: { is_blocked: false, blockers: [] }
---

# Requisitos funcionales — Distrecon

> Borrador BA trazable al PDD v0.3.0. No selecciona arquitectura.

| ID | Requisito y aceptación verificable |
|---|---|
| FR-0001 | **Web pública.** Visitante puede consultar servicios publicados, verticales, guía y contacto sin login. Dado un servicio no publicado, cuando visita la web, entonces no puede iniciarlo. |
| FR-0002 | **Registro.** Sistema exige email único, contraseña, nombre y teléfono; apellidos opcionales. Dado términos no aceptados, cuando intenta completar alta, entonces se rechaza. |
| FR-0003 | **Verificación y acceso.** Cliente web no puede crear pedido hasta verificar email. Dado enlace válido, cuando lo completa, entonces accede con cuenta activa. |
| FR-0004 | **Perfil y credenciales.** Cliente modifica nombre/apellidos/teléfono y contraseña, pero no email. Dado olvido de contraseña, cuando solicita recuperación con email existente, entonces recibe enlace de restablecimiento. |
| FR-0005 | **Roles.** Sistema concede exactamente un rol exclusivo por cuenta. Cliente no puede acceder a paneles internos; dueño no accede a CMS; solo superadministrador accede a CMS y corrige email. |
| FR-0006 | **Catálogo publicable.** Dueño/superadministrador crea servicios no publicados. Dado servicio sin precio o plazo, cuando intenta publicarlo, entonces se rechaza. |
| FR-0007 | **Configurador por servicio.** Servicio publicado expone únicamente sus propias opciones, valores obligatorios/opcionales y valores por defecto. |
| FR-0008 | **Pedido web.** Cliente activo y verificado puede cargar uno o más PDF y configurar cada línea. Dado archivo múltiple, cuando configura cada uno, entonces cada línea conserva opciones/precio propios. |
| FR-0009 | **Precio/pago simulado.** Checkout muestra base, IVA y total en euros. Dado pago simulado completado, entonces estado de pago es Completado y se crea pedido persistente. |
| FR-0010 | **Flujo de aprobación.** Con aprobación automática desactivada, pedido web confirmado entra Pendiente de revisión. Si se activa, solo confirma con cliente activo, archivo válido y pago completado. |
| FR-0011 | **Pedidos manuales y correo.** Dueño crea pedido de tienda/teléfono para servicio publicado y puede crear cliente activo/invitarlo. Correo siempre entra a revisión manual, sin alta/impresión automática. |
| FR-0012 | **Cliente inactivo.** Cliente inactivo solo consulta historial. Pedido de canal interno para cliente inactivo queda retenido y exige activar cliente y activar ese pedido explícitamente. |
| FR-0013 | **Modificación previa.** Dado pedido sin producción y pago Pendiente, cliente puede cambiar opciones; sistema recalcula y devuelve el pedido a revisión. Con pago Completado o en producción, no puede hacerlo. |
| FR-0014 | **Incidencia.** Dueño puede marcar solo una línea como Requiere tu acción. Cliente puede sustituir ese archivo, se elimina el binario anterior, se reinicia retención y se recalcula. |
| FR-0015 | **Ajuste económico simulado.** Con diferencia positiva por incidencia, pago pasa a Pendiente por diferencia y cliente realiza pago simulado. Con diferencia negativa, dueño/superadministrador registra reembolso simulado y pago queda Completado. |
| FR-0016 | **Cancelación.** Cliente cancela antes de producción; dueño/superadministrador en cualquier estado. Dado pedido pagado cancelado, entonces se genera reembolso simulado manual y se conserva historial. |
| FR-0017 | **Estados y notificaciones.** Cada cambio de estado genera notificación en área cliente y email. Dueños/superadministrador reciben nuevos pedidos solo en panel interno. |
| FR-0018 | **Disponibilidad/recogida.** Sistema calcula estimación con horario/plazo; operación puede actualizarla. Dueño/superadministrador marca entrega manualmente. Debe permitir Recogida parcial y finalizar como Entregado al completar todas las líneas. |
| FR-0019 | **Archivos/historial.** Archivo vive 30 días desde última carga; avisa 15/10/5; luego se borra y muestra Archivo caducado. Historial es indefinido. Cliente no borra archivo; operación sí, con notificación obligatoria. |
| FR-0020 | **Panel de dueños.** Panel muestra pedidos por estado, incidencias abiertas, pendientes de hoy, listos, origen, servicios solicitados y repetición de clientes. |
| FR-0021 | **Configuración.** Dueño/superadministrador configura horario, plazo por tipo (30 min por defecto), catálogo, precios, disponibilidad y aprobación automática. Cambios afectan solo pedidos nuevos. |
| FR-0022 | **Auditoría funcional.** Sistema conserva trazabilidad de cambios de estado, activación de cliente/pedido, pagos/reembolsos simulados, cancelación y borrado manual de archivo. |