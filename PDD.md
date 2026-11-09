# PDD — Distrecon

> Candidato externo de Definición de Producto. Estado: **DRAFT**. No es un artefacto BMSF aprobado.

- Producto: Distrecon
- Repositorio: `davedan/Web-Distrecon`
- Idioma inicial: español
- Fecha: 9 de noviembre de 2026
- Versión: 0.1.0

## Problem

Distrecon es una copistería e imprenta local de Villanueva del Pardillo cuyos clientes hoy necesitan resolver encargos de documentos, planos, encuadernaciones y otros trabajos de impresión con rapidez y confianza. La oportunidad es convertir la web en una vía de captación local y de pedido: explicar cada servicio por necesidad, permitir configurar trabajos estándar, calcular un precio desde reglas administrables y preparar su recogida en tienda.

## Target users

- Particulares con copias, trámites, documentos, pósteres u otros trabajos puntuales.
- Estudiantes que necesitan imprimir y encuadernar apuntes o trabajos.
- Autónomos y pequeñas empresas con trabajos recurrentes, presentaciones y documentos profesionales.
- Arquitectos y delineantes con planos y trabajos de gran formato.
- Abogados con expedientes, dossiers y documentación que requiere presentación cuidada.
- Personal de Distrecon que revisa, produce, entrega y administra encargos.

## Desired outcomes

- Que un visitante local identifique rápidamente un servicio aplicable a su necesidad y pueda iniciar un pedido.
- Que el cliente pueda consultar el precio de demostración, confirmar el pedido y seguir su estado hasta la recogida.
- Que el equipo disponga de una cola única, trazable y operable de pedidos.
- Que la web consolide presencia local en búsquedas de copistería, impresión y servicios especializados sin crear páginas repetitivas de bajo valor.
- Las métricas y objetivos numéricos se fijarán tras establecer una línea base de visitas, pedidos y contactos.

## Product principles and constraints

- La experiencia y el contenido inicial se publican en español.
- El MVP atiende pedidos con recogida en Av. de Madrid, 18, Villanueva del Pardillo; no incluye entrega a domicilio.
- La web debe reconocer necesidades por perfil y por servicio sin prometer capacidades no vigentes.
- Todos los precios y disponibilidad deben proceder de un catálogo administrable; los importes actuales son de demostración.
- La pasarela de pago es un mockup en el MVP: no se realizan cobros reales.
- La cuenta de cliente, los archivos y los pedidos requieren controles de acceso, transparencia sobre conservación y minimización de datos.
- El propietario ha indicado Payload y Turso como restricciones tecnológicas deseadas. Son insumos para Arquitectura, no una arquitectura aprobada.
- Pressworks se usa como referencia de experiencia visual y flujo; su licencia, activos y posible adaptación de código requieren verificación independiente.

## In scope

- **CAP-001 — Captación pública local:** inicio, contacto, ubicación, servicios y contenido útil para SEO local.
- **CAP-002 — Soluciones por perfil:** estudiantes, particulares, autónomos/empresas, arquitectura/delineación y documentación jurídica.
- **CAP-003 — Guía de archivos:** preparación de PDF, acabados, recogida y preguntas frecuentes.
- **CAP-004 — Cuenta de cliente:** registro, acceso, perfil, historial y trabajos disponibles.
- **CAP-005 — Configurador de pedido:** subida de uno o varios PDF y configuración por trabajo.
- **CAP-006 — Precio y carrito:** total calculado mediante reglas administrables, con valores de demostración.
- **CAP-007 — Confirmación y pago simulado:** confirmación visual del pedido sin integración financiera.
- **CAP-008 — Seguimiento:** estados comprensibles desde pedido confirmado hasta recogida.
- **CAP-009 — Operación interna:** cola de pedidos, ficha del trabajo, cambio de estados, clientes e incidencias.
- **CAP-010 — Catálogo operativo:** administración de servicios, acabados, disponibilidad y reglas de precio.
- **CAP-011 — Archivos reutilizables:** el cliente puede consultar y repetir trabajos mientras los archivos estén disponibles.

## Out of scope

- Cobros reales, suscripciones, financiación, reembolsos o integración con pasarelas de pago.
- Entrega a domicilio, transportistas o puntos de recogida externos.
- Facturación, contabilidad, inventario, compras, costes industriales y planificación de maquinaria.
- Conversión automática de formatos de Office e imágenes en el MVP; el formato inicial aceptado es PDF.
- Descuentos o paquetes comerciales reales hasta que exista un catálogo aprobado.
- Páginas de posicionamiento duplicadas por localidad o profesión.
- Decisiones de infraestructura, autenticación, almacenamiento o arquitectura no aprobadas.

## Capabilities

### CAP-001 — Captación pública local

**Actor:** visitante.  
**Objetivo:** comprender qué ofrece Distrecon, llegar a tienda o comenzar un pedido.  
**Resultado esperado:** el visitante puede navegar a un servicio, solución por perfil, contacto o configurador.  
**Aceptación de producto:** la dirección, los dos teléfonos y el correo de Distrecon aparecen de forma consistente; las páginas tienen una acción clara.

### CAP-002 — Soluciones por perfil

**Actor:** visitante.  
**Objetivo:** reconocer la solución asociada a su necesidad.  
**Comportamiento:** cada perfil dispone de información diferenciada, casos de uso, preguntas frecuentes y una acción hacia el servicio/configurador adecuado.  
**Regla:** solo se publican páginas para capacidades activas y explicables de Distrecon.

### CAP-004 a CAP-007 — Pedido estándar

**Actor:** cliente autenticado.  
**Flujo resumido:** sube PDF, configura uno o varios trabajos, revisa precio y recogida, confirma datos, recorre pago simulado y recibe una confirmación persistente.  
**Opciones iniciales:** formato, color, una o dos caras, orientación, páginas por cara, gramaje, copias, encuadernación, tapas y observaciones.  
**Reglas:** cada trabajo mantiene sus opciones; el pedido conserva una instantánea del precio y configuración; el importe es de demostración hasta que se carguen reglas reales.

### CAP-008 a CAP-010 — Operación del pedido

**Actor:** personal autorizado de Distrecon.  
**Flujo resumido:** pedido confirmado → en revisión → requiere aclaración, en producción o cancelado → listo para recoger → entregado.  
**Resultado esperado:** el personal consulta archivos y especificaciones, actualiza el estado y administra el catálogo sin alterar pedidos ya confirmados.

### CAP-011 — Área de cliente y archivos

**Actor:** cliente autenticado.  
**Objetivo:** consultar pedidos, repetir encargos y gestionar trabajos disponibles.  
**Reglas:** se informará del plazo de disponibilidad; el cliente podrá eliminar un archivo salvo que esté bloqueado por producción; solo el personal necesario para producir el encargo tendrá acceso.

## Assumptions

- El propietario confirma que siguen activos: impresión de documentos, fotocopias, escaneado, encuadernaciones, impresión/ploteado de planos, gran formato, pósteres/fotografía, material de oficina y atención a particulares y empresas.
- Los pedidos estándar se inician con PDF.
- La recogida se realiza exclusivamente en tienda en el MVP.
- El sitio usará fotografías y activos de Distrecon cuando estén disponibles.

## Dependencies

- Confirmación de horario, dominio y accesos de publicación.
- Catálogo de servicios, acabados, límites y reglas de precio reales.
- Decisión de conservación de archivos y revisión legal de privacidad/condiciones.
- Arquitectura aprobada para identidad, base de datos, almacenamiento de archivos y administración.
- Verificación de licencia, procedencia y permisos de la plantilla Pressworks antes de reutilizar código o activos.

## Risks

- **RISK-001 — Privacidad documental:** los archivos pueden contener datos personales o sensibles. Mitigación: acceso mínimo, política de conservación visible y revisión de Arquitectura/privacidad.
- **RISK-002 — Precio no viable:** una regla genérica puede no reflejar un encargo especial. Mitigación: estado “requiere aclaración” y ruta de presupuesto manual.
- **RISK-003 — Capacidad operativa:** un pedido aceptado puede superar plazos o acabados disponibles. Mitigación: disponibilidad administrable y promesas de plazo validadas.
- **RISK-004 — Adaptación de plantilla:** reutilizar código/activos sin evidencia de licencia puede bloquear desarrollo. Mitigación: usarla solo como referencia hasta verificarla.

## Unresolved product decisions

- **UPD-001:** plazo de conservación, borrado y posible reutilización de archivos. Propietario con asesoramiento de Arquitectura/privacidad. Impacto: alto.
- **UPD-002:** comportamiento si un archivo no es imprimible, tiene error o exige un cambio de precio tras la revisión. Propietario. Impacto: alto.
- **UPD-003:** canal de avisos de pedido y recogida: correo, WhatsApp, área privada o combinación. Propietario. Impacto: alto.
- **UPD-004:** plazos de preparación, hora límite y promesa de recogida. Propietario. Impacto: alto.
- **UPD-005:** licencia y nivel de reutilización de la plantilla Pressworks. Propietario/Arquitectura. Impacto: alto.
- **UPD-006:** horario definitivo para contenido público. Propietario. Impacto: medio.

## Release and MVP boundaries

El MVP incluye la captación pública, soluciones por perfil, guía de archivos, cuenta de cliente, pedido configurable, precio de demostración, pago simulado, seguimiento y cola interna de pedidos para recogida en tienda. La integración de cobro real, reparto, facturación, stock y automatización industrial quedan diferidos.

## Product Owner review

Este documento se ha publicado como borrador externo por solicitud expresa del propietario el 9 de noviembre de 2026. No es aprobación de PDD por BMSF ni autorización de desarrollo.

## Traceability

- Estrategia por perfiles: DEC-0001.
- Recogida exclusiva en tienda: DEC-0002.
- Pedido con precio y pago simulado: DEC-0003.
- Catálogo y precios administrables: DEC-0004.
- Área de cliente y archivos: DEC-0005.
- Referencia Pressworks: DEC-0006.
- Datos de contacto: DEC-0007.
