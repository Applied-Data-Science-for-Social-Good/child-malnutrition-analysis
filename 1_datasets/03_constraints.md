# Data Constraints and Limitations

## Missing Data Patterns

Global datasets on malnutrition and socio-economic indicators are incomplete.  
Key patterns include:

- **Geographic Gaps**  
  - Low-income countries tend to have more missing observations due to limited  
    survey capacity.  
  - Conflict-affected regions often lack consistent reporting, creating blind  
    spots in crisis zones.  
  - Small island nations may be excluded entirely from some datasets due to  
    their size or limited survey coverage.  

- **Temporal Gaps**  
  - **UNICEF JME:** Irregular updates; some countries go 5+ years without new  
    survey data.  
  - **World Bank Education Indicators:** Updated every 3–5 years for many  
    countries.  
  - **Economic indicators (GDP, inflation, etc.):** Generally more complete but
    may lag in politically unstable countries.  

- **Variable-Specific Issues**  

  - Stunting, wasting, and severe wasting are survey-based and reported in irregular
years. They are subject to sampling error, seasonality effects, and recall bias.

  - Maternal education data is often missing in older datasets and in countries with
low survey coverage. This can limit analyses that rely on education as a predictor.

  - Refugee and displacement data are incomplete for internally displaced persons
and short-term flows. These datasets likely underestimate actual populations.

  - GDP per capita and other economic indicators are generally complete, but they
mask subnational disparities and regional inequality within countries.

  - Undernourishment data comes from intermittent surveys. Differences in
measurement definitions can introduce inconsistencies across countries and years.

---

## Known Limitations

### Measurement Issues

- **Malnutrition indicators:** Based on intermittent surveys; subject to  
  measurement error.  
- **Economic indicators:** National averages ignore within-country inequality.  
- **Refugee and displacement data:** Often incomplete for internal movements.  

### Methodological Constraints

- **Data quality and comparability:** Surveys differ in design, timing, and  
  definitions.  
- **Missingness handling:** Imputation/interpolation may introduce bias, especially
  where gaps are long.  
- **Multicollinearity:** Strong correlations among socio-economic predictors require
  PCA or dimensionality reduction.  
- **Temporal analysis:** Sparse, irregular time series reduce confidence in causal
  interpretation or Granger-type assessments.  

---

## Summary

The datasets provide insight into global trends but must be interpreted with  
caution. Observed patterns reflect true differences and artifacts from data gaps,
measurement error, and methodological constraints. Analyses are descriptive and
correlational, not causal, and should guide hypotheses, planning, and further  
research rather than definitive policy prescriptions.
