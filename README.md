# Metal Futures Trading using Machine Learning
# Author : Darshit Shah

## Project Overview
This project examines whether simple machine learning models can generate economically meaningful trading signals in metal futures markets. Using daily data for Gold, Silver, and Copper over approximately 15 years, we evaluate multiple models and compare their trading performance against a buy-and-hold benchmark.

Rather than focusing on maximizing predictive accuracy, the goal is to assess whether small predictive edges can improve risk-adjusted performance when combined with a disciplined trading strategy.

---

## Assets Covered
- Gold Futures  
- Silver Futures  
- Copper Futures  

---

## Data
- Frequency: Daily  
- Time Period: ~2010 to 2025 (approximately 15 years)  
- Split: Time-based train/test split to avoid look-ahead bias  

---

## Feature Engineering
The following features are constructed consistently across all assets:
- 1-day and 5-day returns  
- Moving averages (5-day and 20-day)  
- Moving average gap  
- Rolling volatility measures  
- Volume-based features (log volume and volume changes)  
- High-volatility regime indicator  

---

## Models Implemented
- Random Forest (regression-based directional signal)  
- K-Nearest Neighbors (classification)  
- XGBoost (classification)  
- Simple Ensemble (combining Random Forest and KNN signals)  

All strategies are long/flat only with a fixed position size of one unit.

---

## Trading Strategy
- Go long one unit when the model predicts an upward move  
- Stay flat when the model predicts a downward move or shows low confidence  
- No short-selling  
- No transaction costs included  

A buy-and-hold strategy is used as the benchmark.

---

## Evaluation Metrics
Model performance is evaluated using:
- Directional accuracy  
- Annualized return  
- Annualized volatility  
- Sharpe ratio (0% risk-free rate)  
- Number of trades and win rate  
- Maximum flat period  
- Profit and loss streak statistics  

---

## Key Findings
- Small predictive edges (around 52–57% accuracy) can be economically meaningful when paired with disciplined trading rules.  
- Simpler models (KNN and Ensemble) tend to be more robust than more complex models.  
- Model performance varies across assets:
  - Gold benefits from timing due to strong trends.  
  - Silver is difficult to outperform using timing strategies.  
  - Copper shows the clearest gains from timing-based models.  

---

## Files in This Folder
- ml-metal-futures-trading.ipynb – Final Jupyter Notebook with full analysis  
- report_ml-metal-futures-trading.pdf – Final written report (PDF)  
- README.md – Project documentation  
- gold_15y.csv
- silver_15y.csv
- copper_15y.csv

---

## How to Run
1. Open the Jupyter Notebook: `v2_final_15y.ipynb`  
2. Ensure required Python libraries are installed (pandas, numpy, scikit-learn, xgboost)

---

## Limitations

- Transaction costs, slippage, and margin requirements are not modeled.

- Strategies are long-or-flat only with fixed position sizing.

- Results may depend on specific market regimes within the sample period.

---

## Academic Context

This project was completed as part of a graduate-level course in Algorithmic Trading and Portfolio Management and has been refactored for professional and portfolio use.

---

## License

This project is released under the MIT License.