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
A partir del análisis del dataset, se observa una falta de información importante
al contar con solo 108 imágenes para un universo de más de 1800 registros de infracciones.
Sin embargo, un hallazgo clave es que este grupo reducido de fotos concentra la actividad de
apenas 19 vehículos particulares, identificados como los mayores infractores.
Tras procesar la información mediante la función de extracción de patentes,
se logró un impacto significativo al asociar una identificación vehicular al 41,01% del total de
las multas registradas, quedando un 58,99% restante sin resolver debido a la limitación del
material fotográfico de origen. Finalmente, cruzando estos resultados con el estado financiero del
sistema, se detectó que el 75,05% de las multas totales se encuentran pendientes de pago debido a
apelaciones, errores o deuda, gracias al proceso de reconocimiento implementado, se logró
recuperar la identidad del 30,61% de este grupo de infractores,lo que permite
localizar de forma directa a los responsables y efectivizar el cobro de la deuda.
