# Grocery Recommendation System

## Overview

This project aims to enhance the grocery shopping experience by providing personalized recommendations based on users' purchase histories. Utilizing data from the Instacart dataset available on Kaggle, the system employs clustering and association rule mining techniques to generate relevant product suggestions.

## Dataset
The dataset for this project is available on [Kaggle](https://www.kaggle.com/datasets/psparks/instacart-market-basket-analysi). This dataset includes both categorical and continuous variables essential for clustering and recommendation analysis.

The dataset consists of six CSV files:
- **Aisle.csv**: Information about different aisles in the grocery store.
- **Department.csv**: Details regarding product departments.
- **Products.csv**: Contains product details.
- **Orders.csv**: Information about user orders.
- **Order_products_train.csv**: Data on products in training orders.
- **Order_products_prior.csv**: Data on products in previous orders.


## Methodology

### 1. User Clustering with K-Means
- The K-Means algorithm groups users into seven clusters based on their purchase history, allowing for analysis of buying trends.
- Steps:
  1. Determine the number of clusters.
  2. Randomly initialize centroids.
  3. Assign data points to the nearest centroid.
  4. Update centroids until convergence.

### 2. Association Rules for Recommendations
- Association rules are calculated to determine the likelihood of purchasing products together.
- Key metrics used:
  - **Frequency**: Number of times products A and B are bought together.
  - **Support**: Probability of buying products A and B together.
    - Support(A, B) = Freq(A, B) / total number of pairs.
  - **Lift**: Measures the strength of the association between products.
    - Lift(A, B) = Support(A, B) / (Support(A) * Support(B)).

### 3. Recommendation Logic
- Upon adding a new product to the cart, the system identifies user clusters that have previously purchased the item.
- The top products with the strongest associations from these clusters are recommended.

### 4. Search Engine with Autosuggestion
- Implements pattern searching to suggest similar products based on user input in the search bar.


