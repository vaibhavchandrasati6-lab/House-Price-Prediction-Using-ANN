# 🏠 California Housing Price Prediction

## 📌 Project Overview

This project focuses on predicting house prices using the **California Housing Dataset**.
A neural network (ANN) was built using TensorFlow/Keras to model the relationship between housing features and median house value.

---

## 📊 Dataset

* **Name:** California Housing Dataset
* **Rows:** 20,640
* **Features:** 9 numerical + 1 categorical
* **Target:** `median_house_value`

### Key Features:

* `longitude`, `latitude`
* `housing_median_age`
* `total_rooms`, `total_bedrooms`
* `population`, `households`
* `median_income`
* `ocean_proximity` (categorical)

---

## ⚙️ Data Preprocessing

### ✅ Steps performed:

* Handled missing values (`total_bedrooms`)
* Encoded categorical feature (`ocean_proximity`)
* Feature scaling using **MinMaxScaler**
* Train-test split

---

## 🧠 Model Architecture

```text
Input (9 features)
   ↓
Dense (500, ReLU)
   ↓
Batch Normalization
   ↓
Dropout (0.2)
   ↓
Dense (500, ReLU)
   ↓
Batch Normalization
   ↓
Dropout (0.2)
   ↓
Dense (500, ReLU)
   ↓
Batch Normalization
   ↓
Dropout (0.2)
   ↓
Dense (1, Linear Output)
```

* **Total Parameters:** ~512K
* **Optimizer:** Adam
* **Loss Function:** Mean Squared Error (MSE)

---

## ⏱️ Training Strategy

* Epochs: 120
* EarlyStopping used:

  * `monitor = val_loss`
  * `patience = 10`
  * `restore_best_weights = True`

👉 Best model restored at **epoch 68**

---

## 📈 Results

| Metric   | Value       |
| -------- | ----------- |
| R² Score | **0.7269**  |
| MAE      | ~42,178     |
| MSE      | ~3.56 × 10⁹ |

---

## 📊 Observations

### ✅ What worked well:

* Stable training with decreasing loss
* Good generalization (no severe overfitting)
* Proper use of EarlyStopping

---

## 🚀 Future Improvements

### 🔥 High-impact improvements:

👉 Expected improvement:

```text
R² → 0.82 – 0.85+
```

---

## 📌 Key Learnings

* Deep learning is not always the best choice for tabular data
* Feature engineering has a bigger impact than model complexity
* EarlyStopping is critical for preventing overfitting
* Model simplicity often leads to better generalization

---

## 📎 Conclusion

This project demonstrates a solid end-to-end machine learning workflow using neural networks. While the model achieves a respectable R² score (~0.73), further improvements can be achieved through better feature engineering and model selection.

---
