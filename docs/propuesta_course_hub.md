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
| Duración sugerida por video | 5 a 15 minutos |

## Inversión

| Concepto | Valor |
| --- | --- |
| Horas de desarrollo | 180 horas |
| Desarrollo | Q2,500 |
| Mantenimiento | 15% de cada venta |
| Mínimo mensual de mantenimiento | Q400 |
| Hosting, video, dominio y correos | Incluido en el mantenimiento |
| Respaldos, seguridad y actualizaciones | Incluido en el mantenimiento |
| Soporte y corrección de errores | Incluido en el mantenimiento |
| Cambios pequeños al mes | Hasta 2 horas, incluidas en el mantenimiento |

## Condiciones

| Tema | Condición |
| --- | --- |
| Forma de pago inicial | 50% al iniciar y 50% al entregar la plataforma |
| Cálculo del mantenimiento | Sobre el monto cobrado al alumno |
| Pago del mantenimiento | Mensual, los primeros 5 días de cada mes |
| Mínimo mensual | Se cobra si el 15% del mes es menor a Q400 |
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
| Hosting, video, dominio y correos |  | Sí |
| Mantenimiento, respaldos y seguridad |  | Sí |
| Soporte técnico a alumnos |  | Sí |
| Capacitación para usar el panel |  | Sí |
