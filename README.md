# Lab 1 – Data Visualization, Data Preprocessing, and Statistical Analysis Using Python in Jupyter

**Name:** Banoj Kumar Jena  
**Course:** MSCS 634 – Advanced Big Data and Data Mining  
**Lab Assignment:** Week 2 – Lab 1

---

## Overview

This lab explores data analysis through Python in Jupyter Notebook. It involves loading, visualizing, cleaning, preprocessing, and statistically analyzing a dataset representing coffee shop transactions. Key techniques include handling missing values, outlier removal, data reduction, scaling, and statistical interpretation.

---

## Dataset Description

The dataset used (`index_1.csv`) contains 1,818 records of coffee purchases. It includes the following columns:

- `date`: Transaction date  
- `datetime`: Full timestamp of transaction  
- `cash_type`: Type of payment used  
- `card`: Anonymized card ID  
- `money`: Transaction amount  
- `coffee_name`: Type of coffee purchased  

**Missing Values:**  
- 89 missing values in the `card` column  
- All other columns are complete  

---

## Step-by-Step Breakdown

### Step 1: Data Collection

- The dataset was loaded into a Pandas DataFrame.
- First five records were displayed using `.head()`.

### Step 2: Data Visualization

1. **Histogram of Money**  
   - Displays the distribution of transaction values  
   - Insight: Most purchases cluster around mid-price values like 28.9 and 38.7

2. **Line Plot of First 100 Money Entries**  
   - Visualizes trends in the first 100 transactions  
   - Insight: The values are consistent and repeat frequently, suggesting set pricing per coffee type

### Step 3: Data Preprocessing

#### 1. Handling Missing Values  
- Missing values in numeric columns filled using mean  
- `card` column retained as-is since it’s categorical and anonymized  
- Displayed missing values before and after processing

#### 2. Outlier Detection and Removal  
- Used Interquartile Range (IQR) method  
- Removed values lying beyond 1.5×IQR range  
- Resulted in a cleaner and more accurate dataset for further processing

#### 3. Data Reduction  
- Sampled 50% of the cleaned data randomly using `sample()`  
- Dropped non-relevant columns like `Ticker`, `Company Name` (if present)

#### 4. Data Scaling  
- Applied Min-Max Scaling to normalize the `money` column to a 0–1 scale

### Step 4: Statistical Analysis

#### 1. General Data Overview  
- `.info()` displayed structure and non-null counts  
- `.describe()` revealed statistical summaries (mean, std, min, max)

#### 2. Central Tendency Measures  
- Min: 0.0  
- Max: 1.0  
- Mean: 0.6196  
- Median: 0.6718  
- Mode: 0.8062  

#### 3. Dispersion Measures  
- Range: 1.0  
- Variance: 0.0508  
- Standard Deviation: 0.2253  
- IQR: 0.3583  

#### 4. Correlation Analysis  
- Correlation matrix plotted using seaborn heatmap  
- Insight: Focused on numeric variable `money`; shows consistency without strong correlations with other fields

---

## Key Insights

- Most coffee purchases are priced consistently (especially 38.7 and 28.9), indicating fixed pricing.
- Removing outliers helped improve the statistical clarity of the data.
- Normalizing `money` values helped standardize the scale for future machine learning or modeling tasks.
- Visualization revealed pricing consistency and repetitive purchase behavior.

---

## Challenges and Decisions

- The `card` field had 89 missing values, but since it’s anonymized and not essential for price analysis, it was left unchanged.
- Since the dataset did not include time-based metrics like quantity or ratings, the focus remained on transaction value analysis.

---

## Repository Structure

