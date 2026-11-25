# 🎸 Traste · Práctica de guitarra

App web para practicar guitarra, aprender a **improvisar** y **componer**. Funciona en el celular y en la computadora, se puede instalar como app y funciona sin internet. No necesita servidor ni base de datos: todo se guarda en tu navegador.

## Qué incluye

| Sección | Para qué sirve |
|---|---|
| ⏱ **Práctica** | Cronómetro de sesiones, racha de días, gráfica semanal, historial, rutina diaria sugerida (15–60 min) y respaldo en JSON. |
| 🎚 **Afinador** | Afinador cromático con el micrófono y notas de referencia por cuerda (La 440 ajustable). |
| 🥁 **Metrónomo** | De 30 a 260 BPM, compases, subdivisiones, tap tempo y **entrenador de velocidad** (sube el tempo solo). |
| 🎸 **Escalas** | 12 escalas en el diapasón (pentatónicas, blues, modos, menores), por posiciones, con notas o intervalos, y los acordes de cada escala con su digitación. |
| 🎷 **Improvisar** | Pistas de acompañamiento (batería, bajo y guitarra) en cualquier tonalidad: pop, blues de 12 compases, rock, jazz ii–V–I, andaluza, funk dórico… El diapasón marca en verde las **notas objetivo** del acorde que está sonando. |
| ✍️ **Componer** | Arma progresiones con los acordes de la tonalidad, préstamos y dominantes secundarios; botón “Inspírame”, diagramas de acordes, espacio para letra y melodía, y guardado de canciones. Mándala a Improvisar con un toque. |
| 👂 **Oído** | Reconocer intervalos y tipos de acorde en 3 niveles, con canciones de referencia. |

Ajustes (⚙︎): notación latina (Do, Re, Mi) o americana (C, D, E), número de trastes y modo para zurdos.

## Publicarla en GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `traste`), público.
2. Sube **todos** los archivos de esta carpeta a la raíz del repositorio (*Add file → Upload files*).
3. Ve a **Settings → Pages**. En *Build and deployment* elige **Deploy from a branch**, rama `main`, carpeta `/ (root)` y guarda.
4. En un par de minutos estará en `https://TU-USUARIO.github.io/traste/`.

En el celular abre el enlace y usa **“Agregar a pantalla de inicio”** para instalarla como app.

> El afinador necesita **https** para usar el micrófono; GitHub Pages ya lo da. Si abres `index.html` directamente desde tu computadora, todo funciona menos el micrófono en algunos navegadores.

## Probarla en tu computadora

```bash
python3 -m http.server 8000
# abre http://localhost:8000
```

## Archivos

```
index.html            La app completa (HTML, CSS y JavaScript, sin dependencias)
sw.js                 Service worker para que funcione sin conexión
manifest.webmanifest  Datos para instalarla como app
icon.svg, icon-*.png  Íconos
```

Al publicar cambios, sube el número de `CACHE` en `sw.js` (`traste-v2`, `traste-v3`…) para que los celulares reciban la versión nueva.

## Tecnología

- JavaScript puro, sin frameworks ni librerías externas.
- Sonido generado en el navegador con Web Audio (síntesis de cuerda Karplus-Strong, batería y bajo sintetizados) y programación precisa sobre el reloj de audio.
- Afinador por autocorrelación de la señal del micrófono.
- Datos en `localStorage` (exporta un respaldo desde *Práctica → Historial*).

## Licencia

MIT © 2026 Esmeralda Archundia Jiménez
