# Visor de infraestructura vial de Guatemala

Visor estático de los escenarios CA-02, CA-09 y CA-02 + CA-09, con resultados regionales, mapas interactivos y análisis por indicador.

## Publicar en GitHub Pages

1. Crea un repositorio en GitHub, por ejemplo `guatemala-visor`.
2. Descomprime este ZIP. Sube **el contenido de la carpeta** al repositorio: `index.html` debe quedar directamente en la raíz, junto con `app.js`, `style.css`, `leaflet.js`, `leaflet.css` y la carpeta `data`.
3. En el repositorio, abre **Settings → Pages**.
4. En **Build and deployment**, elige **Deploy from a branch**.
5. Selecciona **main** y **/ (root)**, y pulsa **Save**.
6. GitHub mostrará el enlace de publicación cuando termine el despliegue.

Si subes los archivos mediante la web de GitHub, arrastra también la carpeta `data` para conservar su estructura. GitHub no descomprime automáticamente los ZIP.

## Uso local

Desde la carpeta del visor:

```bash
python -m http.server 8000
```

Abre http://localhost:8000. No abras el HTML mediante doble clic: las consultas de datos requieren HTTP.

## Datos y cartografía

- Resultados del ejercicio vial de Guatemala: 306 observaciones regionales.
- Geometrías territoriales de Matriz2026.gdb, capa Celdas_Gra.
- CA-09 y CA-02: extracción de OpenStreetMap de Guatemala por nombres, referencias y relaciones, distribuida por Geofabrik. Se incluye la autopista a Puerto Quetzal como parte de la conexión CA-09 Sur. La cobertura depende del etiquetado de la fuente; las rutas no delimitan la intervención del modelo.
- Puertos: ubicaciones aproximadas de Puerto Quetzal, Santo Tomás de Castilla y Puerto Barrios.
- Fondo OpenStreetMap, alternativa satelital Esri y fondo vectorial regional Natural Earth.
- OpenStreetMap: © OpenStreetMap contributors, datos bajo ODbL (https://www.openstreetmap.org/copyright).
- Leaflet 1.9.4: licencia BSD-2-Clause; véase LICENSE-Leaflet.txt.

Las capas externas y Google Fonts requieren conexión a Internet. El fondo regional integrado funciona sin servicios cartográficos externos. Los valores se mantienen en su escala original, con presentación ×100 opcional. Las etiquetas interpretadas del modelo y las medias no ponderadas se explican en el visor.

## Archivos principales

- `index.html`: estructura y contenido.
- `style.css`: diseño y fondo atenuado.
- `app.js`: filtros, mapas, análisis y exportación CSV.
- `data/results.json`: resultados.
- `data/roads.json`: vías CA-09 y CA-02.
- `data/countries.json`: límites de países.
- `data/grid.json`: malla territorial.

No requiere claves API, instalación de paquetes ni compilación. Si el repositorio y GitHub Pages son públicos, los datos incluidos también serán accesibles públicamente.
