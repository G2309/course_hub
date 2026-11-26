# 05 — Grabación de videos

Recomendación para grabar el curso con buena calidad, sin equipo profesional y sin perder nitidez al subirlo a Bunny Stream. El doctor graba en **Mac** y normalmente lo hace a **1080p**; conviene probar otras configuraciones antes de grabar las 5 horas completas.

## Equipo y permisos

- OBS Studio para macOS, gratis: [obsproject.com](https://obsproject.com/).
- En macOS hay que dar permisos de **Grabación de pantalla** y **Micrófono** a OBS en Ajustes del Sistema → Privacidad y seguridad.
- Micrófono USB externo cerca de la boca. El audio importa más que la cámara: un video algo menos nítido se perdona; un audio con eco, no.
- Luz frontal suave. Evita sentarte con una ventana detrás.
- Si grabas pantalla con texto pequeño, mantén 1080p y aumenta el zoom del navegador a 125–150%.

## Ajustes iniciales en OBS

| Ajuste | Valor sugerido |
| --- | --- |
| Modo de salida | Simple |
| Formato de grabación | MP4 |
| Calidad de grabación | Alta calidad o indistinguible |
| Tasa de bits | 8,000–10,000 Kbps en 1080p; 4,000–5,000 Kbps en 720p |
| Resolución de salida | 1920×1080 o 1280×720 |
| FPS | 30 |
| Codificador | VideoToolbox, que usa el hardware del Mac; x264 como alternativa |
| Audio | AAC, 48 kHz, 160 Kbps |

## Probar antes de grabar

Grabar tres pruebas cortas del mismo fragmento y compararlas:

1. 1080p a 8,000 Kbps.
2. 1080p a 5,000 Kbps.
3. 720p a 4,000 Kbps.

Subir cada prueba a Bunny Stream en privado y revisarla en celular y computadora. Comparar la lectura del texto, el ruido del audio y el tamaño del archivo. Elegir la configuración más baja que siga viéndose nítida; eso deja espacio en disco y reduce el costo de entrega.

## Evitar pérdida de calidad

- Graba directo en MP4/H.264 y súbelo tal cual. Cada conversión vuelve a comprimir.
- Si te preocupa un corte de luz durante un video de 2 horas, graba en MKV y usa **Remux** en OBS para pasarlo a MP4. Remux cambia el contenedor sin recodificar.
- Graba cada lección como un archivo independiente de 1 a 2 horas; no unas videos exportándolos de nuevo.
- No apliques filtros de "mejora" ni zoom digital. Mantén la resolución original.

## Espacio y entrega

Cinco horas a 1080p y 8 Mbps ocupan unos 18 GB; en 720p y 4 Mbps, unos 9 GB. Ten al menos 30 GB libres en el Mac.

Cada lección se entrega como `curso-leccion-XX.mp4`, MP4 con H.264 y AAC. Bunny genera las resoluciones adaptativas a partir de ese archivo.
