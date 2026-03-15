
# Singapore HDB Resale Market Analysis

This project analyzes the Singapore HDB resale housing market using geospatial analysis and interactive visualization.

The notebook explores how resale price per square meter varies across buildings and how MRT/LRT accessibility relates to housing prices. The project combines data cleaning, spatial analysis, and both static and interactive map visualization.

## Project Goals

- Analyze spatial variation in HDB resale prices
- Aggregate transaction data to the building level
- Explore relationships between MRT accessibility and resale prices
- Produce both static geospatial visualizations and interactive maps

## Data Sources

Typical sources used in this analysis include:

- Singapore HDB resale transaction dataset
- Building geolocation data
- MRT/LRT station locations
- Rail line geospatial data
- Basemap tiles from CartoDB (via Contextily)

## Methods

Key techniques used in this project:

- Data cleaning and transformation using pandas
- Geospatial operations using GeoPandas
- Building-level aggregation of resale transactions
- Quantile clipping for map visualization
- Static map rendering using matplotlib + geopandas
- Interactive mapping using folium
- Integration of MRT rail lines and station data

## Technologies

Python libraries used:

- pandas
- numpy
- geopandas
- matplotlib
- folium
- branca
- shapely
- contextily

## Repository Structure

```
singapore-hdb-resale-analysis/
│
├─ singapore_hdb_resale_trends.ipynb
├─ README.md
├─ requirements.txt
├─ .gitignore
│
├─ data/
│   ├─ raw/
│   └─ processed/
│
├─ outputs/
│   ├─ maps/
│   └─ figures/
```

## How to Run

Install dependencies:

```
pip install -r requirements.txt
```

Start Jupyter:

```
python -m notebook
```

Then open:

```
singapore_hdb_resale_trends.ipynb
```

Run all cells to reproduce the analysis.

## Example Outputs

The project produces:

- Building-level price per square meter maps
- MRT accessibility overlays
- Interactive folium-based housing market explorer
- Spatial visualizations of resale price trends

## Notes

This repository is intended as a personal data science portfolio project demonstrating:

- data analysis
- geospatial analytics
- housing market analysis
- interactive visualization
