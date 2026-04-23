# Most Used Beauty Cosmetics Products 2024 - Data Cleaning and EDA (Exploratory Data Analysis)

![Personal Project](https://img.shields.io/badge/TYPE-PERSONAL%20PROJECT-blue)

## Description

Analysis of 15,000 beauty and cosmetics products worldwide, covering data cleaning, categorical encoding and exploratory analysis to uncover trends in brands, categories, ingredients and consumer targeting.

## Motivation

As someone passionate about dermcosmetics, I chose this dataset to combine technical data skills with industry knowledge, exploring what drives product variety, pricing and consumer targeting in the global beauty market.

## Questions that guided the analysis

**Categorical variables:**
- Which brands (Brand) have the most products?
- Which categories (Category) are the most represented? Are there any that appear very little?
- What is the most frequent usage frequency (Usage_Frequency) among products?
- Which skin type (Skin_Type) is most targeted by the products?
- Which country (Country_of_Origin) produces the highest number of products?

**Encoded variables:**
- Which ingredients (Main_Ingredient) are the most common?
- Are products more oriented toward a specific gender?



## Key Findings — Data Cleaning & Initial Inspection

**Dataset:** 15,000 products · 14 columns · 0 nulls · 0 duplicates

**Price (USD):** High variability (std: 40.40 USD, ~50% of mean). 
Products range from $10 to $149.99, with a median of $80 USD, 
suggesting a market split between accessible and premium products.

**Rating:** Moderate variability (std: 1.16). Ratings range from 1 to 5 
with a median of 3, indicating a fairly balanced distribution across 
product quality perception.

**Number of Reviews:** Wide spread (std: 2,855). Range from 52 to 10,000 
reviews per product, reflecting significant differences in product 
visibility and popularity.

**Categorical variable quality:** No categorical column presented misspelled 
values, duplicates or inconsistencies. Data is well written and structured, 
with no additional corrections needed.

**Categorical encoding:**
- Ordinal variables (*Category, *Usage_Frequency, product_Size, *Packaging_Type): 
  encoded using Label Encoding to preserve natural order.
- Nominal variables (*Brand, *Gender_Target, *Main_Ingredient, Product_Name Country_of_Origing): 
  encoded using One-Hot Encoding.


## Project Structure

- ByCProducts2024
  - data
    - most_used_beauty_cosmetics_products_extended.csvc
    - cleaned_most_used_beauty_cosmetics_products_extended.csv
  - img
    - most_used_beauty_cosmetics_products_extended.csvc
  - notebooks
    - data_cleaning.ipynb
    - EDA.ipynb
  - requirements.txt 

## Technologies & Libraries

- **Language:** Python 3
- **Data manipulation:** Pandas
- **Machine Learning / Encoding:** Scikit-learn (LabelEncoder)
- **Environment:** Jupyter Notebook


## Instalation

```bash
git clone https://github.com/MayeLabs/ByCProducts2024.git
cd retail-trends-dataqa
jupyter notebook
```
