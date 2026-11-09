# UXD-DRAFT — Distrecon Product Experience

> Estado: **DRAFT**. Referencia UX/UI de trabajo; no es una puerta UX-G1 superada ni una aprobación para desarrollo.

## Proyecto y escenario

- Proyecto: Distrecon.
- Repositorio: `davedan/Web-Distrecon`.
- Escenario: **GREENFIELD + TEMPLATE_ADAPTATION**.
- Target previsto: experiencia web pública con cuenta de cliente y operación interna.
- Upstream disponible: `PDD.md` borrador; no existen aún FR aprobados ni Architecture Contract.

## Fuente y procedencia de plantilla

- Fuente visual observada: https://pressworks-print-shop-377031.hostingersite.com/
- Identificación visible: plantilla creada con Hostinger.
- Uso actual permitido en este borrador: inspiración de estructura visual, jerarquía y recorrido.
- No autorizado por este documento: copiar código, textos, fotografías, logotipo, activos, dependencias o instrucciones de la plantilla.
- Evidencia pendiente: licencia, autor, versión, checksum, derechos de activos y compatibilidad técnica si se pretende adaptar código.

## Hallazgos observados

Pressworks presenta una cabecera limpia, gran titular, doble CTA, beneficios rápidos, catálogo visual, guía de impresión, cuenta, carrito y presupuesto instantáneo. Su recorrido es producto → cantidad → precio → carrito → carga/gestión de arte.

## Adaptación de experiencia para Distrecon

### Estrategia visual

- Base clara, contraste alto, tipografía editorial legible y acentos inspirados en color de impresión.
- Identidad propia a partir del logotipo de Distrecon y fotografías/activos con derechos confirmados.
- Voz cercana y práctica, en español, centrada en Villanueva del Pardillo.
- No se replica el tono juvenil, catálogo nacional ni promesa de entrega de Pressworks.

### Navegación propuesta

```text
Inicio · Servicios · Guía de archivos · Empresas · Contacto
                                        └─ Tu cuenta · Carrito · Sube tu trabajo
```

### Journeys críticos

1. Visitante local → servicio/perfil → configurador o presupuesto.
2. Cliente → cuenta → PDF/configuración → precio → pago simulado → seguimiento → recogida.
3. Personal → cola → revisión → producción → listo → entrega.
4. Cliente recurrente → área privada → repetir trabajo disponible.

### Inventario de pantallas

| Área | Pantallas |
|---|---|
| Captación | Inicio, servicios, soluciones por perfil, guía de archivos, empresas, contacto/ubicación |
| Pedido | Carga de archivos, configurador, carrito, pago simulado, confirmación |
| Cliente | Registro/acceso, panel, pedidos, detalle/seguimiento, trabajos, presupuestos, perfil |
| Personal | Cola de pedidos, ficha, cambio de estado, catálogo/precios, clientes, incidencias |

### Componentes y estados

- Cabecera, navegación móvil, CTA primario/secundario, tarjetas de servicio y perfil, pruebas de confianza, mapa y contacto.
- Uploader, lista de archivos, configurador por trabajo, desglose de precio, carrito y progreso.
- Estados: vacío, carga, archivo inválido, cálculo pendiente, acabado no disponible, error, permiso denegado, pedido confirmado, requiere aclaración, listo para recoger, archivo próximo a caducar.
- Accesibilidad: semántica, etiquetas, foco visible, navegación por teclado, contraste suficiente, objetivos táctiles y reducción de movimiento.

## Mapeo de producto a UX

| Capacidad PDD | Superficie UX |
|---|---|
| CAP-001 / CAP-002 | Inicio, servicios y soluciones por perfil |
| CAP-003 | Guía de archivos y FAQs |
| CAP-004 / CAP-011 | Acceso, cuenta, pedidos y trabajos |
| CAP-005 / CAP-006 / CAP-007 | Uploader, configurador, carrito y pago simulado |
| CAP-008 / CAP-009 | Seguimiento de pedido, cola interna y ficha |
| CAP-010 | Catálogo y reglas desde administración |

## Riesgos y decisiones pendientes

- No se puede afirmar licencia ni posibilidad de importar la plantilla.
- No se puede diseñar mensaje de privacidad final sin conservación de archivos.
- El diseño de pantallas de cuenta, archivos, autenticación y administración debe alinearse con Architecture Contract futuro.
- Se requiere revisión UX independiente y ejecución QA antes de cualquier declaración UX-G1/UX-G2.
