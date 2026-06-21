# 🏠 Bangalore House Price Prediction Using Machine Learning

## 📌 Project Overview

This project focuses on predicting residential property prices in Bengaluru using Machine Learning techniques. The objective is to estimate house prices based on important property features such as location, area type, total square footage, number of bedrooms (BHK), bathrooms, and balconies.

The project follows a complete Machine Learning pipeline including data cleaning, preprocessing, feature engineering, exploratory data analysis, outlier handling, model training, evaluation, and deployment.

---

## 🎯 Objectives

- Predict housing prices using historical real estate data.
- Perform data cleaning and preprocessing.
- Handle missing values and outliers.
- Compare multiple Machine Learning regression models.
- Deploy a house price prediction system.

---

## 📂 Dataset

**Dataset:** Bengaluru House Price Dataset

### Original Dataset Size
- 13,320 records
- 9 features

### Final Dataset Size
- 8,649 records after preprocessing and outlier removal

### Features Used

- Area Type
- Location
- Total Square Feet
- Number of Bathrooms
- Number of Balconies
- BHK (Bedrooms)

### Target Variable

- House Price (in Lakhs INR)

---

## 🛠 Technologies Used

### Programming Language
- Python

### Libraries
- NumPy
- Pandas
- Matplotlib
- Seaborn
- SciPy
- Scikit-Learn
- XGBoost
- LightGBM
- Streamlit

---

## 🔍 Data Preprocessing

The following preprocessing steps were performed:

### Data Cleaning
- Removed unnecessary columns:
  - availability
  - society

### Missing Value Handling
- Removed records with missing values in:
  - location
  - size
  - bathroom
- Replaced missing balcony values using mean imputation.

### Feature Engineering
- Extracted BHK values from size feature.
- Converted all area measurements into square feet.
- Created a new feature:
  
  `price_per_sqft`

### Dimensionality Reduction
- Reduced location categories from **1304 to 181** by grouping low-frequency locations into an "Other" category.

---

## 📊 Outlier Detection & Treatment

Multiple techniques were used to identify and remove outliers:

### Statistical Outliers
- Flooring and capping using quantile-based methods.
- Applied on:
  - Total Square Feet
  - Price
  - Bathroom Count
  - BHK

### Domain-Based Outliers

Removed unrealistic properties where:

- Bathrooms > BHK + 1
- Square Feet per BHK < 300

### Price Per Square Foot Analysis

Created and analyzed price_per_sqft to identify abnormal pricing patterns across locations.

---

## 📈 Exploratory Data Analysis

### Correlation with Price

| Feature | Correlation |
|----------|------------|
| Total Square Feet | 0.8285 |
| BHK | 0.7200 |
| Bathroom | 0.6770 |
| Balcony | 0.1854 |

### Key Findings

- Total Square Feet had the strongest impact on house price.
- Balcony count showed the weakest correlation.
- Plot Area properties had the highest average property prices.
- Location significantly influenced housing prices.

---

## 🤖 Model Building

Categorical features were encoded using One-Hot Encoding.

### Models Evaluated

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- XGBRegressor
- LGBMRegressor
- HistGradientBoosting Regressor
- MLP Regressor
- Gradient Boosting Regressor
- Bagging Regressor
- Extra Trees Regressor

---

## 📋 Model Performance

| Model | R² Score | RMSE |
|---------|---------:|---------:|
| XGBRegressor | 0.86 | 22.74 |
| LGBMRegressor | 0.85 | 23.88 |
| HistGradientBoostingRegressor | 0.85 | 23.94 |
| MLPRegressor | 0.85 | 24.22 |
| RandomForestRegressor | 0.84 | 24.72 |
| GradientBoostingRegressor | 0.84 | 25.02 |
| LinearRegression | 0.82 | 25.86 |
| DecisionTreeRegressor | 0.79 | 28.57 |

---

## 🏆 Model Selection

Although XGBoost achieved the highest R² Score of **0.86**, Linear Regression was selected as the final deployment model because it provided competitive performance while being computationally efficient, interpretable, and faster to train.

### Final Model Used

**Linear Regression**

### Performance

- R² Score: **0.82**
- RMSE: **25.86**

---

## 🌐 Web Application

A Streamlit-based web application was developed for real-time house price prediction.

### User Inputs

- Total Square Feet
- BHK
- Number of Bathrooms
- Number of Balconies
- Area Type
- Location

### Output

- Estimated House Price

---

## 📁 Project Structure

```text
House-price-prediction/
│
├── Bengaluru_House_Data.csv
├── Cleaned_data.csv
├── Bengaluru_Real_Estate_Price.ipynb
├── app.py
├── bangalore_home_prices_model.pickle
├── columns.json
├── requirements.txt
├── Procfile
├── setup.sh
└── README.md
```

---

## 📌 Results

- Successfully cleaned and processed real-world housing data.
- Reduced dataset noise through statistical and domain-based outlier handling.
- Evaluated multiple regression algorithms.
- Achieved a maximum R² Score of **0.86** using XGBoost.
- Deployed a practical Linear Regression-based prediction system.
- Developed an interactive Streamlit web application for price prediction.

---

## 🎯 Conclusion

This project demonstrates the application of Machine Learning techniques for real estate price estimation. Through extensive preprocessing, feature engineering, exploratory data analysis, and model evaluation, a reliable house price prediction system was developed for Bengaluru residential properties.

---

