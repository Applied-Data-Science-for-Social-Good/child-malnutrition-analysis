# Child Malnutrition Analysis

Analysis of the determinants of child malnutrition using multi-source global datasets
(UNICEF, World Bank, FAO, UNHCR).

This project provides a full analytical workflow for understanding global
malnutrition patterns and the dependent factors linked to them. The
notebook combines multiple datasets and applies descriptive analysis,
statistical tests, trend exploration, and mixed effects regression modeling.

## Project Motivation

Malnutrition remains a major global issue driven by overlapping pressures
related to economic instability, limited food access, conflict exposure,
forced displacement, and unequal access to essential services. These pressures
interact across years and across countries. This project examines these
dynamics through a multi phase analysis pipeline to understand which
conditions are most strongly linked with variations in malnutrition indicators.

## Features

- End to end workflow in one Jupyter notebook
- Automated data loading and validation
- Exploratory visualizations and correlation analysis
- ANOVA and Tukey HSD statistical tests
- Time series trends across countries
- Mixed effects regression models with country level random effects
- Country level and income group comparisons
- Final merged analytical dataset
- Synthesized conclusions and recommendations

## Repository Structure

```text
malnutrition-analysis/
├── .github/
├── .vscode/
├── .gitignore
├── .ls-lint.yml
├── .markdownlint.yml
├── CONTRIBUTING.md
├── LICENSE
├── README.md # Main project README
├── guide.md # Root-level guide (optional)

├── 0_domain_study/
│ ├── README.md
│ └── guide.md

├── 1_datasets/
│ ├── 01_variable_dictionary.md
│ ├── 02_data_sources.md
│ ├── 03_constraints.md
│ ├── README.md
│ └── guide.md

├── 2_data_preparation/
│ ├── README.md
│ └── guide.md

├── 3_data_exploration/
│ ├── README.md
│ └── guide.md

├── 4_data_analysis/
│ ├── README.md
│ ├── analysis.md
│ ├── guide.md
│ ├── method.md
│ └── summary.md

├── 5_communication_strategy/
│ ├── README.md
│ ├── guide.md
│ └── report.md

├── 6_final_presentation/
│ ├── README.md
│ ├── guide.md
│ └── malnutrition_analysis_presentation.pdf
```

### Notebook Phases

- Phase 1: Data Loading and Objectives  
- Phase 2: Exploratory Data Analysis  
- Phase 3: Statistical Testing  
- Phase 4: Mixed Effects Modeling  
- Phase 5: Synthesis and Recommendations  

## Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook
- Required libraries:
  - pandas
  - numpy
  - matplotlib
  - seaborn
  - scipy
  - scikit-learn
  - statsmodels
  - openpyxl

### Installation

```bash
# Clone the repository
git clone git@github.com:Applied-Data-Science-for-Social-Good/child-malnutrition-analysis.git
cd malnutrition-analysis

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels openpyxl
```

### Data Setup

1. Download datasets from sources listed in `1_datasets\02_data_sources.md`
2. Follow steps listed in `2_data_preparation\README.md`

## Contributing

This is a research project. If you find errors or have suggestions, please open
an issue.

## Contact

- GitHub: [Huda Alamassi](https://github.com/hudaalamassi),
[Malak Battat](https://github.com/malakbattat), [Razan Ibrahim](https://github.com/Razan-O-Elobeid)

## Acknowledgments

- UNICEF for malnutrition data
- World Bank for economic indicators
- FAO for food security data
- UNHCR for refugee statistics (via Our World in Data)
