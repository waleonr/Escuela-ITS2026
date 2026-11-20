# Taller práctico: Análisis hidroclimático y evaluación del riesgo hídrico en la cuenca del río Bogotá mediante Google Colab

Escuela ITS2026 · Sesión 3 · 1 de diciembre de 2026

Ejercicio en Google Colab que usa la cuenca del río Bogotá como caso común para revisar la disponibilidad, la representatividad y el alcance de los datos de las propuestas de investigación. Combina estaciones del IDEAM, productos satelitales y de reanálisis (CHIRPS, ERA5-Land, JRC, Sentinel-2) y el marco de riesgo del IPCC AR6.

Es un solo ejercicio, organizado en secciones: cada grupo lo ejecuta, usa lo que necesita según su propuesta (con sus propios datos, si los tiene) y construye sus propios hallazgos.

**El código está en este repositorio. Los datos del IDEAM están en la carpeta de Google Drive del taller.**

## Abrir en Colab

| Notebook | Para qué | Abrir |
|---|---|---|
| `Escuela-ITS2026_prueba_earth_engine.ipynb` | Antes del taller: comprobar que su proyecto de Earth Engine funciona (5 min) | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/waleonr/Escuela-ITS2026/blob/main/notebooks/Escuela-ITS2026_prueba_earth_engine.ipynb) |
| `Escuela-ITS2026.ipynb` | El ejercicio completo: secciones 0 a 9 | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/waleonr/Escuela-ITS2026/blob/main/notebooks/Escuela-ITS2026.ipynb) |

## Antes del taller

1. Tener una cuenta de Google y un **proyecto de Earth Engine** registrado para uso no comercial (https://code.earthengine.google.com/register).
2. Abrir el notebook de prueba, escribir el ID del proyecto y ejecutarlo. Debe terminar con "Todo listo".

## Cómo usar el ejercicio

1. Descargue **`Escuela-ITS2026_datos_ideam.zip`** de la carpeta de Drive del taller.
2. Haga clic en **Abrir en Colab** (notebook `Escuela-ITS2026.ipynb`) y luego en **Archivo → Guardar una copia en Drive**.
3. Suba `Escuela-ITS2026_datos_ideam.zip` a la sesión: ícono de carpeta a la izquierda → **Subir al almacenamiento de la sesión**. También puede subir directamente los CSV que contiene.
4. En la celda **0.1** escriba el ID de su proyecto de Earth Engine y su número de grupo.
5. **Entorno de ejecución → Ejecutar todas.** La primera vez Colab pide autorizar Earth Engine.

Si olvida subir los datos, el notebook muestra un botón para subirlos. Los archivos de la sesión se borran al cerrar Colab: en cada sesión nueva hay que volver a subir el zip. Al final, el notebook descarga `Escuela-ITS2026_resultados_grupoN.zip` con todas las tablas, figuras y mapas.

## Datos (en la carpeta de Drive del taller)

| Archivo dentro de `Escuela-ITS2026_datos_ideam.zip` | Contenido |
|---|---|
| `CNE_rio_bogota.csv` | Catálogo Nacional de Estaciones, subzona río Bogotá (datos.gov.co) |
| `DHIME_PTPM_CON_*.csv` | Precipitación diaria de las 10 estaciones de referencia, 1991–2025 |
| `DHIME_TSSM_MEDIA_D_*.csv` | Temperatura media diaria de las 7 estaciones climatológicas, 1991–2025 |
| `LEEME_datos.txt` | Fuentes, fechas de descarga y condiciones de uso |

Si a una estación le falta su serie de DHIME, el notebook usa CHIRPS en esa ubicación y lo indica en la salida.

Las series se descargaron de [DHIME](http://dhime.ideam.gov.co/atencionciudadano/). Sus términos autorizan el uso personal y no comercial y no permiten redistribuirlas sin permiso escrito del IDEAM. Por eso no están en este repositorio: se comparten solo con los participantes del curso, para uso académico y citando al IDEAM.

Para usar datos propios, súbalos también a la sesión: las series de DHIME de otras estaciones de la cuenca entran solas como puntos de análisis, y un archivo `vulnerabilidad_subcuencas.csv` (columnas `subcuenca` y `valor`) reemplaza el indicador de vulnerabilidad con `VULNERABILIDAD = "archivo"`. La sección 8 del notebook explica los formatos.

## Secciones del ejercicio

| Sección | Resultado |
|---|---|
| 0 · Configuración | Parámetros, datos del taller y conexión con Earth Engine |
| 1 · Cuenca | Mapa interactivo con subcuencas, relieve y embalses |
| 2 · Inventario IDEAM | Tabla y mapa de completitud 1991–2020 |
| 3 · Precipitación y temperatura | Estación vs. CHIRPS y ERA5-Land; gradiente en °C/km |
| 4 · Variabilidad (ENOS) | Anomalías por fase; señal en estaciones vs. CHIRPS |
| 5 · Extremos y tendencias | Índices ETCCDI, Mann-Kendall, pendiente de Sen |
| 6 · Cuerpos de agua centinela | Área de Tominé, Neusa, Sisga y Guatavita (1984–hoy) |
| 7 · Índice de riesgo mínimo | Riesgo relativo por subcuenca (peligro, exposición, vulnerabilidad) |
| 8 · Su propuesta | El grupo decide qué partes del notebook usa, qué cambia y qué datos propios agrega |
| 9 · Hallazgos | Tabla de hallazgos, figura propia, lámina, matriz de alcance, nota y lista de ajustes, construidos por el grupo |

## Fuentes

IDEAM (Catálogo Nacional de Estaciones y DHIME) · CHIRPS (UCSB-CHG) · ERA5-Land (ECMWF/Copernicus) · JRC Global Surface Water · Sentinel-2 (ESA) · HydroBASINS (WWF) · Copernicus DEM · ESA WorldCover · WorldPop · WDPA · FAO GAUL · ONI (NOAA CPC).
