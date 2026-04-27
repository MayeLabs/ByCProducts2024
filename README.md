# Most Used Beauty Cosmetics Products 2024 - Data Cleaning and EDA (Exploratory Data Analysis)

![Personal Project](https://img.shields.io/badge/TYPE-PERSONAL%20PROJECT-blue)
![Status](https://img.shields.io/badge/STATUS-FINISHED-green)

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


## Key Findings — Exploratory Data Analysis (EDA)

**Top Brands:** Milk Makeup leads with 426 products, followed closely by 
Make Up For Ever (414) and Kiehl's (411), with minimal differences between them.

**Top Categories:** Serum dominates with 710 products, followed by Mascara (674) 
and Face Oil (671). Serum's position may reflect its strong presence in social 
media and advertising campaigns prior to 2025. Lip Gloss ranks last (571), 
possibly linked to current makeup trends.

**Usage Frequency — Critical Finding ⚠️:** Although 'Occasional' appears as 
the most common frequency, cross-analysis shows that all categories have nearly 
identical distributions across all frequencies (~140–180 per combination). 
Products like Serum, expected to be Daily use, show no clear pattern. 
This suggests the dataset was likely artificially generated or balanced, 
and does not reflect real consumer behavior.

**Skin Type:** Combination skin is the most represented, though differences 
between skin types are minimal.

**Country of Origin:** Italy produces the highest number of products, 
though again with small differences across countries.

**Top Ingredients:** The most common ingredients — Retinol, Glycerin, 
Vitamin C, Salicylic Acid and Shea Butter — all have strong scientific 
backing and wide presence in the dermatological market.

**Gender Distribution:** Products are distributed almost equally across 
all gender targets — Male (5,017), Female (5,002) and Unisex (4,981) — 
suggesting the beauty market offers a proportional range for all genders.

## Project Structure

- ByCProducts2024
  - data
    - most_used_beauty_cosmetics_products_extended.csv
    - cleaned_most_used_beauty_cosmetics_products_extended.csv
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
cd ByCProducts2024
jupyter notebook
```
