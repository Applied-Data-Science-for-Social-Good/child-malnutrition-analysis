# Detailed Breakdown of Analysis Phases

## **Phase 1: Introduction and Data Loading**

This phase lays the groundwork for the analysis: defining goals, loading the
dataset, and checking its quality.

* **1.1 Analysis Objectives**
  * **Content:** A short introduction explaining what the malnutrition analysis
    aims to explore - overall trends, country-level patterns, and how factors
    such as GDP, education, undernourishment, refugee pressure, and income
    groups relate to outcomes.
  * **Purpose:** To give readers context and a sense of direction.

* **1.2 Load Primary Dataset**
  * **Content:** Code to read the main datasets into a pandas DataFrame,
    including basic error handling for missing files.
  * **Purpose:** To bring all necessary data into the working environment.

* **1.3 Initial Data Inspection**
  * **Content:** Code to review the dataset through `head()`, `info()`, and
    `describe()`.
  * **Purpose:** To get familiar with the structure, column types, and basic
    statistical properties.

* **1.4 Detailed Missingness Report**
  * **Content:** Code to compute and display missing value counts and
    percentages for each column, sorted for clarity.
  * **Purpose:** To assess data quality early on and identify potential issues.

---

## **Phase 2: Exploratory Data Analysis (EDA) – Trends and Predictors**

This phase explores how malnutrition patterns evolve globally and by country,
and how the main predictors behave and relate to the outcomes.

* **2.1 Global Malnutrition Trends**
  * **Content:** Preprocessing steps (e.g., cleaning the year variable),
    computing annual global averages for stunting, wasting, and severe wasting,
    and plotting these trends.
  * **Interpretation:** Discussion of whether global levels rise or fall, which
    indicators change more quickly, and how missing early-year data affects
    patterns.
  * **Purpose:** To set a broad, global baseline.

* **2.2 Country-Level Malnutrition Trends**
  * **Content:**  
    * Line plots for each country’s trends.  
    * Faceted plots for cross-country comparison.  
    * Heatmaps showing country × year patterns.
  * **Interpretation:** Highlights differences across countries, notable gaps,
    and shared patterns.
  * **Purpose:** To show how varied malnutrition trajectories can be.

* **2.3 Improvement & Deterioration Ranking**
  * **Content:** Code to calculate percentage changes in each indicator between
    earliest and latest years per country, plus ranked lists of top improvers
    and decliners.
  * **Interpretation:** Commentary on standout progress or decline.
  * **Purpose:** To quantify change and identify extremes.

* **2.4 Descriptive Statistics & Distributions**
  * **Content:** Summary stats and visualizations (box plots, histograms) for
    GDP, education, undernourishment, and refugee population.
  * **Interpretation:** Notes on distribution shapes, outliers, and implications
    for modeling.
  * **Purpose:** To understand predictor behavior.

* **2.5 Predictor Correlation Analysis**
  * **Content:** Correlation matrix with heatmap and scatter plots with
    regression lines for all predictor - indicator pairs.
  * **Interpretation:** Key relationships and potential multicollinearity.
  * **Purpose:** To explore associations and modeling considerations.

* **2.6 Malnutrition by Income Group**
  * **Content:**  
    * Imputation of missing income groups.  
    * Box plots comparing income groups.  
    * ANOVA tests.  
    * Tukey HSD post-hoc tests.
  * **Interpretation:** Which groups differ significantly and overall gradients.
  * **Purpose:** To examine economic differences in malnutrition outcomes.

---

## **Phase 3: Advanced Modeling for Deeper Insights**

This phase tackles modeling challenges - especially multicollinearity and nested
data structures - to build more reliable models.

* **3.1 Handling Multicollinearity with PCA**
  * **Content:** Markdown explanation and code applying PCA to the predictors,
    followed by interpretation of component loadings.
  * **Purpose:** To generate uncorrelated inputs for stable models.

* **3.2 Hierarchical Mixed-Effects Models**
  * **Content:** Explanation of why mixed-effects models suit nested data,
    followed by baseline and interaction models using PCA components, year,
    and country-level random effects.
  * **Interpretation:** Discussion of fixed effects, random effects, and
    comparisons to OLS.
  * **Purpose:** To account for country-specific structure and temporal change.

* **3.3 Robustness Checks with Random Slopes**
  * **Content:** Attempt to fit models with random slopes for year and report
    convergence results.
  * **Interpretation:** What convergence issues imply about data richness and
    model complexity.
  * **Purpose:** To test whether more flexible models are supported.

* **3.4 Selective Granger Causality Analysis**
  * **Content:** Explanation of Granger causality, selection of countries with
    long time series, stationarity checks, and causality tests.
  * **Interpretation:** Clarification of predictive - not causal - implications,
    plus data limitations.
  * **Purpose:** To explore temporal predictive relationships where possible.

---

## **Phase 4: Country-Specific Temporal Analysis**

This phase zooms in on individual countries for a closer look at their patterns
and dynamics.

* **4.1 Selecting Countries for Deep Dive**
  * **Content:** Code filtering countries with enough complete data for
    detailed analysis.
  * **Purpose:** To focus on countries with usable time series.

* **4.2 Country-Specific Visualizations**
  * **Content:** Subplots showing each country’s malnutrition trends and
    separate plots for predictors.
  * **Purpose:** To visually explore how outcomes and predictors evolve.

* **4.3 Quantifying Country-Level Change**
  * **Content:** Percentage changes and simple regressions of indicators on
    time, summarizing slopes and significance.
  * **Purpose:** To capture both long-term and year-on-year trends.

* **4.4 Synthesizing Country Narratives**
  * **Content:** Concise summaries for a handful of representative countries,
    integrating visuals, trends, and context (without claiming causation).
  * **Purpose:** To illustrate the range of country-level experiences.

---

## **Phase 5: Final Conclusions and Recommendations**

* **5.1 Key Takeaways**
  * **Content:** A high-level summary of the main insights across all phases.
  * **Purpose:** To bring everything together.

* **5.2 Limitations**
  * **Content:** Notes on missing data, short time series, non-causal analysis,
    and other constraints.
  * **Purpose:** To keep conclusions grounded and transparent.

* **5.3 Strengths**
  * **Content:** Highlights such as the merged dataset, clear missingness
    handling, varied analytical methods, and careful interpretation.
  * **Purpose:** To recognize the robustness of the approach.

* **5.4 Recommendations**
  * **Content:** Action-oriented suggestions informed by the findings - education,
    food security, conflict-related support, monitoring improvements.
  * **Purpose:** To translate insights into practical steps.

* **5.5 Demonstrated Skills**
  * **Content:** Highlights the analytical, statistical, and programming
    expertise utilized in this project.
  * **Purpose:** To showcase the comprehensive range of data science techniques
    applied, from data preprocessing and exploration to advanced modeling and
    clear interpretation.
