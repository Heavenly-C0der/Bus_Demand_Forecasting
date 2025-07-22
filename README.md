# 🚌 Route-wise Bus Seat Demand Forecasting

> Hackathon project to predict total seat bookings for intercity bus routes 15 days before the actual date of journey.

## 🎯 Problem Statement

The task is to build a predictive model that forecasts the number of seats to be booked for a given **bus route and journey date**, using booking and search data available **15 days in advance**.

### Provided Data:
- **Seats Booked**: Target variable (historical demand)
- **Date of Journey (DOJ)**: Travel date
- **Date of Issue (DOI)**: Booking date
- **Search Count**: Number of user searches for a DOJ on a specific DOI
- **Route Information**: Source and destination IDs

**Example**: For a journey on `30-Jan-2025`, predict the final demand using data available on `15-Jan-2025`.

---

## 🛠️ Approach

- **Label Encoding** of route identifiers (`srcid`, `destid`).
- Created training datasets grouped by route, preparing feature sets and targets for each route individually.
- Used **Optuna** to find optimal hyperparameters for each model (XGBoost).
- Trained individual models **per route**, enabling fine-tuned route-level predictions.

### ✨ Feature Highlights:
- Advance booking gap (DOJ - DOI)
- Temporal features like day-of-week, month
- Search trends as leading indicators
- Route-specific trends captured via per-route modeling

---

## 🔍 Model

- **Model Type**: LightGBM Regressor
- **Tuning**: Hyperparameters tuned via **Optuna**
- **Validation Strategy**: Time-based holdout
- **Evaluation Metric**: RMSE  
- ✅ **Validation RMSE Achieved**: **192**

---


## 🧰 Tech Stack

- Python, Pandas, NumPy
- XGBoost Regressor, Optuna, Scikit-learn
- Matplotlib, Seaborn (for EDA)

---


