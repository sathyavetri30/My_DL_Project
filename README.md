# My_DL_Project
# Household Power Consumption Forecasting using Transformer & LSTM

## 📌 Project Overview

This project implements **multivariate time series forecasting** on the *Household Power Consumption* dataset using:

* A **Transformer-based deep learning model** (with Multi-Head Attention)
* A **baseline LSTM model** for comparison

The main objective is to predict **Global Active Power** based on historical power usage and related electrical measurements.

This project is designed to meet **advanced deep learning / time series forecasting academic requirements**, going beyond traditional ARIMA or simple RNN models.

---

## 📂 Dataset Description

**Dataset:** Household Power Consumption Dataset

**Features Used:**

* `Global_active_power` (Target variable)
* `Global_reactive_power`
* `Voltage`
* `Global_intensity`
* `Sub_metering_1`
* `Sub_metering_2`
* `Sub_metering_3`

**Time Index:**

* The dataset contains a `time` column
* Converted into `Datetime` and set as the DataFrame index

**Missing Values:**

* Handled using forward-fill (`ffill`)

---

## ⚙️ Project Workflow

### 1️⃣ Data Loading & Preprocessing

* CSV file loaded using Pandas
* `time` column converted to `Datetime`
* All feature columns converted to `float`
* Missing values filled
* Feature names standardized

### 2️⃣ Feature Selection

Only relevant power-related variables are selected for modeling.

### 3️⃣ Train-Test Split

* 80% Training data
* 20% Testing data

### 4️⃣ Data Scaling

* `MinMaxScaler` applied to normalize values between 0 and 1

### 5️⃣ Sequence Creation

* Sliding window approach
* Sequence length: **96 time steps**
* Target: next-step `Global_active_power`

---

## 🤖 Model Architectures

### 🔹 Transformer Model

* Multi-Head Attention (4 heads)
* Key dimension: 32
* Layer Normalization
* Dense layers for regression output
* Loss Function: Mean Squared Error (MSE)
* Optimizer: Adam

**Early Stopping:**

* Prevents overfitting
* Restores best weights

### 🔹 Baseline LSTM Model

* Single LSTM layer (64 units)
* Dense output layer
* Used for performance comparison

---

## 📊 Evaluation Metric

* **RMSE (Root Mean Squared Error)**

Models are evaluated on unseen test data to compare forecasting accuracy.

---

## 💾 Model Saving

* Trained Transformer model is saved as:

```
transformer_household_power_model.h5
```

---

## ▶️ How to Run the Project

1. Upload the dataset:

```
household_power_consumption.csv
```

2. Run the Python script:

```
python final_project_rnn.py
```

3. Observe RMSE values for:

* Transformer Model
* LSTM Baseline

---

## 🧠 Key Learning Outcomes

* Multivariate time series forecasting
* Transformer architecture for sequence modeling
* Attention mechanisms
* Comparison with traditional LSTM
* Proper data preprocessing & evaluation

---

## 📌 Notes

* Designed for **AI Programmer Course**
* Easily extendable with:

  * Longer sequence lengths
  * More attention heads
  * Feature importance analysis

---

## ✨ Author

**Project by:** Sathya Vetri
