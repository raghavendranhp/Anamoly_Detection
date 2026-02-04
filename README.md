# **Project Title:** Unsupervised Anomaly Detection on Transaction Data

---

## Project Overview

This project focuses on identifying anomalous transaction behavior using **unsupervised machine learning techniques**.
Since no labeled anomalies are available, the goal is to detect rare and unusual patterns that deviate from normal user behavior.

---

## Dataset Description

The dataset contains **500 transaction records** with the following key attributes:

* Transaction amount and frequency
* Account age
* Device type and transaction location
* Domestic vs international transaction indicator

The data includes both numerical and categorical features relevant to behavioral analysis.

---

## Approach

### 1: Data Understanding & EDA

* Loaded and inspected the dataset
* Verified data types, missing values, and duplicates
* Performed exploratory analysis using summary statistics, histograms, boxplots, and correlation analysis
* Identified extreme values and skewed distributions indicating potential anomalies

### 2: Feature Engineering

Additional features were created to enhance anomaly detection:

* `amount_per_transaction`
* `is_new_account`
* `amount_deviation`

These features capture transaction intensity, account maturity risk, and deviation from normal behavior.

### 3: Model Selection

* The problem was framed as an **unsupervised anomaly detection task**
* **Isolation Forest** was selected due to its efficiency and suitability for unlabeled, high-dimensional data

### 4: Model Training & Prediction

* Categorical features were one-hot encoded
* Numerical features were scaled
* Isolation Forest was trained assuming ~5% anomalies
* Each transaction was assigned:

  * An anomaly label (Normal / Anomaly)
  * An anomaly score

### 5: Evaluation & Insights

* Anomalies were validated using visual inspection and statistical comparisons
* Key behavioral patterns were identified and translated into business insights

---

## Key Findings

* High transaction amounts and high value per transaction strongly influence anomalies
* New accounts are more frequently associated with anomalous behavior
* International transactions show higher anomaly likelihood
* Extreme transaction frequency within a day is a strong deviation indicator

---

## Business Recommendations

* Flag high-value transactions from new accounts for review
* Apply stricter checks on international transactions
* Use anomaly scores as a risk-ranking mechanism
* Combine ML-based detection with rule-based controls

---

## Assumptions

* Anomalies are rare compared to normal transactions
* Most transactions represent legitimate behavior
* Extreme deviations across multiple features indicate higher risk
* Historical labels are unavailable

---

## Limitations

* No ground-truth labels to measure accuracy
* Results depend on the chosen contamination rate
* Legitimate but rare behavior may be flagged as anomalous
* Contextual factors such as user intent are not captured

---

## Future Improvements

* Incorporate time-based behavioral features
* Add historical user-level aggregation
* Collect labeled data for semi-supervised learning
* Experiment with One-Class SVM and Autoencoders

---

## Files Included

* `anomaly_detection.ipynb` – Complete notebook
* `anomaly_detection_dataset.csv` – Raw dataset
* `cleaned_transactions.csv` – Cleaned dataset
* `anomaly_predictions.csv` – Model output with anomaly labels
* `README.md` – Project documentation

---
