# Flujo de Caja (PWA)

App de flujo de caja para instalar en el celular (Android y iPhone). Sin servidor:
los datos de cada persona quedan guardados sólo en su propio teléfono.

## Publicar en GitHub Pages (una sola vez)

1. Creá un repositorio en GitHub (por ejemplo `flujo-caja`), público.
2. Subí **todos** los archivos de esta carpeta a la raíz del repo
   (`caja.html`, `caja-manifest.json`, `caja-sw.js`, `.nojekyll`, carpeta `icons/`).
3. En el repo: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root) → Save**.
4. En 1–2 minutos la app queda en `https://TU-USUARIO.github.io/flujo-caja/caja.html`.

Ese link se lo pasás a cada persona. Cada una la instala en su celular y tiene su app privada.

## Instalar en el celular

- **Android (Chrome):** abrir el link → aparece el aviso "Instalar" dentro de la app
  (o menú ⋮ → *Agregar a pantalla principal* / *Instalar app*).
- **iPhone (Safari):** abrir el link → botón *Compartir* → *Agregar a pantalla de inicio*.

Después funciona sin conexión y con su propio ícono.

## Actualizar la app

Reemplazá `caja.html` en el repo. Al abrir la app con conexión se actualiza sola
(si querés forzar, cambiá `flujocaja-v1` por `v2` en `caja-sw.js`).

## Datos y respaldo

- Los datos viven en el navegador del teléfono (`localStorage`). Nadie más los ve.
- Desde ⚙️ Ajustes se puede exportar un respaldo (JSON) e importarlo en otro
  teléfono, y exportar los movimientos a CSV para Excel.
- Si se desinstala la app o se borran los datos del navegador, se pierden: por eso
  conviene exportar respaldos cada tanto.

## Dólares

- En movimientos, pendientes y alcancías se puede elegir **$ Pesos** o **US$ Dólares**.
- La cotización es el **dólar oficial Banco Nación (venta)**, tomada de `dolarapi.com`
  (y `bluelytics` como respaldo). Se actualiza sola al abrir la app con conexión
  (como máximo una vez por hora) y se puede cargar a mano en ⚙️ Ajustes.
- Un **movimiento** en dólares queda **congelado** al TC del día en que se cargó; se muestra
  el importe en pesos y, debajo en chico, los dólares y el TC usado.
- Un **pendiente** o una **alcancía** en dólares se convierten **siempre al TC de hoy**.
  Al tildar un pendiente como cobrado/pagado, se congela al TC de ese día.
