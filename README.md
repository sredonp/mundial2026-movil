# Fase Final Mundial 2026 · Versión móvil

Bracket vertical y colapsable de la fase final del Mundial 2026, optimizado
para pantalla de teléfono. Instalable como app (PWA) en iPhone y Android.

Datos en vivo desde el mismo backend (Apps Script) que la versión de escritorio:
https://sredonp.github.io/mundial2026/

## Qué cambia frente a la versión de escritorio

- El bracket se dibuja de **arriba hacia abajo** en vez de izquierda a derecha.
- Cada ronda (1/16, Octavos, Cuartos, Semifinal) es una **sección colapsable**:
  tócala para expandir o cerrar.
- Al abrir la app, **1/16 de Final** aparece expandida; el resto empieza cerrado.
- La Final y el Tercer Puesto siempre están visibles arriba, en una tarjeta
  destacada (como en la versión de escritorio).
- Se puede **instalar en la pantalla de inicio** del teléfono (ver abajo).

## Cómo publicarlo en GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `mundial2026-movil`.
2. Sube estos archivos a la raíz del repo:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - carpeta `icons/` (con `icon-192.png` e `icon-512.png`)
3. En el repo: **Settings → Pages → Branch: main → /(root)** → Save.
4. En 1-2 minutos tu sitio queda disponible en:
   `https://TU-USUARIO.github.io/mundial2026-movil/`

## Cómo instalarlo en el teléfono

**iPhone (Safari):**
1. Abre el link del sitio en Safari (tiene que ser Safari, no Chrome).
2. Toca el botón de compartir (el cuadrado con la flecha hacia arriba).
3. Baja y toca **"Agregar a pantalla de inicio"**.
4. Listo — aparece un ícono como cualquier app, abre en pantalla completa.

**Android (Chrome):**
1. Abre el link en Chrome.
2. Es posible que aparezca un banner abajo ofreciendo instalar la app, o:
3. Toca el menú (los tres puntos) → **"Instalar app"**.
4. Listo.

Quien no quiera instalarla puede simplemente abrir el link en el navegador,
sin perder ninguna función.

## Cómo se instala ahora

La app ya no requiere que busques instrucciones por tu cuenta: te las muestra
ella misma, apenas la abres.

**iPhone (Safari):** a los 1-2 segundos de abrir el sitio aparece un cartel
abajo indicando "toca Compartir → Agregar a pantalla de inicio". Apple no
permite que ningún sitio web se instale solo en iOS (ni Spotify, ni Twitter,
ni nadie puede saltarse ese paso) — es una restricción del sistema, no de esta
app. Lo más cercano a "automático" es justamente esto: que el cartel aparezca
solo y te diga exactamente qué tocar, sin que tengas que acordarte tú.

**Android (Chrome):** aparece un cartel con un botón **"Instalar"**. Al
tocarlo, Chrome muestra su diálogo nativo de instalación directamente — un
solo toque, sin tener que buscar el menú de los tres puntos.

En ambos casos el cartel tiene una "✕" para cerrarlo, y una vez cerrado no
vuelve a aparecer (se recuerda en el propio teléfono).

## Notas técnicas

- El `sw.js` (service worker) cachea los archivos estáticos para que la app
  abra rápido incluso con mala señal. Los datos en vivo del bracket **nunca**
  se cachean — siempre se piden frescos al backend.
- Si cambias el backend (Apps Script URL), actualiza la constante `PROXY`
  dentro de `index.html`.
- Los IDs de partido (73–104) siguen exactamente la misma numeración que la
  versión de escritorio, documentada en los comentarios del archivo.
