# CONCLUSIÓN DEL DATASET

Se observa que el dataset original posee más de 1800 filas con valores
faltantes, lo cual indica inconsistencias en el almacenamiento de la
información, ya sea por el sistema o por la persona encargada de cargar
los datos.

Las columnas de patente, fecha y hora presentan errores de
normalización y algunas filas no contienen información. En la columna
patente se observan valores con espacios adicionales, caracteres
especiales o directamente faltantes.

En la columna fecha se identifican distintos formatos y filas con
'invalid_date', lo que indica la ausencia del registro en ese día. En la
columna hora hay filas con formato AM/PM, mientras que otras solo
contienen la hora o 'invalid_hour', evidenciando inconsistencias en la
carga de datos.

Se detectan 1957 velocidades no registradas (nulas) en la columna
'velocidad_registrada', lo que afecta el proceso de cobro de multas, ya
que no se conoce la velocidad del vehículo. En la columna 'radar_id' hay
1002 filas nulas que impiden identificar qué radar capturó la
infracción.

En la columna 'estado_multa' se observan varias filas con el valor
'ERROR', lo que evidencia otra falla en el registro de la información.

Luego de normalizar los valores erróneos y eliminar aquellos sin datos,
el dataset se reduce a menos del 50% de las filas originales, lo que
obliga a realizar un análisis con una gran cantidad de información
faltante.

Además, se observa que el mes 1 (enero) se convierte en un outlier,
representando un 19.61% del total de multas. De igual forma, el año
1932 también se presenta como outlier, concentrando un 26.42% de las
multas.
