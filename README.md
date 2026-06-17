# Employee Turnover Prediction

## Project Overview & Purpose
TalentCore Pvt. Ltd., a multinational company, has been experiencing an increasing rate of employee resignations. This attrition leads to higher recruitment costs, project delays, and the loss of highly skilled talent. The goal of this project is to build an intelligent Machine Learning system that predicts whether an employee is likely to leave the company. By evaluating various work-related factors—such as job satisfaction, salary, age, and work-life balance—this predictive tool empowers the HR department to take proactive retention measures.

---

## Dataset Description
The model is trained on a corporate dataset consisting of 900 employee records, featuring 15 distinct predictive metrics and 1 target variable. 

Below is a structured breakdown of the dataset features:

| Feature | Description |
| :--- | :--- |
| **Job_Satisfaction** | Level of satisfaction with the job |
| **Performance_Rating** | Employee performance score |
| **Years_At_Company** | Number of years worked in the company |
| **Work_Life_Balance** | Balance between work and personal life |
| **Distance_From_Home** | Distance of home from the workplace |
| **Monthly_Income** | Monthly salary |
| **Education_Level** | Education qualification level |
| **Age** | Age of the employee |
| **Num_Companies_Worked** | Number of companies worked previously |
| **Employee_Role** | Encoded job role |
| **Annual_Bonus** | Bonus received annually |
| **Training_Hours** | Training hours attended |
| **Department** | Encoded department |
| **Annual_Bonus_Squared** | Engineered feature (bonus²) |
| **Annual_Bonus_Training_Hours_Interaction** | Engineered interaction feature between annual bonus and training hours |
| **Employee_Turnover (Target)** | `1` = Employee Left, `0` = Employee Stayed |

---

## Models Utilized
To find the most accurate predictive engine, three different classification strategies were implemented and evaluated:

1. **Baseline Logistic Regression:** A standard logistic regression algorithm (`max_iter=200`) used as a foundational benchmark to establish initial predictive capabilities.
2. **L1 Regularization (Lasso):** A penalized logistic regression model (`C=0.5, solver='liblinear'`) that shrinks less critical feature coefficients exactly to zero, essentially performing automated feature selection to improve generalization.
3. **L2 Regularization (Ridge):** A penalized logistic regression model (`C=1.0`) that restricts the magnitude of all coefficients to prevent the model from over-relying on any single feature, thereby reducing overfitting.

### Performance Comparison
A comparative analysis on the test set revealed the following results:

| Model | Overall Accuracy | F1-Score (Turnover Class) |
| :--- | :--- | :--- |
| Baseline Logistic Regression | 85.92% | 0.84 |
| **Lasso (L1) Regularization** | **87.03%** | **0.86** |
| Ridge (L2) Regularization | 85.92% | 0.84 |

**Recommendation:** The **Lasso (L1)** model outperforms the others, providing the highest accuracy and the best balance of precision and recall for detecting employee turnover.

---

## Technical Requirements & Dependencies

To execute this project, the following core libraries are required:
* `pandas` (For data loading and manipulation)
* `scikit-learn` (For model training, regularization, and evaluation)
* `jupyter` (To execute the notebook environment)

### Setup & Installation Guide (Apple MacBook Air M5)
Apple Silicon (M-series chips like the M5) handles data science libraries exceptionally well, but it's best to use environments optimized for ARM64 architecture. Follow these beginner-friendly steps to set up your environment:

**Step 1: Install Homebrew (If not already installed)**
Open your terminal and paste the following command:
```bash
/bin/bash -c "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh))"