# 06 — Roadmap

## Objetivo

Entregar la plataforma de cursos de Academia Vitaris con 180 horas de desarrollo.

## Honorarios

| Concepto | Valor |
| --- | --- |
| Horas de desarrollo | 180 |
| Tarifa sugerida | Q14/hora |
| Total con esa tarifa | Q2,520 |
| Total acordado en la propuesta | Q2,520 |

Opción elegida: **Q14/hora, total Q2,520**. La propuesta ya registra ese monto.

## Actividades por branch

| Branch | # | Actividad | Horas |
| --- | --- | --- | --- |
| `feat/fundamentos` | 1 | Análisis y planificación de cursos, lecciones y cuestionarios | 10 |
| `feat/fundamentos` | 3 | Configuración del proyecto: repositorio, Railway, Cloudflare, dominio y entornos | 8 |
| `feat/diseno` | 2 | Diseño de interfaz: bocetos, colores, tipografía y versión celular | 12 |
| `feat/base-datos` | 4 | Base de datos: usuarios, cursos, lecciones, preguntas, inscripciones, progreso y pagos | 10 |
| `feat/autenticacion` | 5 | Cuentas y login: registro, verificación, recuperación, sesiones, roles y 2FA | 16 |
| `feat/catalogo` | 6 | Catálogo y página del curso: lista de cursos, detalle y lecciones en orden | 12 |
| `feat/video` | 7 | Integración de video: Bunny, enlaces firmados, reproductor y correo del alumno | 12 |
| `feat/cuestionarios` | 8 | Cuestionarios: preguntas, calificación en servidor, nota mínima y desbloqueo | 18 |
| `feat/cuestionarios` | 9 | Progreso del alumno: lecciones completadas, notas y porcentaje de avance | 8 |
| `feat/pagos` | 10 | Integración de pagos: QPayPro Premium, confirmación e inscripción automática | 16 |
| `feat/pagos` | 11 | Inscripción corporativa: la empresa paga y se crean cuentas para empleados | 4 |
| `feat/panel` | 12 | Panel de administración: videos, preguntas, alumnos y ventas | 16 |
| `feat/certificado` | 13 | Certificado en PDF con la plantilla de Vitaris | 8 |
| `feat/correos` | 14 | Correos automáticos: bienvenida, recibo y recuperación | 6 |
| `fix/seguridad` | 15 | Seguridad: límites, sesiones, encabezados, respaldos y revisión final | 8 |
| `test/integracion` | 16 | Pruebas en celular y computadora y 2 rondas de ajustes | 10 |
| `release/entrega` | 17 | Publicación y capacitación para usar el panel | 6 |
|  |  | **Total** | **180** |

La documentación vive en la rama `docs`, fuera de estas 180 horas. El pipeline de CI/CD se trabajará en ramas `ci/...` cuando se apruebe, también fuera de este total.

## Hitos de aceptación

- Diseño aprobado por el doctor.
- Videos y preguntas entregados.
- Precios definidos y acceso a QPayPro Premium disponible.
- Dos rondas de ajustes cerradas.
- Plataforma publicada y capacitación realizada.

## Condición de las horas

El estimado alcanza si el doctor entrega videos y preguntas antes de integrar el video, aprueba el diseño antes de construir la interfaz, define los precios y da acceso a QPayPro Premium antes de integrar pagos. No hay margen para cambios de alcance: cualquier demora o ajuste adicional se reprograma. Si se quiere un colchón, se pueden sumar unas 27 horas, un 15%.

## Entregable final

Plataforma publicada con dominio en Cloudflare, backend y base de datos en Railway, video en Bunny, cobros con QPayPro Premium, correos en Resend, certificado con la identidad de Vitaris, respaldos diarios, soporte y capacitación del panel.
