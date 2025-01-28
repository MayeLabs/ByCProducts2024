
![Badge en Desarollo](https://img.shields.io/badge/STATUS-EN%20DESAROLLO-green)
 

# Índice

### [Entendiendo conceptos](#entendiendo-conceptos)  


[Estadística descriptiva - Dada por df.describe()](#estadística-descriptiva)

- [Desviación Estandar](#desviación-estandar)  
    - Como interpretarla
- [Percentiles - Cuartiles](#percentiles---cuartiles)
    - ¿ Que se puede obtener de los cuartiles ?    

[Preprocesamiento](#preprocesamiento)

[Análisis exploratorio de datos (EDA) ](#análisis-exploratorio-de-datos(eda))
- [Tipos de EDA](#tipos-de-eda)


# Entendiendo Conceptos

## Estadística descriptiva
La estadística descriptiva se obtiene de la inspeccion inicial, donde df.describe() es uno de los protagonistas, aunque al visualizar los valores dados no se usan para obtener conclusionessi muestra un abreboca de los datos del dataset, acontinuacion conceptos y como interpretar lo obtenido de df.describe()

### ***Desviación Estandar***

Es una medida que nos ayuda a ver que tan dispersos estan los datos de la media(promedio), respondiendo a: 

> **¿ Cuanto varian los datos respecto a la media ?**

*Como interpretarla:*  

1. Si es baja -> Los valores estan muy cerca de la media.  
    Los datos son consistentes
2. Si es alta -> Los valores estaran mas dispersos.  
    Hay mas variabilidad

**¿ Como usarla en el analisis ?**

1. *Consistencia o variabilidad*
    Al haber variabilidad se podria usar para observar que es lo que la produce.  
    Ej: Observar si la variabilidad de los precios se basa en la marca  

2. *Detectar valores atipicos*
    Un valor atipico: Es un valor que se encuentra muy alejado del resto,es decir, esta mas lejos de la media en comparacion de otros valores. 
    > No siguen la tendencia general de los datos  

    **¿ Como diferencio el minimo de valores atipicos ?**

    Un valor atipico puede no ser precisamente el valor minimo de los datos, sino un valor que se encuentre fuera del rango esperado de los datos ya sean por encima o por debajo de la media.


    > El minimo es un valor mas bajo del conjunto de los datos, **puede o no ser un valor atipico** dependiendo de la distribucion de los datos

    *¿ cuando se considera y como detectar valores atipicos ?*

    Se considera  valor atipico cuando esta a 3 desviaciones estandar de la media, ya sea por encima o por debajo.

    Un valor minimo puede ser un valor atipico si esta por debajo de media - 3 * desviacion_estandar

    Un valor maximo puede ser un valor atipico si esta por encima de media + 3 * desviacion_estandar

3. *Comparar columnas*  
    El objetivo es ver la variabilidad entre diferentes columnas, para visualizar si siguen patrones similares

Como saber que tan grande o pequenha es, se hace a traves de la proporcion de la desviacion estandar con respecto a la media, la idea es comparar la desviacion estandar con la media se puede hacer uso de:

> [!NOTE]  
> *Calculo del porcentaje Relativo*
>
> Porcentaje relativo = (Desviacion estandar/Media) * 100
>
> Si es pequenho sera < 10 %  
> Si es alto sera > 30 %
> 
> :eyes: :heavy_exclamation_mark:
>> Se debe tomar en cuenta el contexto del dato para una mejor interpretacion  


### Percentiles - Cuartiles

Los percentiles dividen el conjunto de datos en 100 partes iguales mientras los cuartiles dividen los datos en 4 partes iguales:

1. Primer cuartil (Q1): El valor por debajo del cual esta el 25% de los datos
2. Segundo cuartil (Q2): Es la mediana que divide los datos en dos mitades 
3. Tercer cuartil (Q3): Es el valor por debajo del cual esta el 75%

_________________
**Ejemplo**   
Tenemos:  
[1, 2, 3, 4, 5, 5, 6, 7, 8, 9 , 10]

- El Q1 seria el valor en 25% de los datos seria 3
- El Q2 seria el que esta en el 50% de los datos seria 5
- El Q3 seria el valor en el 75% 8
_________________

> Los percentiles seran mas especificos, 10%, 20% y 30%
>  

**¿ Que se puede obtener de los cuartiles ?**

1. Identificar la dispersion de los datos, respondiendo a como se que encuentran distribuidos, ejemplo:  
    La mayoria de los datos entre que quartiles estan

2. Detectar valores atipicos, Observando si hay un valor mas lejos de los cuartiles
2. Hacer una visualizacion usando el diagrama caja de bigotes o boxplot para observar la distribucion

## Preprocesamiento

### Limpieza de datos
### Verificar valores únicos en columnas categóricas
### Normalización de texto

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


#### ***Convertir datos categoricos***

Los datos categoricos poseen un tipo y naturaleza, los tipos principales son:
1. Nominales: No poseen un orden o clasificacion, es decir siguen una secuencia o clasificación ej: Genero, color.
    Solo son adecuados para la moda

2. Ordinales: Poseen un orden o clasificacion claros, ej: Tamano, clasificacion o nivel.
    Pueden permitir el uso de mediana o la moda como medidas de tendencia central


> [!TIP]
> Regla práctica para decidir
>
> Preguntarse:
> ***¿Tiene sentido establecer un orden natural entre las categorías en este contexto?***
> - Si NO → Es nominal.
> - Si SÍ → Es ordinal.
> 
> Si no se esta analizando ninguna jerarquia explícita entre las categorías, lo más adecuado sería considerarlas nominales. 


Segun el tipo de datos categorico, se asigna un encode, para

- Nominales -> Dummy variables (One-Hot Encoding), EJ: Color (Rojo, Azul, Verde) => (1,0,0),(0,1,0)(0,0,1)
- Ordinales -> codificación de etiquetas (Label enconding) para preservar el orden, EJ: Nivel (Alto, medio, bajo) => 0,1,2

> [!WARNING]  
> ***One-Hot*** puede ser simple y efectiva, pero se puede crear una gran cantidad de caracteristicas y aumentar la dimensionalidad de los datos
>  Lo que puede traer problemas como *el sobreajustes*,  *la dispersión* y *la complejidad computacional*.
> 
> ***Label encoding*** Puede introducir una falsa sensacion de magnitud (distancia entre categorias) tener precaucion y aplicar técnicas de escalado o normalización si es necesario.


"Existen otros métodos para convertir datos categóricos en datos numéricos, como la codificación binaria, la codificación de frecuencia, la codificación de destino o la incrustación. "

***¿ Por que es importante transformarlas ?***
La mayoria de los modelos estadisticos y algoritmos de aprendizaje estan disenados para trabajar con datos numericos.


**Variables categóricas en modelado estadístico**

1. Regresión: Se necesitan transformar usualmente a one-hot para la regresion lineal
2. Clasificacion: Se usand los datos categoricos para dividir los datos en clases distintas
3. Análisis de serie de tiempo: Pueden ayudar a segmentar los datos o actuar como parte del conjunto de caracteristicas.
4. Análisis de conglomerados: Agrupar entidades similares y el manejo afecta la clusterizacion.


***¿Por qué las variables categóricas son cruciales en la ciencia de datos?***
 Las variables categóricas son esenciales para problemas de clasificación, reconocimiento de patrones y para proporcionar información matizada en diversos contextos analíticos, desde estadísticas descriptivas hasta modelos avanzados de aprendizaje automático.


 ***¿Cuando transformar los datos categoricos?***
 1. Se desee usar modelos de aprendizaje automatico
 2. Se desea reducir la complejidad: Categorias redundantes o demasiado niveles
 3. Preparacion para visualizacion o metricas: En formato numerico es mas sencillo de visualizas.


#### ***Convertir categoricos - Encoding One-Hot y Label Encoding***

***One-Hot (agrega columnas)***

```python
color_encoded = pd.get_dummies(df['Color'], prefix='Color')
df_new = pd.concat([df, color_encoded], axis=1)
```

**Antes**

| Color |
|-------|
| Rojo  |
| Azul  |
| Verde |

**Despues**

|Color	|Color_Rojo	|Color_Azul	|Color_Verde |
|-------|-----------|-----------|------------|
|Rojo	|1	        |0	        |0           |
|Azul	|0	        |1	        |0           |
|Verde	|0	        |0	        |1           |


***Label encode***

**Antes**

| Freq |
|-----------|
| Weekly    |
| Monthly   |
| Daily     |

1. Mapeando

```python
order = {'Monthly':0, 'Weekly':1, 'Daily':2}
df['Freq_encoded'] = df['Freq'].map(order)
df.head()
```

**Despues con Mapeo**

| Freq      | Freq_encoded |
|-----------|--------------| 
| Weekly    | 1            |
| Monthly   | 0            |
| Daily     | 2            |


2. Importando LabelEncoder de sklearn 

```python
import sklearn.preprocessing import LabelEncoder
freq_label_encoder = LabelEncoder()
df['Freq_encoded'] = freq_label_encoder.fit_transform(df['Freq'])
df.head()
```

**Despues con LabelEncoder**

| Freq      | Freq_encoded |
|-----------|--------------| 
| Weekly    | 0            |
| Monthly   | 1            |
| Daily     | 2            |



#### Normalización de texto

El objetivo es tranformar el texto en un formato estandarizado para facilitar su analisis, comparacion y procesamiento.

 ***¿Que incluye?***
 - Conversion a minuscula: Pasarlas al mismo formato. *Ej: Texto  texto.*
 - Eliminación de caracteres no deseados: Remover caracteres especiales irrelevantes. *Ej: hello! -> hello.*
 - Eliminación de espacios extras: Quitar espacios extras o redundantes. *Ej: Hola    mundo -> hola mundo.*
 - Lematizacion: Reducir palabras a su forma base. *Ej: Corriendo -> correr.*
 - Sremming: Recortar palabra a su raiz. *Ej: Corriendo -> corr o Rapidamente -> rapid.*
 - Eliminación de palabras vacias: Quitar palabras sin singnificado. *Ej: el gato esta en casa -> gato casa.*
 - Sustitucion de abreviaturas: Expandir abreviaturas. *Ej: EE.UU. -> Estados Unidos.*
 - Extración de informacion: Remover unidades de medida, valores irrelevantes; *Ej: 250ml -> 250*
 - Correcion de errores tipográficos.


 ***¿Por que es importante?***
 - Reduce la variabilidad.
 - Reduce el ruido y hace mas facil extraer patrones
 - Facilita la agrupacion, clasificacion y analisis.
 - Permite que los modelos procesen la información de manera coherente.
 - Ayuda a evitar resultados inexactos o inconsistente por las diferencias en el formato de texto.


"La normalización es esencial siempre que se necesite una entrada de texto estandarizada"

> [!WARNING]  
> Es recomendable siempre realizar primero la normalización antes de la identificación y el encoding de las variables categóricas.

## Análisis exploratorio de datos (EDA)

> :memo: Responde que tengo y que me dicen los datos.  

Conciste en analisar e investigar el conjunto de datos usando a menudo metodos de visualizacion de datos

Se usa principalmente para observar que pueden revelar los datos y proporciona una mejor comprension de las variables del conjunto de datos.

*¿ Por que es importante hacer EDA ?*

> Extrae conocimientos
- Evita suposiciones.
- Identificar errores obvios.
- Comprender e identificar patrones.
- Encontrar relaciones interesantes entre variables.
- Confirma si las preguntas son correctas.

### Tipos de EDA
- Univariante no gráfico:
    - Concisten en una sola variable
    - Obj: Describir los datos y encontrar patrones
    Como se puede conseguir patrones si conciste en una sola variable ?

- Univariante gráfico:
    - Incluye: 
        - Diagramas de tallos
        -  Histogramas
        -  Diagrama de cajas 
- Multivariante no gráfico:
    - Concisten en mas de una variable
    - Relacion de entre dos datos y mas
    - Usando: Tabulaciones cruzadas o estadisticas
    

- Multivariante gráfico:
    - Usan graficas para mostrar relaciones entre dos o mas variables.
    - Incluye:
        - Diagrama de barras
        - Diagramas de dispersion
        - Grafico multivariante
        - Grafico de burbujas
        - Mapa de calor

**¿ Que son tabulaciones cruzadas ?**  
Las tabulaciones cruzadas son las tablas que muestran relacion entre dos variables categóricas al contar la frecuencia con que ocurren combinaciones especificas.

_________________
**Ejemplo**   

| Genero    |	Shampoo |	Crema|	Jabón|
|-----------|-----------|--------|-------| 
| Femenino	|   15	    |     20 |  10   |
| Masculino	|   10	    |     5	 |  30   |
_________________