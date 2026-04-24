# Rotating Machinery Health Monitoring

A portfolio project exploring machine learning approaches to predictive maintenance and condition-based health monitoring of rotating machinery. Built as a self-directed upskilling exercise using publicly available benchmark datasets.

## Motivation

Traditional maintenance strategies for rotating assets are time-based, reactive, or run-to-failure. This leads to unnecessary downtime, excessive maintenance costs, and safety risks. Data-driven approaches offer a route to proactive, condition-based strategies by identifying faults and degradation patterns before failure occurs.

This repo explores three progressively more complex approaches to that problem.

---

## Projects

### 1. Bearing Fault Classification
**Dataset:** [CWRU Bearing Dataset](https://engineering.case.edu/bearingdatacenter) — vibration signals from drive-end and fan-end accelerometers under four fault conditions.

**Approach:** Extract time and frequency domain features from raw vibration signals (RMS, kurtosis, FFT spectral features), then train a Random Forest classifier to distinguish normal operation from three fault types (inner race, outer race, ball fault).

**Key outputs:** Classification report, confusion matrix, feature importance ranking.

---

### 2. Anomaly Detection on Sensor Data
**Dataset:** [Pump Sensor Dataset](https://www.kaggle.com/datasets/nphantawee/pump-sensor-data) — multivariate time-series from 52 sensors on an industrial pump.

**Approach:** Two complementary methods. Isolation Forest for classical unsupervised anomaly detection, and an LSTM autoencoder to model normal behaviour and flag deviations via reconstruction error. The reconstruction error time-series serves as a continuous asset health score.

**Key outputs:** Anomaly labels over time, reconstruction error plots, comparison of both methods.

---

### 3. Asset Health Dashboard
**Dataset:** Outputs from Project 2.

**Approach:** Streamlit dashboard visualising the continuous health score from the LSTM autoencoder, with a RAG (Red/Amber/Green) status indicator per asset and time-series plots of sensor behaviour around flagged anomalies.

**Key outputs:** Interactive dashboard deployable locally or via Streamlit Community Cloud.

---

## Repo Structure

```
rotating-machinery-health-monitoring/
├── 01_bearing_fault_classification/
│   ├── src/
│   └── notebooks/
├── 02_anomaly_detection/
│   ├── src/
│   └── notebooks/
├── 03_health_dashboard/
│   └── src/
├── tests/
├── environment.yml
└── README.md
```

## Setup

```bash
git clone https://github.com/Dazcam/rotating-machinery-health-monitoring.git
cd rotating-machinery-health-monitoring
conda env create -f environment.yml
conda activate rmhm
```

Each project folder contains its own README with dataset download instructions and a Colab badge to run the notebooks directly in the browser.

---

## Tools and Libraries

Python, Scikit-learn, PyTorch, Streamlit, NumPy, Pandas, SciPy, Matplotlib, Seaborn

---

## Status

| Project | Status |
|---|---|
| 01 Bearing fault classification | Complete  |
| 02 Anomaly detection | 🔧 In progress |
| 03 Health dashboard | 🔧 In progress |
