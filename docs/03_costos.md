# 03 — Costos para mantener el proyecto

Precios consultados el 25 de noviembre de 2026. Montos en dólares salvo que diga Q (quetzales). Tipo de cambio referencial: 1 USD ≈ Q7.75, a verificar al facturar.

## Modelo de cobro

| Concepto | Quién lo paga | Detalle |
| --- | --- | --- |
| Desarrollo | Doctor | Q2,500: 50% al iniciar y 50% al entregar |
| Dominio | Doctor, en su cuenta propia | Si usa el dominio que tiene en UVG no hay costo nuevo. Si compra uno, un `.com` en Cloudflare Registrar cuesta desde $7.85/año (~Q61/año) |
| Hosting en Railway | Doctor | El desarrollador entrega y administra el proyecto en Railway, pero la cuenta y el pago son del doctor |
| Mantenimiento | Doctor al desarrollador | 20% de cada venta, aparte del hosting. Incluye hasta **5 horas mensuales** para cambios, actualizaciones, soporte técnico, seguridad y respaldos. No incluye hosting ni dominio |
| Video y correos | Incluidos en el mantenimiento | Bunny Stream con mínimo de $1/mes y Resend gratis hasta 3,000 correos/mes |
| QPayPro | Doctor | Comisión por transacción, según el plan que tenga contratado |

## Costo fijo mensual

| Concepto | Costo mensual | En quetzales |
| --- | --- | --- |
| Dominio (si usa el actual de UVG) | $0 | Q0 |
| Dominio `.com` nuevo, prorrateado | ~$0.65 | ~Q5 |
| DNS, CDN, HTTPS y WAF en Cloudflare Free | $0 | Q0 |
| Frontend en Cloudflare Pages | $0 | Q0 |
| Hosting backend y PostgreSQL en Railway Hobby | $5–15 | Q39–116 |
| Almacenamiento de video en Bunny Stream | $1 (mínimo del plan) | Q7.75 |
| Correos en Resend | $0 hasta 3,000 correos | Q0 |
| **Total fijo** | **$6–16** | **Q47–129** |

El mínimo de $1 de Bunny cubre el almacenamiento de un curso de 5 horas en 1080p (~20 GB). El gasto que cambia con los alumnos es la entrega del video, no el almacenamiento.

## Costo variable por alumno

El curso se ve **una sola vez** cuando el alumno lo completa. No hay cargo mensual por alumno.

| Concepto | Costo por alumno |
| --- | --- |
| Entrega del video en Bunny, 1080p (~20 GB), tarifa Standard | Q1.55 (~$0.20). En tarifa Volume, Q0.78 (~$0.10) |
| Comisión de QPayPro | Alrededor de 5.95% + Q2.95 por venta. Con un curso de Q500 son ~Q32.7 |

Si el alumno ve solo entre 50% y 60% del video, el costo de entrega baja a la mitad.

## Estimados para el primer año

Supuestos: curso de 5 horas en 1080p, tarifa Standard de Bunny, dominio propio ya existente y Railway en el rango medio de $10/mes (~Q78). No se esperan 100 alumnos de golpe: esa es una meta optimista.

| Alumnos en el primer año | Fijo mensual | Video, pago único | Total de operación | QPayPro si el curso cuesta Q500 |
| --- | --- | --- | --- | --- |
| 1 | Q47–129 | Q1–2 | Q48–131 | Q32.7 |
| 10 | Q47–129 | Q8–16 | Q55–145 | Q327 |
| 30 | Q47–129 | Q23–47 | Q70–176 | Q981 |

Si se compra un `.com` nuevo, sumar ~Q5 al fijo mensual. El mantenimiento de 20% se calcula sobre las ventas y es aparte de estas cifras.

## Fuentes

- [Railway — precios](https://railway.com/pricing)
- [Cloudflare — planes de red y CDN](https://www.cloudflare.com/plans/network-cdn)
- [Cloudflare Registrar](https://www.cloudflare.com/products/registrar/)
- [Cloudflare Pages — límites](https://developers.cloudflare.com/pages/platform/limits/)
- [Bunny Stream — precios](https://bunny.net/pricing/stream)
- [Resend — precios](https://resend.com/pricing)
- [QPayPro — precios Guatemala](https://www.qpaypro.com/gt/precios)
