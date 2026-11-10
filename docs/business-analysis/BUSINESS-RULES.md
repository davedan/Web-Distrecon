# Reglas de negocio — Distrecon

| ID | Regla |
|---|---|
| BR-001 | Email identifica de forma única una ficha de cliente. |
| BR-002 | Todo pedido web requiere cliente autenticado, verificado y activo. |
| BR-003 | Roles son exclusivos. |
| BR-004 | Cliente manual nace activo; acceso privado depende de verificación de email. |
| BR-005 | Cliente inactivo queda solo en lectura y no inicia acciones operativas. |
| BR-006 | Activar cliente no libera pedidos retenidos; cada pedido necesita activación propia. |
| BR-007 | Servicio no publicado no admite pedidos por ningún canal. |
| BR-008 | Publicar exige precio y plazo; cada servicio declara opciones y defaults propios. |
| BR-009 | Todo precio incluye IVA y se desglosa. |
| BR-010 | Pago MVP solo es Pendiente o Completado; no hay cobro real. |
| BR-011 | Aprobación automática web inicia desactivada y solo actúa con sus tres condiciones. |
| BR-012 | Pedido de dueño nace aprobado salvo selección explícita contraria. |
| BR-013 | Cliente edita opciones solo con pago pendiente y sin producción. |
| BR-014 | Sustitución normal de archivo no existe; se cancela y crea nuevo pedido. |
| BR-015 | Sustitución por incidencia elimina binario anterior y reinicia 30 días. |
| BR-016 | Diferencia positiva exige pago simulado adicional; negativa exige reembolso simulado manual. |
| BR-017 | Cancelación pagada exige reembolso simulado manual. |
| BR-018 | Cancelación operativa puede llevar motivo/comunicación opcionales. |
| BR-019 | Incidencia de línea no paraliza otras líneas válidas. |
| BR-020 | Recogida parcial es posible; Entregado solo llega al completar líneas. |
| BR-021 | Archivo se borra a 30 días; historial nunca se borra por esta regla. |
| BR-022 | Cliente no borra archivos; operación puede borrar y debe notificar. |
| BR-023 | Todos los cambios de estado notifican a cliente por web y email. |
| BR-024 | Operación recibe pedidos nuevos solo en panel. |
| BR-025 | Entrega se registra como gestión humana, sin validación digital. |
| BR-026 | Configuración nueva no reescribe pedidos existentes. |
| BR-027 | Solicitud de presupuesto manual y WhatsApp no pertenecen al MVP. |