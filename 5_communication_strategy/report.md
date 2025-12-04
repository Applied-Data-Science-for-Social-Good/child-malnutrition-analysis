# Malnutrition Analysis Report

## Introduction

Malnutrition remains one of the most persistent global public-health
challenges, shaped by food insecurity, poverty, conflict, displacement, and
unequal access to health and education services. While global datasets
attempt to summarize these pressures, they inevitably simplify complex local
realities. Indicators such as GDP, maternal education, undernourishment, and
refugee movements offer important clues, but they cannot fully account for the
cultural, political, and environmental contexts shaping nutritional outcomes.

This analysis brings together several publicly available datasets to examine
stunting, wasting, and severe wasting alongside economic and social
indicators. Through a multi-phase workflow - including data loading,
exploratory analysis, advanced modeling approaches, and country-specific
deep dives - the project evaluates global trends, cross-country differences,
and broad associations with development, education, and food-security
measures. The goal is not to claim causal relationships, but instead to
document patterns, highlight constraints, and demonstrate a complete
analytical pathway for complex public-health data.

## Critical Reflection on Usefulness

This work does not seek to produce groundbreaking discoveries about global
malnutrition. The dataset is aggregated, incomplete for many countries, and
inconsistent across years. Many observed patterns arise from structural
differences, measurement variability, and contextual factors that cannot be
captured at the national level.

Still, the analysis has meaningful value:

- It demonstrates how to load, clean, merge, and inspect multiple global
  datasets.
- It tackles common challenges such as missing data, inconsistent country-year
  coverage, and correlated predictors.
- It applies a transparent, real-world analysis workflow including trend
  evaluation, group comparisons, PCA, mixed-effects modeling, and limited
  temporal causality checks.
- It reinforces widely known relationships - such as the link between income,
  education, food security, and child nutrition - without overstating what
  the data can prove.

The project’s contribution is methodological and practical: it shows how to
thoughtfully examine global health data while remaining honest about its
limitations.

## Objectives of the Analysis

1. **Analytical Objective**  

   Examine associations between malnutrition indicators (stunting, wasting,
   severe wasting) and socio-economic variables such as GDP, maternal
   education, undernourishment, refugee inflows, and income group
   classifications.

2. **Methodological Objective**  

   Demonstrate competence in loading, harmonizing, and analyzing multi-source
   datasets while documenting missingness and resolving irregularities.

3. **Interpretive Objective**  

   Summarize long-term malnutrition trends, identify countries moving in
   positive or negative directions, and situate these patterns within broader
   social and economic contexts.

4. **Reflective Objective**  

   Recognize the limits of aggregate global data, avoid causal claims, and
   communicate results with transparency and caution.

## Executive Summary

This analysis integrates global indicators related to child malnutrition,
economic development, education, undernourishment, and displacement. Through
exploratory data analysis, trend visualizations, correlation assessments, PCA
components, mixed-effects modeling, and selective country-level deep dives,
the study aims to understand how malnutrition outcomes vary and what broad
patterns they follow.

**Key observations include:**

- Countries with higher GDP tend to experience lower rates of stunting,
  wasting, and severe wasting.
- Maternal education consistently aligns with improved nutritional outcomes.
- Regions affected by conflict, displacement, or chronic food insecurity tend
  to experience higher and more volatile levels of malnutrition.
- Stunting shows the clearest long-term decline globally, while wasting and
  severe wasting remain more sensitive to short-term shocks.
- Modeling efforts revealed substantial multicollinearity in predictors,
  justifying the use of PCA and mixed-effects frameworks.
- The project’s main value lies in demonstrating a rigorous, end-to-end
  workflow for analyzing complex, imperfect global datasets and interpreting
  them responsibly.

## Methods Overview

### Phase 1: Introduction and Data Loading

- **1.1 Objectives and Context**  

  Understanding global malnutrition levels, exploring predictor behavior, and
  identifying countries with improvement or decline.

- **1.2 Loading the Primary Dataset**  

  Multiple datasets loaded into pandas DataFrames, with error handling for
  missing or corrupted files.

- **1.3 Initial Structure and Quality Checks**  

  Data was reviewed using `head()`, `info()`, and `describe()` to confirm
  data types, detect formatting issues, and identify unusual distributions.

- **1.4 Missingness Assessment**  

  Detailed missingness tables were produced to inform decisions on which
  indicators could support time series analysis.

### Phase 2: Exploratory Data Analysis (EDA) - Trends and Predictors

- **2.1 Global Malnutrition Trends**  

  Computed annual global averages. Trend plots revealed long-term declines in
  stunting, slower progress in wasting, and volatile severe wasting values.

- **2.2 Country-Level Patterns**  

  Line plots, faceted panels, and heatmaps identified:

  - Countries showing persistent improvement
  - Countries with stagnation or reversals
  - Regions with limited reporting

- **2.3 Improvement and Deterioration Rankings**  

  Percentage changes from earliest to latest year highlighted major
  improvements and worsening areas.

- **2.4 Predictor Distributions**  

  GDP, maternal education, undernourishment, and refugee population examined
  using histograms, boxplots, and summary statistics.

- **2.5 Correlation and Association Analysis**  

  Correlation matrices revealed strong relationships:

  - Higher income → lower malnutrition
  - Higher maternal education → better outcomes
  - Higher undernourishment → higher stunting/wasting

- **2.6 Malnutrition by Income Group**  

  Imputed missing income groups; comparisons using boxplots, ANOVA, and Tukey
  HSD tests.

### Phase 3: Advanced Modeling for Deeper Insights

- **3.1 PCA to Address Multicollinearity**  

  Applied PCA to correlated predictors. Loadings highlighted economic and
  educational dimensions.

- **3.2 Mixed-Effects Modeling**  

  Incorporated PCA components, year as fixed effect, and country as random
  effect to capture global trends and country-specific variation.

- **3.3 Random Slopes and Robustness Checks**  

  Attempts to add random slopes for year led to convergence issues due to
  limited data depth.

- **3.4 Selective Granger Causality Tests**  

  Explored temporal associations for countries with long, stable time series;
  informative but not causal.

### Phase 4: Country-Specific Temporal Analysis

- **4.1 Selection Criteria**  

  Chose countries with sufficient and consistent reporting.

- **4.2 Visual Trend Assessment**  

  Plotted malnutrition trends and predictor time-series to highlight
  short-term deteriorations.

- **4.3 Quantitative Change Measures**  

  Percentage changes and regressions captured nutritional trajectory direction
  and speed.

- **4.4 Country Narratives**  

  Short interpretive narratives contextualized statistical patterns with
  real-world conditions.

### Phase 5: Conclusions and Recommendations

- **5.1 Key Takeaways**  

  - Stunting shows the most consistent global improvement.
  - Wasting and severe wasting respond more immediately to shocks.
  - Income, education, and food access strongly align with nutritional
    outcomes.
  - Conflict-affected and displaced populations remain the most vulnerable.

- **5.2 Limitations**  

  - Large gaps in country-year coverage
  - Measurement inconsistencies
  - Inability to assess local variations
  - No causal identification

- **5.3 Strengths**  

  - Transparent and reproducible workflow
  - Integrated multi-source data
  - Advanced modeling techniques
  - Careful interpretation aligned with data limits

- **5.4 Recommendations**  

  - Expand maternal education and local health programs
  - Strengthen food-system resilience
  - Increase humanitarian and protection efforts in conflict zones
  - Improve monitoring systems for real-time nutritional data
  - Scale social-protection programs supporting vulnerable households

- **5.5 Demonstrated Skills**  

  - Data cleaning and wrangling
  - Visualization and exploratory statistics
  - PCA and mixed-effects modeling
  - Time-series assessment
  - Clear, responsible scientific communication

## Conclusion

This analysis provides a detailed, methodologically transparent exploration of
global malnutrition using publicly available indicators. While reaffirming
recognized relationships between economic development, maternal education, and
nutritional outcomes, the primary value lies in demonstrating responsible
handling, analysis, and interpretation of imperfect international data.

Future progress will require richer micro-level data, stronger causal designs,
and on-the-ground insights. Within its scope, this project delivers a clear and
carefully reasoned examination of global malnutrition dynamics and their
broader socio-economic determinants.

