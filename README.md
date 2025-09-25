# Customer Segmentation with Python
## Project Overview
This project aims to analyze customer data from various sources to identify distinct customer segments. The process involves two phases:

* Data Cleaning and Anonymisation
* Customer Segmentation with Sci-kit Learn clustering model

## Workflow
### 1: Data Cleaning and Anonymisation
  * **Data Consolidation:** Merging four separate datasets, each representing a different region.
    
  * **Standardisation:**
    - Column names were unified (e.g., "Given Name" and "First Name" were merged into a single "MemberName" column).
    - Categorical data, like the "Cred Card User" column, was standardised to a binary format (1/0).
    
  * **Data Imputation:**
    - Logical inconsistencies, such as customers having a purchase count but zero amount spent, were identified.
    - KNN imputer was used to estimate and fill in these incorrect zero values for "Amount Spent" and "Purchases".
      
  * **Anonymization:**
    - To protect personal information, sensitive fields like "NRIC" and "MemberName" were replaced with an 8-character SHA-256 hash.
    - "Birthdate" was generalized into "Birth Year" to reduce specificity while retaining its utility for age-based analysis.

Output: The final cleaned and anonymized dataset containing 1,501 records was exported to cleaned_data.xlsx for use in the clustering phase. A separate lookup.xlsx file was created to map the hashed values back to the original NRICs and names for internal reference.

### 2: Part 2: Customer Segmentation using Clustering
  * **Feature Engineering:** New features were created:
    - Age: Calculated as 2025 - Birth Year.
    - Years as Member: Calculated as 2025 - Year Joined.
      
  * **Data Transformation:**
    - Binning: Continuous variables like "Age" and "Years as Member" were categorized into bins (e.g., "20s," "30s," and "0-10 years") to facilitate analysis.
    - Encoding: Categorical features, including the newly created bins and "Region," were converted into a numerical format using one-hot encoding.
    - Scaling: All numerical features were standardized using StandardScaler to ensure that each feature contributes equally to the clustering model.

  * **Clustering:** The K-Means algorithm was applied to the preprocessed data to partition it into three distinct customer clusters.

## Findings & Recommendations

The analysis revealed three primary customer segments :

Cluster |	Segment Name | Characteristics | Recommendations
---|---|---|---|
Cluster 2 | High-Value Customers | The smallest group, but the most valuable. They exhibit high purchase frequency and high spending.	| Implement loyalty programs with exclusive perks. Offer personalized products and actively gather their feedback.
Cluster 1	| Core Customers | The largest segment. They have moderate income, purchase frequency, and spending, making them a consistent source of revenue. | Use targeted campaigns to increase their average order value. Cross-sell new products and encourage repeat business with a points-based system.
Cluster 0 | At-Risk Customers | This group has low purchase frequency and spending despite having above-average incomes. A significant portion is from the USA. | Launch re-engagement campaigns. Use surveys to identify reasons for low engagement and develop regional activation plans.


## Tools & Libraries
* Python
* pandas & numpy (data manipulation)
* matplotlib & seaborn (visualisations)
* scikit-learn (preprocessing & clustering)
