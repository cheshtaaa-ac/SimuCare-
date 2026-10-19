## 📏 Evaluation Methodology
- **Clinical models:** trained and evaluated on 140 ICU stays (MIMIC-IV) using [train/test split, e.g. 80/20 stratified] [and 5-fold cross-validation, if used].
- **Financial models:** trained and evaluated on ~1,300 records using [split details].
- **Metrics:** accuracy, AUC, F1-score for classification; R² and MAE for cost regression.
- Models compared: Logistic Regression, Random Forest, XGBoost, LightGBM, [others actually run].

## ⚠️ Limitations
- The clinical dataset is small (140 ICU stays), so results may not generalise to other hospitals or populations.
- Readmission prediction is modest (AUC 0.65) and should be treated as exploratory.
- Clinical and financial datasets come from **different sources** and are not linked per patient; the digital twin combines them at the framework level rather than on one real patient cohort.
- Scenario simulation shows associations learned from the data, **not causal effects** of treatments.
- [SHAP explanations: say here whether they are implemented or still future work.]

## 🔒 Ethics, Privacy & Disclaimer
- SimuCare is a **decision-support research prototype**. It is not a medical device and must not replace clinical judgment or be used for real patient care.
- The datasets used are public/de-identified research datasets (MIMIC-IV from PhysioNet, Mendeley Health Insurance Dataset). No personal patient data is collected or stored by this application.
- Any real-world deployment would require ethical approval, validation on real cohorts, bias audits, and compliance with applicable data-protection law (e.g. India's DPDP Act).

## 🧪 How to Run the ML Part
```bash
cd backend
pip install -r ../requirements.txt
python [your_training_script].py     # trains models and saves them to backend/models/
```
Then start the backend and frontend as described in Installation above.

## 🤝 Contributions
- Saparya Jagannath: [your teammate's part]
- Gauri Sharma: [part]
- Cheshta Arora: [your part]
- Yashasvi Saini: [part]
