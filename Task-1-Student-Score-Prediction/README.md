# Student Score Prediction Using Linear Regression

## Project Overview

This project develops a machine learning model to predict students' examination scores based on study hours and other relevant academic and lifestyle factors.

It was completed as part of the **Elevvo Pathways Machine Learning Track – Task 1**.

The project applies Linear Regression to understand how different factors contribute to students' examination performance and evaluates the predictive performance of different feature combinations.

## Dataset

**Dataset:** [Student Performance Factors – Kaggle](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors)

- Records: 6,607 students
- Features: 19 input variables
- Target variable: `Exam_Score`

The dataset contains information about students' study habits, attendance, sleep, previous academic performance, tutoring sessions and other factors.

## Objectives

1. Perform data cleaning and exploratory data analysis.
2. Investigate the relationship between study hours and examination scores.
3. Develop a Linear Regression model to predict examination scores.
4. Evaluate model performance using appropriate regression metrics.
5. Experiment with Polynomial Regression and multiple feature combinations.
6. Validate model performance using 5-fold cross-validation.

## Tools and Libraries

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

## Methodology

### 1. Data Cleaning and Exploration

The dataset was inspected for missing values and duplicate records.

- Missing values were identified in some categorical columns.
- No missing values were found in the selected numerical features.
- No duplicate records were identified.

Exploratory data analysis included descriptive statistics, scatter plots and correlation analysis.

The relationship between `Hours_Studied` and `Exam_Score` showed a positive correlation of approximately **0.445**.

### 2. Baseline Linear Regression

The initial model used `Hours_Studied` as the only predictor.

The dataset was divided into:
- 80% training data
- 20% testing data

The model was evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE) and R².

**Baseline results:**

| Metric | Result |
|---|---:|
| MAE | 2.448 |
| RMSE | 3.295 |
| R² | 0.232 |

### 3. Bonus Experiment 1: Polynomial Regression

A degree-2 Polynomial Regression model was developed to investigate whether a nonlinear relationship could improve prediction.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 2.448 | 3.295 | 0.232 |
| Polynomial Regression | 2.445 | 3.293 | 0.233 |

The improvement was marginal, suggesting that the degree-2 polynomial model did not provide a meaningful predictive advantage.

### 4. Bonus Experiment 2: Multiple Feature Combinations

Three Linear Regression models were compared using different combinations of numerical features.

**Model A – One Feature**
- Hours_Studied

**Model B – Three Features**
- Hours_Studied
- Attendance
- Sleep_Hours

**Model C – Six Features**
- Hours_Studied
- Attendance
- Sleep_Hours
- Previous_Scores
- Tutoring_Sessions
- Physical_Activity

**Performance comparison:**

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Model A – One Feature | 2.448 | 3.295 | 0.232 |
| Model B – Three Features | 1.471 | 2.412 | 0.588 |
| Model C – Six Features | **1.266** | **2.251** | **0.642** |

Model C achieved the best performance on the 20% test dataset.

### 5. Cross-Validation

Five-fold cross-validation was performed to assess how consistently the models performed across different data partitions.

| Model | Mean R² | Standard Deviation |
|---|---:|---:|
| Model A – One Feature | 0.198 | 0.019 |
| Model B – Three Features | 0.542 | 0.050 |
| Model C – Six Features | **0.598** | 0.054 |

The six-feature model maintained the strongest average performance across the five folds.

### 6. Model Visualisation

The following visualisations were developed:

- Actual vs Predicted Examination Scores
- Residual Plot
- Comparison of Linear Regression Models

These visualisations helped assess prediction quality, model performance and prediction errors.

## Key Findings

1. Study hours have a positive relationship with examination scores.
2. Using multiple relevant features significantly improved predictive performance.
3. The six-feature model performed better than the single-feature and three-feature models.
4. Polynomial Regression produced only marginal improvement over ordinary Linear Regression.
5. Cross-validation supported the stronger performance of the six-feature model.
6. The residual analysis revealed some substantial prediction errors, particularly where the model underestimated unusually high examination scores.

## Conclusion

The project demonstrated that student examination performance can be predicted using Linear Regression techniques.

Although the baseline model using study hours alone achieved an R² score of 0.232, incorporating six numerical features improved the test R² score to 0.642, with an MAE of 1.266 and RMSE of 2.251.

Five-fold cross-validation produced a mean R² score of 0.598 for the six-feature model.

The findings suggest that considering multiple academic and lifestyle factors provides better predictive performance than relying on study hours alone.

## Limitations and Future Improvements

- The models were developed using a single dataset.
- Some unusually high examination scores were underestimated.
- The six-feature model may benefit from further feature engineering.
- Future work could investigate other regression algorithms, nonlinear relationships and additional relevant predictors.
- Further validation on independent datasets would help assess generalisability.

## Repository Structure

```text
Machine-Learning-Projects/
│
├── README.md
│
└── Task-1-Student-Score-Prediction/
    ├── README.md
    ├── Student_Score_Prediction.ipynb
    └── StudentPerformanceFactors.csv
```

## Acknowledgements

This project was completed as part of the **Elevvo Pathways Machine Learning Track**.

Dataset source: [Kaggle – Student Performance Factors](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors).
