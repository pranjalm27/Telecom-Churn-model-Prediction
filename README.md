# Machine Learning for Churn Prediction

## Project Overview

Customer churn is a critical metric for businesses, representing the percentage of customers who stop using a company's products or services over a specified period. Accurately predicting churn allows businesses to proactively engage with at-risk customers, potentially reducing churn rates and improving customer retention. In this project, I aimed to develop a machine learning model to predict customer churn using a dataset from a phone/internet service provider.

## Project Steps

### 1. Exploratory Data Analysis (EDA)
Began by loading and exploring the dataset, identifying key characteristics and understanding the distribution of features:
- The dataset contains 7,043 rows and 21 columns.
- There are no missing values, but the `TotalCharges` column needed to be converted from a string to a numeric type after handling whitespace values.

### 2. Data Cleaning
To prepare the data:
- Replaced whitespace in the `TotalCharges` column with `NaN` values and filled these using the column's median.
- The `customerID` column, which was not useful for modeling, was dropped.
- The `PaymentMethod` column was cleaned to simplify the categories.

### 3. Data Analysis
Conducted a thorough analysis of categorical and numeric features:
- Bar charts and scatter plots were used to identify correlations between features and churn.
- Key insights include the higher likelihood of churn among customers with month-to-month contracts, electronic checks as the payment method, and those lacking additional services like online security and tech support.

### 4. Data Preparation
To prepare the data for modeling:
- Categorical variables were encoded using `LabelEncoder` for binary variables and `get_dummies` for others.
- The dataset was split into training and testing sets, and used RandomUnderSampler to balance the training data.

### 5. Model Training and Evaluation
Trained and evaluated multiple machine learning models, including:
- Logistic Regression
- Decision Trees
- Support Vector Machines (SVM)

**Evaluation Metrics:**
- **Recall** was prioritized as it reflects the proportion of correctly identified churns.
- **Precision** was also considered to measure the accuracy of the positive predictions.

The models trained on balanced data yielded better recall results, with SVM showing the best performance.

### 6. Hyperparameter Tuning
Used GridSearchCV to tune the hyperparameters for the SVM and Logistic Regression models:
- The best recall score for SVM was 0.9319 with a `poly` kernel and `C=0.01`.
- The Logistic Regression model had a best recall score of 0.832 with `liblinear` solver and `C=0.001`.

### 7. Final Model Evaluation
The tuned SVM model was evaluated on the test set:
- The model achieved a recall of 0.94 for the churn class, indicating strong performance in identifying churning customers.
- The overall accuracy was 55%, which highlights the model's conservative approach to predicting churn, favoring recall over precision.

## Conclusion
This project successfully built a churn prediction model using machine learning, with a particular focus on maximizing recall to identify potential churners. The SVM model, after hyperparameter tuning, provided the best performance, making it a valuable tool for businesses aiming to reduce churn and improve customer retention.
