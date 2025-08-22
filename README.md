# ✈️ Flight Delay Analysis & Prediction

Predicting flight delays helps airlines, passengers, and airports make smarter decisions. This project analyzes historical flight data, identifies delay patterns, and builds machine learning models to predict flight delays.

---

## 🚀 Features

- Explore **departure & arrival delays** across airlines and airports  
- Investigate **causes of delays**: weather, security, aircraft, etc.  
- Feature engineering for better prediction:
  - `DayOfWeek`, `Hour`, and high-cardinality airports reduced to top 20  
- Train and evaluate **Logistic Regression, Random Forest, XGBoost**  
- Predict flight delays using a pre-trained **Random Forest model**

---

## 📊 Dataset

Three datasets are used:

| Dataset | Description |
|---------|-------------|
| `flights.csv` | Flight details with times, delays, and status |
| `airlines.csv` | Airline codes and names |
| `airports.csv` | Airport information: city, state, coordinates |

**Full flights dataset (~3GB)**:  
[Kaggle - US DOT Flight Delays](https://www.kaggle.com/datasets/usdot/flight-delays)  

> **Tip:** Use `flights_sample.csv` (~200k rows) for faster experimentation.

---

## ⚡ Feature Engineering

- **Categorical Encoding:** One-hot encoding for airlines and top airports  
- **Missing Values:** Median imputation for numeric columns  
- **Feature Scaling:** StandardScaler for numeric features  
- **Engineered Features:**  
  - `FL_DATE` → full flight date  
  - `DayOfWeek` → day of the week  
  - `Hour` → scheduled departure hour  
  - High-cardinality airports reduced to top 20, others labeled `OTHER`  

---

## 🛠 Models & Evaluation

| Model | Notes |
|-------|-------|
| Logistic Regression | Simple & interpretable |
| Random Forest | Handles non-linear relationships, robust on structured data |
| XGBoost | High accuracy, handles imbalanced datasets |

**Random Forest** was selected as the best model because:

- Handles complex, non-linear relationships  
- Resistant to overfitting  
- Performs well on structured tabular data  

**Metrics:** Accuracy, Recall, F1 Score, ROC-AUC, Confusion Matrix  

---
## 💡 Notes & Tips

Preprocessing and training on the full dataset can be time-consuming; use flights_sample.csv for testing.

Random Forest model is saved and can be reused for predictions.

This project is compatible with Google Colab for quick experimentation.

