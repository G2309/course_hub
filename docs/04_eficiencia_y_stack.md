# 04 — Eficiencia del stack

Investigado el 25 de noviembre de 2026. La pregunta es si conviene cambiar React o Fastify para reducir dependencias, memoria, CPU o tiempo de respuesta.

## Primero, una distinción

`node_modules` grandes no consumen memoria ni CPU en producción: ocupan disco y alargan la instalación y el build. Eso se ataca con un gestor de paquetes eficiente y con menos dependencias, no cambiando de framework. El costo en el navegador es el JavaScript que se envía; el costo en el servidor es el proceso en ejecución.

## Backend

| Opción | Peticiones/s en benchmark de Fastify | Memoria en reposo | Paquetes instalados |
| --- | --- | --- | --- |
| Fastify 5.12 | 89,733 | ~72–78 MB | Moderado |
| Hono 4.13 | 84,930 | ~63–66 MB | 4 con Zod |
| Express 5.3 | 67,794 | ~65–75 MB | 66 con Zod |
| NestJS 12 | — | ~100–106 MB | 104 |

Otras mediciones en un solo núcleo dan Fastify 19,918 lecturas/s y Hono 18,397, contra 10,963 de Express. En POST con JSON, Fastify lleva ventaja de unos 17% sobre Hono porque usa su propio parser y serializador compilado.

Si te referías a **FastAPI de Python**: no aparece en estas comparativas de Node y no es más ligero. Python tiene un runtime más pesado y más sobrecarga por petición. Cambiar de Fastify a FastAPI subiría el consumo y obligaría a reescribir el proyecto.

Hono es la alternativa real: arranca más rápido, usa algo menos de memoria e instala muchos menos paquetes. Elysia va aún mejor, pero depende de Bun. Migrar hoy no compensa: la diferencia absoluta son unos pocos MB y el costo es rehacer validación, plugins, logging y pruebas dentro de las 180 horas previstas.

**Decisión:** mantener Fastify. Es el más rápido o el segundo en casi todas las mediciones, ya está en el stack y su sobrecarga es de decenas de MB, no de cientos.

## Frontend

| Opción | JavaScript enviado | Cuándo conviene |
| --- | --- | --- |
| Vite + React SPA | ~58 KB gzip | Aplicaciones con mucha interacción y estado compartido |
| Astro sin islas | 0 KB | Páginas de contenido, landing, documentación |
| Astro con una isla de React | ~59 KB | Una interacción aislada; sigue cargando React completo |
| SvelteKit | ~12–32 KB | Aplicaciones interactivas con presupuesto de bundle ajustado |

Astro no abarata React: en cuanto hidratas un componente, el navegador descarga React y React DOM igual que en una SPA. La ventaja aparece solo cuando puedes no enviar framework alguno. Course Hub tiene login, cuestionarios, progreso y panel de administración: son islas por todas partes, así que Astro perdería su ventaja y añadiría una capa más.

**Decisión:** mantener Vite + React. Para bajar el peso real sin cambiar de stack: separar el código por ruta, cargar el panel de administración de forma diferida, no traer una librería completa de componentes y dejar que el CDN comprima los assets.

## Despliegue

Railway puede alojar backend y frontend, y es la opción más simple de administrar en un solo lugar. El frontend es estático, así que también puede vivir en Cloudflare Pages sin costo, con 500 builds al mes y 100 dominios personalizados. La combinación recomendada es backend y PostgreSQL en Railway, frontend en Cloudflare Pages y DNS/WAF en Cloudflare. Si prefieres tener todo en Railway, el plan Hobby de $5/mes incluye $5 de uso y es suficiente para empezar.

## Fuentes

- [Fastify — benchmarks](https://fastify.dev/benchmarks/)
- [Comparativa de frameworks Node.js 2026](https://geekflare.com/open-source/node-js-frameworks)
- [Hono, Fastify y Express en Node 26](https://fabwaseem.com/blog/nestjs-vs-hono-vs-fastify)
- [Astro frente a Vite + React, payloads medidos](https://prismetic-group.medium.com/astro-ships-0-kb-of-javascript-vite-react-ships-58-kb-10538a8a64ef)
- [Astro vs SvelteKit](https://www.pkgpulse.com/guides/astro-vs-sveltekit-2026)
- [Railway — precios](https://railway.com/pricing)
- [Cloudflare Pages — límites](https://developers.cloudflare.com/pages/platform/limits/)
