# CHANGELOG

## [Día 1] - 2026-04-23

### Añadido
- Estructura de directorios creada
- Creación del archivo `README.md` con la descripción del Sprint 1.
- Configuración inicial de Git y vinculación con el repositorio remoto.
- Implementación del archivo `CHANGELOG.md` con acciones realizadas.

## [Día 2] - 2026-04-23

### Añadido
- Creación y cambio a la rama de Sprint_1.
- Descarga del dataset raw original y almacenado en `urban_flow/data/raw`.
- Muestra de las 5 primeras filas.
- Análisis de tipos de datos
- Contar los valores nulos.

## [Día 3] - 2026-04-23

### Añadido
- Normalización de fechas a formato 'YYYY-MM-DD', reemplazando fechas
  inválidas por `1932-01-01`.

- Normalización de horas a formato 24 hs, reemplazando valores
  inválidos por `00:00`.

- Normalización de ubicaciones: eliminación de caracteres especiales
  y conversión a mayúsculas.

- Eliminación de filas con valores relevantes para las multas que
  se encuentran vacías.

- Detección y eliminación de outliers.

- Creación de la columna `exceso_velocidad_real` y su cálculo.

- Creación de la columna `exceso_velocidad` y su cálculo.

- Eliminación de filas sin infracciones según el exceso de velocidad.

- Guardado del dataset limpio en
  `urban_flow/data/interim/speeding_fines.csv`.csv`

## [Día 4] - 2026-04-23

### Añadido
- Definición de clase FineAnalyzer
- Prueba de métodos de la clase FineAnalyzer

## [Día 5] - 2026-04-23

### Añadido
- Gráfico de patentes
- Gráfico de horas
- Gráfico de meses
- Gráfico de horas medianoche
- Gráfico de fecha medianoche

## [Día 6] - 2026-04-23

### Añadido
- Cálculo de porcentaje de infracciones en la fecha 1932-01-01
- Cálculo de porcentaje de infracciones a la hora 00:00

## [Día 7] - 2026-04-23

### Añadido
- Conclusión del dataset
# Sprint 2

## Día 1

### Añadido
- Creación de la rama 'Sprint_2' y cambio a la misma
- Descarga del dataset de imágenese de patentes y almacenado
en 'urban_flow/data/raw/imgs'

## Día 2

### Añadido
- Clasificaión de imágenes según el tipo de imagen y
almacenado en json urban_flow/data/interim/group_images.json.
- Creación de la función mostrar_reporte_imagenes para mostrar 4 imágenes
aleatorias de ambas categorías en una matriz de 4x2.
## Día 3

### Añadido
- Conversión a escala de grises de las imágenes originales y
almacenado en
'urban_flow/data/interim/imgs/03_01_gray_scale/plates' y
'urban_flow/data/interim/imgs/03_01_gray_scale/completes',
según la clasificación previa.
- Suavizado de las imágenes en escala de grises y almacenamiento en
'urban_flow/data/interim/imgs/03_02_blur' según la clasificación previa.
- Detección de bordes sobre las imágenes suavizadas para intentar detectar
las patentes y almacenado en
'urban_flow/data/interim/imgs/03_03_canny' según la clasificación previa.

## Día 4

### Añadido
- Definción de la función extraer_patente para extraer las patentes de las imágenes.
- Definción de la función vincular_imagenes_multas para vincular las patentes
extraídas con los registros existentes.
- Definición de nuevas columnas 'imagen', 'patente_imagen' y 'ratio' en el
dataframe de multas.
- Guardado del archivo final en la carpeta processed.

## Día 5

### Añadido
- Cálculo de métricas del dataset final.
