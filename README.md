# Instacart Market Basket Analysis

## Introduction

This project analyzes the Instacart Online Grocery Shopping Dataset 2017, aiming to understand customer purchasing behavior and predict which products will be in a user's next order. Instacart is an American technology company that operates as a same-day grocery delivery and pick-up service in the U.S. and Canada.

### Objectives:
- Analyze anonymized data of 3 million grocery orders from more than 200,000 Instacart users
- Discover hidden associations between products for better cross-selling and upselling
- Perform customer segmentation for targeted marketing
- Build a Machine Learning model to predict which previously purchased products will be in a user's next order

## Project Organization

```
.
├── 1_initial_exploration.ipynb        : Initial data exploration and analysis
├── 2_EDA.ipynb                        : In-depth Exploratory Data Analysis
├── 3_customer_cluster.ipynb           : Customer Segmentation using clustering
├── 4_market_basket_analysis.ipynb     : Market Basket Analysis for product associations
├── 5_ml_feature_extraction.ipynb      : Feature engineering and extraction for ML models
├── 6_ml_data_prep.ipynb               : Data preparation for modeling
├── 7_xgboost_model.ipynb              : XGBoost model for product reorder prediction
├── data/                              : Directory containing dataset files
├── img/                               : Directory containing generated plots and images
└── README.md                          : Project documentation (this file)
```

## Data Description

The dataset includes several files:
- `aisles.csv`: Contains 134 unique aisles
- `departments.csv`: Contains 21 unique departments
- `products.csv`: Contains 49,688 unique products and their aisle/department
- `orders.csv`: Contains 3,421,083 orders from 206,209 users
- `order_products__prior.csv` and `order_products__train.csv`: Contain products in each order and if they were reordered

## Key Findings from Exploratory Data Analysis

1. Most orders are made during daytime, with peaks on weekends.
2. Customers typically order once a week.
3. Fresh vegetables and fruits are the most popular departments.
4. Organic products have a high reorder rate despite lower overall volume.
5. Products added to cart earlier have a higher reorder percentage.

## Customer Segmentation

Using K-means clustering on product aisle data, we identified 5 distinct customer segments:
1. Water enthusiasts
2. Fresh produce lovers (vegetables)
3. Packaged produce and fruit buyers
4. Fresh fruit enthusiasts
5. Diverse, low-frequency shoppers

## Market Basket Analysis

Using the Apriori algorithm, we discovered product associations. Top pairs include:
- Limes and Large Lemons
- Organic Strawberries and Organic Raspberries
- Organic Avocado and Large Lemon

## Machine Learning Model

We built an XGBoost model to predict product reorders. Features include:
- Product-level features (e.g., reorder percentage, total orders)
- Aisle and Department-level features
- User-level features (e.g., average order day, total unique products bought)
- User-product level features (e.g., user's average add-to-cart order for a product)

The model achieved an AUC score of >75%, demonstrating strong predictive power for reorders.

## Future Work

- Implement collaborative filtering for product recommendations
- Explore deep learning models for prediction
- Analyze the impact of time and seasonality on purchasing patterns
- Incorporate pricing data for revenue optimization

## Requirements

- Python 3.7+
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost
- MLxtend (for market basket analysis)
