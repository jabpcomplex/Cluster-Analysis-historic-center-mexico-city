# Clasificación geodemográfica del Centro Histórico de la CDMX mediante análisis de clusters

Para el Análisis de agrupamiento utilizamos las siguientes bases:

Datos públicos sociodemográficos del INEGI.

Información pública del Directorio Estadístico Nacional de Unidades Económicas (DENUE).

Datos sobre disturbios reportados al 911 (C5)

El periodo de análisis comprende los años 2019 a 2022. El ámbito geográfico es a nivel Manzanas para los perímetros A y B del Centro Histórico de la  Ciudad de México (CDMX).

METODOLOGIA:

Imputamos valores nulos o sin información de la base de Datos públicos del INEGI. Dicho proceso se realizó por el método de imputación conocido como los k- vecinos más cercanos en su versión ponderada, es decir, el valor imputado se toma al promediar el número k de observaciones más cercanas al valor  imputado, ponderado por  la distancia a cada punto y se obtuvo la base base_IMPUTADA_kNN.csv

1. Creación de la variable de OPORTUNIDAD [1] Dicha variable se logro al identificar las manzanas que presentaron reportes de desorden social y fisico reportadas al 911. 

2. Creación de las variables relacionadas con la base DENUE 2020. COMERCIO, ESCUELA,MANUFACTURA, SERVICIOS, SERVICIOS PRIVADOS, TRANSPORTES, VENTA DE ALCOHOL, RESTAURANTES.

3. Análisis de Componentes Principales por sus siglas en ingles PCA sobre la base de INEGI. Para extraer las variables más cercanamente relacionadas con los tres primeros componentes principales.

4. Elección del algoritmo de clustering: utilizaremos el método de k-means y k-medoids de R-studio.

5 . Elección de la métrica de distancia:  La métrica utilizada será la distancia euclidiana para k-means y manhattan en k-medoids

6. Elección del número de clusters por medio del método del codo

7. Asignación de objetos a clusters: agrupación en k-clusters.

8. Clasificaciones geo-demográfica derivado del análisis de clusters.

## Clusters por el método de k-means
![image](https://github.com/jabpcomplex/Cluster-Analysis-historic-center-mexico-city/assets/86539158/23b75012-6fab-443f-ad06-da8c850a1182)

## Clusters por el método de k-medoids
![image](https://github.com/jabpcomplex/Cluster-Analysis-historic-center-mexico-city/assets/86539158/49ba9c84-4cd1-49bf-a9e7-e2e25bba6f4f)

# RESULTADOS

Cluster 1: Periferia urbana I

Este cluster presenta los mayores porcentajes en cuanto a la media poblacional por manzana, es decir, están densamente poblados. También presentan los mayores porcentajes en la población económicamente activa y población ocupada tanto para hombres y mujeres entre los 4 clusters. 

Esta población vive en viviendas particulares habitadas de cualquier clase (casa única en el terreno, departamento en edificio, vivienda o cuarto en vecindad, etc.) y que no disponen de automóvil o camioneta ni motocicleta o motoneta. Dichos espacios son predominantemente utilizados para la vivienda, por ende tienen menores porcentajes en cuanto a las variables de unidades económicas entre los 4 clusters. Su localización geográfica es principalmente en los extremos del perímetro B.

De todos los clusters el cluster 1 tiene la mayor población de creencia o preferencia espiritual la religión católica con cierta presencia de personas que hablan alguna lengua indígena. También tienen los mayores números en cuanto hogares censales donde la persona de referencia es mujer. Y contiene a la población  que en promedio tiene mayores estudios de los 4 clusters.

En términos de la variable de OPORTUNIDAD  los 4 clusters  tienen valores similares, es decir, la oportunidad criminal es homogénea en los perímetros A y B. Sin embargo si agrupamos el cluster 1 con 4 y 3 con 2, entonces el cluster 1 y 4 presentan en promedio mayores oportunidades para que los criminales cometan delitos por la presencia de desorden social y físico. 

Cluster 2: Zonas Comerciales (Tipo I)

Este cluster presenta los menores porcentajes en cuanto a la media poblacional por manzana, es decir, son las menos densamente poblados. También presenta los menores porcentajes en la población económicamente activa y población ocupada tanto para hombres y mujeres.

Tienen los menores números en cuanto a población de religión católica  y personas en hogares censales donde la persona de referencia es mujer. Y contiene a la población  que en promedio tiene los menores estudios de todos los clusters. Su localización geográfica se encuentra en la mayor parte del perímetro A y en los extremos del perímetro B. Tienen los menores porcentaje en cuanto hogares censales donde la persona de referencia es mujer. La mayor parte del Perimetro A y B pertenece a este cluster con 121 objetos y 238 respectivamente.


Las manzanas del cluster 2 son principalmente para uso comercial por lo tanto tienen los mayores porcentajes en las variables asociadas a las unidades económicas, principalmente COMERCIO, MANUFACTURA, SERVICIOS_PRIVADOS , TRANSPORTE y VENTA DE ALCOHOL.

La variable de OPORTUNIDAD para el cluster 2 y 3 juntos, presentan en promedio menores oportunidades para que los criminales cometan delitos por la presencia de desorden social y físico.

Cluster 3: Zonas Comerciales (Tipo 2)

Este cluster es 5 veces mas densamente poblado por manzana que el cluster 2 y representa muy bien la media poblacional por manzana de toda la ciudad que es de 192.2462 hab/mza. También presenta los menores porcentajes en la población económicamente activa y población ocupada de las 2 “Zonas Comerciales”.

La población del cluster 3 se caracteriza por tener los mayores porcentajes promedio en cuanto de ocupantes por cuarto en viviendas particulares habitadas. 

Las manzanas del cluster 3 son principalmente para uso comercial por lo tanto tienen los mayores porcentajes en las variables asociadas a las unidades económicas que el cluster 1 y 4 pero menores que el cluster 3; por ejemplo este cluster presenta porcentajes menores  al cluster 2, en las variables COMERCIO, MANUFACTURA, SERVICIOS_PRIVADOS , TRANSPORTE y VENTA DE ALCOHOL y solo mayores porcentajes para la variable de SEVICIOS.

La variable de OPORTUNIDAD para cluster el 2 y 3 juntos, presentan en promedio menores oportunidades para que los criminales cometan delitos por la presencia de desorden social y físico.

Cluster 4: Periferia urbana II

Las manzanas del cluster 4 son principalmente hogares censales por lo tanto presenta los porcentajes por encima del promeido en cuanto a la media poblacional por manzana pero menores que el cluster 1, y por encima de la media poblacional. Las manzanas que pertenecen al cluster 4 presentan porcentajes por encima del promedio en la población económicamente activa y población ocupada tanto para hombres y mujeres. 

Sin embargo dichos espacios no solo son para la vivienda, presentan mayores porcentajes mayores en promedio en cuanto a unidades económicas con respecto al cluster 1. Y se encuentran en la periferia del perímetro A y B.

En términos de la variable de OPORTUNIDAD el cluster 1 y 4 juntos, presentan en promedio mayores oportunidades de desorden social y físico para la población.

El general el cluster 4 presenta porcentajes menores en todas sus variables asociadas con respecto al cluster 1.

