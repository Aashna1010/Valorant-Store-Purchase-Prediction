# Valorant Store Purchase Prediction

## Project Overview

This project aims to predict whether a player will purchase a Valorant skin from the in-game store using machine learning. The dataset used in this project is synthetically generated to simulate player behavior such as spending capacity, wishlist usage, discounts, and purchase history.
    The main objective is to analyze customer behavior and build a model that can predict if a player is likely to purchase a skin based on several features.
    This type of predictive system can help gaming companies understand customer purchasing patterns and design better marketing strategies such as targeted discounts or recommendations.

---

# Project Objectives

The objectives of this project are:

- Generate a synthetic dataset representing Valorant store customers
-  Perform Exploratory Data Analysis (EDA) to understand purchasing behavior
-  Visualize important patterns in the dataset
-  Train machine learning models to predict purchases
-  Evaluate and compare different classification algorithms

---

# Technologies and Libraries Used

### Programming Language

- Python

### Libraries

Pandas
- Used for data manipulation and dataset creation.

NumPy
- Used for numerical operations and probability calculations.

Matplotlib
- Used to create basic visualizations and graphs.

Seaborn
- Used to create more advanced statistical visualizations.

Scikit-Learn
- Used to build and evaluate machine learning models.

The following models from Scikit-Learn were used:

* Logistic Regression
* Decision Tree Classifier
* Random Forest Classifier

---

# Dataset Description

The dataset contains 3000 simulated players interacting with the Valorant store.

Each row represents a player and their interaction with a skin in the store.

## Dataset Features

| Feature            | Description                                              |
| ------------------ | -------------------------------------------------------- |
| skin_name          | Name of the skin                                         |
| weapon_type        | Weapon category of the skin                              |
| base_price_vp      | Original price of the skin in Valorant Points            |
| discount_percent   | Discount applied to the skin                             |
| final_price_vp     | Price after discount                                     |
| region             | Player region (Asia, EU, NA)                             |
| rank               | Competitive rank of the player                           |
| age_group          | Age category of the player                               |
| avg_monthly_spend  | Estimated monthly spending capacity                      |
| previous_purchases | Number of skins purchased before                         |
| wishlist_added     | Whether the skin was added to wishlist (1 = Yes, 0 = No) |
| event_active       | Whether a special event is active                        |
| purchased          | Target variable indicating if the skin was purchased     |


The target variable for prediction is:

purchased

 1 = Player purchased the skin
 0 = Player did not purchase the skin

---

# Data Generation

Since real Valorant purchase data is not publicly available, the dataset was generated using random simulation techniques.

The simulation includes behavioral logic such as:

- Wishlist increases purchase probability
- Higher discounts increase purchase probability
- Players with more previous purchases are more likely to buy again
- Players with higher spending capacity are more likely to purchase expensive skins

This approach allows the dataset to simulate realistic purchasing behavior.

---

# Exploratory Data Analysis (EDA)

EDA was performed to explore patterns and relationships within the dataset.

Several visualizations were created to better understand the data.

## Purchase Distribution

A bar chart was created to show how many players purchased a skin compared to those who did not.

Results showed approximately:

40% purchased
60% did not purchase

This indicates a slightly imbalanced dataset.

---

## Average Monthly Spending by Region

Players were grouped by region to analyze their average spending capacity.

This visualization helps identify whether certain regions have higher spending potential.

---

## Discount vs Purchase

A bar plot was created to analyze the relationship between **discount percentage and purchase behavior.

The visualization shows that players are more likely to purchase skins when higher discounts are applied.

---

## Wishlist vs Purchase

Another bar plot compares purchase behavior between players who added skins to their wishlist and those who did not.

Players who added skins to their wishlist showed a significantly higher purchase rate. This indicates that wishlist behavior is a strong indicator of purchase intent.

---

## Previous Purchases vs Purchase

Players with a higher number of previous purchases were more likely to buy skins again. This suggests that loyal customers tend to make repeat purchases.

---

## Spending Capacity vs Purchase

A comparison was made between average monthly spending and purchasing behavior.

Players with higher spending capacity are more likely to purchase skins, especially when the final price is within their budget.

---

## Weapon Type Purchase Rate

The purchase rate for different weapon skins was analyzed to identify which weapon categories tend to sell more frequently.

---

## Correlation Heatmap

A correlation heatmap was generated for all numerical variables.

The heatmap helps identify relationships between variables such as:

* Average monthly spending
* Previous purchases
* Discount percentage
* Final price
* Purchase decision

Variables with stronger correlations can be more useful for prediction models.

---

# Data Preprocessing

Before training machine learning models, the data was prepared using the following steps:

### Removing Unnecessary Columns

Some columns were removed because they were not useful for prediction:

skin_name(text label not useful for modeling)
base_price_vp (redundant since final price already exists)

### Encoding Categorical Variables

Categorical variables such as region, rank, and weapon type were converted into numerical format using one-hot encoding with "pd.get_dummies()".

This converts categories into binary columns that machine learning models can process.

### Train-Test Split

The dataset was divided into:

80% training data
20% testing data

This allows the model to be trained on one portion of the data and evaluated on unseen data.

---

# Machine Learning Models

Three classification models were trained and compared.

## Logistic Regression

Logistic Regression is a statistical model used for **binary classification problems** where the output variable has two possible outcomes.

Model Accuracy: 0.63

---

## Decision Tree

Decision Trees classify data by creating a structure of rules that split the dataset based on feature values.

Model Accuracy: 0.625

---

## Random Forest

Random Forest is an ensemble learning algorithm that builds multiple decision trees and combines their predictions.

This helps improve stability and reduce overfitting.

Model Accuracy: 0.656

Random Forest achieved the highest accuracy among the three models.

---

# Model Evaluation

### Confusion Matrix

The confusion matrix for Logistic Regression was:

[[270 101]
 [121 108]]


This matrix shows:

* True Negatives: 270
* False Positives: 101
* False Negatives: 121
* True Positives: 108

This helps evaluate how well the model distinguishes between purchased and non-purchased cases.

---

### Classification Report

The classification report provides three important metrics:

Precision
- Measures how many predicted purchases were actually correct.

Recall
- Measures how many actual purchases the model correctly identified.

F1 Score
- A balance between precision and recall.

For purchase prediction, the F1 score was approximately 0.49, indicating moderate performance.

---

# Results Summary

| Model               | Accuracy  |
| ------------------- | --------- |
| Logistic Regression | 0.63      |
| Decision Tree       | 0.625     |
| Random Forest       | 0.656     |

Random Forest produced the best performance among the tested models.

---

# Conclusion

This project demonstrates how machine learning can be used to predict customer purchasing behavior in a gaming store environment.

The project successfully:

* Generated a simulated dataset representing Valorant store customers
* Performed exploratory data analysis to identify behavioral patterns
* Built and evaluated multiple classification models
* Compared model performance

Among the tested models, Random Forest performed the best with an accuracy of approximately 65.6%.

---

# Future Improvements

The project could be improved by:

* Collecting real player behavior data
* Adding more features such as playtime or match activity
* Performing hyperparameter tuning
* Increasing dataset size
* Applying advanced models such as Gradient Boosting or XGBoost

These improvements could significantly increase prediction accuracy and model reliability.

---


