# Informe de preparación — Distrecon

## Estado

**NEEDS_DECISIONS** — Publicado como borrador de trabajo por solicitud del propietario. El paquete es suficiente para revisar y continuar descubrimiento, pero no está listo para aprobar ni para entregar a Business Analysis como línea base cerrada.

## Artefactos

- `PDD.md`: definición de producto candidata.
- `docs/requirements/FUNCTIONAL-DISCOVERY.md`: flujos y comportamiento por explorar.
- `docs/requirements/DECISIONS.md`: decisiones y preguntas abiertas.
- `contracts/experience/UXD-DRAFT.md`: propuesta UX/UI y fuente visual.

## Hallazgos de preflight

| ID | Perspectiva | Severidad | Hallazgo | Disposición |
|---|---|---|---|---|
| FIND-0001 | Producto / privacidad | BLOCKING | No existe plazo ni política de conservación/borrado de archivos de clientes. | OPEN — UPD-001 |
| FIND-0002 | Negocio / QA | BLOCKING | No está definido el comportamiento tras revisión de un archivo no imprimible o cambio de precio. | OPEN — UPD-002 |
| FIND-0003 | Operaciones | HIGH | No está definido el canal de avisos ni los plazos de recogida. | OPEN — UPD-003, UPD-004 |
| FIND-0004 | UX / legal | HIGH | La referencia Pressworks no tiene aún licencia, revisión de activos ni alcance de adaptación verificados. | OPEN — UPD-005 |
| FIND-0005 | Contenido | MEDIUM | Falta confirmar horario final y activos fotográficos antes de publicar contenido local. | OPEN — UPD-006 |
| FIND-0006 | Arquitectura | MEDIUM | Payload y Turso son una restricción de propietario, pero no hay Architecture Contract aprobado. | OPEN — escalación a Arquitectura después de PDD/FR |

## Cobertura actual

La visión, actores, alcance, servicios confirmados, flujos centrales, exclusiones y riesgos están documentados. Faltan reglas de excepción, privacidad, notificaciones y compromisos operativos que el Business Analyst necesita para producir requisitos verificables sin inventar comportamiento.

## Próximo paso

Resolver UPD-001 a UPD-005, actualizar este paquete y presentar el PDD consolidado para revisión explícita del propietario. Solo entonces se debe solicitar el análisis funcional. La publicación en GitHub no equivale a aprobación BMSF, ni a autorización de arquitectura o desarrollo.
