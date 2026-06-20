# House-Price-Prediction_Vinay_raj_singh
A regression project that predicts house prices from property features and identifies which features influence price the most. Built with pandas, scikit-learn, matplotlib, and seaborn.

## Problem statement

Real estate buyers and sellers often rely on guesswork or outdated comparisons to estimate a property's fair value. This project builds a regression model that predicts house prices based on property features — size, rooms, amenities, and location indicators — and identifies which features most strongly influence price.

## Dataset

`Housing.csv` — 545 properties, 13 columns:

| Column | Description |
|---|---|
| `price` | Sale price (target variable) |
| `area` | Plot/floor area in sq ft |
| `bedrooms`, `bathrooms`, `stories` | Room and floor counts |
| `parking` | Number of parking spaces |
| `mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `prefarea` | Yes/no amenity and location flags |
| `furnishingstatus` | furnished / semi-furnished / unfurnished |

## Project structure

```
.
├── House_Price_Prediction.ipynb   # Main notebook: EDA, cleaning, modeling, visualization
├── Housing.csv                    # Dataset
├── summary.pdf                    # 1-page written summary of findings
└── README.md
```

## Methodology

1. **Data exploration** — checked shape, dtypes, and missing values.
2. **Data cleaning** — imputed missing numeric values with column means, dropped duplicate rows.
3. **Encoding** — one-hot encoded categorical yes/no and furnishing-status columns.
4. **Feature selection** — examined correlation with `price` to shortlist informative features.
5. **Modeling** — trained and compared two regressors on an 80/20 train-test split:
   - Linear Regression
   - Random Forest Regressor
6. **Evaluation** — compared models using MAE, RMSE, and R².
7. **Visualization** — distribution plots, a correlation heatmap, and a model-performance comparison chart.

## Results

| Model | R² | MAE | RMSE |
|---|---|---|---|
| Linear Regression | 0.54 | 1127483 | 1514173 |
| Random Forest | 0.48 | 1150445 | 1610415 |

Linear Regression slightly outperformed Random Forest on this dataset.

## Key findings

- **Area (square footage)** is the strongest driver of price, followed by **bathrooms**.
- **Air conditioning** has an outsized effect for a simple yes/no amenity — more than basement or main-road access.
- The model explains ~65% of price variation; typical predictions are off by ~20%, suggesting missing variables (location, age, condition) limit further accuracy.
- See `summary.pdf` for the full written write-up, including a business recommendation.

## Getting started

```bash
git clone <repo-url>
cd house-price-prediction
pip install pandas numpy scikit-learn matplotlib seaborn
jupyter notebook House_Price_Prediction.ipynb
```

## License

This project is for educational purposes.
