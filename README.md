## Patrones  de distribución espacial del margen de seguridad térmica de *Danaus plexippus* (Mariposa Monarca) en Ecuador

**Autores:**  Nugra, M., Rueda, V., Tello, M., & Urbina, O.
**Objetivo:** 

- Estimar los patrones de margen de seguridad térmica de *Danaus plexippus* de manera espacial en Ecuador.

# Métodos 

Utilizamos modelamiento ecológico junto con datos extraídos de la literatura de ensayos fisiológicos de la temperatura óptima de desempeño de la especie, para visualizar los patrones espaciales de distribución de la especie que garanticen condiciones óptimas para su supervivencia.  

# Modelamiento de nicho

-Utilizamos el modelo de máxima entropía (Maxent; Phillips et al., 2006), el cual requiere de datos georreferenciados de presencia de la especie junto con variables bioclimáticas. La base de datos de presencias georreferenciadas de esta especie se obtuvieron de [GBIF](https://www.gbif.org/), [Monarch Watch](https://monarchwatch.org/) , [iNaturalist](https://www.inaturalist.org/), [Natural History Museum](https://www.nhm.ac.uk/) (London).  

-Se obtuvo un registro de 96 datos de presencias de la especie en Ecuador.

![presecia](C:\Users\Milena\Pictures\presecia.png)

-Las variables climáticas fueron obtenidas de [WorldClim](https://www.worldclim.org/bioclim) para escenarios actuales y futuros de tipo extremo a nivel mundial (versión 1.4). Fueron escogidas 19 variables bioclimáticas (bios)  para el presente (2020) y el futuro (2050) del laboratorio CCSM4 en formato ráster (.tiff) a una resolución de 30 seg (≈1 Km).  

Con el software [ArcMap](https://desktop.arcgis.com/es/arcmap/) se cortaron las bios con la capa del área geográfica de interés con la función Extrack by mask de la caja de herramientas.

- arcToolbox -> RasterTools-> Extract by mask

-Se analizó la multicolinealidad entre las variables bioclimáticas previo a la construcción del modelo en el software [MaxEnt3.3.3k ](http://www.cs.princeton.edu/~schapire/maxent/).

-De todas las variables correlacionadas (Coeficiente de correlación de Pearson; r > |0.8|), se escogió solo una variable,  debido a que fue la de mayor porcentaje de contribución al modelo de acuerdo al análisis Jackknife.

-Se usó un total de 10000 iteraciones máximas con 10 réplicas  y  se aplicó la regla de umbral de 10 percentil de presencias de entrenamiento. Finalmente, se proyectó a un escenario climático del 2050 y se escogió el modelo resultante con el mejor valor de AUC obtenido.

# Patrones del margen de seguridad térmica (MST)

En  [ArcMap](https://desktop.arcgis.com/es/arcmap/) a través de la calculadora ráster se aplicó la fórmula [MST = Topt – Thab] (Deutsch et al, 2008) para 300.000 puntos aleatorios generados sobre la capa de temperatura media anual (bio1) en el área de distribución potencial de D. plexippus donde:
-Topt es la temperatura óptima de desempeño fisiológico de la especie 
-Thab es la temperatura climática actual. 

![proximidad termica](C:\Users\Milena\Pictures\proximidad termica.png)

Los puntos con mayor valor de MST(azules) son lugares que presentan condiciones idóneas para que se desarrolle la especie. 

