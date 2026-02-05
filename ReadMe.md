# 🏠 House Price Prediction

An end-to-end machine learning project that analyzes housing data and predicts house prices using regression models.

## 📌 Project Overview

The goal of this project is to build a machine learning system capable of estimating house prices based on property characteristics such as living area, grade, location, condition, and other features.

The project covers the complete machine learning workflow, from exploratory data analysis and preprocessing to model training, hyperparameter tuning, evaluation, and deployment through a Streamlit application.

## 🎯 Objectives

- Explore and understand the housing dataset
- Clean and prepare the data
- Analyze relationships between housing features and price
- Engineer useful features from the sale date
- Train and compare regression models
- Tune the best-performing model
- Evaluate model performance using regression metrics
- Analyze feature importance
- Build an interactive house price prediction application

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Streamlit

## 📊 Dataset

The dataset contains **21,613 housing records** with information about property characteristics, location, condition, and sale price.

After removing unnecessary columns and rows containing missing values, **21,597 records** were used for modeling.

The target variable is:

```text
price
```

### Important Features

- `bedrooms`
- `bathrooms`
- `sqft_living`
- `sqft_lot`
- `floors`
- `waterfront`
- `view`
- `condition`
- `grade`
- `sqft_above`
- `sqft_basement`
- `yr_built`
- `yr_renovated`
- `zipcode`
- `lat`
- `long`
- `sqft_living15`
- `sqft_lot15`
- `year`
- `month`

The original `date` feature was converted into `year` and `month` before modeling.

## 🔍 Exploratory Data Analysis

Several important relationships were identified during EDA.

### Strong relationships with price

- `grade`
- `sqft_living`
- `sqft_above`
- `sqft_lot`

Location-related features such as `lat` and `long` also provided useful predictive information.

The analysis also revealed several price outliers, including houses with prices substantially higher than the majority of observations.

## 🤖 Machine Learning Workflow

```text
Raw Data
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Feature Engineering
   ↓
Train/Test Split
   ↓
Linear Regression
   ↓
Random Forest
   ↓
Hyperparameter Tuning
   ↓
Model Evaluation
   ↓
Feature Importance
   ↓
Model Saving
   ↓
Streamlit Prediction App
```

## 📈 Models

Two main regression approaches were evaluated.

### Linear Regression

```text
MAE:  $125,390
RMSE: $199,863
R²:   0.693
```

### Random Forest

The Random Forest model significantly outperformed Linear Regression.

Baseline Random Forest:

```text
MAE:  $67,289
RMSE: $124,891
R²:   0.880
```

After hyperparameter tuning:

```text
MAE:  $67,229
RMSE: $124,306
R²:   0.881
```

### Final Model

The final model is a **tuned Random Forest Regressor**.

It achieved an R² score of approximately **0.881**, meaning it explains around 88% of the variation in house prices on the test set.

## ⭐ Feature Importance

The most important features in the final Random Forest model were:

| Feature | Importance |
|---|---:|
| `grade` | 30.69% |
| `sqft_living` | 28.00% |
| `lat` | 16.04% |
| `long` | 6.88% |
| `waterfront` | 3.35% |
| `sqft_living15` | 3.02% |
| `yr_built` | 2.52% |
| `sqft_above` | 2.20% |

The model relies particularly heavily on house grade, living area, and geographical location.

## 🌐 Streamlit Application

The trained model is integrated into a Streamlit application that allows users to enter property information and receive an estimated house price.

The application includes sections for:

- 🏠 House information
- ⭐ House quality
- 🏗️ House structure
- 📍 Location and age
- 📅 Sale information

The application then displays the predicted house price along with the model's performance metrics.

## 📁 Project Structure

```text
HousePricePrediction/
│
├── data/
│   └── housing.csv
│
├── models/
│   └── house_price_model.pkl
│
├── notebooks/
│   └── eda.ipynb
│
├── src/
│
├── app.py
├── ReadMe.md
└── requirements.txt
```

## 🚀 Running the Project

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd HousePricePrediction
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit application

```bash
streamlit run app.py
```

The application will open in your browser.

## 🔮 Future Improvements

- Experiment with XGBoost and Gradient Boosting
- Perform more extensive hyperparameter optimization
- Add additional model explainability
- Improve prediction uncertainty estimates
- Deploy the application online
- Add automated model monitoring
- Improve the user interface

## 👨‍💻 Author

**Muizz Karim**

AI Developer & Machine Learning Engineer

GitHub: [Muizzkarim10](https://github.com/Muizzkarim10)