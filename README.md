# 🏥 SimuCare – Patient Digital Twin for Joint Clinical & Financial Risk Prediction

> **Research prototype. Decision support only. Not for clinical use.**
> Live demo: https://simu-care.vercel.app/

SimuCare is an AI-powered Digital Twin framework that integrates healthcare analytics and financial risk modeling to predict both medical and economic outcomes for patients. By combining Electronic Health Records (EHRs), healthcare costs, and insurance data, SimuCare creates a virtual representation of a patient that supports forecasting of clinical risks and financial impacts.

---

## 🧠 Problem Statement

Healthcare providers and insurance companies often evaluate patient risk and financial outcomes independently. This fragmented approach leads to:

- Poor resource allocation
- Increased healthcare costs
- Delayed interventions
- Inefficient decision-making

SimuCare bridges this gap with a unified framework that predicts clinical and financial risks together.

---

## 🚀 Features

**Clinical Risk Prediction**
- ICU stay duration prediction (extended ICU stay classification)
- Hospital readmission risk prediction
- Complication risk assessment and patient outcome forecasting

**Financial Risk Prediction**
- Treatment cost estimation
- High-cost patient identification
- Insurance coverage analysis and out-of-pocket expense prediction

**Digital Twin Simulation**
- Virtual patient profile
- Simulation of multiple treatment scenarios
- Comparison of outcomes and costs to support data-driven decisions

**Explainable AI**
- Feature importance analysis and transparent risk scoring
- SHAP-based explanation dashboard (planned, see Future Work)

---

## 🏗️ System Architecture

```
Patient Data (EHR + Insurance + Cost Data)
            │
            ▼
   Data Processing Pipeline
            │
            ▼
   Feature Engineering
            │
 ┌──────────┴──────────┐
 ▼                     ▼
Medical Models    Financial Models
 ▼                     ▼
ICU Risk          Cost Prediction
Readmission       Financial Risk
Complications     Insurance Analysis
 └──────────┬──────────┘
            ▼
      Digital Twin Engine
            ▼
   Scenario Simulation Dashboard
            ▼
 Clinical + Financial Insights
```

---

## 📊 Datasets

| Dataset | Source | Size | Used for |
|---|---|---|---|
| Healthcare | MIMIC-IV (MIT PhysioNet) | 140 ICU stays, 20 key features (demographics, diagnoses, vital signs, lab results) | Extended ICU stay and readmission risk |
| Financial | Mendeley Health Insurance Dataset | ~1,300 records (costs, insurance information, financial indicators) | High-cost patient identification and out-of-pocket expense estimation |

The two datasets come from different sources and are not linked per patient (see Limitations).

---

## 🤖 ML Framework & Model Details

**Libraries:** Python, scikit-learn, XGBoost, LightGBM, Pandas, NumPy

**Tasks**
- Extended ICU stay: binary classification
- Hospital readmission: classification
- Treatment cost estimation: regression
- High-cost patient identification: classification

**Models compared**
- Clinical: Logistic Regression, Random Forest, XGBoost, LightGBM
- Financial: Linear Regression, Logistic Regression, Decision Trees, Random Forest, Gradient Boosting
- Future scope: LSTM and Transformer-based models

**Metrics:** accuracy, AUC and F1-score for classification; R² and MAE for regression.

---

## 📈 Results

**Clinical models**

| Task | Best Model | Accuracy | AUC | F1 |
|---|---|---|---|---|
| Extended ICU stay | Random Forest | 86% | 0.93 | 0.74 |
| Readmission risk | Random Forest | 84% | 0.65 | – |

**Financial model**

| Metric | Value |
|---|---|
| R² score | 0.87 |
| MAE | ~3,137 |

**Key findings**
- Random Forest gave the best performance for the clinical predictions.
- The financial model showed strong cost-forecasting capability (R² 0.87).

---

## ⚠️ Limitations

- The clinical dataset is small (140 ICU stays), so results may not generalise to other hospitals or populations.
- Readmission prediction is modest (AUC 0.65) and should be treated as exploratory.
- Clinical and financial datasets are from different sources and are not linked per patient, so the twin combines them at the framework level, not on one real patient cohort.
- Scenario simulation reflects associations learned from the data, not causal effects of treatments.

---

## 🔒 Ethics, Privacy & Disclaimer

- SimuCare is a research prototype for decision support. It is not a medical device and must not replace clinical judgment.
- It uses public, de-identified research datasets (MIMIC-IV, Mendeley Health Insurance Dataset). The application does not intentionally collect real patient data.
- Any real-world use would need ethical approval, validation on real cohorts, bias audits, and compliance with applicable data-protection law (for example, India's DPDP Act).

---

## 💻 Tech Stack

| Layer | Tools |
|---|---|
| Frontend | React.js, Tailwind CSS |
| Backend | Node.js, Express.js, MongoDB |
| Machine Learning | Python, scikit-learn, XGBoost, Pandas, NumPy |
| Authentication | JWT (JSON Web Tokens) |
| API testing | Postman |

---

## 📂 Project Structure

```
SimuCare/
│
├── frontend/
│   ├── src/
│   ├── public/
│
├── backend/
│   ├── data/
│   ├── models/
│
├── README.md
│
└── requirements.txt
```

---

## ⚡ Installation & Running

```bash
git clone https://github.com/cheshtaaa-ac/SimuCare-.git
cd SimuCare-
```

**Frontend**
```bash
cd frontend && npm install
```

**Backend**
```bash
cd ../backend && npm install
```

**Environment variables** (create a `.env` file in `backend/`)
```
MONGO_URI=<your_mongodb_uri>
JWT_SECRET=<your_secret>
PORT=5000
```

**Run**
```bash
# Backend
npm run dev

# Frontend (in a second terminal)
npm start
```

---

## 🔄 Workflow

1. Collect patient and financial data
2. Clean and preprocess the datasets
3. Engineer relevant features
4. Train clinical prediction models
5. Train financial prediction models
6. Integrate the models into the Digital Twin framework
7. Simulate treatment scenarios
8. Visualize outcomes through the dashboard

---

## 🎯 Objectives

- Build a Patient Digital Twin framework
- Predict medical outcomes accurately
- Forecast financial risks proactively
- Enable treatment scenario simulation
- Improve healthcare decision-making and help reduce costs

---

## 🔮 Future Work

- SHAP-based explainability dashboard
- Real-time hospital data integration and Hospital Information System (HIS) integration
- IoT-enabled patient monitoring
- Multi-hospital deployment and expanded population datasets
- LSTM and Transformer-based prediction models

---

## 👨‍💻 Authors

Cheshta Arora, Gauri Sharma, Saparya Jagannath, Yashasvi Saini
Department of Computer Science and Engineering, Bharati Vidyapeeth's College of Engineering (BVCOE), New Delhi

---

## 📜 License

Released under the MIT License (see `LICENSE`).
