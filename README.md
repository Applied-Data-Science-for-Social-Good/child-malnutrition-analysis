# Child Malnutrition Analysis

Analysis of the determinants of child malnutrition using multi-source global datasets
(UNICEF, World Bank, FAO, UNHCR).

## 🎯 Project Objectives

1. Identify key socioeconomic determinants of child malnutrition
2. Analyze cross-country patterns and time trends
3. Provide evidence-based insights for policy interventions

## 📊 Data Sources

- **UNICEF JME**: Child malnutrition indicators (stunting, wasting)
- **World Bank**: GDP per capita, education statistics
- **FAOSTAT**: Food security indicators
- **UNHCR/OWID**: Refugee population data

See [docs/02_data_sources.md](docs/02_data_sources.md) for detailed information.

## 📁 Repository Structure

```text
malnutrition-analysis/
│
├── README.md                # This file
├── LICENSE                  # Project license
├── .gitignore               # Git ignore rules
│
├── data/
│   ├── raw/                 # Original datasets (not in git)
│   ├── processed/           # Cleaned datasets
│   └── final/               # Merged analysis-ready data
│
├── docs/
│   ├── 01_variable_dictionary.md  # Variable definitions
│   ├── 02_data_sources.md         # Dataset sources
│   ├── 03_constraints.md          # Limitations
│   └── 04_methods.md              # Methodology
│
├── notebooks/
│   ├── 01_exploration_dependents.ipynb
│   ├── 02_phase_1_analysis.ipynb
│   ├── 03_phase_2_analysis.ipynb
│   ├── 04_phase_3_country_trends.ipynb
│   └── 05_results_interpretation.ipynb
│
└── communication/
    ├── report.md            # Final report
    └── presentation.pptx    # Presentation
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook
- Required libraries (see requirements.txt)

### Installation

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/malnutrition-analysis.git
cd malnutrition-analysis

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Data Setup

1. Download datasets from sources listed in `docs/02_data_sources.md`
2. Place raw data in `data/raw/`
3. Run cleaning notebooks in order

## 📖 Documentation

- **[Variable Dictionary](docs/01_variable_dictionary.md)**: All variables used
in analysis
- **[Data Sources](docs/02_data_sources.md)**: Detailed source information
- **[Constraints](docs/03_constraints.md)**: Data limitations and gaps
- **[Methods](docs/04_methods.md)**: Analytical methodology

## 📈 Analysis Phases

### Phase 1: Cross-Country Analysis

Complete-case dataset analysis examining relationships between malnutrition and
key predictors.

## 🤝 Contributing

This is a research project. If you find errors or have suggestions, please open
an issue.

## 📝 License

## 📧 Contact

- Email:
- GitHub:

## 🙏 Acknowledgments

- UNICEF for malnutrition data
- World Bank for economic indicators
- FAO for food security data
- UNHCR for refugee statistics (via Our World in Data)
