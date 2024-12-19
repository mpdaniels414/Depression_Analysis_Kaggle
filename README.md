# Classification Model Evaluation for Depression Prediction

This project evaluates multiple machine learning models for predicting depression using various classification techniques. The models were assessed based on their **Accuracy**, **Sensitivity**, and **Specificity**, with a focus on understanding their strengths and limitations for real-world applications.

---

## Project Overview

### Objective:
To identify the best-performing model for depression classification, considering trade-offs between accuracy, sensitivity (true positive rate), and specificity (true negative rate).

### Dataset:
The dataset contains predictors related to demographic, behavioral, and psychological factors, along with a binary target variable (`Depression`).

---

## Models Evaluated

1. **Full Logistic Regression**
2. **Decision Tree**
3. **Random Forest**
4. **Stepwise Logistic Regression**:
   - Forward Selection
   - Backward Elimination
   - Both Directions
5. **Ridge Regression**
6. **Regular Lasso**
7. **Elastic Net**
8. **XGBoost**

---

## Evaluation Metrics

- **Accuracy**: Proportion of correct predictions.
- **Sensitivity**: Ability to correctly identify positive cases (true positives).
- **Specificity**: Ability to correctly identify negative cases (true negatives).

### Results Summary:

| **Model**          | **Accuracy** | **Sensitivity** | **Specificity** |
|---------------------|--------------|------------------|------------------|
| Full Logistic       | 0.9902       | 0.9918           | 0.9773           |
| Decision Tree       | 0.9220       | 0.9560           | 0.6522           |
| Random Forest       | 0.9390       | 0.9721           | 0.7059           |
| Step Forward        | 0.9878       | 0.9891           | 0.9767           |
| Step Backward       | 0.9878       | 0.9891           | 0.9767           |
| Step Both           | 0.9878       | 0.9891           | 0.9767           |
| Ridge               | 0.9780       | 0.9837           | 0.9302           |
| Regular Lasso       | 0.9854       | 0.9864           | 0.9762           |
| Elastic Net         | 0.9902       | 0.9891           | 1.0000           |
| XGBoost             | 0.9610       | 0.9754           | 0.8409           |

---

## Key Findings

1. **Best Overall Model**: **Elastic Net**
   - Achieved the best balance between all metrics.
   - Perfect **Specificity** (1.0000), high **Accuracy** (0.9902), and strong **Sensitivity** (0.9891).

2. **Alternative Recommendation**: **Full Logistic Regression**
   - Provides similar Accuracy and Sensitivity to Elastic Net.
   - More interpretable, making it suitable for applications requiring model transparency.

3. **Interpretable Models**: **Stepwise Logistic Regression**
   - Step Forward, Backward, and Both directions perform almost as well as Full Logistic Regression.
   - High Accuracy (0.9878) and balanced metrics with simpler predictor sets.

4. **If Sensitivity is Critical**:
   - Full Logistic Regression has the highest Sensitivity (0.9918), making it ideal for applications prioritizing true positive detection.

5. **If Specificity is Critical**:
   - Elastic Net achieves perfect Specificity, minimizing false positives.

---

## Usage

### Requirements
- **R Packages**:
  - `caret`
  - `glmnet`
  - `MASS`
  - `xgboost`
  - `pROC`

### How to Run
1. Clone this repository:
   ```bash
   git clone <repository-url>
   cd <repository-folder>

```
install.packages(c("caret", "glmnet", "MASS", "xgboost", "pROC"))
```

```
rmarkdown::render("classification_models.Rmd")
```
