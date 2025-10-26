---
title: "Heart Disease Prediction and Interpretability"
summary: "This project compares LIME and SHAP for explaining heart disease predictions using the UCI Heart Disease dataset. Several models were built from scratch, with XGBoost achieving the highest accuracy (83.3%). While SHAP produced stable, theory-based feature attributions, LIME offered intuitive, instance-level insights that benefited from an aggregated approach to improve consistency. Together, they highlight how combining interpretability tools can make machine learning in healthcare both accurate and transparent."
tags:
  - Data Science
  - Machine Learning
  - Statistics
  - Medicine
date: "2024-06-25T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ''

image:
  caption: "GenAI generated"
  focal_point: Smart

links:
  - icon: github
    icon_pack: fab
    name: github
    url: "https://github.com/christian-hobelsberger/Heart_Disease_Interpretability"

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: example
---
## Abstract  
Interpretable machine learning (ML) plays a crucial role in healthcare, where understanding *why* a model makes a prediction can be as important as the prediction itself. This project explores the use of **LIME** (Local Interpretable Model-agnostic Explanations) and **SHAP** (SHapley Additive exPlanations) for explaining heart disease predictions made by several classifiers trained on the **UCI Heart Disease dataset**. Four models—logistic regression, decision tree, random forest, and XGBoost—were implemented, with XGBoost achieving the highest accuracy of 0.833. LIME provided intuitive, instance-level explanations, while SHAP offered consistent, theory-based global insights. By combining both tools, this study demonstrates how interpretable ML can balance transparency and accuracy in healthcare applications.

---

## 1. Introduction  

### 1.1 Background and Motivation  
Machine learning models have become powerful tools for medical diagnosis, offering high predictive accuracy in detecting diseases. However, complex models—like ensemble or boosted trees—often act as *black boxes*, providing little insight into their decision-making processes. In high-stakes areas such as healthcare, this opacity limits trust and practical adoption.  

To address this, **interpretable ML** methods have emerged to explain model predictions post-hoc. Two widely adopted approaches are **LIME**, which approximates local decision boundaries with simple interpretable models, and **SHAP**, which attributes feature importance using game-theoretic Shapley values. Both methods aim to bridge the gap between accuracy and interpretability, helping medical professionals understand, validate, and trust predictive systems.

### 1.2 Aim  
The goal of this project was to build and interpret ML models for **heart disease prediction**, focusing on how **LIME and SHAP** provide complementary insights into model behavior. The analysis emphasizes reproducibility, modular design, and interpretability evaluation.

---

## 2. Data: UCI Heart Disease Dataset  

The dataset contains **303 patient records** with **13 clinical features** such as chest pain type, cholesterol level, and resting blood pressure. The original multiclass labels were simplified into a **binary classification problem**:  
- **0** – No heart disease  
- **1** – Presence of heart disease  

This transformation makes the task suitable for interpretable binary classification, where both global feature importance and individual explanations can be effectively analyzed.

---

## 3. Methods and Experiments  

### 3.1 Model Implementation  
Four models were trained and evaluated:  
- **Logistic Regression (with momentum optimization)** – implemented from scratch for stable and fast convergence.  
- **Decision Tree** – using recursive binary splitting with pruning to avoid overfitting.  
- **Random Forest** – combining multiple trees through bootstrapping and feature bagging.  
- **XGBoost** – a gradient-boosted ensemble for benchmark comparison.  

All models were evaluated using **5-fold stratified cross-validation** with accuracy and mean squared error metrics.

### 3.2 Interpretability Framework  
Two post-hoc explanation methods were applied:  
- **LIME** was implemented from scratch, generating local surrogate models for each prediction by perturbing inputs and fitting a weighted linear model.  
- **SHAP** values were computed using the official library, providing additive, consistent feature attributions grounded in Shapley theory.  

A novel extension, **Aggregated LIME**, was introduced to improve stability by averaging explanations across multiple runs.

---

## 4. Results  

### 4.1 Model Performance  
| Model              | Accuracy |
|--------------------|-----------|
| Logistic Regression | 0.817 |
| Decision Tree       | 0.700 |
| Random Forest       | 0.817 |
| **XGBoost**         | **0.833** |

XGBoost achieved the highest accuracy, confirming the strength of ensemble methods for medical prediction tasks.

### 4.2 Interpretability Insights  
Both SHAP and LIME consistently identified the same key predictors:  
- **Thalassemia (thal)**  
- **Chest pain type (cp)**  
- **Fluoroscopy vessel count (ca)**  
- **ST depression (oldpeak)**  

**SHAP** produced stable and globally consistent results, aligning with clinical understanding.  
**LIME** provided clear, local explanations tailored to individual cases but required aggregation for stability. The **Aggregated LIME** approach successfully revealed which features consistently influenced predictions across runs.

---

## 5. Conclusion  
This project demonstrates that **interpretable ML techniques** can enhance transparency in healthcare prediction systems without sacrificing accuracy. **SHAP** delivers robust, theoretically sound explanations, while **LIME** offers accessible, instance-specific insights. Combining both methods forms a comprehensive interpretability pipeline that balances depth, reliability, and usability—crucial qualities for real-world medical applications.
