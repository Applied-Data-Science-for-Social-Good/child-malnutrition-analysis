# Variable Dictionary – Child Malnutrition Project

This document provides comprehensive definitions, sources, and specifications for
all variables used in the child malnutrition analysis.

---
<!-- markdownlint-disable MD013 -->
## Quick Reference Table

| Variable | Source | Type | Unit | Description | Notes / Constraints |
|----------|--------|------|------|-------------|-------------------|
| `country` | All datasets | Categorical | Text | Standardized country name | Must be consistent across datasets; missing or non-country rows removed |
| `year` | All datasets | Numeric | Year | Year of data collection | Some datasets are annual, some are multi-year averages |

---
<!-- markdownlint-disable MD013 -->
## Dependent Variables

### 1. Stunting

- **Variable name**: `stunting`
- **Source**: UNICEF – Joint Malnutrition Estimates (JME)
- **Type**: Dependent variable
- **Unit**: Percent (%)
- **Definition**: Percentage of children under 5 whose height-for-age is below
–2 standard deviations (moderate + severe)
- **What it measures**: Chronic undernutrition indicating long-term nutritional deficiency
- **Constraints**: Missing values in some countries/years

### 2. Wasting

- **Variable name**: `wasting`
- **Source**: UNICEF – Joint Malnutrition Estimates (JME)
- **Type**: Dependent variable
- **Unit**: Percent (%)
- **Definition**: Percentage of children under 5 whose weight-for-height is below
–2 standard deviations (moderate + severe)
- **What it measures**: Acute undernutrition indicating recent rapid weight loss
or failure to gain weight
- **Constraints**: Missing values in some countries/years

### 3. Severe Wasting

- **Variable name**: `severe_wasting`
- **Source**: UNICEF – Joint Malnutrition Estimates (JME)
- **Type**: Dependent variable
- **Unit**: Percent (%)
- **Definition**: Percentage of children under 5 whose weight-for-height is below
- –3 standard deviations (severe)
- **What it measures**: Severe acute malnutrition requiring immediate intervention
- **Constraints**: Missing values in some countries/years

---

## Independent Variables

### 1. GDP per Capita (PPP)

- **Variable name**: `gdp_ppp_per_capita`
- **Source**: World Bank – World Development Indicators (WDI)
- **Type**: Independent variable
- **Unit**: International dollars (constant 2017 $)
- **Definition**: GDP per capita adjusted for purchasing power parity
- **What it measures**: Average economic output per person, adjusted for inflation
and cost of living differences
- **Relevance**: Reflects national wealth and access to food, healthcare, sanitation,
and education
- **Constraints**:
  - Some missing country-years
  - Does not capture within-country inequality
  - Annual data

### 2. Income Group

- **Variable name**: `income_group`
- **Source**: UNICEF – Joint Malnutrition Estimates (JME)
- **Type**: Independent variable / Control
- **Unit**: Categorical
- **Categories**:
  - `low income` – Countries classified as low-income by World Bank
  - `lower middle income` – Countries classified as lower-middle-income
  - `upper middle income` – Countries classified as upper-middle-income
  - `high income` – Countries classified as high-income
  - `nan` – Missing value (no income group information available)
- **Definition**: World Bank income classification based on Gross National Income
(GNI) per capita
- **What it measures**: Overall level of national economic development
- **Relevance**: Captures structural differences in government capacity, healthcare
systems, infrastructure, and vulnerability to shocks
- **Constraints**:
  - Missing for some countries
  - Categories are broad
  - Must be encoded for statistical modeling

### 3. Refugee Population (Origin)

- **Variable name**: `refugee_population_origin`
- **Source**: Our World in Data (based on UNHCR data)
- **Type**: Independent variable
- **Unit**: Number of refugees
- **Definition**: Number of people leaving a country due to conflict, instability
, or persecution
- **What it measures**: Population displacement from the country
- **Relevance**: Proxy for conflict, food insecurity, political instability, and
breakdown of services
- **Constraints**:
  - May underestimate internal displacement
  - Sensitive to conflict patterns
  - Annual data

### 4. Female Primary Education

- **Variable name**: `female_primary_education`
- **Source**: World Bank – Education Statistics
- **Type**: Independent variable
- **Unit**: Percent (%)
- **Definition**: Percentage of women aged 25+ who have completed at least primary
education

- **What it measures**: Female educational attainment and human capital
- **Relevance**: Maternal education is one of the strongest predictors of child
nutrition, correlating with better feeding practices, hygiene, income, and lower
malnutrition risk
- **Constraints**:
  - Missing values common in low-income countries (LICs)
  - Measures completion only, not quality of education

### 5. Prevalence of Undernourishment

- **Variable name**: `prevalence_undernourishment`
- **Source**: FAO – FAOSTAT Food Security Indicators
- **Type**: Independent variable
- **Unit**: Percent (%)
- **Definition**: Percentage of population whose habitual dietary energy intake
is insufficient for a healthy, active life (3-year rolling average)
- **What it measures**: National food security and diet adequacy
- **Relevance**: Reflects food system stability; countries with higher undernourishment
typically show higher child malnutrition
- **Constraints**:
  - Uses 3-year rolling averages (smooths short-term shocks)
  - May not reflect individual-level consumption variation

---

## Data Standards

### WHO Child Growth Standards

All malnutrition indicators (stunting, wasting, severe wasting) follow WHO Child
Growth Standards, which define:

- **-2 SD**: Moderate undernutrition threshold
- **-3 SD**: Severe undernutrition threshold

### Standardization Requirements

- **Country names**: Must be standardized across all datasets
- **Year values**: Must be consistent (some sources use fiscal years, others
calendar years)
- **Missing data**: Coded as `NaN` or left blank; documented in constraints file

---

## Variable Selection Rationale

**Dependent Variables:** The three malnutrition indicators capture different aspects
of child undernutrition:

  1. **Stunting**: Long-term/chronic effects
  2. **Wasting**: Short-term/acute effects
  3. **Severe wasting**: Critical cases requiring immediate intervention

**Independent Variables**: Selected based on established literature showing strong
associations with child malnutrition:

1. **Economic factors**: GDP per capita, income group
2. **Stability factors**: Refugee population (conflict proxy)
3. **Human capital**: Female education
4. **Food security**: Undernourishment prevalence

---

## Updates and Versioning

- **Last updated**: 29-November-2025
- **Data period covered**: Varies by source (see data sources document)

---

## References

See `02_data_sources.md` for detailed source information and official links.
