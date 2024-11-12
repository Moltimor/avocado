# Proyecto aguacate 

## Info del equipo

### Integrantes

- Elvis Ortega-Ochoa

- Jordi Via

- Manuel Garcia

### Planeación del proyecto

https://trello.com/b/yINYmvhD/avocado-project

## Introducción

Más que seguir al pie de la letra lo que piden los enunciados hemos intentado, con el poco conocimiento que tenemos, buscar rutas alternativas para confirmar o desmentir hipótesis que hemos estado lanzando. Estas hipótesis las iremos enunciando en las secciones correspondientes.

De acuerdo a la fuente oficial de la base de datos de avocado (Hass Avocado Board - https://hassavocadoboard.com/), la distribución es de regiones y áreas de regiones es la siguiente:

General:
‘TotalUS’

Regions:
'California' 'GreatLakes'  'Midsouth' 'Northeast' 'Plains' 'SouthCentral' 'Southeast' 'West'

Area per Regions:

Total U.S. (2024) – Northeast: 'Albany' 'Boston'  'BuffaloRochester'  'HarrisburgScranton' 'HartfordSpringfield' 'NewYork'  'NorthernNewEngland' 'Philadelphia' 'Pittsburgh' 'Syracuse'

Total U.S. (2024) – Midsouth: 'BaltimoreWashington' Charlotte' 'Louisville' 'Nashville' 'RaleighGreensboro' 'RichmondNorfolk' 'Roanoke'

Total U.S. (2024) – Southeast: 'Atlanta'  'Jacksonville' 'MiamiFtLauderdale' 'Orlando'  'SouthCarolina'  'Tampa'

Total U.S. (2024) - Great Lakes: 'Chicago' 'CincinnatiDayton' 'Columbus' 'Detroit' 'GrandRapids' 'Indianapolis'

Total U.S. (2024) – Plains: 'StLouis'

Total U.S. (2024) - South Central: 'DallasFtWorth' 'Houston' 'NewOrleansMobile'

Total U.S. (2024) – West: 'Boise' 'Denver' 'LasVegas' 'PhoenixTucson'  'Portland' 'Seattle' 'Spokane' 'WestTexNewMexico'

Total U.S. (2024) – California: 'LosAngeles' 'Sacramento' 'SanDiego' 'SanFrancisco'

## Análisis de Series Temporales

En esta sección no se ha hecho un análisis detallado más allá de lo que se pide en el enunciado, pero sí que hemos comprobado comportamientos interesantes que vienen confirmados por el análisis que se hace en la sección de elasticidad.

![1](https://github.com/user-attachments/assets/f426e3db-0249-4e99-bd6d-259cbfa0a492)

Aquí se analiza el precio medio del aguacate, tanto orgánico como convencional, para todas las regiones. Es decir, todos los datos están mezclado, pero aun así vemos una variación importante en el precio alrededor del verano de 2017

![image](https://github.com/user-attachments/assets/992fb346-1eb7-4aad-9357-a59bfabda324)

Esta subida se ve reflejada si graficamos el precio medio respecto al año, pero al estar considerando un valor medio para tod el año este comportamiento temporal se ve atenuado. Aquí ya se empieza a ver la importancia de elegir cierto intervalo temporal para analizar los datos y cómo esto influye en los resultados.

## Gráficos para Visualización de Datos

Se puede observar que hay una diferencia de volumen de ventas por región. Una de las razones es la cantidad de áreas que abarca esas regiones y consecuentemente la población total de cada región.

These estimates are based on the U.S. Census Bureau's data as of July 1, 2023 (https://www.census.gov).

California: 39,237,836

GreatLakes: 46,536,266

Midsouth: 11,481,054

Northeast: 57,159,838

Plains: 20,489,920

SouthCentral: 40,777,241

Southeast: 66,732,931

West: 78,896,805

![image](https://github.com/user-attachments/assets/e6b108dd-a646-48d6-9245-34e6370c01ce)

El precio promedio ha variado a lo largo de los años, teniendo como valor máximo en 2017 y mínimo 2016. Sin embargo, los datos muestran que la evolución del precio promedio ha sido suave.

![image](https://github.com/user-attachments/assets/cc9301c4-4510-4e1c-816c-6ad39d398fc4)

Mayoritariamente, la región de "California", "Northest", y "West", tuvo un mayor precio promedio a lo largo de los años.

![image](https://github.com/user-attachments/assets/372bc161-dd85-4ba2-b3c1-3293a05b3d72)

La frecuencia de volumen de ventas por cada una de las regiones es similar en valores bajos, pero tiende a resaltar algunas regiones ("California", "SouthCentral", y "West") cuando el volumen de ventas aumenta. Esto es coherente con la primera gráfica.

![image](https://github.com/user-attachments/assets/cd8ce721-1313-4968-ba9a-96c5e936db46)

El tipo de aguacate convencional tiene mayor volumen de ventas comparado con el orgánico.

![image](https://github.com/user-attachments/assets/54ead810-5e0f-400f-8f95-33df3ac398a9)

Las ventas de acuerdo con el tipo de bolsa van de mayor a menor, en el siguiente orden: pequeñas, grandes, y extragrandes. Este orden también es por región.

![image](https://github.com/user-attachments/assets/2801d1aa-b2e5-4f52-ac32-04b0c02d1b3e)

El precio promedio tuvo una baja en el 2016 y el pico en 2017. Con respecto al siguiente año, 2018 no tiene datos completos. Por región, la tendencia se mantiene a excepción de "Northeast", "Midsouth", y "California", donde en el 2016 el precio promedio subió a comparación del anterior año. En el caso de las otras regiones, el precio promedio bajó en comparación con el año previo.

![image](https://github.com/user-attachments/assets/4573e498-c2fd-451b-b54b-fca10b545a53)

## Elasticidad del Precio

La idea de esta sección es intentar buscar valores anómalos de la elasticidad tanto para el aguacate orgánico y convencional para todas las regiones del dataframe. Inicialmente hemos elegido hacer un análisis anual para concretar en qué año hay más variación para posteriormente hacer un análisis mensual.

Un argumento en contra de este análisis viene de que estamos eligiendo intervalos temporales muy altos. Mientras con los datos que tenemos podemos calcular elasticidades semanales hemos decidido hacer un análisis grueso anual. Esto puede eliminar comportamientos anómalos durante los años analizados pero hemos supuesto que la media es un indicador suficiente para ver comportamientos anómalos. Para poder confirmar esto tendriamos que gacer un análisis en intervalos temporales más pequeños o bien intentar contrastar este análisis con el que han hecho el resto de compañeros.

Nos hemos querido centrar en valores grandes de la elasticidad, tanto negativo como positivos, ya que según la fórmula de la elasticidad:

$E_d = \frac{\% \text{Cambio en la cantidad demandada}}{\% \text{Cambio en el precio}} = \frac{\Delta Q / Q}{\Delta P / P}$

esto vendría a decir que cambios pequeños en P, el precio del aguacate, hace que Q, la demanda, se mueva mucho. 

![image](https://github.com/user-attachments/assets/5bc7b56c-7a1f-4671-ab05-23416fd025ac)

Obtenemos este mapa de calor para el aguacate convencional, y vemos como, aunque hay valores grandes de elasticidad, los valores absolutos son mucho más pequños que lo obtenido para el aguacate orgánico:

![image](https://github.com/user-attachments/assets/1b4dcd3b-7f87-44da-8b66-abea881d98e5)

Aquí se ve una discrepancia brutal en el año 2017 entre aguacates organicos y convencionales. Mientras los convencionales más o menos mantienen elasticidad entre [-1,1], lo que quiere decir que pequeños cambios en el precio no influyen demasiado en la demanda; en los organicos, los valores que se tienen para varias regiones tienen valores muy altos. Esto quiere decir que pequeños cambios en el precio influyen muchisimo en la demanda.

Pasamos ahora a analizar la elasticidad para el aguacate orgánico en este año, para ver qué información encontramos.

![image](https://github.com/user-attachments/assets/8a06552b-0e99-4840-8664-ab56e090f1d1)

Podemos ver que en julio varias regiones tuvieron una elasticidad negativa muy grande. Esto sugiere que en esta fecha concreta, y para esas regiones, variaciones pequeñas del precio movian la demanda de manera inversa. Se podría analizar este mismo mes en otros años para ver si ese patrón continúa o ha sido una casualidad ya que si se repite podría ser una buena fecha para bajar el precio unos centimos el precio del aguacate organico ya que la demanda aumentaría mucho según se ve en la elasticidad. También, a partir de julio, vemos unos valores de elasticidad muy dispares para varias regiones. Por ejemplo, en Tampa, hay valores tanto positivos como negativos de varios miles. Durante la segunda mitad de 2017 la demanda fue mucho más susceptible a variaciones del precio.

Este artículo https://money.cnn.com/2017/09/09/news/economy/avocado-prices-soar/index.html , donde se ve que el precio del aguacate en 2017 subió un 125% ese año podría explicar la primera mitad del año, donde la elasticidad tiene valores pequeños; es decir, para cambios grandes en el precio, la demanda se mueve en esa misma proporción. Pero parece haber algún evento que, durante el verano, hace que esa variación en el precio sea muchisimo más importante para la demanda. Una posible explicación sería que los precios se estabilziasen, bajaran bastante y en consecuencia mucha gente volvió a coprar en masa al ver esas bajadas de precio. Pero habría que analizar más a fondo para poder llegar a una conclusión.

Antes de acabar también estaría bien mostrar un análisis cuatrimestral para el aguacate orgánico y ver si estas conclusiones se siguen manteniendo:

![image](https://github.com/user-attachments/assets/6b861684-dc32-4ed4-b628-df67d9a2c552)

Aquí podemos confirmar que los valores más altos de elasticidad los obtenemos de la segunda mitad de 2017, tal y como podíamos ver en el análisis mensual de 2017. Esto no hace más que confirmar que vamos por buen camino al hacer este análisis.

## Análisis de Cohortes

Se observa que, por trimestres, el precio promedio es inversamente proporcional al volumen de ventas. Mientras el precio promedio sube, el volumen de ventas baja. El pico del precio promedio se encuentra en Q3 (Julio, Agosto, y Septiembre) del 2017 y el trimestre que menos volumen de ventas se tuvo fue Q4 (Octubre, Noviembre, y Diciembre) del 2016. La dinámica no cambia mucho por regiones ni tampoco por tipo de aguacate, “conventional” y “organic”.

Noticias sobre lo que pasó en 2017 (agosto, septiembre y octubre) con la subida del aguacate: Avocado prices have soared 125% this year (https://money.cnn.com/2017/09/09/news/economy/avocado-prices-soar/index.html) Situación de Mexico durante el 2017 (https://en.wikipedia.org/wiki/2017_in_Mexico): el gasolinazo (Enero) y huracanes y terremotos (Julio a Septiembre).

![image](https://github.com/user-attachments/assets/febf3461-44a1-4f88-b7c3-96b105a03220)

![image](https://github.com/user-attachments/assets/053f9795-9553-490a-851b-dcb9e95ed496)

![image](https://github.com/user-attachments/assets/fb47eab9-17f5-4f9d-8ed2-99f1fb71d29e)

![image](https://github.com/user-attachments/assets/14bcc050-49e4-4afb-835d-f6592d1c3ce4)

![image](https://github.com/user-attachments/assets/83fafae5-96e4-4652-80fc-90b6a9a77da7)

Por tipo de bolsa se observa que el volumen de ventas ha variado durante tiempo, pero manteniendo una relación entre los tres tipos de bolsas. El tipo de bolsa que mayor variabilidad ha tenido es la pequeña.

![image](https://github.com/user-attachments/assets/81466be7-add9-497f-ab67-2db07c9ac601)

En cuanto al comportamiento de compra, considerando el promedio de volumen total de ventas la cohorte de clientes baja ha aumentado su porcentaje de compra a lo largo de los años, mientras que la mediana se ha disminuido, y la cohorte alta se ha mantenido.

![image](https://github.com/user-attachments/assets/7359b718-0724-4b66-a686-78b34954bf8d)

Las retenciones de ventas por año tienen un patrón similar, las ventas son menos al final de año a comparación que al inicio. Uno de los mayores declives fue en el año 2016. Por otro lado, los dos primeros años, 2015 y 2016, tienen un patrón similar en los meses de mayo y junio donde el porcentaje de retención tuvo una subida máxima a comparación con el primer mes del año.

![image](https://github.com/user-attachments/assets/dc8075cf-6501-4ebf-9a38-9d717522742c)

## Análisis de Correlación y Regresión
