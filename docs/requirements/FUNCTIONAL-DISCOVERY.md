# Descubrimiento funcional — Distrecon

> Línea base consolidada para Business Analysis. No contiene decisiones de arquitectura.

## Actores

| Actor | Capacidades |
|---|---|
| Visitante | Navegar web pública, servicios, verticales, contacto y guía. |
| Cliente | Registrarse, verificar email, cargar PDF, crear pedidos, consultar estado/historial, sustituir archivo por incidencia y gestionar perfil. |
| Dueño | Gestionar clientes, cuentas de dueños, pedidos y configuración operativa; crear pedidos manuales y activar excepciones. |
| Superadministrador | Todas las capacidades operativas y CMS; única corrección de email existente. |

## FD-001 — Registro y acceso

1. Visitante rellena email único, contraseña, nombre obligatorio, apellidos opcionales y teléfono obligatorio.
2. Acepta términos obligatoriamente; se registra versión y fecha.
3. Recibe enlace de verificación.
4. Tras verificar email, se crea/activa la ficha como cliente activo.
5. Puede iniciar sesión, recuperar contraseña por correo o actualizar perfil salvo email.

**Reglas:**
- Sin email verificado no se crea pedido web.
- Email no es editable por cliente ni dueño; superadministrador puede corregirlo.
- Roles exclusivos.
- Todo dueño se crea por invitación y establece contraseña desde el correo recibido.

## FD-002 — Pedido web estándar

1. Cliente activo inicia sesión antes de cargar archivo.
2. Sube PDF y configura uno o varios trabajos.
3. El sistema calcula precio de demostración según reglas configurables.
4. Cliente confirma y completa pago simulado.
5. Sistema crea pedido con origen web y conserva instantánea de opciones/precio.
6. Con aprobación automática desactivada —valor inicial—, entra en Pendiente de revisión.
7. Dueño revisa y mueve a Confirmado/En producción; cliente recibe los avisos correspondientes.

**Reglas:**
- No hay pedido anónimo.
- Formato inicial: PDF.
- Los cambios de catálogo no alteran pedidos existentes.
- Si se habilita aprobación automática, requiere cliente activo, archivo válido y pago simulado completado.
- Solicitud de presupuesto manual no pertenece al MVP.

## FD-003 — Pedido manual de dueño

1. Dueño elige origen tienda o teléfono y busca cliente por email.
2. Si no existe, crea ficha con email obligatorio; el sistema envía invitación automática.
3. Si email existe, se prohíbe duplicar y se ofrece vincular al perfil mostrado.
4. Dueño registra pedido y puede subir el archivo entregado en pendrive.
5. El pedido nace aprobado por defecto, salvo que el dueño lo deje Pendiente de confirmación.
6. Entra en la misma cola e historial que los pedidos web.

## FD-004 — Entrada por correo

1. Llega una solicitud al buzón que definirá Arquitectura.
2. Se crea entrada para revisión manual, con remitente y adjuntos.
3. Dueño vincula a cliente existente o crea ficha tras validar datos.
4. No hay alta automática, impresión automática ni producción automática.
5. Si faltan datos, queda Pendiente de información y se avisa por centro de notificaciones y email.

## FD-005 — Cliente inactivo

1. Nuevo pedido de cliente inactivo genera alerta para dueños y superadministrador con marca “Cliente inactivo · revisión manual”.
2. Pedido queda separado de la cola ordinaria.
3. Responsable activa la ficha del cliente.
4. Responsable abre el pedido concreto y pulsa Activar pedido.
5. Solo después entra en el flujo operativo ordinario.

**Regla crítica:** activar al cliente nunca libera pedidos ya retenidos.

## FD-006 — Incidencia y reemplazo de archivo

1. Dueño marca pedido “Requiere tu acción” al detectar archivo no imprimible/incompleto.
2. Producción queda pausada.
3. Cliente recibe notificación dentro de la plataforma y por email.
4. Cliente puede reemplazar archivo o cancelar pedido.
5. Reemplazo elimina binario anterior, reinicia la conservación a 30 días y recalcula precio.
6. Pedido vuelve a revisión antes de producir.

## FD-007 — Archivos, historial y recogida

- Archivo: 30 días desde última carga; avisos a 15, 10 y 5 días por web y email.
- Día 30: borrado automático del binario; en el historial se muestra “Archivo caducado”.
- Historial: indefinido para cliente y operación.
- Pedido listo permanece así hasta entrega; no hay cancelación ni expiración automática por falta de recogida.
- Al entregar, estado final “Entregado”; la caducidad no modifica ese estado.

## FD-008 — Configuración y permisos

| Configuración | Dueño | Superadministrador |
|---|---:|---:|
| Horario comercial | Sí | Sí |
| Plazo por tipo de trabajo; 30 min por defecto | Sí | Sí |
| Catálogo, precios y disponibilidad | Sí | Sí |
| Aprobación automática web; inicial desactivada | Sí | Sí |
| Clientes y cuentas de dueños | Sí | Sí |
| CMS Payload | No | Sí |
| Corrección de email | No | Sí |

## Pendiente para análisis funcional

- Matriz final de servicios, acabados y campos de cada configurador.
- Validaciones técnicas exactas de PDF y límites de fichero.
- Cancelación fuera de una incidencia, edición de pedido y recogida.
- Catálogo exhaustivo de disparadores y plantillas de notificación.
- Cuadro de mando de primera versión y definición de cada métrica.
- Horario público final, catálogo/tarifa real, activos y licencia de Pressworks.
- Especificación arquitectónica de correo, antivirus, almacenamiento, privacidad y pagos.