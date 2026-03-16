# Singapore HDB Resale Analysis

This repository contains two Jupyter notebooks for analyzing and modeling the Singapore HDB resale market.

The workflow is:

1. Run `singapore_hdb_resale_trends.ipynb`
2. Run `singapore_hdb_resale_prediction.ipynb`

The first notebook prepares geospatial outputs and geocode cache files that are also used by the second notebook.

## Project Overview

This project studies Singapore HDB resale transactions from both a **market trends** and a **price prediction** perspective.

### Notebook 1: `singapore_hdb_resale_trends.ipynb`
This notebook focuses on data cleaning, geocoding, geospatial aggregation, and visualization.

Main tasks:
- load the HDB resale transaction CSV
- clean and transform transaction data
- geocode unique building addresses using OneMap
- merge transactions with latitude / longitude
- aggregate transactions to the building level
- compute recent median resale price metrics
- compute 5-year price change metrics
- download and overlay MRT / LRT station and rail line layers
- generate static PDF maps
- generate interactive HTML maps
- export building-level summary data

Outputs include:
- `outputs/sg_hdb_psm_map.pdf`
- `outputs/sg_hdb_psf_map.pdf`
- `outputs/sg_hdb_5y_change_map.pdf`
- `outputs/sg_hdb_psm_interactive.html`
- `outputs/sg_hdb_5y_change_interactive.html`
- `outputs/building_metrics.csv`
- `cache/address_geocodes.csv`

### Notebook 2: `singapore_hdb_resale_prediction.ipynb`
This notebook focuses on feature engineering, model training, evaluation, and model interpretation.

Main tasks:
- load the HDB resale transaction CSV
- load geocode results from `cache/address_geocodes.csv`
- create predictive features
- split data into train / validation / test sets
- train and compare multiple machine learning models
- evaluate model performance
- visualize actual vs predicted prices
- inspect feature importance and SHAP explanations
- create geospatial market heatmaps
- visualize high-dimensional structure with dimension reduction

Models included:
- Linear Regression
- Polynomial Regression
- Random Forest
- k-Nearest Neighbors
- MLP Regressor
- XGBoost
- LightGBM

## Data Requirements

Place the following file in the project root before running the notebooks:

- `ResaleflatpricesbasedonregistrationdatefromJan2017onwards.csv`

The trends notebook will create cache files that the prediction notebook reuses.

## Recommended Run Order

### 1) Create and activate an environment
```bash
python -m venv .venv
```

On macOS / Linux:
```bash
source .venv/bin/activate
```

On Windows PowerShell:
```powershell
.\.venv\Scripts\Activate.ps1
```

### 2) Install dependencies
```bash
pip install -r requirements.txt
```

### 3) Start Jupyter
```bash
jupyter notebook
```

### 4) Run notebooks in this order
```text
singapore_hdb_resale_trends.ipynb
singapore_hdb_resale_prediction.ipynb
```

## Repository Structure

```text
.
├── singapore_hdb_resale_trends.ipynb
├── singapore_hdb_resale_prediction.ipynb
├── README.md
├── requirements.txt
├── .gitignore
├── cache/
│   ├── address_geocodes.csv
│   └── geocode_batches/
├── outputs/
│   ├── *.pdf
│   ├── *.html
│   └── building_metrics.csv
└── ResaleflatpricesbasedonregistrationdatefromJan2017onwards.csv
```

## Python Libraries Used

Core analysis and visualization:
- pandas
- numpy
- matplotlib
- geopandas
- shapely
- contextily
- folium
- branca
- requests
- tqdm

Modeling and interpretation:
- scikit-learn
- xgboost
- lightgbm
- shap
- umap-learn

Notebook environment:
- jupyter

## Notes

- The raw resale CSV is not included in this repository.
- Geocoding depends on OneMap availability and may take time on the first run.
- The trends notebook is designed to save geocode progress in batches so it can be resumed.
- Some modeling sections may be computationally heavy depending on your machine.
