### Project Title

**Author**
Nina Kaushik

#### Executive summary
This project investigates whether machine learning models can predict short-term stock returns using a combination of 
technical indicators and fundamental company metrics. Historical stock price data and financial fundamentals were collected 
for a diversified set of large-cap U.S. equities. Features such as momentum, volatility, and valuation ratios were engineered 
and used to train regression models.
I evaluated linear modeling approaches: Ordinary Least Squares (OLS), Ridge regression, and Lasso regression. Model 
performance was evaluated using Mean Squared Error (MSE) and out-of-sample R². Results indicate that predictive power for 
short-horizon equity returns is limited, with R² values near zero. However, the modeling framework demonstrates how financial 
signals can be systematically evaluated using machine learning techniques.
#### Rationale
Predicting stock market movements is one of the most challenging problems in finance. Even small predictive signals can be economically 
valuable when applied at scale in quantitative trading strategies.
Understanding whether technical indicators and fundamental metrics provide predictive power can help investors and researchers evaluate
the efficiency of financial markets and develop systematic investment strategies.
Accurate predictions of the stock market can help people and businesses make profitable investment decisions. It also helps investors 
manage risk and plan for the future.

#### Research Question
Can short-term stock returns be predicted using technical indicators and fundamental company characteristics?
Do features such as momentum, volatility, trading volume, and valuation ratios provide predictive power for 5-day forward stock returns?

#### Data Sources
The project uses financial market data retrieved using the yfinance API.
Data includes: Price Data: Daily open, high, low, close; Trading volume
Technical Indicators: 1-day return; 5-day return; 10-day volatility; 20-day volatility; volume z-score; 10-day momentum
Fundamental Indicators: Price-to-earnings ratio; Forward P/E; Price-to-book ratio
The dataset consists of a diversified group of large-cap U.S. equities across technology, finance, retail, and industrial sectors.

#### Methodology
The modeling process consisted of several steps.

Data Preparation
  Historical price data was downloaded for selected large-cap stocks.
  Technical indicators were computed from price and volume data.
  Fundamental metrics were retrieved using the Yahoo Finance API.
  The target variable was defined as 5-day forward stock return.
Feature Engineering
  Features included: Technical Indicators; 1-day return; 5-day return; 10-day volatility; 20-day volatility; Volume z-score; 10-day momentum; 
  Fundamental Indicators; P/E ratio; Forward P/E; Price-to-book; Beta
Data Splitting
  A time-based split was used to avoid lookahead bias.
  Training data: Before January 1, 2025
  Testing data: After January 1, 2025
Model Training
  Three regression models were trained:
    Ordinary Least Squares (baseline)
    Ridge Regression (L2 regularization)
    Lasso Regression (L1 regularization)
  Features were standardized prior to model training.
Evaluation Metrics
  Two evaluation metrics were used.
    Mean Squared Error (MSE)
    R² 
  MSE was chosen as the primary metric because it directly measures prediction error magnitude.

#### Results
The regression models produced very low out-of-sample R² values, approximately: R² ≈ 0.007
This indicates that the models explain less than 1% of the variance in short-term stock returns. While this may appear small, 
it is consistent with the finance literature. Short-term equity returns are known to be highly noisy and difficult to predict 
due to market efficiency and the influence of unpredictable news events. Regularized models such as Ridge and Lasso produced 
results similar to the baseline OLS model, suggesting that the available features contain only weak predictive signals. Overall, 
the results highlight the difficulty of forecasting short-horizon market movements using simple technical and fundamental indicators.

Although the predictive models produced low R² values, this does not imply that the analysis lacks practical value. Financial markets 
are extremely noisy environments, and even small predictive signals can be economically meaningful when deployed at scale. In quantitative 
investing, predictive models are often applied across hundreds or thousands of securities simultaneously. Even a model with very modest 
predictive accuracy can generate profitable strategies when combined with diversification and disciplined risk management. The modeling 
framework developed in this project demonstrates how machine learning can systematically evaluate potential trading signals using historical 
data. Investment firms can extend this framework by incorporating additional data sources such as macroeconomic indicators, alternative 
datasets, or market sentiment. Ultimately, this type of analysis forms the foundation for data-driven investment strategies used by hedge 
funds, asset managers, and quantitative trading firms.

#### Next steps
Incorporate additional financial indicators such as macroeconomic variables.
Explore nonlinear machine learning models such as Random Forest or Gradient Boosting.
Increase the dataset to include a broader universe of stocks.
Incorporate sentiment analysis from financial news or earnings transcripts.
Evaluate model performance using trading strategy simulations.

#### Outline of project
https://github.com/ninakaushik/Capstone_Module_20/blob/main/Capstone_Project_Module_20_final.ipynb

