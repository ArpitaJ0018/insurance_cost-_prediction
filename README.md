# 🏥 Insurance Cost Prediction

A machine learning project that predicts medical insurance charges based on customer demographics and health-related attributes using supervised regression techniques.

---

## 📌 Objective

The primary objective of this project is to analyze medical insurance data and build a machine learning model that accurately predicts insurance charges based on customer attributes. This enables insurance companies to set data-driven premiums and helps individuals understand potential costs based on their profile.

---

## 📂 Dataset Overview

| Property | Details |
|---|---|
| Source | insurance.csv |
| Records | 1,338 |
| Features | 7 (6 input + 1 target) |

### Features

| Column | Type | Description |
|---|---|---|
| age | Numerical | Age of the beneficiary |
| sex | Categorical | Gender (male / female) |
| bmi | Numerical | Body Mass Index |
| children | Numerical | Number of dependents |
| smoker | Categorical | Smoking status (yes / no) |
| region | Categorical | Residential region (northeast, southeast, southwest, northwest) |
| **charges** | **Numerical** | **Target — Medical insurance cost** |

---

## 🔧 Tech Stack

- **Language:** Python 3
- **Libraries:** NumPy, Pandas, Seaborn, Matplotlib, Scikit-learn

---

## 🚀 Project Workflow

### 1. Data Loading & Exploration
- Loaded dataset using Pandas
- Inspected shape, dtypes, and column names
- Confirmed **zero null values** across all columns
- Generated descriptive statistics (mean age ~39, mean BMI ~30.7, mean charges ~$13,270)

### 2. Exploratory Data Analysis (EDA)
- Analyzed distributions of numerical features (age, bmi, charges)
- Explored relationships between smoking status, BMI, age, and insurance charges
- Visualized feature correlations using heatmaps and distribution plots

### 3. Feature Engineering
- Created `age_group` column (binned age into ranges like 18–30, 31–45, etc.)
- Created `bmi_category` column (Underweight, Normal, Overweight, Obese)
- Encoded categorical variables using `pd.get_dummies()`

### 4. Model Building & Evaluation
- Split data into training and testing sets
- Trained and compared multiple regression models
- Evaluated using R² Score and other regression metrics
- Selected **Random Forest Regressor** as the final model

### 5. Prediction on New Data
- Demonstrated prediction on a new customer profile
- Example: 35-year-old male, BMI 27.5, 2 children, non-smoker, southeast → **Predicted charge: ~$5,472.10**

---

## 📊 Model Comparison

| Model | Performance |
|---|---|
| Linear Regression | Lower R² — struggled with non-linear patterns |
| Random Forest Regressor | ✅ Best — R² score of 90%+ |

---

## 🔍 Feature Importance

| Feature | Importance |
|---|---|
| smoker_yes | 61.1% |
| bmi | 15.5% |
| age | 13.7% |
| bmi_category_Obese | 5.1% |
| children | 1.9% |

> Smoking status is the single most critical factor driving insurance charges, followed by BMI and age.

---

## 💡 Key Insights

- **Smokers** pay significantly higher insurance charges than non-smokers
- **Higher BMI**, especially in the obese category, leads to higher costs
- **Older individuals** tend to have higher insurance costs
- **Gender** and **region** have relatively minimal impact on pricing
- Insurers can use this model to design risk-based premiums and optimize pricing strategies

---

## ⚠️ Challenges Faced

- Outliers in `charges` and `bmi` skewed predictions and reduced model accuracy
- Categorical features required careful encoding to be used in ML models
- Linear Regression failed to capture non-linear relationships in the data
- Preventing overfitting in Random Forest required tuning
- Skewed distribution in `charges` needed careful handling during analysis

---

## ✅ Conclusion

The project successfully built a regression model to predict medical insurance charges. Random Forest Regressor was selected as the final model due to its superior accuracy and ability to capture non-linear relationships. The model effectively predicts insurance charges for new customers, providing valuable insights for data-driven insurance pricing and risk assessment.

---

## 📁 Project Structure
insurance-cost-prediction/
│
├── insurance.csv                    # Dataset
├── insurance_cost_prediction.ipynb  # Main notebook
├── insurance_cost_model.pkl         # Saved model (optional)
└── README.md                        # Project documentation
