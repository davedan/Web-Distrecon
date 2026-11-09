# Informe de preparación — Distrecon

## Estado

**READY_FOR_BUSINESS_ANALYSIS_DISCOVERY**

La línea base de producto contiene alcance, roles, autenticación, canales de entrada, ciclo de pedido, custodia de archivos, retención, notificaciones, operación de pedidos inactivos y límites del MVP. Puede entregarse a Business Analysis para producir requisitos funcionales verificables.

No está lista para arquitectura ni desarrollo: continúan escalaciones técnicas, contenido y licencia de plantilla.

## Cobertura consolidada

| Área | Estado |
|---|---|
| Plataforma pública/privada y roles | Definido |
| Registro, verificación, cuentas y permisos | Definido |
| Pedido web, manual, correo e incidencias | Definido |
| Cliente inactivo y doble activación | Definido |
| Archivos, avisos, borrado e historial | Definido |
| Recogida y plazos operativos | Definido a nivel de producto |
| SEO, verticales y referencia visual | Definido a nivel de producto |
| Presupuesto manual | Diferido como deuda |
| Arquitectura y seguridad | Pendiente de Arquitectura |

## No bloquea el análisis funcional

- Catálogo/precios reales y horario público final: se modelan como configuración pendiente.
- Panel de métricas: BA debe definir requisitos y aceptación desde las métricas previstas.
- Fotos y textos definitivos: contenido posterior.
- Pressworks: puede guiar UX, pero no importarse sin licencia.

## Requiere escalación antes de desarrollo

1. Auth/RBAC, Payload/Turso y sesión.
2. Almacenamiento seguro, antivirus, límites, borrado, backup y auditoría.
3. Buzón de correo e ingestión de adjuntos.
4. Emails transaccionales, entregabilidad y recuperación de contraseña.
5. Protección de datos, política final y cobro real futuro.
6. Licencia/procedencia de plantilla y activos.

## Siguiente paso

1. Business Analyst crea Functional Requirements trazables desde PDD y Functional Discovery.
2. Propietario valida las decisiones abiertas de catálogo, notificaciones y cuadro de mando.
3. Arquitectura produce Architecture Contract y resuelve las escalaciones técnicas.
4. UX/UI actualiza pantallas a partir de FR y Architecture Contract.

La publicación en GitHub no constituye aprobación BMSF ni autorización de desarrollo.