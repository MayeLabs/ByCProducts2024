
![Badge en Desarollo](https://img.shields.io/badge/STATUS-EN%20DESAROLLO-green)
 
# Índice

1. [Entendiendo Conceptos](#entendiendo) - Desviación Estandar
--- 

# Entendiendo Conceptos
### Desviación Estandar
### Percentiles
## preprocesamiento
### Limpieza de datos


## Desviación Estandar

Es una medida que nos ayuda a ver que tan dispersos los datos de la media(promedio), responde a: Cuanto varian los datos respecto a la media ?

Como interpretarla:  

1. Si es baja, entonces los valores estan muy cerca de la media, los datos son consistentes
2. Si es alta; Los valores estaran mas dispersos, hay mas variabilidad

Como usarlos en el analisis ?

1. Consistencia o variabilidad  
    Al haber variabilidad se puede usar para ver que es lo que lo produce, en este dataset
    puedo observar si la variabilidad de precios se basa en la marca

2. Detectar valores atipicos
    Un valor atipico es un valor que se encuentra muy alejado del resto, esta mas lejos de la media que 
    otros valores, en otras palabras quiere decir que no siguen la tendencia general de los datos

    Un valor se considera atipico, cuando esta 3 desviaciones estandar de la media, ya sea por encima o por debajo

    Como diferencio el minimo de valores atipicos ?

        Un valor atipico puede no ser precisamente el valor minimo de los datos, sino un valor que
        se encuentre fuera del rango esperado de los datos ya sean por encima o por debajo de la media

        El minimo es un valor mas bajo del conjunto de los datos, puede o no ser un valor atipicos dependiendo
        de la distribucion de los datos

        Como se como detectarlos los valores atipicos ?

            Un valor minimo puede ser un valor atipico si esta por debajo de media - 3 * desviacion_estandar

            Un valor maximo puede ser un valor atipico si esta por encima de media + 3 * desviacion_estandar



3. Comparar columnas
    El objetivo es ver la variabilidad entre diferentes columnas, para ver si siguen patrones similares



Como saber que tan grande o pequenha es, se hace a traves de la proporcion de la desviacion estandar con respecto a la media, la idea es comparar la desviacion estandar con la media se puede hacer uso de:

Calculo del porcentaje Relativo

Porcentaje relativo = (Desviacion estandar/Media) * 100

Si es pequenho sera < 10 %
Si es alto sera > 30 %

OJO -> Se debe tomar en cuenta el contexto del dato para una mejor interpretacion


## Percentiles - Cuartiles

Dividen el conjunto de datos en 100 partes iguales mientras los cuartiles dividen los datos en 4 partes iguales

1. Primer cuartil (Q1): El valor por debajo del cual esta el 25% de los datos
2. Segundo cuartil (Q2): Es la mediana que divide los datos en dos mitades 
3. Tercer cuartil (Q3): Es el valor por debajo del cual esta el 75%

Ejemplo:

Tenemos

[1, 2, 3, 4, 5, 5, 6, 7, 8, 9 , 10]

El Q1 seria el valor en 25% de los datos seria 3
El Q2 seria el que esta en el 50% de los datos seria 5
El Q3 seria el valor en el 75% 8

Los percentiles seran mas especificos, 10%, 20% y 30%

Que se puede hacer con ello ?

1. Identificar la dispersion de los datos, como se que encuentran distribuidos, ejemplo
    la mayoria de los datos esta entre que quartiles
2. Detectar valores atipicos, ya que se podria observar si hay un valor mas lejos de los cuartiles
2. Hacer una visualizacion usando el diagrama caja de bigotes o boxplot visualizando mejor la distribucion

## preprocesamiento
### Limpieza de datos
### Verificar valores únicos en columnas categóricas

**Columnas categóricas**

Son los que representar diferentes categorias o grupos, es decir hay un conjunto limitado de estos y no posee un significado matematico, como precio o cantidad

***Como diferenciarlos:***

*Categóricas*
- Valores discretos
- No poseen un significado matematico directo 

*No categóricas*
* Valores numericos continuos u ordinales
* Valores que representen magnitudes


>[!NOTE]
>
> El objetivo es normalizar los valores categoricos y evitar problemas identificando:
>
> 1. Posibles inconsistencias, viendo si hay irregularidades 
> 2. Errores tipograficos
> 3. Categorias innecesarias
