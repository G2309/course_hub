# 03 — Costos para mantener el proyecto

Precios consultados el 25 de noviembre de 2026. Montos en dólares salvo que diga Q (quetzales). Tipo de cambio referencial: 1 USD ≈ Q7.75, a verificar al facturar.

## Modelo de cobro

| Concepto | Quién lo paga | Detalle |
| --- | --- | --- |
| Desarrollo | Doctor | Q2,520 |
| Dominio | Doctor | Descartado el dominio de UVG. Se compra un `.com` en Cloudflare Registrar, alrededor de $8–11 al año (~Q62–85) |
| Hosting en Railway | Doctor | El desarrollador entrega y administra el proyecto, pero la cuenta y el pago son del doctor |
| QPayPro | Doctor | Plan Premium, Q195/mes, con comisión desde 3.5% + Q2.95 por transacción. La tarifa exacta depende del giro y se confirma en su cuenta |
| Mantenimiento | Doctor al desarrollador | 20% de cada venta, aparte del hosting. Incluye hasta **5 horas mensuales** para cambios, actualizaciones, soporte técnico, seguridad y respaldos. No incluye hosting ni dominio |
| Video y correos | Incluidos en el mantenimiento | Bunny Stream con mínimo de $1/mes y Resend gratis hasta 3,000 correos/mes |

El doctor preguntó a dónde deposita el pago del dominio. Falta definir si lo paga directamente en Cloudflare Registrar o si te reembolsa a ti.

## Costo fijo mensual

| Concepto | Costo mensual | En quetzales |
| --- | --- | --- |
| Dominio `.com` en Cloudflare Registrar, prorrateado | ~$0.70–0.95 | Q5–8 |
| DNS, CDN, HTTPS y WAF en Cloudflare Free | $0 | Q0 |
| Frontend en Cloudflare Pages | $0 | Q0 |
| Hosting backend y PostgreSQL en Railway Hobby | $5–15 | Q39–116 |
| Almacenamiento de video en Bunny Stream | $1 (mínimo del plan) | Q7.75 |
| Correos en Resend | $0 hasta 3,000 correos | Q0 |
| QPayPro Premium | ~$25 | Q195 |
| **Total fijo** | **~$32–42** | **Q247–327** |

El mínimo de $1 de Bunny cubre el almacenamiento de un curso de 5 horas en 1080p (~20 GB). El gasto que cambia con los alumnos es la entrega del video, no el almacenamiento.

## Costo variable por alumno

El curso se ve **una sola vez** cuando el alumno lo completa. No hay cargo mensual por alumno.

| Concepto | Costo por alumno |
| --- | --- |
| Entrega del video en Bunny, 1080p (~20 GB), tarifa Standard | Q1.55 (~$0.20). En tarifa Volume, Q0.78 (~$0.10) |
| Comisión de QPayPro Premium | Desde 3.5% + Q2.95. Con un curso de Q500 son ~Q20.45 |

Si el alumno ve solo entre 50% y 60% del video, el costo de entrega baja a la mitad.

## Estimados para el primer año

Supuestos: curso de 5 horas en 1080p, tarifa Standard de Bunny, Railway en el rango medio de $10/mes (~Q78), dominio nuevo y QPayPro Premium. No se esperan 100 alumnos de golpe: esa es una meta optimista.

| Alumnos en el primer año | Fijo mensual | Video, pago único | QPayPro por ventas | Total del primer mes |
| --- | --- | --- | --- | --- |
| 1 | Q247–327 | Q1–2 | Q20 | Q268–349 |
| 10 | Q247–327 | Q8–16 | Q205 | Q460–548 |
| 30 | Q247–327 | Q23–47 | Q614 | Q884–988 |

El mantenimiento de 20% sobre las ventas se calcula aparte de estas cifras y lo paga el doctor al desarrollador.

## Fuentes

- [Railway — precios](https://railway.com/pricing)
- [Cloudflare — planes de red y CDN](https://www.cloudflare.com/plans/network-cdn)
- [Cloudflare Registrar](https://www.cloudflare.com/products/registrar/)
- [Cloudflare Pages — límites](https://developers.cloudflare.com/pages/platform/limits/)
- [Bunny Stream — precios](https://bunny.net/pricing/stream)
- [Resend — precios](https://resend.com/pricing)
- [QPayPro — precios Guatemala](https://www.qpaypro.com/gt/precios)
