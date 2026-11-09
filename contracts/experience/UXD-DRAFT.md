# UXD-DRAFT — Distrecon Product Experience

> Estado: **DRAFT**. Debe actualizarse tras los requisitos funcionales y Architecture Contract.

## Alcance y procedencia

- Escenario: GREENFIELD + TEMPLATE_ADAPTATION.
- Fuente visual: https://pressworks-print-shop-377031.hostingersite.com/
- Se toma inspiración de jerarquía, doble CTA, catálogo y flujo; no se reutilizan código, textos ni activos sin licencia verificable.
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
- Copys finales, fotos, logo de alta resolución, horarios y licencias.
- Deuda DTD-001 de presupuesto manual fuera de las pantallas MVP.