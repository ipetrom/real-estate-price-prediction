_the project was developed in March 2025_


# Real Estate Price Prediction

This project predicts real estate prices in Poland by combining **web-scraped** listings (Otodom) with **external** and **synthetic** datasets such as unemployment, inflation, salaries, and population statistics. It includes scraping notebooks, geocoding, preprocessing, optional synthetic data generation, and end-to-end modeling with a final report.

The process involves:
- Scraping offers (apartments, houses, studios) from Otodom.
- Generating synthetic observations to augment the dataset.
- Enriching listings with macroeconomic indicators.
- Geocoding addresses to obtain coordinates and neighborhood features.
- Preprocessing, merging all sources and creating final datasets.
- Training and evaluating ML models to predict prices.

---

## Project Structure

```
.
├── data/
│   ├── average_salary.csv
│   ├── data_final.csv
│   ├── gradual_unemployment_rate.csv
│   ├── inflation.xlsx
│   ├── otodom_apartment_offers.csv
│   ├── otodom_house_offers.csv
│   ├── otodom_offers_coordinates.csv
│   ├── otodom_studio_offers.csv
│   └── population.csv
├── web_scraping/
│   ├── WebScraping_apartments.ipynb
│   ├── WebScraping_house.ipynb
│   └── WebScraping_studio.ipynb
├── Coordinates.ipynb
├── real_estate_prediction.ipynb
├── raport_rep_project.html
└── README.md
```

---

## How It Works

### Web Scraping
`web_scraping_*.ipynb` collect listing data (title, price, area, rooms, description, address, date posted). Tools used: `requests`, `BeautifulSoup`, `pandas`. Results are saved to CSVs in `data/`.

### Coordinates Assignment
`Coordinates.ipynb` geocodes addresses to lat/lon, fills missing coordinates and computes simple spatial features (distance to center, neighborhood).

### Synthetic Observations Generation
Notebooks/scripts create synthetic listings by sampling and perturbing real distributions to increase dataset diversity for model training.

### External Data Merging
Listings are enriched with:
- Average Salaries
- Unemployment Rate
- Population Statistics
- Inflation Rates

Merged datasets form `data/data_final.csv`. Example sources: GUS, World Bank, NBP.

### Model Building
`real_estate_prediction.ipynb` performs cleaning, feature engineering, model training (e.g., Linear Regression, Random Forest, XGBoost) and evaluation (RMSE, MAE, R²).

---

## Raport

See the full analysis and visualizations in:
- `raport_rep_project.html`

---

## Technologies Used

- Python 3.8+
- Jupyter Notebook
- pandas, numpy
- scikit-learn
- xgboost / lightgbm
- matplotlib, seaborn, folium
- BeautifulSoup, requests, geopy

---
