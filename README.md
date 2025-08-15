# MSCS_634_ProjectDeliverable_3

## Overview
This project applies **classification**, **clustering**, and **pattern mining** techniques to the `heart.csv` dataset to explore predictive modeling for heart disease, identify patient groupings, and discover frequent attribute patterns.

The work is part of **Deliverable 3** for MSCS 634 and demonstrates:
- Multiple classification models with performance evaluation
- Hyperparameter tuning
- Clustering analysis with visualization
- Association rule mining for pattern discovery

---

## Dataset Summary

- **Dataset Name**: Heart Disease UCI
- **Source**: [Kaggle] https://www.kaggle.com/datasets/ineubytes/heart-disease-dataset
- **Records**: 1026
- **Attributes**: 14 (including target)
- **Objective**: Predict the presence (1) or absence (0) of heart disease based on features like age, sex, cholesterol, resting blood pressure, maximum heart rate, and more.

**Columns include:**
- Demographic: `age`, `sex`
- Clinical: `cp` (chest pain type), `trestbps` (resting BP), `chol` (cholesterol), `fbs` (fasting blood sugar)
- ECG/Exercise: `restecg`, `thalach` (max heart rate), `exang` (exercise-induced angina), `oldpeak`, `slope`, `ca`, `thal`
- Target: `target` (1 = disease, 0 = no disease)

## Key Findings

- **Decision Tree** achieved high accuracy but showed signs of overfitting.
- **Tuned KNN** provided balanced accuracy and generalization with optimal `k`.
- **K-Means Clustering** separated patients into two clusters that partially aligned with disease presence.
- **Association Rules** revealed patterns linking specific chest pain types and cholesterol levels to heart disease risk.

## Key Observations
- The **Decision Tree Classifier** achieved high accuracy on the training set but showed slight overfitting compared to test results.  
- The **tuned KNN model** (optimal *k* from GridSearchCV) provided balanced accuracy and better generalization than the untuned version.  
- **ROC Curves** indicated both models were effective at distinguishing between patients with and without heart disease, though KNN had a slightly higher AUC.  
- **K-Means Clustering** with 2 clusters revealed groupings that partially aligned with the target variable, suggesting clustering could provide useful patient segmentation for risk assessment.  
- **Association Rule Mining** using the Apriori algorithm revealed patterns linking specific chest pain types, cholesterol levels, and thalassemia status to heart disease presence or absence, which could inform preventive healthcare strategies.  

## Practical Relevance

- Classification models can assist in **early detection** of heart disease, enabling preventive care.
- Clustering can help **segment patients** for targeted interventions.
- Association rules can be integrated into **hospital triage systems** to prioritize testing for high-risk individuals.

## Challenges
- **Data Scaling** was essential for KNN and K-Means to function properly; without scaling, results were biased toward features with larger numerical ranges.  
- **Class Imbalance** in some train-test splits slightly affected F1 scores, requiring careful evaluation using multiple metrics beyond accuracy.  
- **Overfitting in Decision Trees** — needed to consider pruning or limiting tree depth for better generalization.  
- **Choosing the number of clusters** in K-Means required experimentation; while `k=2` matched the binary target, elbow and silhouette methods could refine this choice.  
- **Association Rule Mining** produced many rules, so filtering by lift and support was critical to extract meaningful, actionable patterns.  

## Author
Pawan Pandey  
Advanced Big Data and Data Mining (MSCS-634-B01)  
University of the Cumberlands 