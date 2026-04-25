# Stroke Prediction

This project develops a machine learning model to predict stroke risk in patients based on clinical and demographic data. The dataset contains patient records with features such as age, BMI, glucose levels, hypertension and smoking status. The key challenges addressed during the analysis were: missing values, class imbalance and threshold optimization.

## Dataset
The dataset contains 5,110 patient records with 12 features including demographic information (age, gender, residence type), lifestyle factors (smoking status, work type) and clinical measurements (BMI, average glucose level, hypertension, heart disease). The target variable is stroke (binary: 0/1). The dataset was provided as part of a university course project.

## Methodologies
1. **Exploratory Data Analysis:** descriptive statistics, distribution of categorical variables and identification of missing values and class imbalance.
2. **BMI Imputation:** missing BMI values (4%) were predicted using Linear Regression on correlated features.
3. **Encoding:** categorical variables were converted to numerical using Label Encoding.
4. **Handling Class Imbalance:** upsampling of the minority class (stroke=1) applied exclusively on the training set to prevent data leakage.
5. **Modeling:** Random Forest Classifier with 100 trees.
6. **Threshold Optimization:** custom threshold (0.3) selected to maximize stroke recall in a medical screening context.

## Results
| Metric | Value |
|--------|-------|
| ROC-AUC Score | 0.792 |
| Stroke Recall (threshold=0.3) | 0.24 |
| Stroke F1-score (threshold=0.3) | 0.22 |
| Overall Accuracy | 0.92 |

## Key Findings
Age is the strongest predictor of stroke risk (feature importance: 39.3%).

Average glucose level and BMI follow (20.1% and 18.1% respectively).

Lowering the classification threshold from 0.5 to 0.3 increased stroke detection by 7.5x.

At threshold=0.5 the model detected only 2 out of 62 stroke cases, highlighting the danger of using accuracy alone in imbalanced medical datasets.

## Limitations
30% of smoking_status values are labeled 'Unknown', representing hidden missing data.

Small number of actual stroke cases (249) limits model generalization.

Stroke recall remains low (0.24) after threshold optimization.

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
