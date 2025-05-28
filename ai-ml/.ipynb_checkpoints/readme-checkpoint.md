Price‑Mover Classifier

I built a simple machine learning project that tries to predict whether a stock or cryptocurrency price will go up or down the next day. I'm new to ML, so I focused on using just price and volume data to keep things straightforward.

What I Did

Data Loading: I used the Yahoo Finance API (yfinance) to download daily price data (Open, High, Low, Close) and trading volume for any ticker (for example, BTC-USD or AAPL).

Data Cleaning: If the data had hierarchical column names, I flattened them so I could easily work with the columns.

Feature Engineering: I created a few basic features:

Return1: the percentage change in closing price from the previous day

MA5 and MA10: the 5‑day and 10‑day moving averages of the closing price

VolChg: the percentage change in daily volume

Label Creation: I made a target column that is 1 if tomorrow’s closing price is higher than today’s, and 0 otherwise.

Model Training: I trained two simple models:

Logistic Regression, because it’s easy to interpret

Random Forest, to see if a non‑linear model helps

Evaluation: I checked each model’s accuracy, precision, recall, and confusion matrix to understand how often they predict correctly.

Interpretability: I plotted the coefficients for Logistic Regression and feature importances for Random Forest to see which features mattered most.

Key Things to Know

I only used past price and volume data—no news articles or sentiment analysis.

I split the data in time order (first 80% for training, last 20% for testing) to avoid peeking into the future.

This is a very basic approach and may not work well for real trading decisions.

What I’d Try Next

Add more technical indicators like RSI or MACD.

Use a rolling (walk‑forward) validation method instead of a single train/test split.

Tune hyperparameters (e.g., regularization for LR or tree depth for RF) to improve performance.

Experiment with more advanced models (like LSTM) once I’m more comfortable with ML.