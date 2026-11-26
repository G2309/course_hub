# Propuesta: plataforma de cursos en línea

## Qué incluye la plataforma

| Función | Detalle |
| --- | --- |
| Cuentas de alumnos | Registro, inicio de sesión, verificación de correo y recuperación de contraseña |
| Catálogo de cursos | Página con los cursos disponibles y su precio |
| Página del curso | Lista de lecciones en orden: videos y cuestionarios intercalados |
| Cuestionarios | Preguntas de opción múltiple, calificación automática y nota mínima para avanzar |
| Progreso del alumno | Lecciones completadas y notas de cada cuestionario |
| Pagos en línea | Cobro con tarjeta en quetzales con QPayPro |
| Inscripción manual | Para alumnos que pagan por depósito o transferencia |
| Panel de administración | Subir videos, crear cuestionarios y ver alumnos inscritos |
| Certificado | Certificado en PDF al terminar el curso |
| Correos automáticos | Bienvenida, recibo de pago y recuperación de contraseña |
| Diseño para celular | Pensado primero para verse bien en el teléfono |

## Plan de trabajo y horas hombre

| # | Actividad | Qué se hace | Semana | Horas |
| --- | --- | --- | --- | --- |
| 1 | Análisis y planificación | Definición de la estructura de cursos, lecciones y cuestionarios | 1 | 10 |
| 2 | Diseño de interfaz | Bocetos de pantallas, colores, tipografía, versión para celular | 1–2 | 12 |
| 3 | Configuración del proyecto | Repositorio, Railway, Cloudflare, dominio, entornos de prueba y producción | 1 | 8 |
| 4 | Base de datos | Tablas de usuarios, cursos, lecciones, preguntas, inscripciones, progreso y pagos | 2 | 10 |
| 5 | Cuentas y login | Registro, verificación de correo, recuperación de contraseña, sesiones, roles, verificación en dos pasos | 2–3 | 16 |
| 6 | Catálogo y página del curso | Lista de cursos, detalle del curso, lista de lecciones en orden | 3 | 12 |
| 7 | Integración de video | Conexión con Bunny, enlaces firmados, reproductor, correo del alumno sobre el video | 3–4 | 12 |
| 8 | Cuestionarios | Creación de preguntas, calificación en el servidor, nota mínima, desbloqueo de lecciones | 4–5 | 18 |
| 9 | Progreso del alumno | Lecciones completadas, notas, porcentaje de avance | 5 | 8 |
| 10 | Integración de pagos | Cobro con QPayPro, confirmación del pago, inscripción automática, pruebas en modo de prueba | 5–6 | 16 |
| 11 | Inscripción manual | Inscribir alumnos que pagan por depósito o transferencia | 6 | 4 |
| 12 | Panel de administración | Subir videos, crear y editar cuestionarios, ver alumnos y ventas | 6–7 | 16 |
| 13 | Certificado | Generación del certificado en PDF al terminar el curso | 7 | 8 |
| 14 | Correos automáticos | Bienvenida, recibo de pago, recuperación de contraseña | 7 | 6 |
| 15 | Seguridad | Límite de intentos, límite de sesiones, encabezados de seguridad, respaldos diarios, revisión final | 7 | 8 |
| 16 | Pruebas y correcciones | Pruebas en computadora y celular, corrección de errores, 2 rondas de ajustes | 8 | 10 |
| 17 | Publicación y capacitación | Puesta en línea y capacitación para usar el panel | 8 | 6 |
|  | **Total** |  | **8 semanas** | **180** |

## Tecnología

| Parte | Herramienta |
| --- | --- |
| Interfaz | Vite + React + TypeScript + Tailwind CSS |
| Servidor | Node.js + Fastify |
| Base de datos | PostgreSQL |
| Cuentas y sesiones | Better Auth |
| Hosting | Railway |
| Video | Bunny Stream |
| Pagos | QPayPro |
| Correos | Resend |
| Dominio, HTTPS y protección | Cloudflare |

## Seguridad

| Riesgo | Cómo se protege |
| --- | --- |
| Acceso a cursos sin pagar | Cada lección y cada video revisan que el alumno esté inscrito |
| Pagos falsos | Cada pago se confirma directamente con QPayPro |
| Videos compartidos o descargados | Enlaces que vencen en pocas horas y correo del alumno visible sobre el video |
| Cuentas compartidas | Máximo 2 sesiones activas por alumno |
| Copiar respuestas de cuestionarios | Las respuestas correctas nunca llegan al navegador |
| Robo de contraseñas | Contraseñas cifradas y límite de intentos de inicio de sesión |
| Cuenta de administrador robada | Verificación en dos pasos |
| Ataques al sitio | Protección de Cloudflare y conexión HTTPS |
| Pérdida de información | Respaldo diario de la base de datos |

## Video

| Ajuste | Valor |
| --- | --- |
| Resolución | 720p (1080p en lecciones con texto pequeño) |
| Calidad adaptativa | Sí, se ajusta al internet de cada alumno |
| Formato para grabar | MP4, H.264 |
| Duración sugerida por video | 5 a 15 minutos en cursos cortos; hasta 1–2 horas en el curso de 5 horas |

## Video: proveedor y costo estimado

Se propone **Bunny Stream** para alojar las lecciones. La decisión se tomó comparando los servicios que permiten controlar el acceso a videos de pago.

| Concepto | Bunny Stream | Cloudflare Stream | Mux |
| --- | --- | --- | --- |
| Codificación | Gratis | Gratis | Gratis en 1080p basic; Plus desde $0.03125/min |
| Almacenamiento | Desde $0.01/GB al mes | $5/mes por bloque de 1,000 minutos | $0.003/min al mes |
| Entrega | Desde $0.005/GB | $1 por cada 1,000 minutos | $0.001/min después de 100,000 min gratis al mes |
| Mínimo o crédito | $1/mes | Bloque de $5/mes | $20 de crédito mensual en PAYG |
| Seguridad incluida | Token, hotlink y marca de agua | URLs firmadas | URLs firmadas y restricción de dominio y referidor |
| Página de precios | [bunny.net/pricing/stream](https://bunny.net/pricing/stream) | [developers.cloudflare.com/stream/pricing](https://developers.cloudflare.com/stream/pricing/) | [mux.com/pricing/video](https://www.mux.com/pricing/video) |

Precios consultados el 25 de noviembre de 2026, en dólares.

**Estimado para el curso más largo.** 5 horas (300 minutos) repartidas en 3 videos de 1 a 2 horas, H.264, 720p a ~4 Mbps y 1080p a ~8 Mbps, con ~10% de sobrecarga.

| Resolución | Tamaño del curso | Almacenamiento Bunny | Entrega por alumno | 100 alumnos/mes | 500 alumnos/mes |
| --- | --- | --- | --- | --- | --- |
| 720p | ~10 GB | ~$0.10 | ~$0.05 | ~$5 | ~$25 |
| 1080p | ~20 GB | ~$0.20 | ~$0.10 | ~$10 | ~$50 |

Con la tarifa Standard de $0.01/GB, recomendable para Latinoamérica por su mayor cobertura, la entrega se duplica: ~$20/mes con 100 alumnos y ~$100/mes con 500 en 1080p. En cursos largos cada alumno ve entre 50% y 60% del video en promedio, así que el gasto real suele ser la mitad de esos valores. Cloudflare Stream cobraría $30 y $150 en los mismos casos; Mux regala 100,000 minutos de entrega al mes, pero no incluye marca de agua.

Bunny Stream es la opción presentada: mantiene 720p y 1080p nítidos, incluye enlaces que vencen y marca de agua sin costo adicional, y deja un gasto estimado de ~$10/mes con 100 alumnos y ~$50/mes con 500 en 1080p, más el mínimo de $1. Las tarifas se revisan antes de contratar.

## Plan de ejecución

| Fase | Semanas | Horas | Entregable |
| --- | --- | --- | --- |
| 1. Análisis y configuración | 1 | 18 | Estructura de cursos y entornos listos en Railway y Cloudflare |
| 2. Diseño de interfaz | 1–2 | 12 | Pantallas de celular y escritorio aprobadas |
| 3. Base de datos y cuentas | 2–3 | 26 | Login, recuperación, roles y verificación en dos pasos |
| 4. Catálogo y video | 3–4 | 24 | Cursos visibles y lecciones con video protegido |
| 5. Cuestionarios y progreso | 4–5 | 26 | Calificación en el servidor, nota mínima y avance guardado |
| 6. Pagos e inscripción | 5–6 | 20 | Cobro con QPayPro e inscripción manual |
| 7. Panel, certificado y correos | 6–7 | 30 | Panel de administración, certificado en PDF y correos automáticos |
| 8. Seguridad, pruebas y entrega | 7–8 | 24 | Respaldos, pruebas, 2 rondas de ajustes, publicación y capacitación |

La suma de las 17 actividades es 180 horas en 8 semanas, con un promedio de 22.5 horas semanales. La semana 7 concentra 35 horas, así que se adelantarán de 6 a 8 horas de seguridad y pruebas a las semanas 4 a 6 sin cambiar el total.

Las horas alcanzan para el alcance descrito si el cliente entrega videos y preguntas antes de la semana 3, aprueba el diseño en la semana 2, define los precios antes de la semana 5 y abre su cuenta de QPayPro antes de la semana 5. No hay margen para cambios de alcance: cualquier demora o ajuste adicional se reprograma. Si se desea un colchón, se pueden sumar unas 27 horas, un 15%.

### Pasos para integrar el video

1. Crear la cuenta y la biblioteca en Bunny Stream, con región Standard para Latinoamérica.
2. Guardar las claves de acceso como variables de entorno en Railway, nunca en el repositorio.
3. Subir los videos desde el panel o por API con TUS reanudable, indicado para archivos de 1 a 2 horas.
4. Activar enlaces con token que vencen en pocas horas y la marca de agua con el correo del alumno.
5. Revisar la inscripción en el servidor antes de entregar cada URL firmada.
6. Integrar el reproductor con HLS adaptativo, 720p como calidad estándar y 1080p como límite.
7. Probar enlace vencido, hotlink, marca de agua, reproducción en celular y reanudación de subida.
8. Revisar el consumo de almacenamiento y entrega al cierre de cada mes.

## Inversión

| Concepto | Valor |
| --- | --- |
| Horas de desarrollo | 180 horas |
| Desarrollo | Q2,500 |
| Mantenimiento | 20% de cada venta, aparte del hosting |
| Mínimo mensual de mantenimiento | No aplica |
| Hosting y dominio | Los paga el cliente; el desarrollador entrega y administra el hosting en Railway |
| Video y correos | Incluidos en el mantenimiento |
| Cambios, actualizaciones, soporte técnico, seguridad y respaldos | Hasta 5 horas mensuales, incluidas en el mantenimiento |

## Condiciones

| Tema | Condición |
| --- | --- |
| Forma de pago inicial | 50% al iniciar y 50% al entregar la plataforma |
| Cálculo del mantenimiento | Sobre el monto cobrado al alumno |
| Pago del mantenimiento | Mensual, los primeros 5 días de cada mes |
| Horas incluidas en el mantenimiento | Hasta 5 horas mensuales para cambios, actualizaciones, soporte técnico, seguridad y respaldos |
| Mínimo mensual | No se cobra; el mantenimiento es el 20% de las ventas |
| Duración mínima | 12 meses desde la entrega |
| Terminación anticipada | Pago de Q6,000 |
| Funciones nuevas | Se cotizan aparte |
| Cambios incluidos en la entrega | 2 rondas de ajustes |
| Contenido del curso | Propiedad del cliente |
| Datos de los alumnos | Propiedad del cliente |
| Código de la plataforma | Propiedad del desarrollador, con licencia de uso para el cliente durante el acuerdo |
| Tiempo de entrega estimado | 6 a 8 semanas |

## Responsabilidades de cada parte

| Responsabilidad | Cliente | Desarrollador |
| --- | --- | --- |
| Grabar los videos y crear las preguntas | Sí |  |
| Definir el precio de cada curso | Sí |  |
| Abrir y mantener la cuenta de QPayPro | Sí |  |
| Cargo de QPayPro por transacción | Sí |  |
| Emitir factura electrónica (FEL) por cada venta | Sí |  |
| Desarrollar y publicar la plataforma |  | Sí |
| Dominio en cuenta propia y pago del hosting en Railway | Sí |  |
| Entrega y administración del hosting en Railway, video y correos |  | Sí |
| Mantenimiento, respaldos y seguridad, hasta 5 h/mes |  | Sí |
| Soporte técnico a alumnos |  | Sí |
| Capacitación para usar el panel |  | Sí |
