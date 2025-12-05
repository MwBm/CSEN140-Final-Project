# Disneyland Wait Time Prediction

A machine learning project comparing multiple forecasting models to predict wait times for Disneyland California Adventure rides.

## Project Structure

```
├── data/
│   ├── csvFiles/                    # Raw data sources
│   │   ├── disney_wait_times.csv    # Historical wait times
│   │   ├── disneyland_hours_2024_2025.csv
│   │   ├── disneyland_tiers_2024_2025.csv
│   │   ├── holidays_2024_2025.csv
│   │   └── weather_data.csv
│   ├── mergingAndCleaningLogic/     # Data preprocessing notebooks
│   ├── results/                     # Model output CSVs
│   └── final_merged_data.csv        # Processed dataset
├── models/
│   ├── seasonalNaive.ipynb          # Baseline model
│   ├── XGBoost.ipynb                # XGBoost with cross-validation
│   └── NHITS.ipynb                  # Neural forecasting model
├── comparison/
│   └── compare.ipynb                # Model comparison and analysis
└── requirements.txt
```

## Installation

```bash
pip install -r requirements.txt
```

## Models

| Model              | Description                                       |
| ------------------ | ------------------------------------------------- |
| **Seasonal Naive** | Baseline using same time last week                |
| **XGBoost**        | Gradient boosting with temporal cross-validation  |
| **NHITS**          | Neural Hierarchical Interpolation for Time Series |

## Features Used

- **Temporal**: Hour, day of week, month, weekend flag
- **External**: Temperature, precipitation, holiday flag, park tier

## Usage

1. Run data preprocessing: `data/mergingAndCleaningLogic/mergingData.ipynb`
2. Train models: Run notebooks in `models/`
3. Compare results: `comparison/compare.ipynb`

## Data

- **Date Range**: July 2024 - June 2025
- **Records**: ~590,000 wait time observations
- **Rides**: 30+ attractions (seasonal/redundant rides filtered)
