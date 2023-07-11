# Data Science Project - Market Crash Prediction

This is a data science project that focuses on predicting market crashes using historical stock market data. The project involves data preprocessing, exploratory data analysis (EDA), feature engineering, feature selection, model training, hyperparameter tuning, evaluation, and interpretation.

## Project Overview

The main goal of this project is to develop a predictive model that can identify market crashes based on historical stock market data. The dataset used for this project is obtained from the S&P 500 index.

## Installation

To run this project, make sure you have the following libraries installed:

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

You can install these libraries using pip:

```
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Usage

To use this project, follow the steps below:

1. Open the project in Google Colab using the provided Colab link.
2. Run the code cells in sequential order.

## Data

The dataset used in this project is stored in a CSV file named 'SPX.csv'. The file contains historical stock market data for the S&P 500 index, including information such as date, open price, high price, low price, close price, adjusted close price, volume, and the 5-day percent change in the close price.

## Project Steps

The project can be divided into several steps:

1. **Data Loading and Preprocessing**: The dataset is loaded into a pandas DataFrame, and the 5-day percent change in the close price is calculated.

2. **Exploratory Data Analysis (EDA)**: Statistical summaries and visualizations are used to explore the dataset. This includes analyzing the statistical characteristics of the data and visualizing the closing prices over time and the volume distribution.

3. **Feature Engineering**: New features are created based on the existing data. This involves calculating 1-day, 2-day, and 3-day percent changes in the close price, creating a lagged version of the volume column, and computing a volatility measure based on the standard deviation of the percent change features.

4. **Feature Selection**: The top 5 features are selected using the SelectKBest method based on the ANOVA F-value. These selected features will be used for model training.

5. **Splitting the Data**: The data is split into a training set and a test set using the train_test_split function from scikit-learn. The test set constitutes 20% of the total data.

6. **Model Training**: A Logistic Regression model is chosen and trained on the training data. Logistic Regression is suitable for binary classification problems like market crash prediction.

7. **Hyperparameter Tuning**: GridSearchCV is used to find the optimal hyperparameters for the Logistic Regression model. The hyperparameters tuned are 'C' and 'penalty'.

8. **Model Evaluation**: The trained model is used to predict market crashes on the test data, and the accuracy of the model is calculated using the accuracy_score metric.

9. **Model Interpretation**: The coefficients of the Logistic Regression model are examined to understand the relationship between the selected features and the likelihood of a market crash.

## Results

The project achieves a high accuracy rate of approximately 99.98% in predicting market crashes using the selected features. The most influential feature in predicting market crashes is the 5-day percent change in the close price ('Return_5d').

The coefficients of the Logistic Regression model indicate that higher values of the selected features, such as 'Return_5d', 'Return_1d', 'Return_2d', 'Return_3d', and 'volatility', make a market crash less likely according to the model.

## Conclusion

This data science project demonstrates the application of machine learning techniques to predict market crashes using historical stock market data. The trained model achieves a high accuracy rate and provides insights into the relationship between selected features and market crashes.
