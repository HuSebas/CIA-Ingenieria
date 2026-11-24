# Registro de solicitudes de cambio

| Campo | Valor |
|---|---|
| Versión | 1.0 · 2026-11-16 |
| Rige desde | SRS-GO-001 v0.9. Antes de esa versión los cambios se registran en el historial de cada documento |

## 1. Flujo

| Paso | Qué se hace | Evidencia |
|---|---|---|
| 1. Solicitud | Quién pide, qué, por qué y con qué urgencia | Fila en el registro y ficha SC-nn |
| 2. Análisis de impacto | Con `29-srs/apendices/trazabilidad.csv`: requisitos, casos de uso, reglas, pantallas y escenarios que cambian; efecto en plazo y alcance | Lista de identificadores en la ficha |
| 3. Decisión | El gerente general, o quien él delegue, aprueba, difiere o rechaza | Fecha y motivo en la ficha |
| 4. Actualización | Versión nueva del SRS, fila en G.1 y G.2, etiqueta nueva; se vuelven a correr los verificadores | Pull request y etiqueta |
| 5. Comunicación | Aviso a quienes usan el documento | Mensaje o acta |

**Qué es un cambio.** Si quien construya el sistema leyendo la versión anterior construiría algo distinto, es un cambio y lleva solicitud. Si construiría lo mismo, es una corrección editorial y va solo al historial.

## 2. Registro

| SC-nn | Fecha | Origen (HR-nn o quién la pide) | Qué cambia | Elementos afectados | Decisión · quién · fecha | Versión del SRS |
|---|---|---|---|---|---|---|
| | | | | | | |

Sin solicitudes a la fecha.

## 3. Ficha de una solicitud

| Campo | Contenido |
|---|---|
| Identificador y fecha | SC-nn · AAAA-MM-DD |
| Quién la pide y por qué canal | |
| Clase | Cambio de requisito, de regla, de mensaje o de alcance |
| Descripción | Qué texto o comportamiento cambia, con identificadores |
| Motivo | Qué problema resuelve, con un ejemplo |
| Requisitos afectados | |
| Casos de uso e historias | |
| Reglas de negocio | |
| Pantallas y mensajes | |
| Escenarios de aceptación | |
| Costo y alcance | Horas de análisis; ¿cambia el alcance o el plazo? |
| ¿Toca algo legal? | Si sí, por confirmar con la Oficina Jurídica |
| Decisión, quién y cuándo | Aprobada, rechazada o diferida, con motivo |
| Qué se actualizó | Versión anterior → versión nueva; fila del historial |
