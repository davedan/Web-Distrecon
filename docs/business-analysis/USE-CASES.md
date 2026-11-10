# Casos de uso — Distrecon

## UC-001 Registro y primer pedido web
Cliente se registra, acepta términos, verifica email, inicia sesión, carga PDF, configura, revisa total con IVA, completa pago simulado y ve el pedido en revisión.

## UC-002 Pedido manual de mostrador
Dueño busca por email; si no existe, crea cliente activo e invita. Selecciona servicio publicado, carga PDF del pendrive, configura, aprueba por defecto y gestiona desde cola.

## UC-003 Correo entrante
Correo llega a bandeja operativa. Dueño revisa adjunto/remitente, vincula o crea cliente, solicita datos si faltan y solo entonces crea pedido.

## UC-004 Cliente inactivo
Pedido entrante de canal interno queda marcado y separado. Responsable activa cliente desde ficha, abre pedido, lo activa y lo incorpora al flujo.

## UC-005 Incidencia en pedido múltiple
Dueño marca una línea problemática. Las válidas siguen; cliente recibe aviso, sustituye PDF y se recalcula. Si cambia total, resuelve diferencia o se registra reembolso.

## UC-006 Cancelación
Cliente cancela antes de producción; operación puede cancelar siempre. Con pago completado, responsable registra reembolso simulado; historial muestra cancelación.

## UC-007 Recogida parcial
Operación marca líneas listas, entrega parte, pedido muestra Recogida parcial. Entrega final cambia a Entregado.

## UC-008 Caducidad
A 15/10/5 días sistema avisa; al día 30 elimina binario. Pedido permanece histórico y muestra Archivo caducado.

## UC-009 Administración de catálogo
Dueño crea servicio, define precio/plazo/opciones/defaults y publica. Solo entonces puede usarse en web/manual. Una indisponibilidad se muestra como No disponible.

## UC-010 Gestión de estimación
Sistema estima disponibilidad por plazo y horario. Dueño detecta retraso, actualiza estimación y cliente recibe aviso.