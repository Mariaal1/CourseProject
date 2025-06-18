#  “Analysis of the impact of information flow on stock prices” (Course Project)

This course project investigates how financial news sentiment influences short-term stock price changes. We use FinBERT (a finance-specific BERT model) to extract sentiment from financial news, and combine it with macroeconomic indicators (S&P 500 returns) to improve predictive accuracy.

##  Goal

To build a machine learning model that predicts next-day stock price movement magnitude based on:
- Sentiment extracted from financial news
- Macroeconomic signals (S&P 500 return)

##  Key Features

- FinBERT-based sentiment analysis on financial news
- Regression models predicting next-day price impact
- Hybrid model: combining text features with market indicators
- Evaluation across three companies: Honda (HMC), Intel (INTC), Google (GOOGL)
- Metrics: RMSE, MAPE, F1-score

##  Dataset

- **News**: Financial/economic news articles (2009–2023)
- **Stock Prices**: Daily OHLC for selected tickers
- **Macro**: S&P 500 daily return as market context

##  Results Summary

| Model                 | RMSE   | MAPE           | F1-score |
|----------------------|--------|----------------|----------|
| FinBERT              | 0.545  | 71,766,200.26% | 0.341    |
| FinBERT Fine-Tuned   | 0.023  | 9,023,962.65%  | 0.336    |
| FinBERT with Macro   | 0.022  | 2,206,747.41%  | 0.339    |

> ⚠ **Note**: MAPE is highly inflated due to division by very small actual returns. RMSE is the more reliable metric here.

##  Limitations

- High MAPE caused by near-zero returns in denominator
- No temporal modeling (e.g., LSTM/GRU not used)
- Only 3 companies analyzed
- Sentiment treated as discrete; no intensity scoring

##  Future Work

- Add sequence-aware models (LSTM, GRU)
- Expand stock universe (50+ companies)
- Use alternative macro indicators (VIX, sector ETFs)
- Streamline for real-time sentiment forecasting

##  Tech Stack

- Python 3.10+
- PyTorch, HuggingFace Transformers
- FinBERT (nlp model)
- pandas, NumPy, scikit-learn
- Jupyter Notebook

##  Project Structure

