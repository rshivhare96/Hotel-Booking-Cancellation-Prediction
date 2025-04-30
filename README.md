
# 🏨 Hotel Booking Cancellation Prediction

## 📑 Project Overview

This project aims to predict whether a hotel booking will be **canceled or not**, using various customer-related features. We preprocess the data, perform exploratory data analysis (EDA), encode categorical variables, and build machine learning models to classify bookings as "Canceled" (1) or "Not Canceled" (0).

---

## 🗃️ Dataset Information

- **Total Entries:** 36,285
- **Final Processed Rows:** 33,312
- **Features:** 30 (after one-hot encoding)
- **Target Column:** `booking status`  
  - `Canceled = 1`, `Not_Canceled = 0`

---

## 🔍 Feature Overview

Numerical features include:
- `number of adults`, `number of children`
- `number of weekend nights`, `number of week nights`
- `car parking space`, `lead time`, `repeated`
- `P-C` (Previous Canceled), `P-not-C` (Previous Not Canceled)
- `average price`, `special requests`
- Date features: `day`, `month`, `year`

Categorical features (One-Hot Encoded):
- `type of meal`
- `room type`
- `market segment type`

---

## 🧹 Data Preprocessing

- Converted **date of reservation** into **day**, **month**, **year**
- Encoded target variable:
  - `Canceled` → 1  
  - `Not_Canceled` → 0
- Applied **One-Hot Encoding** to:
  - `type of meal`
  - `room type`
  - `market segment type`
- No missing values were present

---

## 📊 Feature Importance (Top Contributors)

| Feature                          | Importance Score |
|----------------------------------|------------------|
| `lead time`                      | 6755.25          |
| `special requests`               | 2136.14          |
| `year`                           | 952.07           |
| `market segment type_Online`     | 646.78           |
| `average price`                  | 614.84           |
| `market segment type_Corporate`  | 414.32           |
| `repeated`                       | 343.90           |
| `market segment type_Offline`    | 250.21           |
| `number of week nights`          | 248.88           |
| `car parking space`              | 216.60           |

---

## 🤖 Model Performance

| Model               | Accuracy | Best Params                                |
|---------------------|----------|---------------------------------------------|
| **Logistic Regression** | 0.7930   | `C=0.1`, `penalty='l2'`                    |
| **KNN**                 | 0.8295   | `n_neighbors=2`                            |
| **Decision Tree**       | 0.8597   | `criterion='entropy'`, `max_depth=15`      |
| **Random Forest**       | 0.8759   | Default parameters                         |
| **SVC**                 | 0.8285   | Default parameters                         |

---

## 🧾 Best Model (Random Forest)

- **Accuracy:** 88%
- **Confusion Matrix:**
  ```
  [[4241  336]
   [ 491 1595]]
  ```

- **Classification Report:**
  | Class         | Precision | Recall | F1-Score | Support |
  |---------------|-----------|--------|----------|---------|
  | **0 (Not_Canceled)** | 0.90      | 0.93   | 0.91     | 4577    |
  | **1 (Canceled)**     | 0.83      | 0.76   | 0.79     | 2086    |
  | **Accuracy**         |           |        | **0.88** | 6663    |

---

## ✅ Conclusion

- **Random Forest** provided the best performance, balancing both precision and recall.
- Important predictors include `lead time`, `special requests`, and `average price`.
- The model can effectively support hotel businesses in managing cancellations proactively.
