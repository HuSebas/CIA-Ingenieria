# Reglas de validación y autopruebas

| Campo | Valor |
|---|---|
| Versión | 1.0 · 2026-11-16 |
| Dónde viven | `app/reglas.js` (reglas) y `app/pruebas.js` (autopruebas) |

Las pantallas no validan por su cuenta: llaman a las funciones de `reglas.js`, que son las mismas que ejecutan las autopruebas. Así lo que se prueba es lo que el usuario usa.

## 1. Fichas de pantalla

### P-03 · Solicitar una compra

| Campo | Tipo | Obligatorio | Regla | Mensaje | Autoprueba |
|---|---|---|---|---|---|
| Rubro | Lista de los rubros de la obra, sin imprevistos | Sí | Debe pertenecer a la obra | ERR-01 | AP-07 |
| Insumo | Texto | Sí | No vacío | ERR-02 | AP-07 |
| Cantidad | Texto con unidad | Sí | No vacío | ERR-03 | AP-07 |
| Valor estimado | Número entero, en pesos | Sí | Mayor que cero | ERR-04 | AP-07 |
| Fecha requerida | Fecha | Sí | No anterior a hoy | ERR-05, ERR-06 | AP-07, AP-08 |
| Saldo del rubro | Calculado | — | Presupuesto menos gasto acumulado (RN-01) | A-03 si el valor lo supera | AP-01, AP-10 |
| Quién la decide | Calculado | — | Tabla de decisión (RN-02 a RN-05) | — | AP-03 a AP-06 |

Al enviar: la solicitud queda «Pendiente» y el saldo no cambia (AP-09).

### P-06 · Decidir una solicitud

| Campo o acción | Tipo | Obligatorio | Regla | Mensaje | Autoprueba |
|---|---|---|---|---|---|
| Saldo del rubro hoy | Calculado | — | Se calcula al abrir, con las compras urgentes incluidas | — | AP-01, AP-20 |
| Motivo | Texto | Solo al rechazar | No vacío | ERR-13 | AP-15 |
| Aprobar | Acción | — | Solo quien sigue en la ruta y no registró la solicitud | ERR-11, ERR-12 | AP-14, AP-17 |
| Aprobar, ruta de uno | Acción | — | Queda «Aprobada» y el saldo baja | OK-02 | AP-11 |
| Aprobar, ruta de dos | Acción | — | Tras el primero sigue «Pendiente»; tras el segundo, «Aprobada» | OK-03, OK-02 | AP-12, AP-13 |
| Aprobar con saldo cambiado | Acción | — | Si la ruta ya no corresponde, se reasigna | OK-05 | AP-16 |
| Rechazar | Acción | — | Queda «Rechazada»; el saldo no cambia | OK-04 | AP-15 |
| Cualquier acción sobre una solicitud ya decidida | Acción | — | Se rechaza | ERR-10 | AP-19 |

### P-04 · Anular una solicitud

| Campo o acción | Tipo | Obligatorio | Regla | Mensaje | Autoprueba |
|---|---|---|---|---|---|
| Motivo de la anulación | Texto | Sí | No vacío | ERR-13 | AP-18 |
| Anular | Acción | — | Solo el solicitante y solo si está «Pendiente» | ERR-12, ERR-10 | AP-18 |

### P-07 · Registrar una compra urgente

| Campo | Tipo | Obligatorio | Regla | Mensaje | Autoprueba |
|---|---|---|---|---|---|
| Rubro | Lista | Sí | Debe pertenecer a la obra | ERR-01 | AP-22 |
| Valor pagado | Número entero, en pesos | Sí | Mayor que cero | ERR-04 | AP-22 |
| Qué compró | Texto | No | — | — | — |
| Foto de la factura | Imagen o PDF | Sí | Debe adjuntarse | ERR-07 | AP-22 |
| Aviso de tope | Calculado | — | Si el valor supera el tope de caja menor, se marca y se registra | A-02 | AP-23 |

Al registrar: queda «Por legalizar» y el saldo baja ese mismo día, aunque quede negativo (AP-20, AP-21).

### P-08 · Legalizar una compra urgente

| Campo o acción | Tipo | Obligatorio | Regla | Mensaje | Autoprueba |
|---|---|---|---|---|---|
| Observación | Texto | Solo al devolver | No vacío | ERR-13 | AP-25 |
| Legalizar | Acción | — | Queda «Legalizada»; el saldo no cambia | OK-08 | AP-24 |
| Devolver con observación | Acción | — | Sigue «Por legalizar» | OK-09 | AP-25 |

### P-09 · Registrar el avance del corte

| Campo | Tipo | Obligatorio | Regla | Mensaje | Autoprueba |
|---|---|---|---|---|---|
| Corte | Lista de cortes | Sí | No debe tener un reporte vigente sin devolver | ERR-14 | AP-32 |
| Avance por actividad | Número | Sí | Entre 0 y 100 | ERR-08 | AP-29 |
| Fotografía por actividad | Imagen | Sí | Debe adjuntarse | ERR-09 | AP-29 |

Al guardar: sin conexión queda «Pendiente de sincronizar»; al recuperarla se envía una sola vez (AP-30, AP-31). Un reporte devuelto admite una versión nueva (AP-33).

### P-10 · Presupuesto y ejecución

| Elemento | Regla | Autoprueba |
|---|---|---|
| Qué ve cada rol | El residente, solo saldos; los demás, presupuesto, gasto y saldo | AP-28 |
| Marca de alerta | Gasto acumulado igual o mayor al 80 % del presupuesto | AP-26 |
| Efecto de una devolución | Sube el saldo en su valor | AP-27 |

## 2. Catálogo de autopruebas

Cada prueba parte de una copia limpia de los datos de ejemplo. Resultado de la última ejecución: **<!--RESUMEN-->33 de 33 pasan**.

<!--PRUEBAS-->
| ID | Regla, requisito o transición | Qué comprueba | Resultado |
|---|---|---|---|
| AP-01 | RN-01 | El saldo es el presupuesto menos el gasto acumulado: $20.000.000 − $16.500.000 = $3.500.000 | Pasa |
| AP-02 | RN-01 | Una solicitud pendiente no cuenta en el gasto acumulado | Pasa |
| AP-03 | RN-02 | Dentro del saldo y no grande: la ruta es la administradora | Pasa |
| AP-04 | RN-03 | Dentro del saldo y mayor al 10 % del rubro: gerente de obra y después administradora | Pasa |
| AP-05 | RN-04 | Exceso de $500.000 que cabe en imprevistos: administradora y gerente de obra | Pasa |
| AP-06 | RN-05 | Exceso de $2.500.000 que supera imprevistos: gerente general | Pasa |
| AP-07 | RF-002 | Sin rubro, insumo, cantidad, valor ni fecha se devuelven los cinco errores | Pasa |
| AP-08 | RF-002 | Una fecha requerida anterior a hoy se rechaza | Pasa |
| AP-09 | RF-001 | Una solicitud válida queda «Pendiente» con su ruta y no cambia el saldo | Pasa |
| AP-10 | RF-006 | Una solicitud de $4.000.000 con saldo de $3.500.000 registra un exceso de $500.000 | Pasa |
| AP-11 | T-04 · RF-008 | Aprobar una solicitud de ruta simple la deja «Aprobada» y baja el saldo en su valor | Pasa |
| AP-12 | T-02 · RF-042 | Con ruta de dos, la primera aprobación la deja «Pendiente» y no cambia el saldo | Pasa |
| AP-13 | T-04 · RN-19 | Con ruta de dos, la segunda aprobación la deja «Aprobada» | Pasa |
| AP-14 | RN-19 | No puede decidir quien no sigue en la ruta | Pasa |
| AP-15 | T-05 · RF-009 | Rechazar exige motivo; con motivo queda «Rechazada» y el saldo no cambia | Pasa |
| AP-16 | T-03 · RF-043 | Si el saldo se consume antes de decidir, la ruta se reasigna y la solicitud sigue «Pendiente» | Pasa |
| AP-17 | RN-06 | Nadie decide una solicitud que él mismo registró | Pasa |
| AP-18 | T-06 · RF-038 | Solo el solicitante anula, con motivo, y el saldo no cambia | Pasa |
| AP-19 | Estado × evento | Una solicitud aprobada no admite otra decisión | Pasa |
| AP-20 | T-07 · RN-07 | Una compra urgente de $800.000 queda «Por legalizar» y el saldo pasa a $2.700.000 | Pasa |
| AP-21 | RN-07 | Una compra urgente mayor que el saldo se registra y deja el saldo negativo | Pasa |
| AP-22 | RF-013 · RN-08 | Sin rubro o sin soporte la compra urgente no se registra ni cambia el saldo | Pasa |
| AP-23 | RN-09 | Una compra urgente de $1.200.000 queda marcada «sobre el tope» | Pasa |
| AP-24 | T-09 · RF-014 | Legalizar deja la compra «Legalizada» sin cambiar el saldo | Pasa |
| AP-25 | T-08 · RF-039 | Devolver con observación la mantiene «Por legalizar»; sin observación se rechaza | Pasa |
| AP-26 | RN-11 · RF-020 | La alerta se genera cuando el gasto llega al 80 % del presupuesto del rubro | Pasa |
| AP-27 | RN-12 · RF-033 | Una devolución de $300.000 sube el saldo a $3.800.000 | Pasa |
| AP-28 | RN-16 · PD-05 | El residente ve solo saldos; administradora, gerentes y contador ven el presupuesto completo | Pasa |
| AP-29 | RN-13 · RF-023 | Un avance de 120 % o sin fotografía se rechaza | Pasa |
| AP-30 | T-10 · RF-024 | Sin conexión el reporte queda «Pendiente de sincronizar» | Pasa |
| AP-31 | T-11 · RF-025 | Al recuperar la conexión se sincroniza una sola vez | Pasa |
| AP-32 | RN-14 | Un corte con reporte vigente no admite otro | Pasa |
| AP-33 | T-12 · T-13 | Un reporte devuelto con motivo admite una versión nueva y conserva la anterior | Pasa |

## 3. Reglas sin autoprueba en esta versión

| Regla | Por qué no |
|---|---|
| RN-03, parte «cambia lo planeado» | El prototipo solo detecta la compra «grande»; no hay dato que diga si una compra cambia lo planeado. |
| RN-09, plazo de legalización | No hay paso del tiempo en el prototipo. |
| RN-15, RN-20, RN-22 | Recepción, ajuste del presupuesto y orden de compra no están en esta versión. |
| RN-17, RN-21 | El registro de cambios y la asignación de roles por obra son transversales y no tienen pantalla. |
| RN-18 | Un solo dispositivo por obra: no se puede comprobar con un prototipo de un solo navegador. |
