# CIA-gestion-obras

Ingeniería de requisitos del **sistema de información para la gestión de obras de CIA Ingeniería** (obra civil e infraestructura): compras de insumos, presupuesto y costos, avance de obra y recepción de materiales.

Asignatura Ingeniería de Requisitos — Ingeniería de Sistemas y Computación, UPTC. Grupo 6.

## Equipo

| Integrante | Usuario |
|---|---|
| Paola Andrea Camacho González | `paola044` |
| Sebastián Felipe Huertas Salas | `HuSebas` |
| Juan Miguel Blanco Perilla | `miguelbpj13` |
| Jhonnyd Bleyck Arias Santafé | `usuario-por-confirmar` |

## Estructura

| Carpeta | Tarea del proceso | Contenido |
|---|---|---|
| [`26-empresa-acuerdo/`](26-empresa-acuerdo/) | Concepción | Acta de constitución, stakeholders, ficha de organización, plan, riesgos y acuerdos |
| [`27-levantamiento/`](27-levantamiento/) | Obtención | Plan de levantamiento, cuestionario, entrevistas, actas, análisis documental y requisitos candidatos |
| [`28-analisis-modelado/`](28-analisis-modelado/) | Elaboración y negociación | Metas, casos de uso, historias, diagramas UML, conflictos, priorización y prototipo |
| [`29-srs/`](29-srs/) | Especificación | SRS, catálogo de requisitos, reglas de negocio, pendientes, trazabilidad, revisión interna y estándares |
| [`30-validacion-sustentacion/`](30-validacion-sustentacion/) | Validación y gestión | Sesión de revisión, aceptación, cambios, cierre con la empresa, informe final, sustentación y evaluación del equipo |

Archivos transversales: [`GLOSARIO.md`](GLOSARIO.md) · [`BITACORA.md`](BITACORA.md) · [`CONTRIBUCIONES.md`](CONTRIBUCIONES.md)

## Artefactos

### Concepción

| Artefacto | Ubicación |
|---|---|
| Acta de constitución | [`acta-constitucion.md`](26-empresa-acuerdo/acta-constitucion.md) |
| Stakeholders y matriz de poder-interés | [`matriz-poder-interes.md`](26-empresa-acuerdo/matriz-poder-interes.md) |
| Ficha de organización y problema | [`ficha-organizacion-problema.md`](26-empresa-acuerdo/ficha-organizacion-problema.md) |
| Plan del proyecto | [`plan-proyecto.md`](26-empresa-acuerdo/plan-proyecto.md) |
| Registro de riesgos (`R`) | [`registro-riesgos.md`](26-empresa-acuerdo/registro-riesgos.md) |
| Acuerdos de alcance y de confidencialidad | [`acuerdo-alcance.md`](26-empresa-acuerdo/acuerdo-alcance.md) · [`acuerdo-confidencialidad.md`](26-empresa-acuerdo/acuerdo-confidencialidad.md) |

### Levantamiento

| Artefacto | Ubicación |
|---|---|
| Plan de levantamiento | [`plan-levantamiento.md`](27-levantamiento/plan-levantamiento.md) |
| Cuestionario preliminar | [`cuestionario-preliminar.md`](27-levantamiento/cuestionario-preliminar.md) |
| Entrevistas (`E-01`, `E-02`) con sus hallazgos | [`entrevistas/`](27-levantamiento/entrevistas/) |
| Actas de entrevista | [`actas/`](27-levantamiento/actas/) |
| Análisis documental del proceso actual (`AD`) | [`analisis-documental.md`](27-levantamiento/analisis-documental.md) |
| Inventario de requisitos candidatos (`RC`) | [`requisitos-candidatos.md`](27-levantamiento/requisitos-candidatos.md) |

### Análisis y modelado

| Artefacto | Ubicación |
|---|---|
| Árbol de metas KAOS (`G`, `OB`) | [`metas/arbol-kaos.md`](28-analisis-modelado/metas/arbol-kaos.md) |
| Historias de usuario (`HU`) y escenarios de aceptación | [`historias/`](28-analisis-modelado/historias/) · [`aceptacion/`](28-analisis-modelado/historias/aceptacion/) |
| Catálogo de casos de uso (`CU`) y fichas de actor | [`catalogo-casos-de-uso.md`](28-analisis-modelado/casos-de-uso/catalogo-casos-de-uso.md) · [`fichas-actores.md`](28-analisis-modelado/casos-de-uso/fichas-actores.md) |
| Casos de uso especificados: CU-01, CU-02, CU-03, CU-04, CU-09 | [`casos-de-uso/`](28-analisis-modelado/casos-de-uso/) |
| Diagramas de casos de uso (`DCU`) | [`diagramas/casos-de-uso/`](28-analisis-modelado/diagramas/casos-de-uso/) · [verificación](28-analisis-modelado/casos-de-uso/checklist-diagramas-casos-de-uso.md) |
| Diagramas de actividades AS-IS y TO-BE (`DAC`), hallazgos y brechas | [`diagramas/actividades/`](28-analisis-modelado/diagramas/actividades/hallazgos-brechas.md) |
| Diagramas de secuencia (`DSE`), escenarios y operaciones del sistema | [`diagramas/secuencia/`](28-analisis-modelado/diagramas/secuencia/escenarios-operaciones.md) |
| Máquinas de estados (`DES`) | [`diagramas/estados/`](28-analisis-modelado/diagramas/estados/estados.md) |
| Modelo de dominio (`DCL`) | [`diagramas/clases/modelo-dominio.md`](28-analisis-modelado/diagramas/clases/modelo-dominio.md) |
| Patrones de diseño aplicados | [`diagramas/clases/patrones-diseno.md`](28-analisis-modelado/diagramas/clases/patrones-diseno.md) |
| Matriz de consistencia entre modelos | [`matriz-consistencia.md`](28-analisis-modelado/matriz-consistencia.md) |
| Prototipo de interfaz (`P`, `WF`): aplicación, personas, pantallas, wireframes, reglas de validación y evaluación | [`prototipo/`](28-analisis-modelado/prototipo/README.md) |
| Conflictos y decisiones (`C`) | [`priorizacion/conflictos.md`](28-analisis-modelado/priorizacion/conflictos.md) |
| Priorización y backlog | [`priorizacion/priorizacion.md`](28-analisis-modelado/priorizacion/priorizacion.md) · [`backlog.md`](28-analisis-modelado/priorizacion/backlog.md) |

### Especificación

| Artefacto | Ubicación |
|---|---|
| **SRS-GO-001, versión 0.9** | [`srs.md`](29-srs/srs.md) · [`srs-v0.9.docx`](29-srs/srs-v0.9.docx) · [`srs-v0.9.pdf`](29-srs/srs-v0.9.pdf) |
| Plan de redacción y equivalencia IEEE 830 ↔ 29148 | [`plan-redaccion.md`](29-srs/plan-redaccion.md) · [`equivalencia-tailoring.md`](29-srs/equivalencia-tailoring.md) |
| Revisión interna de cuatro filtros y checklist de propiedades | [`revision-interna-v0.8.md`](29-srs/revisiones/revision-interna-v0.8.md) · [`checklist-propiedades-srs.md`](29-srs/revisiones/checklist-propiedades-srs.md) |
| Matriz de trazabilidad verificable y su verificador | [`trazabilidad.csv`](29-srs/apendices/trazabilidad.csv) · [`trazabilidad-verificacion.txt`](29-srs/apendices/trazabilidad-verificacion.txt) · [`herramientas/`](29-srs/herramientas/) |
| Pendientes con la empresa (`PD`) y tareas del equipo (`PT`) | [`pendientes.md`](29-srs/apendices/pendientes.md) |
| Catálogo de requisitos (`RF`, `RNF`, `RES`) y fichas | [`catalogo-requisitos.md`](29-srs/catalogo-requisitos.md) · [`fichas-requisitos.md`](29-srs/fichas-requisitos.md) |
| Reglas de negocio (`RN`) | [`reglas-negocio.md`](29-srs/reglas-negocio.md) |
| Requisitos de calidad (ISO/IEC 25010) | [`requisitos-calidad.md`](29-srs/requisitos-calidad.md) |
| Matriz de trazabilidad, vista por meta y caso de uso | [`matriz-trazabilidad.md`](29-srs/matriz-trazabilidad.md) |
| Estándares aplicados y plan de adopción | [`estandares.md`](29-srs/estandares.md) |

### Validación y cierre

| Artefacto | Ubicación |
|---|---|
| Índice y orden de trabajo | [`README.md`](30-validacion-sustentacion/README.md) |
| Guía de la sesión de revisión y acta con hallazgos (`HR`) | [`guia-sesion-revision.md`](30-validacion-sustentacion/revision-cliente/guia-sesion-revision.md) · [`acta-revision.md`](30-validacion-sustentacion/revision-cliente/acta-revision.md) |
| Acta de aceptación y registro de cambios (`SC`) | [`acta-aceptacion.md`](30-validacion-sustentacion/aceptacion/acta-aceptacion.md) · [`registro-cambios.md`](30-validacion-sustentacion/aceptacion/registro-cambios.md) |
| Inventario de datos y acta de cierre | [`inventario-datos.md`](30-validacion-sustentacion/cierre-empresa/inventario-datos.md) · [`acta-cierre.md`](30-validacion-sustentacion/cierre-empresa/acta-cierre.md) |
| Informe final | [`informe-final.md`](30-validacion-sustentacion/informe-final/informe-final.md) |
| Guion y presentación de la sustentación | [`guion-sustentacion.md`](30-validacion-sustentacion/sustentacion/guion-sustentacion.md) · [`presentacion-sustentacion.pptx`](30-validacion-sustentacion/sustentacion/presentacion-sustentacion.pptx) |
| Evaluación del equipo | [`evaluacion-equipo/`](30-validacion-sustentacion/evaluacion-equipo/) |

## Convenciones

- **Fuentes en texto.** Documentos en Markdown y diagramas en PlantUML (`.puml`), para revisarlos por diff. Junto a cada `.puml` está su imagen `.png`, generada con `plantuml -tpng`. Los PDF solo se generan para las versiones etiquetadas.
- **Nombres de archivo.** Minúsculas, sin espacios ni tildes, con el identificador al inicio: `cu-01-…`, `hu-02-…`, `e-01-…`, `dcu-02a-…`.
- **Identificadores.** Son estables: uno publicado no se renumera ni se reutiliza. El prefijo de cada tipo está entre paréntesis en las tablas de arriba.
- **Versiones.** Cada documento lleva su versión y fecha; los diagramas, en el título.
- **Confidencialidad.** Las personas de la empresa se citan por cargo o por código de fuente, nunca por nombre.

## Reglas de trabajo

- Cada entrega se revisa y valida por otro integrante distinto de su autor antes de integrarse a la versión final.
- Cada integrante hace al menos un commit propio por sesión, bajo su usuario.
- `CONTRIBUCIONES.md` y `BITACORA.md` se actualizan en cada sesión.

## Correspondencia con la estructura anterior

| Antes | Ahora |
|---|---|
| `01-Kickoff/` | `26-empresa-acuerdo/` |
| `02-elicitacion/` | `27-levantamiento/` |
| `03-especificacion/` | `28-analisis-modelado/` (metas, casos de uso, historias) |
| `04-priorizacion/` | `28-analisis-modelado/priorizacion/` |
| `05-validacion/` | `30-validacion-sustentacion/` |
