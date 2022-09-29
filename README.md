# Reporte de calidad y detalle de los datos - PI03

## Análisis de calidad

Ante la posibilidad de presentar errores en los datos extraídos de FTX-API utilizados para la creación del Dashboard
del proyecto se ha realizado una verificación de la calidad de datos siguiendo las siguientes preguntas:

* ¿Se identificaron atributos perdidos y campos vacíos? Si es así, ¿los valores perdidos tienen significado?

No se detectaron atributos perdidos y campos vacíos.
 
Los datos históricos traídos de FTX-API están completos para todas las monedas desde la fecha 01-01-2022 hasta la actual con las excepciones de
las moneda ATOM/USD que trae desde 28-02-2022 y ORCA/USD que trae desde 17-08-2022. Lo anterior no se considera dentro de atributos perdidos debido
a que es realmente todo el dato histórico que se tiene de dicha moneda correspondiente a este año.

* ¿Existen faltas de ortografía que puedan causar problemas en futuras fusiones o transformaciones?

La estructura de los datos extraídos es en su totalidad numérica por lo que no presentamos faltas ortográficas que presentaran o puedan presentar problemas a futuro.

* ¿Ha considerado excluir los datos que no tengan ninguna influencia en sus hipótesis?

Si, aunque no se elimino la columna con la información de la fecha en segundos si se excluyó su uso de lo presentado en el dashboard. Los datos utilizados para la
representación del tiempo de la fecha se ha trabajado completamente a partir de la fecha dada en la columna de "Start Time".

* ¿Los datos están almacenados en archivos planos? Si es así, ¿los delimitadores mantienen la coherencia entre los archivos? ¿Contiene cada registro el mismo
número de campos?

Los datos son extraídos a través de una conexión directa con FTX-API y esos datos extraídos fueron limpiados y reorganizado para que todos las tablas tuvieran los mismo
numero de campos y un mismo orden. 

## Tipo de datos utilizados

1. Los datos utilizados para la representación del gráfico de velas son: 
    * En el eje X tenemos la fecha presente en la columna "Start Time".
    * Para la representación de las velas utilizamos los valores de las columnas "Precio de Apertura", "Precio de cierre", "Pico mas alto", "Pico mas bajo", que como su nombre lo indica 
    son los diferentes valores de la moneda tomo durante el día.
    * Se adicionaron a la gráfica otras tres (3) líneas de tendencias para mayor ilustración del comportamiento. Estas líneas de tendencias son generada con medidas calculadas
     que son "Media móvil de 3 meses precio de cierre", "Media móvil de 7 días precio de cierre" y "Precio de cierre average"
 
2. Los datos utilizados en la gráfica de área para representar el volumen de transacciones de cada moneda son:
    * En el eje X tenemos la fecha presente en la columna "Start Time".
    * En el eje Y tenemos los datos de la columna "Volumen de Transacciones", que es la cantidad de transacciones (compra y venta) que se presentaron visto por moneda en el día.

3. En las cuatro (4) tarjetas utilizadas para ilustrar datos característicos de cada moneda tenemos: 
    * Medida calculada "Precio de cierre variance"
    * Valor mínimo de la columna "Pico mas Bajo"
    * Valor máximo de la columna "Pico mas alto"
    * Valor promedio de la columna "Volumen de Transacciones"

4. En las dos (2) tarjetas utilizadas para ilustrar los resultados de cálculos entre monedas son:
    * Medida calculada "Coin to USD"
    * Medida calculada "USD to Coin"

## Link a Dashboard
https://app.powerbi.com/view?r=eyJrIjoiNGI4ZmIxNWYtZjIwMy00YWRhLTllNzQtNjMxOGI2N2JjMzQ2IiwidCI6ImJhYjBiNjc5LWJkNWYtNGZlOC1iNTE2LWM2YjhiMzE3Yzc4MiIsImMiOjR9
