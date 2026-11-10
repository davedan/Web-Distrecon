# UXD-DRAFT — Distrecon Product Experience

> Estado: **DRAFT**. Referencia UX; debe actualizarse contra los requisitos BA de esta rama y un Architecture Contract aprobado.

## Escenario y procedencia

- Escenario: **GREENFIELD + TEMPLATE_ADAPTATION**.
- Plantilla local: `template/printop`, Printop 1.0.0 de Wowtheme7.
- ZIP SHA-256: `70A5E95E401FD5B0D0C8AEA0850B2B10911C300674818491019E49F5C2AAEA8B`.
- El propietario confirma que la licencia fue adquirida. Código/HTML declara GPL; CSS, diseño y activos se usarán únicamente conforme a la licencia comprada. No se ejecutó código ni scripts de la plantilla.
- Arquitectura debe validar compatibilidad, dependencias, seguridad y derechos de activos antes de adaptación.

## Estructura de experiencia

```text
Web pública sin login
  ├─ Inicio · Servicios · Verticales · Guía · Contacto
  └─ Registro / login
       └─ Zona privada exclusiva por rol
          ├─ Superadministración + CMS Payload
          ├─ Dueños: catálogo, pedidos, clientes y operación
          └─ Clientes: pedidos, archivos, notificaciones y perfil
```

## Cobertura UX vinculada a BA

- Catálogo publica servicios explícitamente y sus configuradores son específicos por servicio.
- Flujo web: registro → verificación → carga/configuración → precio IVA → pago simulado → revisión → recogida.
- Pedido múltiple permite estados/líneas parciales y recogida parcial.
- Cliente inactivo: área de solo lectura; pedido interno con doble activación.
- Incidencia: archivo/línea problemática se pausa sin frenar líneas válidas; sustitución y ajuste económico simulado.
- Archivo caduca visualmente sin cambiar el estado del pedido.

## Gate y riesgos

- UX-G1/UX-G2 no aplicados ni certificables. CAP-16 y su matriz se encontraron solo en la rama no fusionada `feature/core-product-experience-v1` de BMSF-Arquitecture.
- No hay Architecture Contract aprobado.
- La plantilla es una entrada de implementación, no un requisito ni decisión de stack.
- Los demos de Printop, incluidos textos no relacionados con impresión, no se reutilizan.
