# Nonprofit Direct Marketing Analytics Project

## Project Overview

This project develops an end-to-end analytics pipeline to help a nonprofit organization optimize its direct mail fundraising campaign. Using historical donor data, machine learning models are built to predict both **donor response likelihood** and **expected donation amount**, and the results are translated into **actionable business decisions** through an expected profit framework.

The goal is to move beyond mass mailing and identify **which individuals should be contacted to maximize net fundraising profit**.

---

## Business Problem

Direct mail campaigns are costly, and mailing every individual often leads to financial losses.
This project addresses two key business questions:

1. **Who is likely to donate?** (Classification problem)
2. **How much will they donate if they do?** (Regression problem)

The final solution recommends a targeted mailing list that maximizes expected profit after accounting for mailing costs.

---

## Data Description

Two datasets are used:

* **nonprofit.xlsx** – Training dataset containing donor outcomes
* **nonprofit_score.xlsx** – Scoring dataset without outcomes (used for deployment)

Key variables include:

* Demographics (region, income, homeownership, children)
* Past donation behavior (gift history, recency, frequency)
* Targets:

  * `donr`: Donor indicator (1 = donor, 0 = non-donor)
  * `damt`: Donation amount

---

## Methodology

### 1. Data Preparation

* Cleaned and explored data using descriptive statistics and visualizations
* Converted categorical variables using one-hot encoding
* Scaled numeric features where required
* Split data into training and validation sets

---

### 2. Classification Modeling (Donor Prediction)

Models evaluated:

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Random Forest

Evaluation metrics:

* Accuracy, ROC-AUC, confusion matrix
* Business-driven threshold selection based on expected profit

**Best model:** Random Forest
Used to predict donor probability on unseen scoring data.

---

### 3. Regression Modeling (Donation Amount Prediction)

Applied **only to predicted donors**.

Models evaluated:

* Multiple Linear Regression (with regularization)
* KNN Regressor
* Decision Tree Regressor

Evaluation metrics:

* RMSE
* R²

**Best model:** Linear Regression
Used to estimate donation amounts for predicted donors.

---

### 4. Business Evaluation & Profit Optimization

Expected profit calculated as:

Expected Profit=(Predicted Donation Amount×Predicted Donation Probability)−Mailing Cost

* Compared **baseline mass mailing** vs **model-driven targeting**
* Ranked prospects by expected profit
* Selected only individuals with **positive expected profit**

---

## Key Results

* Mass mailing strategy resulted in **negative expected profit**
* Model-based targeting produced a **substantial profit improvement**
* Over **96% of prospects** were identified as profitable to mail
* Demonstrated strong alignment between statistical performance and business value

---

## Deployment

* Models applied to `nonprofit_score.xlsx`
* Generated predictions for:

  * Donor classification
  * Donation amount
  * Expected profit
* Final scored dataset saved as a **CSV file** for business use and submission

---

## Files in This Repository

* `nonprofit.xlsx` – Training data
* `nonprofit_score.xlsx` – Scoring data
* `nonprofit_score_predictions.csv` – Final deployment output
* `Project_Notebook.ipynb` – Full analysis and modeling workflow
* `Project_Report.pdf` – Final project report
* `README.md` – Project documentation

---

## Tools & Technologies

* Python
* pandas, NumPy
* scikit-learn
* matplotlib, seaborn
* Jupyter Notebook

---

## Key Skills Demonstrated

* Predictive modeling (classification and regression)
* Feature engineering and preprocessing
* Model evaluation using statistical and business metrics
* Profit-driven decision making
* End-to-end model deployment

---

## Author

**Hiren Bista**
M.S. Geography (GIS & Data Analytics)
University of North Texas

---
