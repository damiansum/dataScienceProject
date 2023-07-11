# Market Crash Prediction Project

This project aims to predict a market crash, defined as a 10% drop within a 5-day period, using historical stock market data.

## Tools and Packages Used

- Python: The project is implemented using Python, a popular language for data science due to its readability and extensive library support.
- Pandas: Used for data loading, preprocessing, and manipulation. Pandas provides data structures and functions needed to manipulate structured data.
- Numpy: Used for numerical computations and array manipulations.
- Matplotlib: Used for data visualization, specifically for plotting the closing prices over time.
- Seaborn: Another data visualization library used to create a boxplot for volume.
- Scikit-learn: A machine learning library used for feature selection, data splitting, model creation, training, and evaluation. Specific modules used include:
    - `SelectKBest` and `f_classif` for feature selection.
    - `train_test_split` for splitting the data into training and test sets.
    - `LogisticRegression` for creating the Logistic Regression model.
    - `GridSearchCV` for hyperparameter tuning.
    - `accuracy_score` for model evaluation.

## Project Steps

1. **Data Loading and Preprocessing:** The data is loaded using `pandas.read_csv()`. A new column 'Return_5d' is created to represent the 5-day percent change.

2. **Exploratory Data Analysis (EDA):** Basic EDA is performed to get a better understanding of the data. This includes getting a statistical summary of the data, information about the DataFrame, and visualizing the data.

3. **Creating the 'Crash' Column:** A new column 'Crash' is created. If 'Return_5d' is less than -10, 'Crash' is 1, indicating a market crash; otherwise, it's 0.

4. **Feature Engineering:** New columns for 1-day, 2-day, and 3-day percent changes are created. A new column for 1-day lag of the 'Volume' column is created. A new feature for volatility is created as the standard deviation of 'Return_1d', 'Return_2d', and 'Return_3d'.

5. **Feature Selection:** SelectKBest with f_classif is used to select the top 5 features.

6. **Splitting the Data:** The data is split into a training set and a test set using `train_test_split()`.

7. **Model Creation and Training:** A Logistic Regression model is created and fitted to the training data.

8. **Hyperparameter Tuning:** GridSearchCV is used to find the best parameters for the Logistic Regression model.

9. **Model Evaluation:** The model is used to predict the market crash on the test data. The accuracy of the model is calculated using `accuracy_score()`.

10. **Model Interpretation:** The coefficients of the logistic regression model are printed to understand the relationship between the features and the likelihood of a market crash.

## Findings

The Logistic Regression model was able to predict the occurrence of a market crash with an accuracy of approximately 99.98% on the test data. While this is an extremely high accuracy rate, it may suggest overfitting, although additional validation would be needed to confirm this.

The 'Return_5d' feature, representing the 5-day percent change, was found to be the most influential feature in predicting a market crash. This suggests that the performance of the stock in the past 5 days is a significant indicator of a potential market crash.

Other significant features include 'Return_1d', 'Return_2d', 'Return_3d', and 'volatility'. These features represent the 1-day, 2-day, 3-day percent changes, and the standard deviation of these percent changes respectively. These features indicate that both recent performance and volatility of the stock are important factors in predicting a market crash.
