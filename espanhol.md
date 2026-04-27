# Most Used Beauty Cosmetics Products 2024 - Limpieza de Datos y EDA (Análisis Exploratorio de Datos)

![Personal Project](https://img.shields.io/badge/TYPE-PERSONAL%20PROJECT-blue)
![Status](https://img.shields.io/badge/STATUS-FINISHED-green)

## Descripción

Análisis de 15,000 productos de belleza y cosmética a nivel mundial, que abarca 
limpieza de datos, codificación de variables categóricas y análisis exploratorio 
para descubrir tendencias en marcas, categorías, ingredientes y segmentación de consumidores.

## Motivación

Como apasionada de la dermocosméctica, elegí este dataset para combinar 
habilidades técnicas con conocimiento del sector, explorando qué impulsa 
la variedad de productos, los precios y la segmentación de consumidores 
en el mercado global de la belleza.

## Preguntas que guiaron el análisis

**Variables categóricas:**
- ¿Qué marcas (Brand) tienen más productos?
- ¿Cuáles son las categorías (Category) más representadas? ¿Hay alguna que aparezca muy poco?
- ¿Cuál es la frecuencia de uso (Usage_Frequency) más común entre los productos?
- ¿Qué tipo de piel (Skin_Type) es el más objetivo de los productos?
- ¿Qué país (Country_of_Origin) produce la mayor cantidad de productos?

**Variables codificadas (encoded):**
- ¿Qué ingredientes (Main_Ingredient) son los más comunes?
- ¿Los productos están más orientados hacia un género específico?

## Hallazgos Clave — Limpieza e Inspección Inicial

**Dataset:** 15,000 productos · 14 columnas · 0 nulos · 0 duplicados

**Precio (USD):** Alta variabilidad (desv. est: 40.40 USD, ~50% del promedio).
Los productos van de $10 a $149.99, con una mediana de $80 USD,
lo que sugiere un mercado dividido entre productos accesibles y premium.

**Rating:** Variabilidad moderada (desv. est: 1.16). Las puntuaciones van
de 1 a 5 con una mediana de 3, indicando una distribución bastante
equilibrada en la percepción de calidad de los productos.

**Número de Reseñas:** Alta dispersión (desv. est: 2,855). Rango de 52
a 10,000 reseñas por producto, reflejando diferencias significativas
en visibilidad y popularidad entre productos.

**Calidad de variables categóricas:** Ninguna columna categórica presentó
valores mal escritos, duplicados ni inconsistencias. Los datos están
bien escritos y estructurados, sin necesidad de correcciones adicionales.

**Codificación de variables categóricas:**
- Variables ordinales (Category, Usage_Frequency, Product_Size, Packaging_Type):
  codificadas con Label Encoding para preservar el orden natural.
- Variables nominales (Brand, Gender_Target, Main_Ingredient, Product_Name, Country_of_Origin):
  codificadas con One-Hot Encoding.

## Hallazgos Clave — Análisis Exploratorio de Datos (EDA)

**Marcas destacadas:** Milk Makeup lidera con 426 productos, seguida de cerca
por Make Up For Ever (414) y Kiehl's (411), con diferencias mínimas entre ellas.

**Categorías más representadas:** El Serum domina con 710 productos, seguido
por la Máscara (674) y el Face Oil (671). La posición del Serum puede reflejar
su fuerte presencia en redes sociales y campañas publicitarias previas a 2025.
El Lip Gloss ocupa el último lugar (571), posiblemente vinculado a las
tendencias actuales del maquillaje.

**Frecuencia de Uso — Hallazgo Crítico ⚠️:** Aunque 'Occasional' aparece como
la frecuencia más común, el análisis cruzado muestra que todas las categorías
tienen distribuciones casi idénticas entre frecuencias (~140–180 por combinación).
Productos como el Serum, que se esperaría fueran de uso Diario, no muestran
ningún patrón claro. Esto sugiere que el dataset fue probablemente generado o
balanceado artificialmente y no refleja el comportamiento real del consumidor.

**Tipo de Piel:** La piel Combination es la más representada, aunque las
diferencias entre tipos de piel son mínimas.

**País de Origen:** Italia produce la mayor cantidad de productos,
aunque también con diferencias pequeñas entre países.

**Ingredientes más comunes:** Los ingredientes más frecuentes — Retinol,
Glicerina, Vitamina C, Ácido Salicílico y Manteca de Karité — cuentan con
fuerte respaldo científico y amplia presencia en el mercado dermatológico.

**Distribución por Género:** Los productos están distribuidos de forma casi
equitativa entre todos los géneros — Male (5,017), Female (5,002) y
Unisex (4,981) — lo que sugiere que el mercado de la belleza ofrece una
gama proporcional de productos para todos los géneros.

## Estructura del Proyecto

- ByCProducts2024
  - data
    - most_used_beauty_cosmetics_products_extended.csv
    - cleaned_most_used_beauty_cosmetics_products_extended.csv
  - notebooks
    - data_cleaning.ipynb
    - EDA.ipynb
  - requirements.txt

## Tecnologías y Librerías

- **Lenguaje:** Python 3
- **Manipulación de datos:** Pandas
- **Machine Learning / Encoding:** Scikit-learn (LabelEncoder)
- **Entorno:** Jupyter Notebook

## Instalación

```bash
git clone https://github.com/MayeLabs/ByCProducts2024.git
cd ByCProducts2024
jupyter notebook
```