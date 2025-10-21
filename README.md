# EDA-Flight-Delays-2019-2023  

## Overview   
This project performs an **Exploratory Data Analysis (EDA)** on a large-scale flight dataset (2019–2023), containing over **2.9 million flight records** across major U.S. airlines. Due to its massive size, the dataset was processed **efficiently in chunks** using pandas’ `read_csv(..., chunksize=...)` approach. The goal of this project was to analyze flight **(arrival) delays**, **cancellations**, and **temporal patterns** (by year, month, day of month, day of week and time of day) to uncover meaningful insights  

## Methodology  
The analysis pipeline followes the main steps:  

**Step 1: Data Import and Loading into Chunks**  
1. We imported all the required libraries  
2. Downloaded the Dataset via Kaggle  
3. Loaded the first chunk into a DataFrame (size 1 million rows)  

**Step 2: Data Inspection**  
1. Inspected the first chunk to understand schema, data types, and missing values.  

**Step 3: Data Cleaning**  
1. Dropped columns to reduce size, column type conversion, dropped duplicates. Tried to secure as much data possible without filling missing values with mean, meadian or predicting them.  
2. Defined a data cleaning function  

**Step 4: Feature Engineering**  
1. Created usefull columns for the analysis such as `YEAR`, `MONTH`, `DAY` and more such as binning the time of day.  
2. Defined a feature engineering function  

**Step 5: Statistical Analysis**  
1. Created a filtered dataframe not including outliers of the column `ARR_DELAY`. We secured up to 95% of the observations within 2 sample standard deviations of the sample mean.
2. Performed an initial Groupby Analysis at the first chunk to validate first results, then later created a loop to include all chunks in the analysis. GroupBy Analysis for all data, for diffrent time of year, found the most problematic arrival and departure city and the most problematic route.  

**Step 6: Visualization**  
Visualised all the preceding results.  

**Step 7: Conclusion**  
Conclusion is summarised below:  

**Key Findings**  
  
  **Airlines with the highest average delays (Top 3):**  
    1. Allegiant Air  
    2. JetBlue  
    3. Frontier Airlines  

  **Origin airports with the highest departure delays (Top 3):**  
    1. Pago Pago (TT)  
    2. Portsmouth (NH)  
    3. Santa Maria (CA)  

  **Destination airports with the most delays (Top 3):**  
    1. Williamsport (PA)  
    2. Watertown (NY)  
    3. Cold Bay (AK)  

  **Yearly trend:**  
    Delays were negative in 2020 (COVID-19 impact), but have been increasing steadily since 2021.  

  **Months with the highest delay averages (Top 3):**  
    1. June  
    2. July  
    3. December  

  **Within-month pattern:**  
    Highest delays occur during the **second 10-day period (11–20)** of each month.  
    
  **Day and time patterns:**  
    1. Most delayed day: **Friday**  
    2. Most delayed time window: **Evening (18:00–00:00)**  

  **Cancellations:**  
    Southwest, American, and SkyWest Airlines show the highest cancellations overall, but with a **decreasing trend** year over year.  

## Libraries Used  
*  **Kagglehub**  
*  **cudf.pandas** (utilizing GPU where is possible in an older way)  
*  **pandas** (chunk-based processing)  
*  **matplotlib / seaborn** (visualizations)  
*  **numpy** (numerical operations)  
*  **Google Colab / Jupyter Notebook** (used userdata for credentials)  
*  **OS** (for filepath manipulation)  

## Conclusion  
Overall, this analysis provided actionable insights into how delays and cancellations evolved from 2019 to 2023.  
It also demonstrated how to conduct large-scale EDA efficiently using **chunk-based pandas processing**, making it ideal for real-world, memory-heavy datasets.  

## Author  
Panagiotis Kardatos,  
Mathematician, Aspiring ML Engineer  
