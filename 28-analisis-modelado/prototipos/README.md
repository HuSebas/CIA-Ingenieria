# Prototipo de interfaz

| Campo | Valor |
|---|---|
| Versión | 1.0 · 2026-11-16 |
| Qué es | Prototipo funcional en HTML, CSS y JavaScript, pensado primero para celular, con las reglas de negocio implementadas y datos de ejemplo |
| Para qué | Validar con los usuarios los flujos de compras y de avance antes de cerrar el SRS |

## Cómo abrirlo

Abra [`app/index.html`](app/index.html) en un navegador. No necesita servidor ni conexión. Elija un rol para entrar; al recargar la página los datos vuelven al inicio.

[`app/pruebas.html`](app/pruebas.html) ejecuta las 33 autopruebas de las reglas y muestra cuáles pasan. También corren con `node app/pruebas.js`.

## Contenido

| Documento | Contenido |
|---|---|
| [`personas-contexto.md`](personas-contexto.md) | Personas, escenarios, contexto de uso, tareas y requisitos de usabilidad y accesibilidad |
| [`pantallas-navegacion.md`](pantallas-navegacion.md) | Inventario de pantallas, mapa de navegación por rol y matriz caso de uso × pantalla × rol × requisito |
| [`wireframes-mensajes-estilo.md`](wireframes-mensajes-estilo.md) | Wireframes anotados, los cuatro estados de cada pantalla, catálogo de mensajes y guía de estilo |
| [`reglas-validacion.md`](reglas-validacion.md) | Fichas de pantalla con sus reglas de validación y catálogo de autopruebas |
| [`evaluacion/`](evaluacion/evaluacion-heuristica.md) | Evaluación heurística, guion de la prueba de usabilidad, consentimiento, cuestionario SUS y registro de hallazgos |
| [`pantallas/`](pantallas/) | Capturas del prototipo a 360 px de ancho |
| [`wireframes/`](wireframes/) | Wireframes y mapa de navegación en PlantUML, con su imagen |

## Archivos de `app/`

| Archivo | Responsabilidad |
|---|---|
| `datos.js` | Datos de ejemplo en formato JSON: obra, rubros, actividades, compras y reportes. Ninguna cifra es real |
| `mensajes.js` | Catálogo de mensajes |
| `reglas.js` | Reglas de negocio como funciones puras; cada una cita la regla, el requisito o la transición que implementa |
| `app.js` | Pantallas y navegación. No decide nada: llama a `reglas.js` |
| `estilos.css` | Guía de estilo |
| `pruebas.js` · `pruebas.html` | Autopruebas de las reglas |

## Qué implementa y qué simula

| Implementado | Simulado o fuera del prototipo |
|---|---|
| Cálculo del saldo, tabla de decisión de la ruta, rutas de uno y dos aprobadores, reasignación de ruta, rechazo y anulación con motivo | Ingreso con contraseña: se elige el rol |
| Compra urgente con tope, legalización y devolución con observación | Envío real de notificaciones: se muestran como avisos en pantalla |
| Registro de avance con y sin conexión, sincronización y devolución del reporte | La falta de conexión: se activa con el botón «Con conexión» |
| Alerta al 80 % del rubro y acceso al presupuesto según el rol | Almacenamiento: los datos viven en memoria |
| Los cuatro estados: vacío, cargando, error y éxito | Pantallas P-12 a P-19 del inventario |

## Comprobaciones hechas

- Las 33 autopruebas pasan en Node y en el navegador.
- Recorrido completo de los cinco flujos en un navegador a 360 × 740 px: sin desplazamiento horizontal, sin controles de menos de 44 px de alto y sin errores en la consola.
- Contraste de todos los pares de color medido; los valores están en la guía de estilo.
