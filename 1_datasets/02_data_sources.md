<!-- markdownlint-disable MD013 -->
<!-- markdownlint-configure-file { "MD024": { "siblings_only": true } } -->
# Data Sources Documentation

This document provides detailed information about all data sources used in the child malnutrition analysis project.

---

## 1. Malnutrition Indicators (UNICEF – JME)

### Overview

- **Source**: UNICEF – Joint Malnutrition Estimates (JME)
- **Coverage**: Global
- **Variables provided**:
  - Stunting (moderate and severe)
  - Wasting (moderate and severe)
  - Severe wasting
  - Income group classification
- **Unit**: Percent (%)
- **Frequency**: Periodic updates

### Description

The Joint Malnutrition Estimates database provides the primary global measures of child malnutrition. It includes standardized prevalence data for:

- **Stunting**: Low height-for-age (chronic undernutrition)
- **Wasting**: Low weight-for-height (acute undernutrition)
- **Severe wasting**: Very low weight-for-height (severe acute malnutrition)

These indicators measure the percentage of children under five who experience each form of malnutrition.

### Why It's Useful

- Globally standardized methodology
- Primary indicators used by international organizations
- Captures severity, type, and prevalence across countries and time
- Based on WHO Child Growth Standards
- Enables cross-country and temporal comparisons

### Access Links

- **Kaggle dataset**: [Child Malnutrition UNICEF Dataset](https://www.kaggle.com/datasets/usharengaraju/child-malnutrition-unicef-dataset)
- **Official UNICEF data pages (2025 editions)**: [UNICEF Malnutrition Data](https://data.unicef.org/topic/nutrition/malnutrition/)

### Data Characteristics

- **Update frequency**: Periodic (varies by country)
- **Missing data**: Common, especially in:
  - Low-income countries
  - Conflict-affected regions
  - Countries with weak data collection systems
- **Standards**: Follows WHO Child Growth Standards
- **Data quality**: High (internationally validated)

---

## 2. GDP per Capita (PPP) – World Bank (WDI)

### Overview

- **Source**: World Bank – World Development Indicators (WDI)
- **Indicator code**: `NY.GDP.PCAP.PP.KD`
- **Variable name**: GDP per capita, PPP (constant 2017 international $)
- **Unit**: International dollars
- **Frequency**: Annual

### Description

Gross Domestic Product per capita adjusted for purchasing power parity (PPP). This measures the average economic output per person, adjusted for inflation and differences in cost of living between countries.

### Why It's Useful

Children in wealthier economies generally have better access to:

- Nutritious food
- Healthcare services
- Clean water and sanitation
- Maternal education
- Social protection programs

GDP per capita serves as a powerful macro-economic predictor of child malnutrition outcomes.

### Access Links

- **Official page**: [World Bank GDP per capita (PPP)](https://data.worldbank.org/indicator/NY.GDP.PCAP.PP.KD)

### Data Characteristics

- **Update frequency**: Annual
- **Missing data**: Some country-years missing
- **Limitation**: Does not reflect inequality within a country
- **Base year**: Constant 2017 international dollars

---

## 3. Refugee Population (Origin) – Our World in Data

### Overview

- **Source**: Our World in Data (based on UNHCR data)
- **Variable**: Refugee population by country or territory of origin
- **Unit**: Number of refugees
- **Frequency**: Annual

### Description

The number of people leaving a country due to conflict, political instability, persecution, or humanitarian crises. This variable captures forced displacement from the country of origin.

### Why It's Useful

High refugee outflows often indicate:

- Armed conflict
- Food insecurity
- Political instability
- Breakdown of government services
- Economic collapse

These conditions strongly influence child malnutrition rates. Refugee outflow serves as a proxy for national instability and humanitarian stress.

### Access Links

- **Data portal**: [Refugee Population by Country of Origin](https://ourworldindata.org/grapher/refugee-population-by-country-or-territory-of-origin?time=earliest..latest)

### Data Characteristics

- **Update frequency**: Annual
- **Source**: UNHCR (United Nations High Commissioner for Refugees)
- **Sensitivity**: Highly responsive to conflict patterns
- **Limitation**: May underestimate internal displacement (IDPs not included)

---

## 4. Female Educational Attainment – World Bank Education Data

### Overview

- **Source**: World Bank – Education Statistics
- **Variable**: Educational attainment, at least completed primary, population 25+ years, female (%)
- **Unit**: Percent (%)
- **Frequency**: Periodic

### Description

The percentage of adult women aged 25 or older who have completed at least primary education. This measures baseline female human capital and educational achievement.

### Why It's Useful

Maternal education is one of the strongest predictors of child nutrition. Higher education levels correlate with:

- Better child feeding practices
- Improved hygiene and sanitation practices
- Higher household income
- Greater healthcare utilization
- Lower risk of child malnutrition

This variable captures female human capital and caregiving capacity.

### Access Links

- **Official page**: [World Bank Education Statistics](https://data.worldbank.org/topic/education)

### Data Characteristics

- **Update frequency**: Periodic (every 3-5 years for many countries)
- **Missing data**: Common in low-income countries
- **Limitation**: Measures completion, not quality of education
- **Age group**: Women aged 25 and older

---

## 5. Prevalence of Undernourishment – FAOSTAT

### Overview

- **Source**: FAO – FAOSTAT Food Security Indicators
- **Variable**: Prevalence of undernourishment (3-year average)
- **Unit**: Percent (%)
- **Frequency**: Annual (with 3-year rolling average)

### Description

The percentage of the population whose habitual dietary energy intake is insufficient to maintain a healthy, active life. This is based on dietary energy supply, dietary energy requirements, and inequality in food access.

### Why It's Useful

Reflects national-level food security, dietary adequacy, and food system stability. Countries with higher undernourishment rates typically show higher child malnutrition prevalence, as household food insecurity directly impacts children.

### Access Links

- **Official page**: [FAO Food Security Indicators](https://www.fao.org/faostat/en/#data/FS)

### Data Characteristics

- **Update frequency**: Annual
- **Aggregation**: Uses 3-year rolling averages
- **Purpose of averaging**: Smooths short-term shocks and volatility
- **Limitation**: May not reflect individual-level consumption variation
- **Coverage**: Nearly all countries

---

## 6. Country Income Group – World Bank Classification

### Overview

- **Source**: World Bank – Country and Lending Groups
- **Variable**: Income group classification
- **Categories**: Low income, Lower-middle income, Upper-middle income, High income
- **Unit**: Categorical
- **Frequency**: Annual updates

### Description

The World Bank assigns every country to an income category based on Gross National Income (GNI) per capita. These groups reflect the overall level of national economic development.

### Why It's Useful

Income group classifications capture structural differences between countries that influence:

- Government capacity and public spending
- Healthcare system quality
- Sanitation and infrastructure development
- Food security and agricultural systems
- Education access and quality
- Vulnerability to economic shocks

Acts as a categorical control variable in statistical analysis.

### Access Links

- **Official page**: [World Bank Country Classifications](https://datahelpdesk.worldbank.org/knowledgebase/articles/906519-world-bank-country-and-lending-groups)
- **Data included in**: UNICEF JME dataset (see Source 1)

### Data Characteristics

- **Update frequency**: Annual (July 1 of each year)
- **Basis**: GNI per capita (Atlas method)
- **Categories**: Broad but meaningful
- **Use in modeling**: Must be encoded (e.g., ordinal or one-hot encoding)

---

## Data Integration Notes

### Temporal Alignment

- Most datasets are annual
- FAOSTAT uses 3-year rolling averages
- Some UNICEF data has irregular update frequencies
- Merging requires careful attention to year alignment

### Geographic Coverage

- All datasets include most countries globally
- Coverage gaps vary by:
  - Income level (more gaps in low-income countries)
  - Political stability (more gaps in conflict zones)
  - Data collection capacity

### Data Quality Considerations

1. **International standards**: UNICEF and WHO data follow rigorous standards
2. **Statistical methods**: World Bank and FAO use robust estimation methods
3. **Validation**: All sources undergo peer review and validation
4. **Transparency**: Methodologies are publicly documented

---

## Citation Recommendations

When using these data sources, cite:

- **UNICEF**: UNICEF, WHO, World Bank. Joint Child Malnutrition Estimates. [Year]. Available at: <https://data.unicef.org/topic/nutrition/malnutrition/>
- **World Bank**: World Bank. World Development Indicators. [Year]. Available at: <https://databank.worldbank.org/source/world-development-indicators>
- **UNHCR/OWID**: United Nations High Commissioner for Refugees (via Our World in Data). Refugee Statistics. [Year].
- **FAO**: Food and Agriculture Organization. FAOSTAT Food Security Indicators. [Year]. Available at: <https://www.fao.org/faostat/>

---

## Last Updated

29-Novermber-2025

## Maintained By

- Razan Ibrahim
- Huda
- Malak
