# NBA-AllStar-Predictions
A machine learning pipeline that identifies All-Star caliber performance by balancing traditional box scores with advanced metrics
## Project Overview
NBA All-Star selections are often influenced by non-statistical factors like market size, national television exposure, and "legacy" reputation. This project aims to: 
* Remove Human Bias: Create a purely data-driven benchmark for "All-Star" performance. 
* Identify "Snubs": Highlight players with high statistical probabilities who were overlooked by voters. 
* Quantify Impact: Determine which metrics (VORP, Win Shares, Usage %) most strongly correlate with the "All-Star" brand.🛠️ 
## Technical Stack & Methodology
* Language: Python
*Libraries: Pandas, Scikit-learn, Matplotlib, Seaborn, Joblib
* Model: Random Forest Classifier

* Optimization: Hyperparameter tuning via GridSearchCV with 5-fold cross-validation.
* Ranking Logic: Implemented a Top-K Ranking algorithm to select the exact number of players corresponding to the current season's roster size.
## Feature Engineering
To improve model performance beyond raw box scores (PPG, RPG, APG), We integrated several advanced metrics:
* VORP (Value Over Replacement Player): Measures a player's overall contribution relative to a "bench" level player.
* WS/48 (Win Shares per 48 Minutes): An estimate of the number of wins contributed by a player per 48 minutes.Usage %: An estimate of the percentage of team plays used by a player while they were on the floor.
* as_legacy: A custom-engineered feature tracking the cumulative number of previous All-Star appearances to account for veteran recognition bias. 
## Model Performance
Following hyperparameter optimization, the model achieved the following metrics on the 2026 test set:
* Accuracy:	98.0%
* Precision:	0.81
* Recall:	0.81
* F1-Score:	0.81

## How to Run Locally 
Clone the repository: git clone https://github.com/ajruvalcaba148/NBA-AllStar-Predictions.git

Make Virtual Enviornment: python3 -m venv .venv
Activate Virtual Enviornment: source .venv/bin/activate
Install dependencies: pip install -r requirements.txt
Go to notebooks/nba_predict.ipynb
Click Run All to run All Cells in Order

Explore the notebook: Open notebooks/nba_predict.ipynb to see the data cleaning, feature importance plots, and final predictions.
## Future Improvements
Team Success Integration: Incorporate team seed/win percentage as a feature.
Position Constraints: Factor in the mandatory frontcourt/backcourt roster requirements.

## Contributors
Anthony Ruvalcaba, Owen Rotenberg, Patrick Smith

Computer Science, CSU Fullerton

License

Distributed under the MIT License. See LICENSE for more information.
