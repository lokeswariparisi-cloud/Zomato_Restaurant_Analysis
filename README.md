# Zomato Restaurant Rating Prediction Using Machine Learning

## Project Overview

This project analyzes the Zomato restaurant dataset and uses Machine Learning techniques to predict the **Aggregate Rating** of restaurants.

The project is implemented as a **Regression** problem because the target variable, `Aggregate rating`, is a numerical value ranging from 0 to 5.

The project includes data cleaning, exploratory data analysis (EDA), feature engineering, feature selection, regression model training, model evaluation, model comparison, and final restaurant rating prediction.

---

## Project Details

* **Domain:** Data Science & Machine Learning
* **Sub-domain:** Machine Learning
* **Problem Type:** Regression
* **Application Area:** Restaurant / Food Service Analytics
* **Target Variable:** `Aggregate rating`
* **Programming Language:** Python
* **Platform:** Google Colab

---

## Tools and Libraries

The following tools and Python libraries are used:

* Python
* Google Colab
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn

---

## Problem Statement

Zomato contains restaurant information such as ratings, customer votes, average cost, price range, online delivery, table booking, and geographical location.

It can be difficult to predict the aggregate rating of a restaurant based on these factors.

Therefore, this project uses Machine Learning regression algorithms to predict the **Aggregate Rating** of Zomato restaurants and compare the performance of different regression models to identify the final model.

---

## Project Objectives

The main objectives of this project are:

1. To load and understand the Zomato restaurant dataset.
2. To clean and preprocess the dataset.
3. To analyze restaurant-related features using Exploratory Data Analysis.
4. To study relationships between restaurant features and aggregate ratings.
5. To perform feature engineering.
6. To select relevant features for prediction.
7. To predict restaurant aggregate ratings using Machine Learning.
8. To train and compare different regression algorithms.
9. To evaluate the models using regression metrics.
10. To select the final model based on model performance.
11. To generate predictions for test data.
12. To predict the rating of a sample new restaurant.

---

## Dataset

The project uses the **Zomato.csv** dataset.

The dataset contains restaurant-related information such as:

* Restaurant ID
* Restaurant Name
* Country Code
* City
* Address
* Locality
* Longitude
* Latitude
* Cuisines
* Average Cost for two
* Currency
* Has Table booking
* Has Online delivery
* Is delivering now
* Switch to order menu
* Price range
* Aggregate rating
* Rating color
* Rating text
* Votes

---

## Project Workflow

The project follows an 18-step Data Science and Machine Learning workflow:

1. Import Libraries
2. Load Dataset
3. Understand Dataset
4. Check Missing Values
5. Check Duplicate Values
6. Data Cleaning
7. Handle Invalid Values
8. EDA Preparation
9. Univariate Analysis
10. Bivariate Analysis
11. Multivariate Analysis
12. Outlier Handling
13. Feature Engineering
14. Feature Selection and Target Selection
15. Encoding Categorical Data
16. Train-Test Split
17. Train, Evaluate and Compare Regression Models
18. Final Prediction, Insights, Conclusion and Future Scope

---

## Data Cleaning

The dataset is checked for:

* Missing values
* Duplicate records
* Invalid aggregate rating values
* Invalid price range values
* Negative vote values
* Negative average cost values

Duplicate records are removed from the dataset.

An outlier analysis is also performed on the `Average Cost for two` column using the **IQR (Interquartile Range)** method.

---

## Exploratory Data Analysis

### Univariate Analysis

The project analyzes individual variables such as:

* Aggregate Rating
* Price Range
* Votes
* Average Cost for Two
* Table Booking
* Online Delivery

Different visualizations such as histograms and count plots are used to understand the distribution of the data.

### Bivariate Analysis

The following relationships are analyzed:

* Price Range vs Aggregate Rating
* Votes vs Aggregate Rating
* Average Cost for Two vs Aggregate Rating
* Online Delivery vs Aggregate Rating
* Table Booking vs Aggregate Rating

Box plots and scatter plots are used for the analysis.

### Multivariate Analysis

Multivariate analysis includes:

* Correlation analysis
* Correlation heatmap
* Pair plots

The relationships among numerical variables are analyzed to understand the factors associated with restaurant ratings.

---

## Feature Engineering

The categorical Yes/No service-related columns are converted into numerical values.

### Table Booking

```text
Has Table booking
Yes → 1
No  → 0
```

### Online Delivery

```text
Has Online delivery
Yes → 1
No  → 0
```

### Delivering Now

```text
Is delivering now
Yes → 1
No  → 0
```

These transformed columns are used as Machine Learning features.

---

## Feature Selection

The final features used for the regression models are:

```text
Average Cost for two
Price range
Votes
Table booking
Online delivery
Delivering now
Longitude
Latitude
```

### Target Variable

```text
Aggregate rating
```

The model learns the relationship between the selected restaurant features and the restaurant's aggregate rating.

---

## Train-Test Split

The dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

The following setting is used:

```python
test_size = 0.20
random_state = 42
```

The training data is used to train the Machine Learning models, while the testing data is used to evaluate their performance.

---

## Machine Learning Models

Three regression algorithms are trained and compared.

### 1. Linear Regression

Linear Regression is used as a basic regression model to predict the aggregate rating.

### 2. Decision Tree Regression

Decision Tree Regression is used to model non-linear relationships between restaurant features and ratings.

### 3. Random Forest Regression

Random Forest Regression is an ensemble learning algorithm that combines multiple decision trees to make predictions.

The Random Forest model is configured with:

```python
n_estimators = 100
random_state = 42
```

---

## Model Evaluation

The regression models are evaluated using the following metrics:

### MAE – Mean Absolute Error

Measures the average absolute difference between actual and predicted ratings.

### MSE – Mean Squared Error

Measures the average squared difference between actual and predicted ratings.

### RMSE – Root Mean Squared Error

Measures the square root of the Mean Squared Error.

A lower RMSE indicates better prediction performance.

### R² Score

Measures how well the model explains the variation in the target variable.

---

## Model Comparison

The performance of the following models is compared:

| Model                    |
| ------------------------ |
| Linear Regression        |
| Decision Tree Regression |
| Random Forest Regression |

The notebook automatically identifies the model with the **lowest RMSE**:

```python
best_model_name = results.loc[results["RMSE"].idxmin(), "Model"]
```

The selected model is then stored as the final model and used for prediction.

---

## Final Model

Based on the model evaluation performed in the project, **Random Forest Regression** is selected as the final model because it provides better overall prediction performance among the evaluated models.

The final model is used to:

* Predict aggregate ratings for the test dataset.
* Compare actual and predicted ratings.
* Predict the rating of a new restaurant.

---

## Sample Prediction

A sample new restaurant is created using the following information:

```text
Average Cost for two: 800
Price range: 2
Votes: 250
Table booking: Yes
Online delivery: Yes
Delivering now: No
Longitude: 78.48
Latitude: 17.40
```

The final model predicts the restaurant's **Aggregate Rating**.

The prediction is restricted to the valid rating range of **0 to 5**.

---

## Project Outputs

The project produces:

* Dataset information
* Missing-value analysis
* Duplicate-value analysis
* Data cleaning results
* EDA visualizations
* Univariate analysis
* Bivariate analysis
* Multivariate analysis
* Correlation analysis
* Outlier analysis
* Feature engineering
* Feature selection
* Model comparison
* Regression evaluation metrics
* Final model selection
* Actual vs Predicted ratings
* Sample restaurant rating prediction

---

## Conclusion

This project uses the Zomato restaurant dataset to predict **Aggregate Rating** using Machine Learning regression techniques.

The project performs data preprocessing, Exploratory Data Analysis, feature engineering, feature selection, model training, and evaluation.

Three regression algorithms are evaluated:

* Linear Regression
* Decision Tree Regression
* Random Forest Regression

Among the evaluated models, **Random Forest Regression is selected as the final model** based on its overall prediction performance in this project.

The final model can be used to predict restaurant ratings based on features such as customer votes, average cost, price range, table booking, online delivery, delivery status, and geographical location.

---

## Future Scope

The project can be further improved by:

1. Adding more restaurant features.
2. Testing additional Machine Learning regression algorithms.
3. Applying hyperparameter tuning.
4. Developing a web application for restaurant rating prediction.
5. Building a restaurant recommendation system.
6. Using real-time restaurant data.
7. Creating an interactive dashboard for restaurant analytics.
8. Adding advanced geographical analysis using interactive maps.
9. Using customer reviews for sentiment analysis.
10. Developing personalized restaurant recommendations.

---

## Project Structure

```text
Zomato-Restaurant-Analysis/
│
├── Zomato_Restaurant_Analysis.ipynb
├── Zomato.csv
├── README.md
└── Dashboard/
```

---

