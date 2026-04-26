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

### Added
- Conclusión del dataset
