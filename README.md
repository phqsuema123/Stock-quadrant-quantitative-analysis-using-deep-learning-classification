# Stock-quadrant-quantitative-analysis-using-deep-learning-classification
ได้เลยครับ ผมจะช่วยทำ **README.md** สำหรับไฟล์ `present50percent.ipynb` โดยอิงจากไฟล์โปรเจกต์ *Stock quadrant quantitative analysis using deep learning classification* ที่คุณอัปโหลดไว้

---

# 📊 Stock Quadrant Quantitative Analysis using Deep Learning

## 📌 Overview

This project develops a **Quadrant Stock Level System** that classifies Thai stocks into quadrants based on:

* **Fundamental Factors** (e.g., EPS, P/E, PBV, Dividend Yield)
* **Market Trends** (Uptrend, Downtrend, Sideways, etc.)

It integrates **Deep Learning** models with **financial and technical indicators** to provide an automated, systematic, and accurate stock analysis tool for algorithmic trading.

---

## 🚀 Features

* 📈 **Stock Classification** into 25 quadrants (Aa–Ee).
* 🤖 **Deep Learning Model (ANN)** for quantitative trading signals.
* 🔄 **Real-time data ingestion** from **SETTRADE API**.
* 🛠️ **ETL Pipeline** to clean, transform, and store data in Cassandra.
* 📊 **Visualization Dashboard** with Plotly (quadrants, heatmaps, correlation matrix).
* ✅ Model evaluation with **Accuracy & F1-score** benchmarks.

---

## 📂 Project Structure

```
present50percent.ipynb     # Main Jupyter Notebook
Stock quadrant quantitative analysis using deep learning classification.pdf
README.md                  # Documentation (this file)
```

---

## ⚙️ Tech Stack

* **Languages**: Python
* **Libraries**: pandas, numpy, scikit-learn, tensorflow/keras, xgboost, plotly
* **Database**: PostgreSQL
* **APIs**: SETTRADE Open API (Thai stock exchange data)
* **Visualization**: Plotly, Matplotlib

---

## 🧪 Methodology (CRISP-DM)

1. **Business Understanding**
   Define the problem: complexity of stock analysis & lack of prioritization tools.
2. **Data Understanding**
   Collect **fundamental** and **technical** data via SETTRADE API.
3. **Data Preparation**
   Clean, normalize, and create features (EMA, RSI, volatility, etc.).
4. **Modeling**
   Train ANN classifier for quadrant classification.
5. **Evaluation**
   Target accuracy ≥ 85% using accuracy and F1-score.
6. **Deployment**
   Build API & dashboard for real-time visualization.

---

## 📊 Example Quadrant Classification

* **Aa** → Strong fundamentals + Uptrend → Long-term buy
* **Ee** → Weak fundamentals + Downtrend → Avoid
* **Cb / Db** → Moderate fundamentals + Improving trends → Short-term trading

---

## 🔑 Key Results

* 📌 Accuracy benchmark: **≥ 85%**
* 📌 Quadrant visualization improves investor decision-making speed.
* 📌 API dashboard provides **real-time response ≤ 2 seconds**.

---
