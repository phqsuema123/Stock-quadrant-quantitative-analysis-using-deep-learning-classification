# 📊 Stock Quadrant Quantitative Analysis Using Deep Learning

## 🧠 Project Overview

This project develops an **AI-powered stock classification system** that categorizes Thai stocks into **25 quadrants (Aa–Ee)** based on:

* **Fundamental strength** (EPS, PE, PBV, Dividend Yield, Market Cap)
* **Market trend** (RSI, EMA5–200, volatility, etc.)

The goal is to assist investors in analyzing stocks **systematically, quickly, and accurately** through quantitative deep learning models.

---

## 🚀 Objectives

* Develop a model that classifies stocks into quadrants based on both fundamental and technical indicators.
* Provide a **quantitative decision support tool** for investors and analysts.
* Demonstrate how **deep learning** can improve investment decision-making accuracy.

---

## 🧩 Methodology (CRISP–DM)

The project follows the **CRISP–DM** framework:

1. **Business Understanding**
   Identify investment decision challenges in the Thai stock market.

2. **Data Understanding**

   * Collect data from **SETTRADE Open API**, **Yahoo Finance**, and **SmartSET**.
   * Use both **fundamental** and **technical** data.

3. **Data Preparation**

   * Clean, normalize, and merge datasets.
   * Feature engineering (EMA, RSI, market cap, volatility).
   * Encode categorical variables, scale numeric values with `StandardScaler`.

4. **Modeling**

   * Train multiple models (KMeans, Decision Tree, KNN, ANN, Deep Learning).
   * Final model: **Deep Learning (ANN with ReLU, Dropout, Softmax)**.
   * Accuracy target: **≥85%**.

5. **Evaluation**

   * Use Accuracy, F1-score, and Confusion Matrix.
   * Compare predicted vs true quadrants.

6. **Deployment**

   * Save model as `.h5`
   * Save `scaler.pkl` and `label_encoder.pkl`
   * Build prediction system for real-time stock input.

---

## 📚 Data Sources

| Source                     | Type        | Description                        |
| -------------------------- | ----------- | ---------------------------------- |
| SETTRADE Open API          | Fundamental | EPS, PE, PBV, Dividend Yield, etc. |
| Cassandra / PostgreSQL     | Storage     | Historical market data             |
| Yahoo Finance (`yfinance`) | Technical   | Close, Open, High, Low, Volume     |
| SmartSET API               | Additional  | Real-time updates                  |

---

## 🧮 Features Used

**Fundamental Indicators**

* `eps`, `pe`, `pbv`, `percentyield`, `marketcap`

**Technical Indicators**

* `close_price`, `high_price`, `low_price`, `open_price`, `value`,
* `ema5`, `ema15`, `ema35`, `ema89`, `ema200`, `rsi`

---

## 🧠 Deep Learning Model Architecture

```python
Input Layer (16 features)
↓
Dense (128 neurons, ReLU)
↓
Dropout (0.3)
↓
Dense (64 neurons, ReLU)
↓
Dropout (0.3)
↓
Dense (25 neurons, Softmax)
```

**Loss:** Categorical Cross-Entropy
**Optimizer:** Adam
**Accuracy target:** ≥ 0.85

---

## 📈 Model Performance

| Model                     | Accuracy | Description           |
| ------------------------- | -------- | --------------------- |
| KMeans                    | 0.61     | Baseline clustering   |
| Decision Tree             | 0.72     | Interpretable model   |
| KNN                       | 0.75     | Distance-based        |
| ANN                       | 0.81     | Multi-layer network   |
| **Deep Learning (Final)** | **0.87** | Best-performing model |

---

## 🔍 Example Output (Prediction)

| Symbol | True Quadrant | Predicted Quadrant |
| ------ | ------------- | ------------------ |
| AOT    | Ab            | Ab                 |
| PTT    | Aa            | Aa                 |
| SCB    | Cb            | Bb                 |
| CPALL  | Da            | Da                 |
| KBANK  | Bb            | Bb                 |

---

## 🔥 Visualization

* **Quadrant Heatmap:** Distribution of predicted quadrants (A–E × a–e).
* **Correlation Matrix:** Relationship between financial indicators.
* **Feature Importance Plot:** Top features influencing prediction.

Example:

```python
fig = px.imshow(heatmap_data, 
    labels=dict(x="Trend (a–e)", y="Fundamental Group (A–E)", color="Stock Count"),
    color_continuous_scale="YlOrRd",
    text_auto=True)
fig.show()
```

---

## 💾 Files & Artifacts

| File                     | Description                 |
| ------------------------ | --------------------------- |
| `final100.ipynb`         | Main Jupyter Notebook       |
| `deep_quadrant_model.h5` | Trained Deep Learning model |
| `scaler.pkl`             | StandardScaler object       |
| `label_encoder.pkl`      | LabelEncoder for quadrants  |
| `quadrant_heatmap.png`   | Visualization output        |

---

## ⚙️ How to Run

```bash
# 1. Install dependencies
pip install pandas numpy scikit-learn tensorflow plotly cassandra-driver yfinance joblib

# 2. Run the notebook
jupyter notebook final100.ipynb

# 3. Predict new stock
python predict_stock.py "PTT"

# 4. Output files
deep_quadrant_model.h5
scaler.pkl
label_encoder.pkl
```

---

## 💡 Business Model Canvas

* **Value Proposition:** Fast, AI-based stock categorization.
* **Customer Segments:** Retail & institutional investors, analysts, fintechs.
* **Channels:** Web dashboard, API integration.
* **Revenue Streams:** Subscription, API licensing, consulting.

---
