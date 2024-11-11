# Proyecto aguacate 

## Info del equipo

### Integrantes

-Elvis Ortega

-Jordi Via

-Manuel Garcia

### Planeación del proyecto

https://trello.com/b/yINYmvhD/avocado-project

## Introducción

Más que seguir al pie de la letra lo que piden los enunciados hemos intentado, con el poco conocimiento que tenemos, buscar rutas alternativas para confirmar o desmentir hipótesis que hemos estado lanzando. Estas hipótesis las iremos enunciando en las secciones correspondientes.

## Análisis de Series Temporales

En esta sección no se ha hecho un análisis detallado más allá de lo que se pide en el enunciado, pero sí que hemos comprobado comportamientos interesantes que vienen confirmados por el análisis que se hace en la sección de elasticidad.

![1](https://github.com/user-attachments/assets/f426e3db-0249-4e99-bd6d-259cbfa0a492)

Aquí se analiza el precio medio del aguacate, tanto orgánico como convencional, para todas las regiones. Es decir, todos los datos están mezclado, pero aun así vemos una variación importante en el precio alrededor del verano de 2017

![image](https://github.com/user-attachments/assets/992fb346-1eb7-4aad-9357-a59bfabda324)

Esta subida se ve reflejada si graficamos el precio medio respecto al año, pero al estar considerando un valor medio para tod el año este comportamiento temporal se ve atenuado. Aquí ya se empieza a ver la importancia de elegir cierto intervalo temporal para analizar los datos y cómo esto influye en los resultados.

## Gráficos para Visualización de Datos

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

## Análisis de Correlación y Regresión
