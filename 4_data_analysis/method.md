
# **Methods**

## **Used and Loaded Datasets**

- **final_merged_data.xlsx**: This was the primary dataset loaded multiple
  times for various phases of the analysis, including initial inspection,
  global and country-level trends, PCA, and mixed-effects models.

- **final_merged_data_no_duplicates_and_missing.xlsx**: This dataset was
  specifically loaded for the correlation analysis and OLS regression models
  in Phase 2.5, which operated on a smaller, pre-cleaned subset of data.

## Methods

This project followed a structured, multi-phase workflow designed to move from
basic data preparation to deeper statistical modeling and country-level
interpretation. Each phase built upon the previous one, allowing the analysis
to grow in complexity while staying grounded in transparent data handling and
clear reasoning.

---

## Phase 1: Introduction and Data Loading

This first phase set the foundation for the entire project. The goals of the
analysis were defined, datasets were loaded, and the quality of the data was
assessed.

### 1.1 Analysis Objectives

The analysis began with a short orientation outlining what the study aimed to
uncover: broad global trends in stunting, wasting, and severe wasting;
differences across countries; and how economic, social, and structural
indicators—such as GDP, maternal education, undernourishment, and refugee
pressure—relate to malnutrition outcomes. This step provided direction and
logical boundaries for the rest of the notebook.

### 1.2 Loading the Primary Dataset

All required datasets were read into pandas DataFrames with standard checks to
handle missing or incorrectly formatted files. This provided a consistent
starting point and ensured downstream steps operated on valid inputs.

### 1.3 Initial Data Inspection

Basic exploratory functions—`head()`, `info()`, and `describe()`—were used
to familiarize the notebook with the dataset structure. These checks helped
confirm column types, identify unexpected values, and get a high-level view of
key indicators.

### 1.4 Missingness Report

A complete missingness audit was performed across all columns. Missing counts
and percentages were calculated and sorted to expose where data was thin,
inconsistent, or absent. This early awareness shaped later analyses and model
feasibility.

---

## Phase 2: Exploratory Data Analysis (EDA) – Trends and Predictors

With the data prepared, the next step explored global and country-level
behavior of malnutrition indicators and their predictors.

### 2.1 Global Malnutrition Trends

The dataset was standardized and cleaned so annual averages for stunting,
wasting, and severe wasting could be computed and plotted. These global trends
served as a baseline and highlighted broad improvements or stagnation over
time. Early-year gaps or noisy periods were acknowledged in the interpretation.

### 2.2 Country-Level Trends

Country-specific line plots, faceted views, and country × year heatmaps showed
how countries evolved differently. Some improved steadily, others stagnated,
and some had sharp reversals—often due to conflict or economic disruption.

### 2.3 Improvement & Deterioration Ranking

Percentage changes between the earliest and most recent years were calculated
for each country. Ranked lists of top improvers and decliners for each
malnutrition indicator helped identify countries for deeper analysis in later
phases.

### 2.4 Descriptive Statistics & Distributions

Predictors—GDP per capita, maternal education, undernourishment, and refugee
pressure—were examined through summary statistics and distribution plots.
Outliers and skewed variables were identified, informing later modeling
choices.

### 2.5 Predictor Correlation Analysis

A correlation matrix and scatterplots (with smoothing lines) illustrated how
predictors relate to each other and malnutrition outcomes. Patterns such as
inverse relationships between GDP and stunting and clustering of social
variables were clarified, while multicollinearity was also revealed.

### 2.6 Malnutrition by Income Group

Income groups were completed through imputation where needed. Statistical
comparisons across income categories were performed using boxplots, ANOVA, and
Tukey HSD tests. This highlighted systematic differences across economic
strata.

---

## Phase 3: Advanced Modeling

More sophisticated modeling techniques were introduced to understand structural
relationships and improve interpretability.

### 3.1 PCA to Address Multicollinearity

High correlations among predictors prompted the use of Principal Component
Analysis (PCA). PCA generated stable, uncorrelated components, reducing noise
from overlapping variables. Component loadings clarified which socio-economic
dimensions each principal component represented.

### 3.2 Hierarchical Mixed-Effects Models

Because the dataset includes repeated measurements nested within countries over
time, mixed-effects models were used. These incorporated fixed effects
(predictor components and year) and random intercepts for countries. Comparisons
to OLS models highlighted the importance of accounting for country-specific
baseline differences.

### 3.3 Robustness Checks with Random Slopes

Random slopes for time were added to test whether trends differed across
countries. Convergence issues were discussed to show how dataset structure
sometimes limited model flexibility.

### 3.4 Selective Granger Causality Tests

For countries with sufficiently long time series, Granger causality tests were
applied to explore whether predictors had short-term predictive value for
malnutrition outcomes. Results were interpreted carefully, noting that
Granger causality is predictive, not causal.

---

## Phase 4: Country-Specific Deep Dives

This phase zoomed in on individual countries to highlight unique trajectories.

### 4.1 Country Selection

Countries with enough complete data were selected for individual review.
Ensured interpretations were based on reliable time series.

### 4.2 Country-Level Visualizations

Subplots were generated for each country showing both malnutrition outcomes
and predictor trends. These visuals aided understanding of how national
conditions evolve together.

### 4.3 Quantifying Change

Long-term percentage changes and simple time-based regressions summarized
whether conditions improved and at what pace. Slopes and statistical
significance offered additional context beyond raw changes.

### 4.4 Narrative Summaries

Short country-specific narratives integrated statistical findings with
contextual interpretation while avoiding overreach. These illustrated how
global patterns manifest at the national level.

---

## Phase 5: Conclusions and Recommendations

### 5.1 Key Takeaways

Insights were collected across global, regional, and country-level results,
showing how economic, educational, and structural factors align with
malnutrition outcomes.

### 5.2 Limitations

Acknowledged constraints of missing data, uneven time series, and the
non-causal nature of methods used.

### 5.3 Strengths

Highlighted transparent data handling, robust exploratory work, layered
modeling approaches, and consistent emphasis on honest interpretation.

### 5.4 Recommendations

Practical, evidence-aligned suggestions were proposed, including investing in
maternal education, strengthening food systems, and improving monitoring
infrastructure.

### 5.5 Demonstrated Skills

The notebook showcased analytical capabilities from data processing and
visualization to PCA and hierarchical modeling.
