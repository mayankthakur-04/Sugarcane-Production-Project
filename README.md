# Sugarcane Production Analysis

This repository includes a Jupyter Notebook that analyzes sugarcane production data using Python, leveraging libraries such as Pandas, Seaborn, and Matplotlib. The analysis is based on the dataset "List of Countries by Sugarcane Production.csv".

### Setup
Before running the code in the notebook, make sure you have the required libraries installed. If you don't have them, you can install them using pip:

pip install pandas seaborn matplotlib

## Table of Contents

- [Description](#description)
- [Setup](#setup)
- [Dataset](#dataset)
- [Data Cleaning](#data-cleaning)
- [Univariate Analysis](#univariate-analysis)
- [Bivariate Analysis](#bivariate-analysis)
- [Correlation Analysis](#correlation-analysis)
- [Analysis by Continent](#analysis-by-continent)
- [Conclusion](#conclusion)

## Dataset

The dataset contains information about sugarcane production in various countries. It includes the following columns:

- `Country`: The name of the country.
- `Continent`: The continent where the country is located.
- `Production(Tons)`: Total sugarcane production in tons.
- `Production_per_person(Kg)`: Sugarcane production per person in kilograms.
- `Acreage(Hectare)`: Total acreage of land used for sugarcane cultivation in hectares.
- `Yield(Kg/Hectare)`: Yield of sugarcane in kilograms per hectare.

## Data Cleaning

### 1. Data Cleaning Process

Before diving into analysis, we first clean the dataset to ensure the data is accurate and usable.

### a. Remove Unwanted Characters

In the dataset **"List of Countries by Sugarcane Production"**, we clean the numerical columns by removing unwanted characters such as periods (`.`) and commas (`,`). This ensures that the data is in a proper format for numerical computations.

- Remove periods from **"Production (Tons)"** and **"Acreage (Hectare)"** columns  
- Replace commas with periods in **"Production per Person (Kg)"** to standardize decimal notation  

### b. Remove Unwanted Columns

The dataset contains extra columns like **"Unnamed: 0"** that are not necessary for the analysis.  
We remove these using the `drop()` function with `axis=1`.

### c. Rename Columns for Consistency

We clean up column names to remove extra spaces or special characters for consistency.

- Change **"Production (Tons)"** to **"Production(Tons)"**  
- Rename other columns similarly  

---

### 2. Checking Missing Values

Checking for missing values is critical, as it can impact the results of our analysis.  
The `isna().sum()` function helps identify columns with missing values.

### a. Missing Values Output
Country 0

Continent 0

Production(Tons) 0

Production_per_person(Kg) 0

Acreage(Hectare) 1

Yield(Kg/Hectare) 1

dtype: int64

### b. Handling Missing Values

- Drop rows with missing values in **"Acreage(Hectare)"** and **"Yield(Kg/Hectare)"**  
- Reset the index after dropping rows to maintain clean data  

---

### 3. Data Conversion

We convert numerical columns related to production, acreage, and yield into appropriate data types (`float`) to facilitate analysis.

## Univariate Analysis

In univariate analysis, we focus on understanding each variable individually. This includes examining distribution, central tendencies, and potential outliers.

### 1. Sugarcane-Producing Countries by Continent

Using the **"Continent"** column, we identify how many countries produce sugarcane in each continent.

**Result:**

Africa 38

Asia 25

North America 22

South America 11

Oceania 4

Europe 2

We can visualize this using a bar chart to highlight the geographical distribution of sugarcane production.

---

### 2. Distribution of Key Variables

We analyze the distribution of the following columns using histograms:

- **Production (Tons)**
- **Production per Person (Kg)**
- **Acreage (Hectare)**
- **Yield (Kg/Hectare)**

Using `sns.distplot()`, we visualize the distribution of these variables, helping identify skewness, normality, and outliers.

**Insights:**

- **Production (Tons):** Highly skewed, with a few countries (Brazil, India, China) having extremely high production  
- **Production per Person (Kg):** Skewed, with some countries showing significantly higher values  
- **Acreage (Hectare):** Less skewed compared to production  
- **Yield (Kg/Hectare):** Varies by country; efficient farming leads to higher yield  

---

### 3. Outlier Detection with Boxplots

Boxplots help visually identify outliers in the dataset.

**Key Insights:**

- **Production (Tons):** Clear outliers, indicating countries like Brazil, India, and China contribute disproportionately  
- **Yield (Kg/Hectare):** High-yield countries appear as outliers  

---

### 4. Violin Plot for Production (Tons)

A violin plot provides a deeper understanding of the distribution of **"Production (Tons)"**, including skewness, spread, and outliers.

**Expected Insights:**

- Wide distribution with noticeable skewness  
- A small number of countries with extremely high production values

## Bivariate Analysis

Bivariate analysis investigates relationships between two variables to identify correlations and patterns within the dataset.

### 1. Countries with the Highest Sugarcane Acreage

Using a bar plot, we identify the **top 15 countries** with the largest sugarcane cultivation area.

**Key Insight:**  
Brazil, India, and China dominate the land area dedicated to sugarcane production, reflecting their large-scale agricultural capacity.

---

### 2. Countries with the Highest Yield per Hectare

By analyzing **yield per hectare**, we identify countries with the most efficient sugarcane production.

**Key Insight:**  
Guatemala has the highest yield per hectare, indicating highly efficient farming practices and strong agricultural productivity.

---

### 3. Countries with the Highest Production per Person

We analyze **production per person (Kg)** to determine which countries produce the most sugarcane relative to their population size.

**Key Insight:**  
Paraguay leads in production efficiency relative to population, highlighting its strong sugarcane production output compared to its population size.

## Correlation Analysis

We perform correlation analysis to understand relationships between key variables.

### Key Correlations

- **Production (Tons) vs Acreage (Hectare):** Strong positive correlation (**0.997**)  
- **Production (Tons) vs Yield (Kg/Hectare):** Weak correlation (**0.132**)  

A heatmap is used to visualize these correlations.

---

### 5. Relationship Between Land and Production

We use a scatter plot to examine the relationship between **Acreage (Hectare)** and **Production (Tons)**.

**Insight:**  
Countries with larger land areas tend to produce more sugarcane, confirming a strong positive relationship.

---

### 6. Relationship Between Yield and Total Production

A scatter plot is used to explore the relationship between **Yield (Kg/Hectare)** and **Production (Tons)**.

**Insight:**  
Higher yield per hectare does not always result in higher total production, indicating other factors (like land size) play a major role.

## Continental Analysis

### 1. Sugarcane Production by Continent

We group the data by **continent** and aggregate key metrics to analyze global production trends.

**Total Production by Continent:**

- **South America:** Leading producer  
- **Asia:** Second highest production  
- **Africa:** Third  

A bar plot is used to visualize the production distribution across continents.

---

### 2. Impact of Number of Countries on Production

We analyze whether the number of countries in a continent affects total sugarcane production.

**Insight:**  
Continents with fewer countries (e.g., South America) can still achieve high production due to the presence of dominant producers such as Brazil.

## Conclusion

This analysis provides insights into sugarcane production across different countries and continents. It explores the relationship between various production-related metrics and uncovers patterns and trends within the dataset.

For more details, please refer to the Jupyter Notebook in this repository.
