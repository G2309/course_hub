# 03 — Costos para mantener el proyecto

Precios consultados el 25 de noviembre de 2026. Montos en dólares salvo que diga Q (quetzales). Tipo de cambio referencial: 1 USD ≈ Q7.75, a verificar al facturar.

## Lo que se cobra

| Concepto | Monto |
| --- | --- |
| Desarrollo | Q2,500. Según la propuesta: 50% al iniciar y 50% al entregar |
| Mantenimiento | 20% de cada venta de cursos, según indicación actual |
| Mantenimiento en la propuesta consolidada | 15% de cada venta con mínimo de Q400/mes |

Hay una diferencia entre el 20% que indicaste ahora y el 15% con mínimo Q400 que dice la propuesta. Este md registra ambos; hay que decidir cuál se presenta al doctor antes de consolidar.

El mantenimiento cubre hosting, video, dominio, correos, respaldos, seguridad, actualizaciones, soporte técnico y hasta 2 horas de cambios pequeños al mes.

## Costos de operación

| Servicio | Uso previsto | Costo estimado | Link |
| --- | --- | --- | --- |
| Dominio `.com` | Registro y renovación | Desde $7.85/año (~Q61/año, ~Q5/mes). Un `.com` estándar suele estar entre $8.57 y $11/año según el registrador | [Cloudflare Registrar](https://www.cloudflare.com/products/registrar/) |
| DNS, CDN, HTTPS y WAF | Plan Free de Cloudflare | $0 | [Planes de Cloudflare](https://www.cloudflare.com/plans/network-cdn) |
| Frontend | Cloudflare Pages, 500 builds/mes y hasta 20,000 archivos | $0 | [Límites de Pages](https://developers.cloudflare.com/pages/platform/limits/) |
| Backend y PostgreSQL | Railway Hobby, siempre activo, $5 de uso incluidos | $5–15/mes (~Q39–116) | [Railway](https://railway.com/pricing) |
| Video | Bunny Stream, curso de 5 horas en 1080p | ~$10/mes con 100 alumnos; ~$50/mes con 500; mínimo $1 | [Bunny Stream](https://bunny.net/pricing/stream) |
| Correos | Resend Free, 3,000 correos/mes y 100/día | $0; Pro $20/mes si se supera | [Resend](https://resend.com/pricing) |
| Certificados PDF | Generados en el servidor | $0 | — |
| QPayPro | Lo paga el cliente; comisión por transacción | Plan Free Q0/mes, alrededor de 5.95% + Q2.95 por cobro según la página actual. Otra página oficial indica 5% + Q2.43; Premium Q195/mes desde 3.5% + Q2.95. Confirmar tarifa exacta | [QPayPro](https://www.qpaypro.com/gt/precios) |

### Total estimado

| Escenario | Costo mensual | Costo mensual en Q | Costo anual en Q |
| --- | --- | --- | --- |
| 100 alumnos, 1080p | $15–25 | Q116–194 | Q1,400–2,300 |
| 500 alumnos, 1080p | $55–70 | Q425–540 | Q5,100–6,500 |

El rango alto de Railway se da si el backend y la base de datos pasan de los $5 de uso incluidos. El plan Pro de Railway cuesta $20/mes por workspace si se necesitan más límites o retención de logs de 30 días.

## Railway: usar la cuenta actual o crear otra

No hace falta pedirle al doctor que abra otra cuenta para empezar. Lo recomendable es crear un proyecto separado, por ejemplo `course-hub`, dentro de tu cuenta actual de Railway: así no pagas otro plan base y la facturación sigue consolidada. Si al entregar quiere todo a su nombre, se le traspasa el proyecto o se migran las variables a su cuenta.

Crear una cuenta aparte solo tiene sentido si quieres separar cobros desde el primer día; implica otro plan Hobby de $5/mes y otra configuración de pagos.

## Punto de equilibrio del mantenimiento

Con el 20% que indicaste: si los costos son ~Q150/mes, necesitas vender ~Q750/mes para cubrirlos. Con un curso de Q500, son 2 ventas al mes.

Con el 15% y mínimo Q400 de la propuesta: el mínimo Q400 cubre los costos desde el primer mes aunque no haya ventas. Es un esquema más seguro para ti, pero más caro para el doctor cuando vende poco.

Esta diferencia conviene resolverla antes de convertir la propuesta a PDF.

## Fuentes

- [Railway — precios](https://railway.com/pricing)
- [Cloudflare — planes de red y CDN](https://www.cloudflare.com/plans/network-cdn)
- [Cloudflare Registrar](https://www.cloudflare.com/products/registrar/)
- [Cloudflare Pages — límites](https://developers.cloudflare.com/pages/platform/limits/)
- [Bunny Stream — precios](https://bunny.net/pricing/stream)
- [Resend — precios](https://resend.com/pricing)
- [QPayPro — precios Guatemala](https://www.qpaypro.com/gt/precios)
