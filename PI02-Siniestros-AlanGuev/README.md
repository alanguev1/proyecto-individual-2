# Proyecto Individual - Análisis de Siniestros Viales con Víctimas Fatales en CABA (2016-2021) 📊🚦

## Introducción ⚠️ 🚧

En el rol de Data Analyst para una consultora, he desarrollado este proyecto en respuesta a la solicitud del Observatorio de Movilidad y Seguridad Vial (OMSV), perteneciente a la Secretaría de Transporte del Gobierno de la Ciudad Autónoma de Buenos Aires (CABA).

El propósito central de este análisis de datos es proporcionar información estratégica para la toma de decisiones, dirigida a la prevención y mejora de la seguridad vial. Nos enfocamos especialmente en la reducción de siniestros viales con víctimas fatales en la Ciudad de Buenos Aires.

Las tasas de mortalidad relacionadas con siniestros viales constituyen un indicador crítico para evaluar la seguridad vial en una región. Estas tasas se calculan usualmente como el número de muertes por cada cierto número de habitantes o por cada cantidad específica de vehículos registrados. La reducción de estas tasas se erige como un objetivo fundamental para salvaguardar la vida de los ciudadanos y mejorar la seguridad en las calles de la ciudad.

Para llevar a cabo este análisis, se han utilizado datos extraídos de un dataset disponible al público que contiene información sobre víctimas fatales en siniestros viales en la Ciudad de Buenos Aires durante los años 2016-2021. Este conjunto de datos se encuentra accesible en la página oficial de CABA, y puede consultarse aquí.

# Contexto y Desafíos⚠️ 🚗
Los siniestros viales, eventos que involucran vehículos en las vías públicas, constituyen una preocupación significativa en Argentina, donde anualmente se registra un promedio de 4,000 víctimas fatales. A pesar de los esfuerzos para reducir estos incidentes, los informes del Sistema Nacional de Información Criminal (SNIC) revelan que entre 2018 y 2022 se contabilizaron 19,630 muertes a nivel nacional, promediando 11 fallecimientos diarios debido a accidentes de tránsito.

Buenos Aires, la capital y ciudad más poblada de Argentina, enfrenta desafíos particulares dada su densidad de más de 15,000 habitantes por kilómetro cuadrado. La distribución de la población en quince comunas y la alta concentración en las zonas centro y norte añaden complejidad al escenario vial.

En 2022, la ciudad experimentó 3,828 muertes fatales en siniestros viales, destacando la urgencia de abordar este problema. Sorprendentemente, los expertos señalan que la probabilidad de fallecer en un accidente vial en Argentina es dos o tres veces mayor que en incidentes delictivos.

El análisis detallado de este problema se vuelve esencial para las autoridades, ya que buscan estrategias efectivas para prevenir y reducir los siniestros viales en la ciudad. La comprensión profunda de los factores contribuyentes se convierte en la clave para desarrollar medidas de seguridad vial eficaces.

# Datos Utilizados y Procesos Analíticos ⛔📊
Para llevar a cabo este proyecto, se emplearon los datos de la Bases de Víctimas Fatales en Siniestros Viales disponibles en formato Excel, divididos en dos pestañas: HECHOS y VICTIMAS. Estas contienen información crucial, desde detalles temporales y espaciales hasta datos de participantes y víctimas, como edad, sexo y modo de desplazamiento.

En el documento adjunto, se encuentran definiciones detalladas relacionadas con los datos y el desarrollo del proyecto. Asimismo, los datos utilizados en el análisis están disponibles aquí.

Proceso de ETL (Extracción, Limpieza y Carga de Datos)
El proceso de ETL se llevó a cabo mediante la extracción y limpieza de los datos de los dos conjuntos, HECHOS y VICTIMAS, utilizando herramientas como Pandas y Jupyter Notebook. Esto incluyó la eliminación de valores nulos, duplicados y la aplicación de transformaciones necesarias, como ajustes en los tipos de datos. Los datos fueron unificados en un archivo llamado siniestros_limpio.csv, que se encuentra aquí.

Proceso de EDA (Análisis Exploratorio de Datos)
Una vez que los datos estuvieron limpios, se procedió al Análisis Exploratorio de Datos (EDA). Este proceso implica examinar las relaciones entre variables numéricas y categóricas, identificar posibles outliers o anomalías, y descubrir patrones relevantes para análisis posteriores. El desarrollo de esta fase se encuentra documentado en el archivo EDA.ipnyb.

# Análisis de los datos⛔

- Se analizan las variables numéricas del dataset su correlación por medio de una matriz, donde se encuentra una relación positiva entre las variables `Edad`y `Hora`
- La máyoria de los siniestros resultan con una víctima fatal, rara vez involucran 3 víctimas.
  
-`Análisis Temporal:` 

En el transcurso de los años, los accidentes con víctimas fatales muestran: para el período 2016-2018 una tendencia alta y estacionaria, que luego se convierte en bajista (teniendo en cuenta el comienzo de la Pandemia por COVID19 durante 2020); puede verse un pico de siniestros durante Diciembre de 2021 y se retoma la tendencia bajista.
Los meses con más victimas fatales son **Diciembre** (86) y **Agosto**(71); mientras que los días de la semana **Sábado** (114) y **Domingo** (114) tienen la mayor cantidad de víctimas.


## Análisis Demográfico y Geográfico:`

Edad de las víctimas : La distribución del rango etario de víctimas, resulta para los `Masculinos` entre 20 y 40 años; mientras que para los `Femeninos` entre 40, 60 y 80 años.

## Rango etario

El patrón de correlación Edad y Hora de las variables númericas se analiza agregando la variable Sexo, de lo que resulta la conclusión que los horarios en que los accidentes son protagonizados por Masculinos es al horario de ingreso y egreso laboral, mientras que para los Femeninos es en el horario cercano al almuerzo.

## Relacion edad hora

Utilizando la herramienta GeoPandas y extrayendo los datos de los detalles de los Barrios que conforman las 15 comunas de CABA; resulta el análisis de las coordenadas geográficas y comunas de CABA, que demostro que las comunas con más siniestos son las 1, 4 , 9, 8 y 7. 

## Tabla comuna

Los siniestros se producen en 62% de los casos en el tipo de calle `Avenida` y en el 82% de los casos se corresponden con un Cruce entre calles. Lo que resulta un patrón que se repite a lo largo de los años.

-`Análisis Participativo:`

Para el caso de la variable `Participantes` de los sinietros; se analiza a `Acusados`, como el vehículo que tiene la responsabilidad del hecho, de lo que resultan los Autos, Colectivos y Vehículos de Carga como mayores involucrados. Para el análisis de las `Victimas`, que en momento del accidente resultaban mayormente en el **Rol** de Conductor o Peatón; y el siniestro se produce en la mayoría de los casos en Motos y luego como Peaton.

### Indicadores de Rendimiento Clave KPI⛔

Una vez finalizado el Análisis Exploratorio, se utiliza el dataset resultante [Siniestros](data/siniestos_limpio.csv) y los extraidos de la página oficial de CABA con los datos de las comunas [Comunas](data/comunas.xlsx); para trabajar en la herramienta PowerBi a fin de obtener los KPI (Indicadores de Rendimiento Clave) y un `dashboard` de presentación del informe y Visualización de datos.

# KPI Propuestos

 - **Reducir en un 10% la tasa de homicidios en siniestros viales de los últimos seis meses, en CABA, en comparación con la tasa de homicidios en siniestros viales del semestre anterior**

Se define la tasa de homicidios en siniestros viales como el número de víctimas fatales en accidentes de tránsito por cada 100,000 habitantes en un área geográfica durante un período de tiempo específico. Su fórmula es: (Número de homicidios en siniestros viales / Población total) * 100,000

Número de Homicidios de Siniestros = Tomando la variable `Num víctimas` del dataset
Población Total = Tomada del Censo 2022. (Fuente:INDEC)



 - **Reducir en un 7% la cantidad de accidentes mortales de motociclistas en el último año, en CABA, respecto al año anterior**

Se define la cantidad de accidentes mortales de motociclistas en siniestros viales como el número absoluto de accidentes fatales en los que estuvieron involucradas víctimas que viajaban en moto en un determinado periodo temporal. Su fórmula para medir la evolución de los accidentes mortales con víctimas en moto es: (Número de accidentes mortales con víctimas en moto en el año anterior - Número de accidentes mortales con víctimas en moto en el año actual) / (Número de accidentes mortales con víctimas en moto en el año anterior) * 100

Cantidad de Accidentes Mortales en Moto = Tomando la variable `Victima` que se iguale a el campo [MOTO] del dataset.

# Conclusiones y Recomendaciones para la Seguridad Vial⚠️ 🚦
Tras una exhaustiva exploración de los datos y su posterior representación visual en el dashboard de PowerBi, se extraen conclusiones cruciales sobre los siniestros viales con víctimas fatales en CABA entre 2016 y 2021.

En este periodo, se lamenta la pérdida de 717 vidas debido a accidentes de tránsito. Se identificaron franjas horarias críticas, siendo las horas de ingreso laboral (5-9h), almuerzo (12-14h) y regreso a casa (17-18h) los momentos más problemáticos. Durante los fines de semana, los accidentes tienden a concentrarse en horarios de salidas nocturnas (3-7h).

Las víctimas, predominantemente masculinas (76%), se sitúan en el rango etario de 20-40 años. En los casos de víctimas masculinas, el rol de conductor es el más afectado. Las motos y peatones son los tipos de vehículos más frecuentes en siniestros, mientras que para los acusados, destacan autos, colectivos y vehículos de carga.

Los siniestros suelen ocurrir con mayor frecuencia en avenidas y cruces de calles. Se observa un patrón distintivo en relación con la edad, hora y sexo, destacando la vulnerabilidad de hombres de 20 a 40 años en las horas pico y salidas nocturnas.

Como recomendaciones, se sugiere mejorar señalizaciones y controles en avenidas, especialmente en las comunas 1 y 4 de CABA. Además, se propone la implementación de campañas preventivas focalizadas en hombres de 20 a 40 años, con el objetivo de concientizar sobre la importancia de la seguridad vial en estas franjas demográficas y horarias críticas.
