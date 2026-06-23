#  Customer Churn Prediction with MLOps-Based Data Drift Detection

An end-to-end MLOps-enabled machine learning pipeline that predicts customer 
churn, monitors data drift, and performs automated model retraining to ensure 
continuous reliability.

##  Project Overview
Traditional ML models degrade over time due to evolving customer behavior.
This project solves that by building a self-correcting pipeline that:
-  Predicts whether a customer will churn using Random Forest
-  Monitors incoming data for distribution shifts (data drift)
-  Automatically retrains the model when drift is detected

##  Tech Stack
- **ML Model:** Random Forest Classifier (scikit-learn)
- **Drift Detection:** Evidently AI
- **Data:** ChurnModelling.csv (10,000 customer records)
- **Serialization:** Joblib (.pkl files)

##  How It Works
1. **Train** — Random Forest trained on 80% of 10,000 customer records
2. **Monitor** — Incoming data compared against training distribution
3. **Detect** — 20% mean deviation triggers drift alert via Evidently AI
4. **Retrain** — Model automatically retrains on updated data and saves new .pkl

##  Results
- High classification accuracy on test data
- Key churn drivers: Age, Balance, Activity Level
- Drift detection successfully triggered on simulated distribution shifts
- Automated retraining recovered model accuracy post-drift

##  Future Scope
- Advanced drift detection using PSI or KL Divergence
- Real-time streaming with Apache Kafka
- Cloud deployment on AWS/GCP with CI/CD pipelines
- Interactive monitoring dashboards via Grafana
