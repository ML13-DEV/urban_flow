
# Trabajo Práctico Integrador: Urban Flow

# Integrantes del grupo:
# - Castillo Nelson
# - Cuello Agustin
# - Lombardi Manuel
# - Rojas Agustin

## Objetivo

El objetivo principal de este proyecto es aplicar los conocimientos
adquiridos en para el versionado de código, la organización,
limpieza del código y la utilización de pandas.

## Sprint 1

La localidad llamada Vaalserberg de Bélgica se encuentra en la zona fronteriza
y limita con los paises de Países Bajos y Alemania. Esta localidad cuenta con
un sistema de radares urbanos para la detección de infracciones por exceso de velocidad.
Los registros históricos provienen de sistemas heredados, el cuál presenta errores de formato,
faltante de datos generando registros inconsistentes en el nuevo sistema.
## Sprint 2

#### Introducción y contexto del nuevo problema

Los radares urbanos generan registros administrativos de multas de forma
automática y las cámaras asociadas registran la evidencia visual que acompaña
y valida de forma visual la infracción. Sin embargo se plantean los siguientes
puntos a tener en consideración:

- No todas las multas tienen una imagen asociada.

- No todas las imágenes corresponden a una infracción.

- Puede haber errores de detección.

El objetivo actual es desarrollar un sistema que determine ¿Qué multas tienen evidencia visual válida?

Para esto vamos a necesitar los siguientes dataset:

- Dataset procesado en el sprint 1.

- [Dataset de imágenes](
https://github.com/HAD141/datasets/raw/refs/heads/main/TrabajosPracticos/urban_flow/urban_flow_plates.zip)
https://github.com/HAD141/datasets/raw/refs/heads/main/TrabajosPracticos/urban_flow/urban_flow_plates.zip

## Sprint 3

### Objetivo
Migrar la solución a una arquitectura de base de datos relacional
(SQLAlchemy) e incorporar una base de datos vectorial (ChromaDB)
para búsquedas semánticas por imagen de patente.

### Introducción y contexto
El sistema de control de infracciones de tránsito ha crecido en
volumen y complejidad. Se profesionaliza la solución con persistencia
relacional, ORM, control de versiones de datos (DVC) y búsquedas
avanzadas por similitud vectorial.
