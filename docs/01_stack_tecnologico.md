# 01 — Stack tecnológico

## Stack decidido

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

## Video: opción que se presenta al cliente

La opción propuesta para alojar las lecciones es **Bunny Stream**. Es la decisión que queda en el stack y la que se presenta al doctor.

### Por qué Bunny Stream

- Codificación H.264 y reproductor incluidos sin costo adicional.
- URLs firmadas con expiración, protección contra hotlink y marca de agua incluidas sin cargo. El correo del alumno puede mostrarse sobre el video.
- Subida por API con TUS reanudable, pensada para archivos grandes de 1 a 2 horas.
- El reproductor entrega HLS adaptativo: cada alumno recibe 720p o 1080p según su conexión.
- 119 puntos de presencia y una API que permite revisar la inscripción en Fastify antes de entregar cada video.

### Precios oficiales

Consultados el 25 de noviembre de 2026. Todos los montos están en dólares.

| Concepto | Bunny Stream | Cloudflare Stream | Mux |
| --- | --- | --- | --- |
| Codificación | Gratis | Gratis | Gratis en 1080p basic; Plus desde $0.03125/min |
| Almacenamiento | Desde $0.01/GB al mes | $5/mes por bloque de 1,000 minutos | $0.003/min al mes |
| Entrega | Desde $0.005/GB | $1 por cada 1,000 minutos | $0.001/min después de 100,000 min gratis al mes |
| Mínimo o crédito | $1/mes | Bloque de $5/mes | $20 de crédito mensual en PAYG |
| Seguridad incluida | Token, hotlink y marca de agua | URLs firmadas | URLs firmadas y restricción de dominio y referidor |
| Página de precios | [bunny.net/pricing/stream](https://bunny.net/pricing/stream) | [developers.cloudflare.com/stream/pricing](https://developers.cloudflare.com/stream/pricing/) | [mux.com/pricing/video](https://www.mux.com/pricing/video) |

### Estimado para el curso más largo

Supuestos: 5 horas (300 minutos) repartidas en 3 videos de 1 a 2 horas, H.264, 720p a ~4 Mbps y 1080p a ~8 Mbps, con ~10% de sobrecarga por contenedor y metadatos.

| Resolución | Tamaño del curso | Almacenamiento Bunny | Entrega por alumno | 100 alumnos/mes | 500 alumnos/mes |
| --- | --- | --- | --- | --- | --- |
| 720p | ~10 GB | ~$0.10 | ~$0.05 | ~$5 | ~$25 |
| 1080p | ~20 GB | ~$0.20 | ~$0.10 | ~$10 | ~$50 |

Las cifras de entrega usan la tarifa Volume de $0.005/GB. Con la tarifa Standard de $0.01/GB, que conviene para Latinoamérica por tener más puntos de presencia, el costo se duplica: ~$20/mes con 100 alumnos y ~$100/mes con 500 en 1080p. Cloudflare cobraría $30 y $150 en esos mismos casos, sin importar la resolución. Mux regala 100,000 minutos de entrega al mes: con 100 alumnos no cobraría entrega, pero no incluye marca de agua.

En cursos largos es normal que cada alumno vea entre 50% y 60% del video, así que la entrega real suele ser la mitad de estos valores. Son estimados a tarifa de lista: la factura depende de la región, el bitrate y el hábito de visualización.

### Conclusión

Bunny Stream ofrece la calidad nítida buscada en 720p/1080p, incluye la protección que promete la propuesta y mantiene un costo estimado de ~$10/mes con 100 alumnos y ~$50/mes con 500 en 1080p, más el mínimo de $1. Es la opción a presentar. Las tarifas se revisan antes de contratar.
