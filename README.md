

# LINK Price Prediction Using Machine Learning

This project seeks to use machine learning to predict tomorrow's price change for the cryptocurrency LINK.

## 1. Problem Statement

The project aims to explore the feasibility of creating price predictions for the cryptocurrency LINK. Unlike some other major cryptocurrencies such as BTC and ETH, which have significant stability and predictability due to their large following and available data, LINK presents challenges due to its heightened volatility and lack of extensive data. 

Cryptocurrency markets are highly volatile, with prices fluctuating rapidly due to various factors such as news events, market sentiment, regulatory changes, etc. Predicting exact future prices is inherently challenging due to this volatility. Given these challenges, I gave opted to design a model which predicts whether the price will go up or down tomorrow, rather than attempting to forecast a specific price. Additionally, binary predictions often times are more useful for traders who are primarily interested in making decisions based on whether the price is likely to move in a particular direction rather than the exact magnitude of the price movement.

## 2. Data Description & Transformation

The dataset used is obtained from Yahoo Finance, providing a time-series of LINK-USD prices including opening, high, low, and closing prices, as well as trading volume on each day. Additionally, sentiment data on market fear and greed indexes are incorporated.

* Data Transformation and Clean-up
  * Removing Unnecessary Columns: The 'Adj Close' column was removed from the dataset as it duplicates the 'Close' column, considering that LINK does not involve     stock splits or halving events.

  * Handling Missing Values: No missing values were detected in the dataset. However, caution was taken to handle missing data appropriately if encountered.
Date Formatting: Date fields were formatted to ensure consistency and compatibility across datasets. The 'Date' columns were converted to datetime format to facilitate filtering and merging operations.

  * Filtering: Data filtering was performed to ensure consistency between the LINK price data and sentiment data. Dates were filtered to match the relevant time period for analysis, ensuring alignment between the datasets.

  * Merging Datasets: The cleaned and filtered datasets were merged based on the 'Date' column to incorporate sentiment data into the LINK price dataset for comprehensive analysis.
    
  * Incorporation of Technical Analysis: Bollinger Bands and moving averages, technical analysis tools, were incorporated into the dataset. Bollinger bands provide insights into potential overvalued and undervalued instances in the price data, enhancing the predictive power of the model.

## 3. Models and Evaluation

### Models

* Algorithms Used
  * Random Forests
  * XGBoost

* Initial Model
  * Utilized a Random Forest classifier as the base model.
* Implementing XGBoost Classifier
  * Adopted the XGBoost classifier and performed backtesting.

* Target Variable
  * Daily price change signal of either positive or negative movement for the next day.

 * Backtesting Process

### Evaluation

* Iterative Testing on Historical Data
  * Backtesting involved splitting the historical dataset into multiple training and testing sets. The model was trained on earlier portions of the dataset and tested on subsequent periods, simulating real-world trading scenarios. This iterative process allowed for the evaluation of model performance across various market conditions and timeframes.

* Assessment of Precision Scores
*  The precision scores obtained from backtesting were used to evaluate the model's accuracy and effectiveness in predicting price movements. Precision scores measure the model's ability to make correct predictions, particularly for positive instances (i.e., correctly predicting price increases or decreases).

* Validation of Model Performance
 * By comparing predicted price movements with actual movements in the testing sets, the model's performance was validated. Consistent and high precision scores across multiple testing periods indicate the model's reliability and predictive power in forecasting cryptocurrency price movements.

## 4. Results

* Initial Model Evaluation
  * Random Forest Classifier: The initial model achieved a prediction accuracy of approximately 48%. This performance was fairly on par with random chance, indicating the need for further refinement.

* Incorporation of Sentiment Data
  * Enhanced Model with Sentiment Analysis: Sentiment data on market fear and greed indexes were incorporated, resulting in a slight improvement in accuracy to around 49.56%. While the addition of sentiment data provided some insights, it did not significantly enhance the model's predictive power.

* Implementation of XGBoost Classifier
  * XGBoost Model with Backtesting: The adoption of the XGBoost classifier, along with backtesting techniques, led to a notable increase in accuracy to about 53.64%. This model demonstrated better performance compared to the Random Forest approach, indicating the effectiveness of gradient boosting algorithms for cryptocurrency price prediction.

* Integration of Additional Predictor Variables
  * Incorporating Moving Averages: 30-day and 60-day moving averages were added as predictor variables, resulting in a precision score of 57.81%. These moving averages provided insights into the trend and momentum of LINK's price movements, contributing to improved prediction accuracy.
  * Utilizing Technical Analysis (Bollinger Bands): Bollinger Bands, a technical analysis tool, were incorporated to identify potential overvalued and undervalued instances in the price data. While this addition increased the precision score to 58.56%, the impact was limited due to the low frequency of such outliers in the dataset.

### Final Conclusions

The project demonstrated the feasibility of predicting price movements of lesser-known cryptocurrencies such as LINK, despite the challenges posed by their volatility and limited data availability. Gradient boosting algorithms, particularly XGBoost, proved to be effective in improving prediction accuracy compared to traditional machine learning models like Random Forest. Incorporating additional predictor variables, such as moving averages and technical analysis indicators, enhanced the model's performance by providing deeper insights into price trends and potential market anomalies.

Despite the improvements achieved, the precision score of 58.56% suggests that predicting cryptocurrency price movements remains a challenging task. Overall, the project highlights the importance of incorporating diverse data sources and advanced machine learning techniques in cryptocurrency price prediction, offering valuable insights for investors and traders in navigating the volatile cryptocurrency markets.

