# 📊 Bank Marketing Subscription Prediction API

This project predicts whether a bank customer will subscribe to a **term deposit** using a machine learning model trained on the **Portuguese Bank Marketing Dataset**.  
The trained model is deployed as a **FastAPI REST API** for real-time predictions.

---

## 🎯 Problem Statement
Banks run marketing campaigns to promote term deposits, but only a small percentage of customers subscribe.  
The dataset is **highly imbalanced**, making accuracy unreliable.

This project:
- Handles class imbalance using **SMOTE**
- Uses **F1-score** as the primary evaluation metric
- Deploys the best-performing model as an API

---

## 🧠 Model Overview
- **Best Model:** Tuned LightGBM
- **Evaluation Metric:** F1 Score
- **Techniques Used:**
  - SMOTE for class imbalance
  - Feature engineering (`duration_log`, `previously_contacted`)
  - Hyperparameter tuning
  - Cross-validation

---

## ⚙️ Tech Stack
- Python  
- Scikit-learn  
- LightGBM  
- FastAPI  
- Uvicorn  
- Joblib  
- Pandas & NumPy  

---

## 📁 Project Structure
bank-marketing-api/
│
├── app.py
├── bank_marketing_model.pkl
├── requirements.txt
├── README.md
└── .gitignore

yaml
Copy code

---

## 🚀 How to Run the API Locally

### 1️⃣ Install dependencies
```bash
pip install -r requirements.txt
2️⃣ Start the API server
bash
Copy code
python -m uvicorn app:app --reload
3️⃣ Open HOPPSCOTCH
arduino
Copy code
http://127.0.0.1:8000/docs
🔍 Sample Prediction Request
json
Copy code
{
  "age": 35,
  "job": "admin.",
  "marital": "married",
  "education": "university.degree",
  "default": "no",
  "housing": "yes",
  "loan": "no",
  "contact": "cellular",
  "month": "may",
  "day_of_week": "mon",
  "duration": 300,
  "campaign": 1,
  "pdays": 999,
  "previous": 0,
  "poutcome": "nonexistent",
  "emp_var_rate": 1.1,
  "cons_price_idx": 93.994,
  "cons_conf_idx": -36.4,
  "euribor3m": 4.857,
  "nr_employed": 5191
}
✅ Sample Response
json
Copy code
{
  "subscription_prediction": 0,
  "subscription_probability": 0.0393
}
📌 Conclusion
This API successfully predicts customer subscription behavior for term deposits.
The tuned LightGBM model demonstrates strong performance on imbalanced data, supported by high F1-score, ROC-AUC, and KS statistics, making it suitable for real-world banking and marketing applications.

👩‍💻 Author
Abisha C
