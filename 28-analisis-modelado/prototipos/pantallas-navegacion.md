# Pantallas y navegación

| Campo | Valor |
|---|---|
| Versión | 1.0 · 2026-11-16 |
| Mapa de navegación | [`wireframes/nav-01-mapa-navegacion.puml`](wireframes/nav-01-mapa-navegacion.puml) · [imagen](wireframes/nav-01-mapa-navegacion.png) |

## 1. Inventario de pantallas

| ID | Pantalla | Propósito | Roles | En el prototipo | Captura |
|---|---|---|---|---|---|
| P-01 | Ingreso | Entrar con un rol | Todos | Sí, sin contraseña | [ver](pantallas/p-01-ingreso.png) |
| P-02 | Inicio | Acciones del rol y alertas de rubros | Todos | Sí | [residente](pantallas/p-02-inicio-residente.png) · [aprobador](pantallas/p-02-inicio-aprobador.png) |
| P-03 | Solicitar una compra | Registrar la solicitud | Residente | Sí | [ver](pantallas/p-03-solicitud.png) |
| P-04 | Mis registros | Ver el estado de lo registrado y anular una solicitud | Residente | Sí | [ver](pantallas/p-04-mis-registros.png) |
| P-05 | Por decidir | Lista de lo que espera la decisión del aprobador | Administradora, gerente de obra, gerente general | Sí | [ver](pantallas/p-05-por-decidir.png) |
| P-06 | Decidir una solicitud | Aprobar o rechazar con el saldo a la vista | Los mismos | Sí | [ver](pantallas/p-06-decidir.png) |
| P-07 | Registrar una compra urgente | Registrar una compra ya hecha | Residente | Sí | [ver](pantallas/p-07-compra-urgente.png) |
| P-08 | Legalizar una compra urgente | Legalizar o devolver con observación | Los de P-05 | Sí | [ver](pantallas/p-08-legalizar.png) |
| P-09 | Registrar el avance del corte | Avance y fotografía por actividad | Residente | Sí | [ver](pantallas/p-09-avance-error.png) |
| P-10 | Presupuesto y ejecución | Presupuesto, gasto y saldo por rubro; el residente ve solo saldos | Todos, según el rol | Sí | [completo](pantallas/p-10-presupuesto.png) · [saldos](pantallas/p-10-saldos-residente.png) |
| P-11 | Avance de la obra | Consultar el avance y devolver un reporte | Administradora, gerente de obra, gerente general | Sí | [ver](pantallas/p-11-avance-obra.png) |
| P-12 | Presupuesto de la obra | Registrar y ajustar el presupuesto por actividad y rubro | Gerente de obra, gerente general | No | — |
| P-13 | Periodicidad de corte | Definir cada cuánto se reporta | Administradora | No | — |
| P-14 | Orden de compra | Registrar la orden de una solicitud aprobada | Administradora | No | — |
| P-15 | Recepción de materiales | Registrar lo recibido contra la orden y adjuntar el soporte | Residente | No | — |
| P-16 | Devolución de material | Registrar una devolución | Residente | No | — |
| P-17 | Verificar compra | Marcar una compra como verificada | Administradora | No | — |
| P-18 | Compras verificadas | Consultar compras verificadas y sus soportes | Contador | No | — |
| P-19 | Consolidado de la obra | Generar el consolidado por periodo | Administradora | No | — |

Las pantallas P-12 a P-19 quedan para la segunda versión del prototipo: son formularios y consultas de la oficina, con menos riesgo de uso que los del frente de obra.

## 2. Navegación por rol

| Rol | Desde Inicio llega a |
|---|---|
| Residente de obra | P-03, P-07, P-09, P-04, P-10 (solo saldos) |
| Administradora de proyectos, gerente de obra, gerente general | P-05 (y de ahí a P-06 y P-08), P-10, P-11 |
| Contador | P-10 |

Reglas: toda pantalla tiene «‹» para volver a Inicio y «Salir» para cambiar de rol. Una pantalla que no corresponde al rol no se abre aunque se escriba su dirección: el prototipo vuelve a Inicio.

## 3. Matriz caso de uso × pantalla × rol × requisito

| Caso de uso | Pantalla | Rol | Requisitos |
|---|---|---|---|
| CU-01 Solicitar compra de insumos | P-03, P-04 | Residente | RF-001, RF-002, RF-003, RF-004 |
| CU-02 Decidir solicitud de compra | P-05, P-06 | Aprobadores | RF-005, RF-006, RF-007, RF-008, RF-009, RF-010, RF-042, RF-043 |
| CU-03 Registrar compra urgente | P-07, P-04 | Residente | RF-011, RF-012, RF-013, RF-040 |
| CU-04 Legalizar compra urgente | P-05, P-08 | Aprobadores | RF-014, RF-015, RF-039, RF-041 |
| CU-05 Calcular saldo del rubro | P-03, P-06, P-08, P-10 | Todos | RF-005, RF-019 |
| CU-06 Registrar presupuesto de la obra | P-12 | Gerente de obra | RF-017 |
| CU-07 Consultar presupuesto y ejecución | P-10 | Todos, según el rol | RF-019, RF-037 |
| CU-08 Alertar rubro cercano a su límite | P-02 | Administradora, gerente de obra | RF-020 |
| CU-09 Registrar avance de obra | P-09, P-04 | Residente | RF-023, RF-024, RF-025 |
| CU-10 Consultar avance de la obra | P-11 | Administradora, gerente de obra, gerente general | RF-027 |
| CU-11 Devolver reporte de avance | P-11 | Gerente de obra | RF-028, RF-029 |
| CU-12 Definir periodicidad de corte | P-13 | Administradora | RF-026 |
| CU-13 Registrar recepción de materiales | P-15 | Residente | RF-011, RF-030, RF-031 |
| CU-14 Registrar devolución de material | P-16 | Residente | RF-032, RF-033 |
| CU-15 Verificar compra | P-17 | Administradora | RF-016 |
| CU-16 Ajustar presupuesto de la obra | P-12 | Gerente de obra, gerente general | RF-018 |
| CU-17 Generar consolidado de la obra | P-19 | Administradora | RF-021, RF-022, RF-029 |
| CU-18 Consultar compras verificadas | P-18 | Contador | RF-045 |
| CU-19 Anular solicitud de compra | P-04 | Residente | RF-038 |
| CU-20 Registrar orden de compra | P-14 | Administradora | RF-044 |

Transversales: RF-036 se ve en P-01 y RF-034 y RF-035 no tienen pantalla propia en esta versión. RF-015 (alerta por plazo de legalización vencido) no está en el prototipo.

## 4. Lista de verificación

| Pregunta | Resultado | Observación |
|---|---|---|
| ¿Cada caso de uso tiene al menos una pantalla? | Sí | Los 20; comprobado por comparación automática con el catálogo. |
| ¿Cada pantalla sirve a algún caso de uso o requisito? | Sí | P-01 y P-02 sirven a RF-036 y RF-020. |
| ¿Cada pantalla tiene los roles que pueden abrirla? | Sí | Coinciden con los actores de cada caso de uso. |
| ¿Ningún rol llega a una pantalla que no le corresponde? | Sí | Probado en el prototipo: el contador no abre «Por decidir». |
| ¿Se puede volver desde toda pantalla? | Sí | «‹» en todas menos Inicio e Ingreso. |
| ¿Los nombres son los del glosario? | Sí | |
| ¿Las tareas frecuentes están a dos toques o menos desde Inicio? | Sí | TA-01 a TA-06. |
