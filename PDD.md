# PDD — Distrecon

> Estado: **CONSOLIDATED_FOR_BA_DISCOVERY**. Producto definido para análisis funcional; no es Architecture Contract ni autorización de desarrollo.

- Producto: Distrecon
- Idioma inicial: español
- Ubicación: Av. de Madrid, 18, 28229 Villanueva del Pardillo
- Contacto público: 918 15 06 30 · 918 15 18 24 · distrecon@distrecon.com
- Versión: 0.2.0
- Fecha: 9 de noviembre de 2026

## Problema y objetivo

Distrecon necesita captar demanda local de copistería, impresión y acabados gráficos, y convertirla en pedidos trazables recogidos en tienda. La plataforma debe consolidar pedidos web, de mostrador, teléfono y correo para que el equipo gestione el negocio sin perder la experiencia digital del cliente.

## Alcance de plataforma

Una sola plataforma contiene:

1. **Web pública, sin login:** SEO local, páginas de servicios y verticales, contacto, guía de archivos y captación.
2. **Acceso:** registro e inicio de sesión; protege solo zonas privadas.
3. **Zona privada por rol:** el sistema muestra el área adecuada a cada identidad.
4. **CMS:** Payload, accesible exclusivamente al superadministrador.

No son aplicaciones separadas. Payload y Turso son restricciones tecnológicas indicadas por el propietario para Arquitectura, no decisiones arquitectónicas aprobadas.

## Usuarios y roles exclusivos

| Rol | Alcance |
|---|---|
| Superadministrador | Único acceso al CMS; gestiona configuración, cuentas, operación y correcciones excepcionales de email. Solo puede cambiar su propia contraseña. |
| Dueño | Gestiona clientes, cuentas de dueños, pedidos, operación, catálogo/configuración permitida y telemetría. Puede gestionar su propia cuenta. |
| Cliente | Gestiona únicamente su perfil, archivos vigentes, pedidos, historial y notificaciones. |

Cada cuenta tiene exactamente un rol: superadministrador, dueño o cliente. No hay roles combinados.

## Captación pública y SEO

- Posicionamiento local de copistería, impresión, planos/gran formato y acabados gráficos.
- Verticales reales: particulares, estudiantes, autónomos/pequeñas empresas, arquitectura/delineación y documentación jurídica.
- Servicios activos: impresión documental, fotocopias, escaneado, encuadernaciones, planos/gran formato, pósteres/fotografía y material de oficina.
- Referencia visual: Pressworks. Puede inspirar jerarquía, navegación y recorrido; no autoriza copiar código, textos, imágenes ni activos sin licencia verificada.
- Recogida únicamente en tienda; sin reparto ni transportistas.

## Cuenta y acceso de cliente

- Registro obligatorio antes de cargar archivos o crear pedidos web.
- Datos de alta: email único, contraseña, nombre obligatorio, apellidos opcionales y teléfono obligatorio.
- Verificación obligatoria de email antes del primer pedido.
- Tras verificar, la ficha se crea activa por defecto.
- El alta exige aceptación explícita de términos; se registra versión y fecha, con enlace a privacidad.
- El cliente puede editar nombre, apellidos, teléfono y contraseña; no puede cambiar email.
- Recuperación de contraseña por enlace al email verificado y regreso posterior al login.
- El email es clave única. Un dueño que intente crear una ficha con email existente no puede duplicarla: ve la cuenta encontrada y decide si vincula el pedido o corrige/cancela el alta.
- Solo el superadministrador puede corregir un email existente.
- Las cuentas de dueños se crean con invitación por email para establecer contraseña.

## Pedidos y canales

### Canales activos

- Web: cliente autenticado.
- Tienda: pedido creado por dueño, incluyendo carga de archivos aportados en pendrive.
- Teléfono: pedido creado por dueño.
- Correo: entrada a revisar manualmente por dueño; no crea cliente ni imprime automáticamente.

Todos terminan en una cola común filtrable por origen. WhatsApp Business es deuda técnica, no integración MVP.

### Pedido web estándar

1. Cliente registrado, verificado y activo.
2. Carga PDF y configura uno o varios trabajos.
3. Ve precio calculado desde catálogo configurable, con importes de demostración.
4. Confirma y completa pago simulado.
5. Se crea pedido persistente para recogida en tienda.

El pago es simulado en MVP; no hay cobros, reembolsos, facturación ni pasarela real.

### Aprobación y estados

Estados operativos: **Recibido**, **Pendiente de revisión**, **Pendiente de confirmación**, **Confirmado**, **En producción**, **Listo para recoger**, **Entregado**, **Pendiente de información**, **Requiere tu acción** y **Cancelado por el cliente**.

- Dueños y superadministrador configuran la aprobación automática de pedidos web; valor inicial: desactivada.
- Si está activada, solo aprueba pedidos de cliente activo, archivo válido y pago simulado completado.
- Pedidos creados por dueño nacen aprobados por defecto, salvo que el dueño elija pendiente de confirmación.
- El dueño controla el paso a producción.
- Si aparece una incidencia de archivo, el pedido se pausa en “Requiere tu acción”. El cliente puede sustituir el archivo o cancelar.
- Al reemplazar un archivo se recalcula el precio por las páginas/configuración reales; no se conserva el binario anterior.
- Un pedido entregado permanece como **Entregado**. “Archivo caducado” es solo disponibilidad del fichero, nunca estado del pedido.

### Clientes inactivos y doble activación

- Cada ficha de cliente tiene estado **Activo / Inactivo**.
- Un pedido entrante de cliente inactivo genera alerta interna “Cliente inactivo · revisión manual” y queda fuera de la cola ordinaria.
- Primero un dueño/superadministrador debe activar al cliente desde su ficha.
- Después debe abrir el pedido concreto y pulsar explícitamente “Activar pedido”.
- Reactivar un cliente no libera pedidos retenidos. Cada pedido exige activación propia.
- La ficha de cliente muestra la lista de pedidos, estados y alertas, con acceso directo al pedido.

## Archivos, historial y notificaciones

- Archivo binario disponible durante 30 días desde su última carga o sustitución.
- Avisos de caducidad a 15, 10 y 5 días.
- Toda notificación al cliente aparece en su centro de notificaciones y por email.
- Al día 30 se elimina el archivo. El historial conserva pedido, configuración, precio, estados y trazabilidad; donde antes habría enlace se muestra “Archivo caducado”.
- Historial de pedidos: indefinido para clientes, dueños y superadministrador.
- Los archivos sustituidos se eliminan; el historial puede indicar que hubo sustitución sin conservar el binario previo.
- Pedidos listos para recoger permanecen en ese estado hasta entrega. El producto físico no tiene regla automática de retirada; queda bajo custodia de Distrecon.

## Operación y configuración

### Panel de dueños

Centro de control con pedidos nuevos, revisiones, incidencias, producción, listos para recoger, pedidos de clientes inactivos y cola filtrable. Debe permitir trabajar pedidos manuales y ver origen, estado, historial y cliente.

Las métricas previstas incluyen carga por estado, incidencias, plazos, pedidos listos, origen, servicios solicitados, repetición y valor de pedidos. Mientras el pago sea simulado, no se denomina facturación.

### Configuración

Dueños y superadministrador pueden configurar horario comercial, plazo de preparación por tipo de trabajo —30 minutos por defecto—, catálogo/precios/disponibilidad y activación de aprobación automática web. Los nuevos ajustes aplican a pedidos nuevos, no reescriben pedidos existentes.

## Fuera de alcance MVP

- Cobro real, reembolsos, facturación, contabilidad, inventario, compras y costes industriales.
- Entrega a domicilio.
- WhatsApp Business como canal integrado.
- Solicitud de presupuesto manual para trabajos especiales: deuda de producto, no MVP.
- Conversión automática de formatos Office o imágenes; el formato inicial de pedido es PDF.
- SEO de páginas duplicadas por localidad o profesión.
- Decisiones de arquitectura, infraestructura, autenticación técnica, correo, almacenamiento o seguridad.

## Dependencias y escalaciones

Arquitectura debe resolver autenticación y permisos, Payload/Turso, almacenamiento privado, borrado y backups, antivirus/validación de adjuntos, buzón de correo, emails transaccionales, límites de archivos, protección de datos y futura pasarela real.

Contenido debe aportar horario definitivo, activos visuales, catálogo y precios reales. La licencia de Pressworks debe verificarse antes de adaptar código o activos.

## Deuda de producto

| ID | Deuda | Motivo |
|---|---|---|
| DTD-001 | Solicitud de presupuesto manual para trabajos especiales. | Aplazada por propietario; no forma parte del MVP. |
| DTD-002 | Integración de WhatsApp Business. | Posible canal futuro; requiere definición e integración segura. |

## Aprobación de producto

Este documento consolida decisiones comunicadas por el propietario. El siguiente destinatario es Business Analysis para transformar la línea base en requisitos funcionales verificables.