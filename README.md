# Generador de GCP para fotogrametría

Página web de un solo archivo que, a partir de un polígono o una línea en **KML/KMZ**, distribuye automáticamente los puntos de control (GCP) y de verificación (CP) para levantamientos fotogramétricos con dron.

**Demo:** `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`

## Características

- Carga de archivos `.kml` y `.kmz` (polígono o línea).
- Coordenadas en lon/lat (estándar KML) o UTM (X/Y en metros, indicando zona y hemisferio).
- Salida en **UTM WGS84** y lat/lon.
- Dos modos de levantamiento:
  - **Polígono:** esquinas, perímetro con margen hacia adentro y relleno interior en malla hexagonal. Separación automática según la superficie o definida por el usuario.
  - **Lineal:** eje a partir de una línea (o calculado desde un polígono), con patrón alternado (zigzag) o en pares, y pares en los extremos.
- Porcentaje configurable de puntos de verificación (CP) independientes.
- Exportación a **CSV** y **KML**.
- Funciona en el navegador, sin servidor ni instalación.

## Uso

1. Abre la página y carga tu archivo KML/KMZ (o usa el botón de ejemplo).
2. Si el archivo está en UTM, indica la zona y el hemisferio (para BCS normalmente 12N).
3. Elige el modo **Polígono** o **Lineal** y ajusta los parámetros.
4. Pulsa **Generar distribución** y descarga el CSV o el KML.

## Publicar con GitHub Pages

1. Sube `index.html` a la raíz del repositorio.
2. En **Settings → Pages** elige *Deploy from a branch*, rama `main` y carpeta `/ (root)`.
3. Espera uno o dos minutos y abre la dirección que muestra GitHub.

## Notas

- No incluye mapa base. Para ver los puntos sobre imagen satelital, exporta el KML y ábrelo en Google Earth o QGIS.
- Los KMZ usan la librería [JSZip](https://stuk.github.io/jszip/) desde cdnjs; los KML funcionan sin conexión.
- La ubicación sugerida es geométrica: debe validarse en campo (suelo firme, visibilidad cenital, sin vegetación ni sombra) y moverse si el punto no es accesible.
