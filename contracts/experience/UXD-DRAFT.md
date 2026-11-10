# UXD-DRAFT — Distrecon Product Experience

> Estado: **DRAFT**. Debe actualizarse tras los requisitos funcionales y Architecture Contract.

## Alcance y procedencia

- Escenario: GREENFIELD + TEMPLATE_ADAPTATION.
- Plantilla local: \`template/printop\`, Printop 1.0.0 de Wowtheme7; ZIP: \`template/printop.zip\`.
- SHA-256 del ZIP inspeccionado: \`70A5E95E401FD5B0D0C8AEA0850B2B10911C300674818491019E49F5C2AAEA8B\`.
- El código/HTML declara GPLv2 o posterior; el \`readme.txt\` indica que CSS, diseño y otros activos siguen la licencia adquirida. No hay evidencia de compra adjunta.
- Se permite documentar su inventario y usarlo como referencia; no se importan ni distribuyen código, CSS, imágenes, fuentes u otros activos hasta validar licencia, dependencias y compatibilidad arquitectónica.
- Identidad y voz propias: Distrecon, español, Villanueva del Pardillo, impresión local y recogida en tienda.

## Estructura de experiencia

```text
Web pública sin login
  ├─ Inicio · Servicios · Verticales · Guía de archivos · Contacto
  └─ Registro / login
       └─ Zona privada por rol
          ├─ Superadministración + CMS Payload
          ├─ Dueños: operación, clientes, configuración
          └─ Clientes: pedidos, archivos, notificaciones, perfil
```

## Journeys críticos

1. Visitante → registro → verificación de email → cliente activo → carga PDF → configurador → pago simulado → pedido.
2. Dueño → alta/búsqueda de cliente → pedido tienda/teléfono → invitación automática si es nuevo → cola.
3. Correo entrante → revisión manual → vinculación/alta controlada → pedido.
4. Cliente inactivo → notificación marcada → activar cliente → abrir pedido → activar pedido.
5. Incidencia → “Requiere tu acción” → sustituir o cancelar → revisión.
6. Pedido listo → aviso → recogida → entregado.
7. Archivo 15/10/5 días → notificación web+email → “Archivo caducado” al borrarse; pedido e historial continúan.

## Pantallas necesarias

| Área | Pantallas |
|---|---|
| Público | Inicio, servicios, verticales, guía de archivo, contacto/ubicación |
| Autenticación | Registro, aviso de verificación, login, recuperación/restablecimiento de contraseña |
| Cliente | Inicio, pedidos, detalle, subida/configurador, pago simulado, historial, notificaciones, perfil |
| Dueño | Inicio operativo, cola, detalle pedido, clientes/ficha, alta manual, cuentas de dueños, configuración |
| Superadministrador | Todo lo anterior según permiso + CMS Payload |

## Reglas UX

- Email no editable por cliente ni dueño.
- Un pedido de cliente inactivo debe mostrar marca persistente y CTA de dos pasos, sin atajos.
- “Archivo caducado” es disponibilidad de fichero; el pedido conserva estado como “Entregado”.
- Estados deben usar lenguaje claro para clientes y detalle operativo para dueños.
- CTA de pedido exige autenticación; no hay pedido anónimo.
- Accesibilidad: etiquetas, foco visible, teclado, contraste, objetivos táctiles y mensajes de error explícitos.

## Pendiente UX

- Matriz final de configurador por servicio.
- Estados visuales de validación de PDF, limites y antivirus definidos por Arquitectura.
- Copys finales, fotos, logo de alta resolución y horarios.
- Antes de adaptar Printop: evidencia de compra/licencia, inventario de dependencias/activos y evaluación de compatibilidad por Arquitectura. La plantilla es una entrada de implementación, no una decisión de stack.
- Deuda DTD-001 de presupuesto manual fuera de las pantallas MVP.
- UX-G1 y UX-G2: no aplicados ni certificables; CAP-16 y su matriz están solo en la rama no fusionada \`feature/core-product-experience-v1\` de BMSF-Arquitecture.