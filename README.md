### periodismo_datos
Periodismo y ciclo de vida de los datos: repositorio del reportaje periodístico

# Tendencia política española en épocas de crisis: ¿la economía condiciona el voto?

## Tema:

Durante los últimos años (y no tan últimos) se han vivido en España una serie de bajones en la economía, así como algunas leves recuperaciones. Durante estas épocas se ha observado una tendencia de voto hacia la izquierda o la derecha. Sería interesante ver cómo las crisis económicas condicionan a la población a votar ciertas ideologías políticas u otras. 


## Hipótesis:

En general siempre se dice que en épocas de crisis todos miramos el bolsillo, nuestro bolsillo. Por tanto, se ha dicho que en malos momentos en la economía se tiende a las políticas de derechas. La hipótesis es verificar o refutar esta teoría económico-social de tendencia de voto, comparando datos económicos de España en los últimos 40 años (des del inicio de la democracia española) y viendo las tendencias del voto en esta misma época. 
Así veremos si realmente en las crisis económicas fuertes la población se decanta por los partidos de derechas o no, y el porqué.


## Estilo:

Este artículo es periodismo económico y social, ya que pretendemos demostrar que la economía y la política están estrechamente relacionadas, y que la economía afecta a las decisiones políticas de la sociedad. Para hacer esta demostración, necesitamos datos históricos que nos respalden y hacer una comparativa fiable entre indicadores económicos y tendencias de votos, así como resultados electorales. 

 
## Fuentes de información y métodos de búsqueda:

### DATOS ECONÓMICOS:


- https://www.ine.es/

Para dictaminar si hay o no una crisis económica, deberemos fijarnos en los indicadores de consumo de la población y también en el desempleo. Estos datos los podemos encontrar en el INE (Instituto Nacional de Estadística). 
A priori, se han encontrado datos en formatos procesables (excel, csv, etc) de los años 2002 al 2018 (17 años). Los datos históricos se encuentran en formatos no procesables de forma automatizada (pdf) y requerirán de más tiempo para ser cargados y analizados.


Resultados/PIB a precios de mercado:

Datos económicos de España: aquí podemos encontrar el PIB centrándonos en los consumidores (demanda, oferta y rentas). 
Para localizar las épocas de crisis tendremos en cuenta que estos datos siguen un patrón: la demanda baja, la oferta y las rentas también bajan (constricción de la economía).


Resultados trimestrales/Parados:

Datos poblacionales del paro por grupo de edad, sexo y comunidad autónoma. A mayor paro, menor consumo. El paro es un indicador del ralentizamiento de la economía, por tanto un indicador de períodos de crisis económica.


Si queremos analizar la evolución económica por comunidad autónoma y si hay variación en el resultado electoral entre los resultados estatales y el voto particular de cada comunidad (dentro de las elecciones generales) en función de cómo afecta el impacto económico en cada comunidad por separado, deberíamos tener en cuenta los datos con detalle de comunidad autónoma.
Para los datos del INE, podemos encontrar el detalle de comunidad autónoma en los mismos enlaces. Aunque deberemos tener en cuenta que en referencia al PIB no tendremos el detalle de demanda/oferta/rentas, sino que tendremos el valor del PIB ya calculado por comunidad. A efectos prácticos es lo mismo, simplemente que no tendremos una explicación con datos del valor del PIB, sino que lo obtendremos ya calculado. 
Para los datos del paro, tenemos el detalle por comunidad autónoma en el mismo apartado que hemos descrito anteriormente.


https://datosmacro.expansion.com/pib/espana

Aquí tendríamos los datos del PIB y del paro también en diferentes períodos. 

Trabajando más profundamente los orígenes de datos, localizamos más concretamente los datos base con los que trabajar. Por temas de disponibilidad de información y fechas, es complicado utilizar una sola fuente. Así pues se ha creado un archivo de texto para indicar exactamente las URLs donde encontramos los datos respecto al PIB y el paro en los períodos indicados:

- PIB - nivel estatal: 1971 - 2017
- PIB - nivel CCAA: 1980 - 2017
- PIB por componentes - nivel estatal: 1995 - 2017 (estos datos complementarán el PIB a nivel estatal en los años disponibles)
- Paro - nivel estatal y por CCAA: 1976 - 2017

El fichero con las URLs que trabajaremos se encuentra en el repositorio bajo el nombre de "urls datos - PIB y PARO".


### RESULTADOS ELECTORALES:

El siguiente punto es ver los resultados electorales. Estos datos los podremos encontrar en la web del Ministerio de Interior que tiene los resultados electorales des de 1976:

- http://www.infoelectoral.mir.es/min/

En este enlace deberemos seleccionar los datos de la elecciones al Congreso, utilizando los filtros que la propia web facilita llegaremos a la información. Mediante el selector de fecha podremos acceder a los resultados de cada una de las elecciones realizadas en España des de 1977.

Para obtener el detalle de cada comunidad autónoma, deberemos seleccionar las elecciones al Congreso y ver cómo ha votado cada comunidad (seleccionándola en el selector apropiado). Así veremos que aunque el resultado general sea hacia un partido, quizás alguna counidad autónoma despunte hacia una intención de voto distinta que otra debido a sus variables económicas. 



# PEC3 - HILO ARGUMENTAL


### Obtención de Datos

Se empieza por obtener los datos de las fuentes mendionadas anteriormente. Después del proceso de obtención, acabamos con múltiples ficheros excel que deberemos procesar para tener algo legible y utilizable en un entorno de análisis.

El procesado de ficheros se ha realizdo en parte de forma manual en el propio excel (eliminando filas que sobrabas y otroa campos que no aportan valor) y también mediante procesos ETL utilizando la herramienta Kettle (Pentaho).

En el repositorio incluímos los ficheros obtenidos directamente de orígen : "ORIGENES_DATOS_EN_CRUDO.rar"

Y también los ficheros obtenidos tras el procesado, aquellos que cargaremos en nuestra herramienta de visualización y con los que construiremos el modelo de datos que nos permitirá realizar los análisis: "DATOS_PROCESADOS.rar"


### Algunos Análisis

Como herramienta de análisis de datos vamos a utilizar Tableau, que además de ser un software muy potente creado para el Data Science, también tiene versiones gratuitas para estudiantes. En el fichero "ANALISIS_DATOS" se encuentran los análisis realizados en la herramienta, bajo el siguiente proceso:

1 - Carga de datos de los archivos .csv procesados a partir de los datos en crudo obtenidos de las URLs
2 - Creación del modelo que nos permite realizar los análisis 
3 - Creación de análisis de datos (gráficos) que nos ayudan a entender los datos y aportan valor añadido

Los archivos de imagen son las exportaciones desde Tableau de los gráficos generados. Analizamos los resultados y prepararemos un esbozo del discurso incluyendo los gráficos generados en un archivo pdf y word: "HILO_ARGUMENTAL"




