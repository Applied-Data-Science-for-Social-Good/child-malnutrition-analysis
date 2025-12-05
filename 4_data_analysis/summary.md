# **Summary:**

## **Data Analysis Key Findings**

* **Global Progress Against Malnutrition**: All three malnutrition indicators (stunting, wasting, and severe wasting) showed a significant global decline over time, with stunting exhibiting the steadiest downward trend.
* **Socio-Economic Development as a Primary Driver**: Principal Component 1 (representing high GDP per capita and education, with low undernourishment and refugee burden) was consistently identified as the most significant negative predictor of all malnutrition outcomes, highlighting the fundamental role of economic prosperity and educational attainment.
* **Diminishing Returns of Development**: Mixed-effects models revealed a significant positive interaction between 'year' and PC1, indicating that the beneficial impact of socio-economic development on reducing malnutrition has been weakening over time.
* **Acute Malnutrition's Volatility**: Wasting and severe wasting showed more volatility and were less strongly correlated with long-term socio-economic factors compared to stunting, suggesting responsiveness to short-term shocks.
* **Significant Country-Level Heterogeneity**: Hierarchical mixed-effects models confirmed substantial baseline differences in malnutrition rates across countries, underscoring the need for context-specific approaches.
* **Income Group Disparities are Stark**: A clear inverse relationship was observed between income group and malnutrition rates, with lower-income countries consistently exhibiting higher and more variable rates across all malnutrition types. ANOVA and post-hoc tests confirmed these differences as statistically highly significant.
* **Pervasive Missing Data**: A significant limitation was the extensive missingness across almost all variables (e.g., approximately 90% for severe wasting, wasting, and stunting), which drastically reduced the effective sample size and limited the generalizability of certain analyses.
* **Robust Methodological Approach**: The analysis successfully integrated diverse datasets, employed advanced techniques like PCA to address multicollinearity, utilized hierarchical mixed-effects models for nested data structures, and selectively applied Granger causality to explore temporal predictive relationships where data permitted.

### **Insights or Next Steps**

* **Prioritize Data Collection and Harmonization**: To overcome the severe limitations of missing data, significant investment is needed in consistent, long-term, and harmonized data collection for malnutrition indicators and related socio-economic factors globally.
* **Tailored Interventions are Crucial**: Given the country-level heterogeneity and the diminishing returns of broad development, future policies should move towards context-specific, nutrition-sensitive interventions, especially for acute malnutrition, rather than relying solely on 'one-size-fits-all' solutions or general socio-economic development alone.

### **Used and Loaded Datasets**

* **final_merged_data.xlsx**: This was the primary dataset loaded multiple times for various phases of the analysis, including initial inspection, global and country-level trends, PCA, and mixed-effects models.

* **final_merged_data_no_duplicates_and_missing.xlsx**: This dataset was specifically loaded for the correlation analysis and OLS regression models in Phase 2.5, which operated on a smaller, pre-cleaned subset of data.python --version
