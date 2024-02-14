# Market-Basket-Analysis

## Project Overview
This project aims to analyze historical data of client receipts to identify items frequently and rarely sold together. By examining transactional data, I uncover patterns that could inform product placement, marketing strategies, and inventory management. The analysis is implemented using Python and various data analysis libraries. 

## Objective
The primary goal is to derive actionable insights on which items are often purchased together and which are seldom paired, facilitating strategic decisions in product bundling, cross-selling opportunities, and enhancing the shopping experience.

### Tools and Libraries Used
- **Pandas & Numpy**: For data manipulation and analysis.
- **Matplotlib & Seaborn**: For data visualization.
- **MLxtend**: For frequent itemset and association rule mining.
- **NetworkX**: For creating and visualizing networks of item pairs.

## Technical Problem Definition
- **Data Source**: The data comes from the H&M Kaggle competition:  https://www.kaggle.com/c/h-and-m-personalized-fashion-recommendations/overview
- **Key Metrics**:
  Where Support is defined as the proportion of transactions containing a certain item set:
    - **Lift** = Support(A&B) / Support(A)*Support(B)
    - **Leverage** = Support(A&B) - Support(A)*Support(B)
- **Objective**: Identify item pairs with high support, lift, and leverage as indicators of frequent co-purchase, and item pairs with low values in these metrics to identify rare combinations.

## Methodology

### Data Preparation
- Merged transaction data with article information to enrich the dataset.
- Grouped transactions by customer ID and date, treating purchases on the same day as a single transaction.
- Utilized the `TransactionEncoder` from mlxtend to convert transaction lists into a sparse matrix format, suitable for frequent itemset mining.

### Exploratory Data Analysis (EDA)
- Visualized the frequency of items sold across different sections to understand the distribution of transactions.
- Employed the FPGrowth algorithm to identify frequent itemsets with varying lengths.

### Frequent Patterns Generation
- Applied the FPGrowth algorithm to the transactional data to find frequent itemsets with a minimal support threshold.
- Generated association rules from frequent itemsets to calculate metrics like lift and leverage for item pairs.

### Results Analysis
- Filtered the association rules to focus on item pairs, analyzing the most and least frequent pairs based on lift and leverage.
- Visualized the relationships between item pairs using network graphs to illustrate items often and rarely sold together.

## Key Findings
- Identified the most frequently bought item pairs, highlighting opportunities for cross-selling and product placement optimization.
- Discovered item pairs that are rarely or never bought together, indicating potential areas for marketing interventions or inventory adjustments.
- Visualized networks of item associations, providing a clear overview of product interrelationships and shopper behavior patterns.

## Conclusion and Future Work
This analysis sheds light on shopper behaviors, revealing patterns in item co-purchases that can drive strategic business decisions. Future work could extend this analysis by incorporating more granular data, such as item categories or customer demographics, to further refine recommendations for product bundling and store layout optimization.

