# Deforestation-Analysis-2000-2020-

<img width="552" height="373" alt="Image" src="https://github.com/user-attachments/assets/56c8bad4-7738-4b00-8f2b-d7673296a605" />

. Project Overview
This project investigates the change in global forest cover over a 20-year period. By analyzing data from 2000 and 2020, we aim to identify geographical patterns of deforestation and reforestation, evaluate the intensity of these changes, and categorize countries based on their conservation performance.

 ## Research Questions
To guide the analysis, the following research questions have been established:

Magnitude of Change: Which countries experienced the highest absolute loss and highest absolute gain in forest share percentage between 2000 and 2020?

Trend Intensity: Is there a correlation between a country's initial forest density in 2000 and the percentage trend (growth or decline) observed by 2020?

Regional Stability: What proportion of the world's countries have successfully maintained "Stable" forest levels versus those categorized as "loss" or "Gained"?

Categorical Analysis: How does forest change differ across the "low," "medium," and "high" density categories?

 ### Methodology
The analysis follows these steps:

Data Extraction: Parsing the complex multi-table structure of Analysis.csv.

Normalization: Cleaning column headers and handling missing values.

Quantitative Analysis: Calculating absolute changes and growth rates.

Categorization: Grouping countries by status (Gained/Stable/Loss) and density (Low/Medium/High).
. Implementation Code
A. Environment Setup & Data Cleaning
The following code extracts the two distinct tables hidden within the provided files.

Python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

#### Load datasets
df_shares = pd.read_csv('SETH excel.xlsx - goal15.forest_shares.csv')
df_raw_analysis = pd.read_csv('SETH excel.xlsx - Analysis.csv')

#### Clean Column Names
df_shares.columns = df_shares.columns.str.strip()
df_raw_analysis.columns = df_raw_analysis.columns.str.strip()

#### Extract the longitudinal data (Table 1)
longitudinal_df = df_raw_analysis[['iso3c', 'Forest Shares', 'Years']].dropna()

#### Extract the categorical summary table (found at the bottom of Analysis.csv)
#### Note: Based on data inspection, the category table starts around index 526
category_df = df_raw_analysis.iloc[526:, 38:43].dropna()
category_df.columns = ['iso3c', 'forest_2000', 'forest_2020', 'trend', 'density_group']
B. Answering Research Question 1: Top Gainers & Losers
Python
#### Sort by Absolute Change
top_losers = df_shares.sort_values(by='Absolute Change', ascending=True).head(10)
top_gainers = df_shares.sort_values(by='Absolute Change', ascending=False).head(10)

print("Top 10 Countries with Forest Loss (% points):")
print(top_losers[['iso3c', 'Absolute Change']])

print("\nTop 10 Countries with Forest Gain (% points):")
print(top_gainers[['iso3c', 'Absolute Change']])
C. Answering Research Question 3: Stability Distribution
Python
plt.figure(figsize=(10, 6))
sns.set_style("whitegrid")
status_plot = sns.countplot(data=df_shares, x='Status', palette='magma')
plt.title('Global Distribution of Forest Cover Status (2000-2020)')
plt.ylabel('Number of Countries')
plt.show()
5. Necessary Requirements
To replicate this analysis, ensure you have the following Python environment:

Python Version: 3.8+

Libraries:

pandas: For data manipulation and CSV parsing.

matplotlib: For basic plotting.

seaborn: For advanced statistical visualizations.

Data Files Required:

SETH excel.xlsx - goal15.forest_shares.csv

SETH excel.xlsx - Analysis.csv

6. Summary of Findings (Expected)
Deforestation Hotspots: Countries with high negative "Absolute Change" values represent areas under environmental stress.

Conservation Success: The "Gained" category highlights regions where reforestation efforts or natural expansion are prevalent.

Data Integrity: The Analysis.csv file contains a high volume of metadata and secondary tables that allow for cross-referencing country codes with density classifications (High/Medium/Low).
