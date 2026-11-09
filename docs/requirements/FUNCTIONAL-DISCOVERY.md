# Descubrimiento funcional — Distrecon

> Borrador de descubrimiento. Complementa `PDD.md`; no sustituye el análisis funcional ni contiene requisitos aprobados.

## Alcance observado

El producto combina una web pública de captación, un flujo de pedido para recogida en tienda, una zona de cliente y una operación interna de pedidos.

## Actores

| Actor | Objetivo |
|---|---|
| Visitante | Encontrar un servicio, un perfil relevante, contacto o guía de preparación. |
| Cliente | Subir un PDF, configurarlo, confirmar un pedido y seguirlo. |
| Personal de tienda | Revisar, producir, marcar listo y entregar pedidos. |
| Responsable | Administrar catálogo, disponibilidad, reglas de precio y personal autorizado. |

## Flujo FD-001 — Pedido estándar

**Precondiciones:** cliente con cuenta, servicio estándar disponible y archivo PDF preparado.  
**Disparador:** el cliente selecciona “Sube tu trabajo”.

1. El cliente inicia sesión o crea una cuenta.
2. Sube uno o varios PDF.
3. Configura cada trabajo: formato, color, caras, orientación, páginas por cara, gramaje, copias, acabados y observaciones.
4. El sistema muestra un precio de demostración y la opción de recogida en tienda.
5. El cliente revisa carrito y confirma sus datos.
6. El cliente completa un pago simulado.
7. El sistema crea el pedido persistente y muestra confirmación.
8. El cliente consulta su pedido en el área privada.

**Alternativas y excepciones:**
- Archivo inválido o demasiado grande: informar del motivo y conservar el trabajo anterior sin pérdida de configuración.
- Acabado no disponible: impedir su selección o mostrar una alternativa antes de confirmar.
- Configuración especial: redirigir a solicitud de presupuesto.
- Archivo no imprimible o cambio necesario tras revisión: comportamiento pendiente de UPD-002.

**Resultado:** pedido con estado “confirmado”, especificaciones, total de demostración e historial de cambios.

## Flujo FD-002 — Producción y recogida

**Precondiciones:** pedido confirmado.  
**Disparador:** el personal abre la cola de pedidos.

1. El personal revisa archivo y especificaciones.
2. Marca el pedido en revisión, requiere aclaración o en producción.
3. Produce y aplica acabados.
4. Marca el pedido como listo para recoger.
5. El cliente recibe el aviso por el canal pendiente de decidir.
6. El personal registra la entrega.

**Estados:** borrador, pendiente de pago, confirmado, en revisión, requiere aclaración, en producción, listo para recoger, entregado, cancelado.

## Flujo FD-003 — Repetir un trabajo

1. El cliente abre un pedido o archivo todavía disponible.
2. Revisa la configuración conservada.
3. Ajusta lo necesario o confirma la repetición.
4. Continúa por carrito, pago simulado y seguimiento.

**Regla:** una actualización posterior del catálogo no modifica un pedido ya confirmado; un nuevo pedido aplica las reglas vigentes.

## Flujo FD-004 — Captación por perfil

1. El visitante llega a una página de perfil o servicio.
2. La página explica una necesidad real, los servicios aplicables, ejemplos y preguntas frecuentes.
3. El visitante inicia el configurador o solicita presupuesto.

**Perfiles:** estudiantes, autónomos/pequeñas empresas, arquitectura/delineación, documentación jurídica y particulares.

## Inventario de comportamiento pendiente para Business Analysis

- Matriz exacta de servicios estándar frente a trabajos con presupuesto.
- Reglas de composición de precio, impuestos y disponibilidad.
- Requisitos de cuenta, recuperación de acceso y roles.
- Gestión de archivos, expiración, borrado y consentimiento.
- Validaciones por formato, tamaño, número de páginas y acabado.
- Reglas de cancelación, cambios y controversias de pedido.
- Plantillas y canal de notificaciones.
- Criterios de entrega y confirmación en tienda.
