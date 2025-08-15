# Premier League 2025/26 Season Prediction 

## Overview
This project predicts the **final standings** of the 2025/26 English Premier League using **machine learning** and **season simulations**.  
Historical match results, team market values, and promoted team performance are combined to train **Random Forest** and **XGBoost** models that forecast match outcomes.

The season is then simulated **10 times**, and the average results are used to estimate each team’s expected points, title probability, and top-4/relegation chances.  
All results are analyzed and visualized in **Power BI**.

---

## Data Sources
- **Premier League Historical Stats** — match scores, goals, shots, cards (2005/06–2024/25)
- **Transfermarkt Market Values** — squad and player values aggregated to team totals
- **Championship Data** — last-season performance of promoted teams

---

## Methodology

1. **Data Cleaning & Feature Engineering**
   - Remove irrelevant columns (e.g., referee, match time)
   - Create features such as `Market_Value_Ratio` and `Total_Market_Value_Diff`
   - Merge promoted team stats from Championship data

2. **Model Training**
   - Train **Random Forest** and **XGBoost** classifiers
   - Target: Match result (`H` = home win, `D` = draw, `A` = away win)
   - Evaluate with cross-validation

3. **Season Simulation**
   - Predict probabilities for all 25/26 fixtures
   - Simulate the season **10 times**
   - Aggregate results for average points and probabilities

4. **Visualization (Power BI)**
   - Predicted standings table with title/top-4/relegation %
   - Bar charts of total and new player market values
   - Historical context of past EPL champions & CL qualifications

---

## Sample Predictions (Top 6 – Average Points)
| Rank | Team        | Avg. Points |
|------|-------------|-------------|
| 1    | Man City    | 77.2 |
| 2    | Arsenal     | 76.8 |
| 3    | Liverpool   | 71.0 |
| 4    | Chelsea     | 65.2 |
| 5    | Man United  | 63.8 |
| 6    | Tottenham   | 61.4 |

- **Man City** & **Arsenal** each have ~40% title probability and 100% top-4 probability
- **Liverpool** holds a 60% top-4 probability
- No relegation threat for any of the top 6 in simulations

---

## Tech Stack
- **Python** — pandas, NumPy, scikit-learn, XGBoost
- **Power BI** — visualization of standings, market values, and historical context
- **Jupyter Notebooks** — EDA, feature engineering, and model training
- **Git** — version control

---

## How to Run
```bash
# Clone the repository
git clone https://github.com/yourusername/epl-2025-26-prediction.git
cd epl-2025-26-prediction

# Install dependencies
pip install -r requirements.txt

# Run the season simulation
python scripts/simulate_season.py
