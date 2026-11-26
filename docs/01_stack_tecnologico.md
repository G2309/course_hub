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

## Dónde alojar el video del curso

Investigado en noviembre de 2026. El caso es específico: videos de pago, acceso solo para alumnos inscritos, enlaces que vencen, marca de agua, grabación en MP4/H.264 y 5 a 15 minutos por lección. Eso descarta cualquier servicio que solo oculte el enlace.

| Servicio | Precio orientativo | Protección | Encaje en Course Hub |
| --- | --- | --- | --- |
| Bunny Stream | Desde $1/mes; almacenamiento desde $0.01/GB y entrega desde $0.005/GB; codificación gratis | URLs con token, bloqueo de hotlink y marca de agua incluidos; DRM de pago | El mejor encaje: plataforma propia, control de acceso desde Fastify y el costo más bajo por GB entregado |
| Cloudflare Stream | $5/mes por cada 1,000 minutos almacenados (prepago) + $1 por cada 1,000 minutos entregados; codificación gratis | URLs firmadas y restricción de dominio | Alternativa sólida: ya usas Cloudflare para DNS/HTTPS y la factura es predecible por minutos, no por bitrate |
| Mux | 100,000 minutos entregados gratis al mes; almacenamiento ~$0.003/min y entrega ~$0.001/min | URLs firmadas; DRM $100/mes + $0.003 por reproducción | Más caro y con extras costosos; solo tiene sentido si necesitas analítica de calidad de reproducción |
| Vimeo | Desde ~$9/mes facturado anualmente | Restricción de dominio, sin anuncios | Cómodo para un creador, pero no encaja con una plataforma propia y los planes de negocio salen caros |
| YouTube (no listado) | Gratis | Ninguna: cualquiera con el enlace puede verlo y compartirlo | Solo para videos promocionales, nunca para las lecciones de pago |

### Comparación de costos

Para una biblioteca de 20,000 minutos vista 200,000 minutos al mes, una comparativa publicada el 19 de noviembre de 2026 calculó aproximadamente $35/mes en Bunny Stream, $160 en Mux, $300 en Cloudflare Stream y $397 en api.video, usando las tarifas de cada proveedor.

El número de Bunny depende del bitrate porque cobra por GB, mientras que Cloudflare cobra por minuto y no penaliza la calidad. Con 720p/1080p y alumnos que ven las lecciones completas, Bunny suele salir más barato; con mucho tráfico y videos de alta calidad, la diferencia se reduce.

### Decisión

Mantener **Bunny Stream**, como ya está en la propuesta.

- Cumple lo que la propuesta promete: enlaces firmados que vencen, marca de agua visible y acceso revisado por inscripción.
- Codificación estándar y reproductor incluidos sin costo adicional.
- Es la opción más económica para una biblioteca que crece y se ve completa.
- Cloudflare Stream queda como plan B si prefieres un solo proveedor y una factura en minutos. Es más predecible, pero en el ejemplo anterior cuesta unas 8 veces más.
- YouTube queda reservado para contenido gratuito de atracción; Vimeo y Wistia para quien quiere una solución cerrada, no para este desarrollo.
- El DRM completo de Bunny es un complemento de pago. Para el riesgo actual, los enlaces con token y la marca de agua son suficientes; si el cliente lo pide, se cotiza aparte.

Revisar las tarifas antes de contratar, porque cambian.

### Fuentes

- [Bunny Stream — precios](https://bunny.net/pricing/stream)
- [Cloudflare Stream — precios](https://developers.cloudflare.com/stream/pricing)
- [Comparativa de precios de streaming 2026](https://www.aitoolbox.hk/articles/best-video-streaming-pricing-2026-mux-vs-cloudflare-stream-vs-bunny-stream-vs-apivideo/)
- [Video hosting para cursos en línea, costos comparados](https://swarmify.com/blog/video-hosting-for-online-courses)
- [Comparativa de plataformas de video](https://cloudinary.com/guides/video/best-video-hosting-platforms)
