# 05 — Grabación de videos

Recomendación para grabar el curso con buena calidad, sin pagar equipo profesional y sin perder nitidez al subirlo a Bunny Stream.

## Equipo mínimo

- OBS Studio, gratis y multiplataforma: [obsproject.com](https://obsproject.com/).
- Micrófono USB externo, colocado cerca de la boca. El micrófono importa más que la cámara: un video algo menos nítido se perdona; un audio con eco, no.
- Luz frontal suave. Evita sentarte con una ventana detrás, porque la cámara oscurece tu rostro.
- Si grabas pantalla con código o texto pequeño, usa 1080p y aumenta el zoom del navegador a 125–150%.

## Ajustes de OBS

| Ajuste | Valor |
| --- | --- |
| Modo de salida | Simple |
| Formato de grabación | MP4 |
| Calidad de grabación | Alta calidad o indistinguible |
| Tasa de bits | 8,000–10,000 Kbps en 1080p; 4,000–5,000 Kbps en 720p |
| Resolución de salida | 1920×1080 o 1280×720, según lo que grabes |
| FPS | 30 |
| Codificador | NVENC o Quick Sync si hay tarjeta gráfica; x264 si no |
| Audio | AAC, 48 kHz, 160 Kbps |

Si el equipo se queda corto, baja primero a 720p antes que bajar la tasa de bits: se mantiene mejor la nitidez del texto.

## Evitar pérdida de calidad

- Graba directo en MP4/H.264 y súbelo tal cual. No lo conviertas a otro formato "para mejorarlo": cada conversión vuelve a comprimir.
- Si te preocupa que un corte de luz arruine un video de 2 horas, graba en MKV y luego usa **Remux** en OBS para convertirlo a MP4. Remux cambia el contenedor sin recodificar, así que no pierde calidad.
- No unas videos recortados con programas que vuelvan a exportar. Graba cada lección como un archivo independiente de 1 a 2 horas.
- No apliques filtros de "mejora" ni zoom digital. Mantén la resolución original.

## Espacio y prueba

Cinco horas a 1080p y 8 Mbps ocupan unos 18 GB; en 720p y 4 Mbps, unos 9 GB. Ten al menos 30 GB libres antes de empezar.

Antes de grabar el curso completo, haz una prueba de 2 minutos con el mismo ajuste, súbela a Bunny Stream en privado y revísala en celular y computadora. Confirma que el texto se lee, que el audio no satura y que la marca de agua se ve. Corrige los ajustes antes de grabar las 5 horas.

## Entrega

Cada lección se entrega como `curso-leccion-XX.mp4`, MP4 con H.264 y AAC. Bunny se encarga de generar las resoluciones adaptativas a partir de ese archivo.

## Mensaje para enviarle al doctor

> Don [nombre], para que los videos se vean nítidos sin que la grabación salga cara, le conviene grabar con OBS Studio, que es gratis. La sugerencia es grabar en MP4, 1080p a 30 cuadros por segundo con tasa de bits de 8 a 10 Mbps, o 720p a 4 a 5 Mbps si grabó pantalla con texto pequeño y el equipo se queda corto. Lo más importante es usar micrófono externo y luz frontal, y grabar cada lección en un archivo separado para no tener que volver a comprimir los videos. Antes de grabar las 5 horas, haga una prueba de 2 minutos y la revisamos juntos en celular y computadora.
