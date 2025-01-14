
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


***Convertir datos categoricos***

Los datos categoricos poseen un tipo y naturaleza, los tipos principales son:
1. Nominales: No poseen un orden o clasificacion, es decir siguen una secuencia o clasificación ej: Genero, color.
    Solo son adecuados para la moda

2. Ordinales: Poseen un orden o clasificacion claros, ej: Tamano, clasificacion o nivel.
    Pueden permitir el uso de mediana o la moda como medidas de tendencia central


> [!TIP] Regla práctica para decidir
>
> Preguntarse:
> ***¿Tiene sentido establecer un orden natural entre las categorías en este contexto?***
> Si NO → Es nominal.
> Si SÍ → Es ordinal.
> Si no se esta analizando ninguna jerarquia explícita entre las categorías, lo más adecuado sería considerarlas nominales. 


Segun el tipo de datos categorico, se asigna un encode, para

- Nominales -> Dummy variables (One-Hot Encoding), EJ: Color (Rojo, Azul, Verde) => (1,0,0),(0,1,0)(0,0,1)
- Ordinales -> codificación de etiquetas (Label enconding) para preservar el orden, EJ: Nivel (Alto, medio, bajo) => 0,1,2

> [!WARNING]  
> ***One-Hot*** puede ser simple y efectiva, pero se puede crear una gran cantidad de caracteristicas y aumentar la dimensionalidad de los datos
>  Lo que puede traer problemas como *el sobreajustes*,  *la dispersión* y *la complejidad computacional*.
> ***Label encoding*** Puede introducir una falsa sensacion de magnitud (distancia entre categorias) tener precaucion y aplicar técnicas de escalado o normalización si es necesario.


"Existen otros métodos para convertir datos categóricos en datos numéricos, como la codificación binaria, la codificación de frecuencia, la codificación de destino o la incrustación. "

*** ¿ Por que es importante transformarlas ? ***
La mayoria de los modelos estadisticos y algoritmos de aprendizaje estan disenados para trabajar con datos numericos.


**Variables categóricas en modelado estadístico**

1. Regresión: Se necesitan transformar usualmente a one-hot para la regresion lineal
2. Clasificacion: Se usand los datos categoricos para dividir los datos en clases distintas
3. Análisis de serie de tiempo: Pueden ayudar a segmentar los datos o actuar como parte del conjunto de caracteristicas.
4. Análisis de conglomerados: Agrupar entidades similares y el manejo afecta la clusterizacion.


***¿Por qué las variables categóricas son cruciales en la ciencia de datos?***
 Las variables categóricas son esenciales para problemas de clasificación, reconocimiento de patrones y para proporcionar información matizada en diversos contextos analíticos, desde estadísticas descriptivas hasta modelos avanzados de aprendizaje automático.


 *** Cuando transformar los datos categoricos? ***
 1. Se desee usar modelos de aprendizaje automatico
 2. Se desea reducir la complejidad: Categorias redundantes o demasiado niveles
 3. Preparacion para visualizacion o metricas: En formato numerico es mas sencillo de visualizas.




