# 🚖 Taxi Demand Forecasting using Machine Learning (Time Series)

## 📌 Project Overview
This project focuses on building a **machine learning regression model** to predict the number of taxi orders for the next hour for the *Sweet Lift Taxi* company. The main objective is to optimize prediction accuracy using the **RMSE (Root Mean Squared Error)** metric.

The goal is to forecast hourly demand to help optimize driver allocation during peak demand periods.

---

## ⚙️ Data Preprocessing
- Verified that **date and time are in chronological order**
- Resampled data from **10-minute intervals to 1-hour intervals**
  - Aggregation method: **sum (total orders per hour)**
- Confirmed **no missing values or duplicates**
- Defined the problem as a **regression task** with a numeric target (`num_orders`)

---

## 📊 Exploratory Data Analysis (EDA)
- Dataset spans from **2018-03-01 to 2018-08-31**
- Contains **4,416 consecutive hourly observations**
- Average demand: **84 orders/hour**
- Standard deviation: **45 (high variability)**
- 25% of values exceed **107 orders**
- Clear seasonal patterns observed:
  - Peak demand: **22:00 – 01:00**
  - Low demand: **around 06:00**
- Weekly and daily seasonality clearly identified
- Slight **non-stationarity** observed (changing mean over time)

---

## 🧠 Feature Engineering
- Extracted **cyclical time features**:
  - Month  
  - Day  
  - Day of week  
  - Hour  
- Created **lag features (12 lags)** to capture temporal dependencies  
- Added **rolling statistics**:
  - Rolling mean  
  - Rolling standard deviation  
- Used `shift()` to ensure **no data leakage**

---

## 🤖 Models Used
The following regression models were evaluated:

- Linear Regression  
- Random Forest Regressor  
- XGBoost Regressor  
- LightGBM Regressor  
- CatBoost Regressor  

---

## 🔧 Model Tuning
- Applied **RandomizedSearchCV** for hyperparameter optimization  
- Used **RMSE** as the evaluation metric  
- Reserved **10% of the dataset as test set** (project requirement)  
- Compared models using validation performance

---

## 🏆 Best Model
**CatBoost Regressor** achieved the best overall performance.

### 📈 Results:
- **Test RMSE:** `41.48`
- **Dummy Regressor RMSE:** `87.21`
- ✅ **Improvement:** ~**52% reduction in error compared to baseline**

---

## 💡 Key Insights
- Gradient boosting models (CatBoost, LightGBM, XGBoost) performed best with very similar results  
- Linear models significantly underperformed → strong **non-linear relationships** exist  
- Feature engineering (lags + time features) had the biggest impact on performance  
- Model successfully captures **seasonality and peak-hour demand patterns**

---

## 🚀 Future Improvements
- Add more advanced lag/rolling features  
- Incorporate external data (weather, holidays, events)  
- Try ensemble blending of top models  
- Explore deep learning models (LSTM, Temporal CNN)

---

## 🛠️ Tech Stack
- Python (Pandas, NumPy)  
- Scikit-learn  
- LightGBM  
- XGBoost  
- CatBoost  
- Matplotlib / Seaborn  

---

## 👤 Author
**Yalchin Alasgarli**

LinkedIn: https://www.linkedin.com/in/yalchin-alasgarli/
- Aspiring Data Scientist  
- Background in GIS & Analytics  
- Focused on time series and predictive modeling  

---

## ⭐ If you found this project useful, feel free to star the repo!
