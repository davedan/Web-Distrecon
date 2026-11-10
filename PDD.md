# PDD — Distrecon

> Estado: **CONSOLIDATED_FOR_BA_REVIEW**. Producto definido para análisis funcional; no es Architecture Contract ni autorización de desarrollo.

- Producto: Distrecon
- Idioma inicial: español
- Ubicación: Av. de Madrid, 18, 28229 Villanueva del Pardillo
- Contacto público: 918 15 06 30 · 918 15 18 24 · distrecon@distrecon.com
- Versión: 0.3.0
- Fecha: 10 de noviembre de 2026

## Problema y objetivo

Distrecon necesita captar demanda local de copistería, impresión y acabados gráficos, y convertirla en pedidos trazables recogidos en tienda. La plataforma consolida pedidos web, mostrador, teléfono y correo para que el equipo gestione el negocio sin perder la experiencia digital del cliente.

## Alcance de plataforma

Una sola plataforma contiene: web pública sin login, acceso, zona privada por rol y CMS Payload exclusivo de superadministrador. No son aplicaciones separadas. Payload y Turso son restricciones indicadas por el propietario para Arquitectura, no decisiones arquitectónicas aprobadas.

## Usuarios y roles exclusivos

| Rol | Alcance |
|---|---|
| Superadministrador | CMS, configuración, cuentas, operación y corrección excepcional de email. Solo cambia su propia contraseña. |
| Dueño | Clientes, cuentas de dueños, pedidos, operación, catálogo, configuración permitida y telemetría. Puede gestionar su propia cuenta. |
| Cliente | Perfil, archivos vigentes, pedidos, historial y notificaciones propios. |

Cada cuenta tiene exactamente un rol.

## Captación pública y SEO

- Posicionamiento local de copistería, impresión, planos/gran formato y acabados gráficos.
- Verticales reales: particulares, estudiantes, autónomos/pequeñas empresas, arquitectura/delineación y documentación jurídica.
- Servicios activos: impresión documental, fotocopias, escaneado, encuadernaciones, planos/gran formato, pósteres/fotografía y material de oficina.
- Plantilla: Printop 1.0.0 de Wowtheme7, disponible localmente en `template/printop`; ZIP SHA-256 `70A5E95E401FD5B0D0C8AEA0850B2B10911C300674818491019E49F5C2AAEA8B`. El propietario confirma que fue adquirida. Arquitectura validará compatibilidad, dependencias y uso de activos.
- Recogida exclusivamente en tienda; sin reparto.

## Cuenta y acceso

- Registro antes de cargar o pedir por web: email único, contraseña, nombre obligatorio, apellidos opcionales y teléfono obligatorio.
- Email verificado antes del primer pedido web. La cuenta web verificada nace activa.
- Un dueño puede crear cliente manualmente: nace activo, se invita por email y la verificación habilita el acceso privado.
- Términos obligatorios con versión/fecha y acceso a privacidad.
- Cliente modifica nombre, apellidos, teléfono y contraseña; no email. Recuperación por enlace de correo.
- Email único. No hay duplicados; el dueño puede vincular pedido con cuenta existente. Solo superadministrador corrige email.
- Las cuentas de dueños se crean por invitación. Roles exclusivos.

## Catálogo y pedido

- Dueños/superadministrador crean servicios sin publicar. Solo servicios publicados están disponibles para web y pedidos manuales.
- Un servicio requiere como mínimo precio y plazo para publicarse; define sus propias opciones, obligatoriedad y valores por defecto.
- Precios en euros, IVA incluido, con desglose de base, IVA y total.
- Pedido web: cliente autenticado, activo y verificado carga PDF, configura trabajos, confirma, completa pago simulado y recibe número/seguimiento.
- Varios archivos admiten configuraciones y precios propios.
- Pago MVP: simulado. Estados: Pendiente/Completado.
- Solicitud de presupuesto manual es deuda DTD-001, fuera de MVP.
- Valores iniciales de catálogo, límites y tarifa: `docs/business-analysis/CATALOG-INITIAL-DEFAULTS.md`; editables por dueños/superadministrador.

## Operación, estado y excepciones

Estados de pedido: Recibido, Pendiente de revisión, Pendiente de confirmación, Confirmado, En producción, Listo para recoger, Recogida parcial, Entregado, Pendiente de información, Requiere tu acción y Cancelado.

- Aprobación automática web configurable por dueños/superadministrador; inicialmente desactivada. Solo puede actuar con cliente activo, archivo válido y pago completado.
- Pedido creado por dueño nace aprobado, salvo decisión de pendiente de confirmación.
- Cliente puede modificar opciones solo antes de producción y con pago pendiente; vuelve a revisión. Para reemplazar archivo sin incidencia, cancela y crea pedido nuevo.
- Incidencia pausa solo la línea problemática. El cliente puede sustituirla; se elimina binario anterior, reinicia retención y recalcula.
- Diferencia positiva tras incidencia: pago pendiente adicional; el cliente realiza pago simulado. Diferencia negativa: dueño/superadministrador registra reembolso simulado y pago continúa completado.
- Cancelación por cliente antes de producción; dueños/superadministrador pueden cancelar en cualquier estado. Pedido pagado cancelado: reembolso simulado manual. Motivo y comunicación de cancelación de dueño son opcionales.
- Cliente inactivo: solo historial de lectura. Pedidos entrantes operados por tienda quedan retenidos y requieren activar cliente y activar pedido por separado.
- Cada cambio de estado notifica al cliente dentro de la aplicación y por email. Estimación de disponibilidad se calcula con plazo/horario; dueño puede actualizarla.
- Entrega es gestión humana registrada manualmente por dueño/superadministrador. Hay recogida parcial.

## Archivos, historia y notificaciones

- Archivo binario: 30 días desde última carga/sustitución.
- Avisos a 15, 10 y 5 días, por centro de notificaciones y email.
- Día 30: borrado de binario; historial indefinido para los tres roles; interfaz muestra “Archivo caducado”.
- Cliente no borra manualmente archivos. Dueño/superadministrador pueden hacerlo y se notifica siempre al cliente.
- Pedido listo permanece hasta entrega; trabajo físico bajo custodia de Distrecon sin retirada automática.

## Panel y configuración

- Panel inicial: pedidos por estado, incidencias abiertas, pendientes de hoy, listos para recoger, origen, servicios más solicitados y repetición de clientes.
- Configuración por dueños/superadministrador: horario comercial, plazo por tipo de trabajo (30 minutos por defecto), catálogo/precios/disponibilidad y aprobación automática. Los cambios solo afectan nuevos pedidos.

## Fuera de alcance MVP

Cobros reales, facturación, contabilidad, inventario, costes industriales, entrega a domicilio, integración WhatsApp, presupuesto manual, conversión automática de Office/imágenes y decisiones de arquitectura.

## Dependencias y escalaciones

Arquitectura resolverá identidad/RBAC, Payload/Turso, almacenamiento, borrado y backups, validación/antivirus, correo entrante, emails, límites de archivo, privacidad, pagos reales y compatibilidad de Printop.

## Deuda

| ID | Descripción |
|---|---|
| DTD-001 | Solicitud de presupuesto manual para trabajos especiales. |
| DTD-002 | Integración WhatsApp Business. |

## Trazabilidad

El detalle funcional está en `docs/business-analysis/`, producido desde este PDD y las decisiones de propietario del 10 de noviembre de 2026.