# Deforestation-Analysis-2000-2020-

<img width="552" height="373" alt="Image" src="https://github.com/user-attachments/assets/56c8bad4-7738-4b00-8f2b-d7673296a605" />

## Project Overview

This project analyzes global forest change between 2000 and 2020 using Microsoft Excel.
The aim is to uncover trends, identify high-risk countries, and provide data-driven insights into deforestation.

 ### Objectives
Identify countries with the highest forest loss
Analyze forest change trends over time
Highlight countries at highest risk
Examine relationships between forest size and change
#### Tools & Techniques
Microsoft Excel
Pivot Tables
Data Cleaning
Data Visualization
##### Key Analysis & Methods
1. Top Countries by Forest Loss
Used Pivot Tables to aggregate total forest loss by country
Sorted in descending order to identify top 10
2. Trend Analysis (2000–2020)
Line charts used to visualize forest change over time
Year-based grouping applied in Pivot Tables
3. Risk Classification

##### Countries were categorized into:

Low Risk
Medium Risk
High Risk

Based on forest loss values.
Excel Formulas Used (Core “Code”)
Percentage Change
=(New Value - Old Value) / Old Value
IF Function (Risk Classification)
=IF(B2>1000,"High Risk", IF(B2>500,"Medium Risk","Low Risk"))
Total Calculation
=SUM(B2:B100)
Average Calculation
=AVERAGE(B2:B100)
📈 Dashboard Features
Interactive charts
Slicers for filtering top countries
Visual comparison of trends
Clean and user-friendly layout
 Files Included
Raw dataset
Cleaned dataset
Pivot tables
Dashboard
###### Key Findings
Several countries consistently show high forest loss
A downward trend in forest area is visible over time
High forest area countries often experience significant losses
###### Conclusion & Recommendations

The analysis reveals a consistent decline in forest cover across several high-risk countries between 2000 and 2020. Countries with larger initial forest areas tend to experience greater absolute losses, indicating increased environmental pressure.

From an analytical perspective, Excel proved to be an effective tool for transforming raw data into meaningful insights through Pivot Tables, charts, and dashboards.
###### Recommendations
Focus conservation efforts on high-risk countries
Promote sustainable forest management practices
Improve data monitoring and reporting systems
Support reforestation initiatives
Use data-driven approaches for environmental decision-making




