# 02 — Plan de trabajo

Este plan acompaña la propuesta y es el que se presenta al cliente junto con la decisión de video de `01_stack_tecnologico.md`.

## Fases y entregables

| Fase | Actividades de la propuesta | Semanas | Horas | Entregable |
| --- | --- | --- | --- | --- |
| 1. Análisis y configuración | 1, 3 | 1 | 18 | Estructura de cursos y entornos de prueba y producción listos en Railway y Cloudflare |
| 2. Diseño de interfaz | 2 | 1–2 | 12 | Pantallas de celular y escritorio aprobadas |
| 3. Base de datos y cuentas | 4, 5 | 2–3 | 26 | Login, verificación, recuperación, roles y verificación en dos pasos funcionando |
| 4. Catálogo y video | 6, 7 | 3–4 | 24 | Cursos visibles y lecciones con video protegido |
| 5. Cuestionarios y progreso | 8, 9 | 4–5 | 26 | Calificación en el servidor, nota mínima y avance guardado |
| 6. Pagos e inscripción | 10, 11 | 5–6 | 20 | Cobro con QPayPro, confirmación e inscripción manual |
| 7. Panel, certificado y correos | 12, 13, 14 | 6–7 | 30 | Panel de administración, certificado en PDF y correos automáticos |
| 8. Seguridad, pruebas y entrega | 15, 16, 17 | 7–8 | 24 | Respaldos, pruebas en celular y computadora, 2 rondas de ajustes, publicación y capacitación |

Total: 180 horas en 8 semanas.

## Carga por semana

Repartiendo a la mitad las actividades que abarcan dos semanas:

| Semana | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Horas | 24 | 24 | 26 | 15 | 25 | 20 | 35 | 11 |

El promedio es 22.5 horas por semana. La semana 7 concentra 35 horas y las semanas 4 y 8 quedan ligeras. Antes de empezar, conviene adelantar 6 a 8 horas de seguridad y pruebas desde la semana 7 a las semanas 4 a 6. El total no cambia; se reparte mejor.

## Verificación de las 180 horas

La suma de las 17 actividades de la propuesta es correcta: 180 horas. Alcanzan para el alcance descrito si se cumple lo siguiente:

- El cliente entrega los videos y las preguntas antes de la semana 3.
- El cliente aprueba el diseño en la semana 2.
- Los precios de los cursos están definidos antes de la semana 5.
- La cuenta de QPayPro está abierta y en modo de prueba antes de la semana 5.
- Las dos rondas de ajustes se piden dentro del plazo acordado.

No hay margen para imprevistos: cualquier cambio de alcance o demora del cliente se reprograma en lugar de absorberse. Para una propuesta cerrada se mantienen las 180 horas y esa condición queda por escrito en las responsabilidades de cada parte. Si el doctor quiere un colchón, la alternativa es sumar cerca de 27 horas, un 15%, para cubrir retrasos y hallazgos de las pruebas finales.

## Pasos para integrar el video

1. Crear la cuenta de Bunny Stream y la biblioteca de videos, con región Standard para mejor cobertura en Latinoamérica.
2. Guardar `BUNNY_LIBRARY_ID`, `BUNNY_API_KEY` y `BUNNY_TOKEN_KEY` como variables de entorno en Railway, nunca en el repositorio.
3. Subir los videos del curso desde el panel o por API con TUS reanudable, indicado para archivos de 1 a 2 horas.
4. Activar token authentication con enlaces que vencen en pocas horas y configurar la marca de agua con el correo del alumno.
5. En Fastify, revisar la inscripción del alumno antes de generar cada URL firmada.
6. Integrar el reproductor con HLS adaptativo y limitar la resolución máxima a 1080p, con 720p como calidad estándar.
7. Probar enlace vencido, hotlink, marca de agua visible, reproducción en celular y reanudación de subida.
8. Revisar el consumo de almacenamiento y entrega en Bunny al cierre de cada mes.

## Checklist de entrega

- [ ] Cada lección verifica inscripción antes de entregar el video.
- [ ] Los enlaces de video vencen y muestran el correo del alumno.
- [ ] Los cuestionarios califican en el servidor y no envían respuestas correctas al navegador.
- [ ] El progreso y las notas se guardan por alumno.
- [ ] El cobro se confirma con QPayPro y la inscripción queda automática.
- [ ] El certificado en PDF se genera al terminar el curso con la plantilla de Vitaris.
- [ ] Las inscripciones corporativas crean cuentas para los empleados cuando la empresa paga la totalidad.
- [ ] Los correos de bienvenida, recibo y recuperación llegan correctamente.
- [ ] Hay respaldo diario de PostgreSQL y se probó una restauración.
- [ ] El panel de administración permite subir videos, crear preguntas y ver alumnos y ventas.
- [ ] Las pruebas pasan en celular y computadora y se cerraron las 2 rondas de ajustes.
- [ ] Está lista la capacitación para usar el panel.
