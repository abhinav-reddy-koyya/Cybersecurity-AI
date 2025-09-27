AI in Cybersecurity – Intrusion Detection System (UNSW-NB15)

Project Summary

This project demonstrates how Artificial Intelligence (AI) can be applied to Cybersecurity by building an Intrusion Detection System (IDS).
Using the UNSW-NB15 dataset, the system learns to differentiate between normal network traffic and various types of cyberattacks (e.g., DoS, Exploits, Fuzzers).

The project includes a Streamlit dashboard that makes the AI model interactive and visual:

Load and preview training/testing datasets

Train an ML model (Random Forest Classifier by default)

Evaluate with confusion matrix, ROC curve, and classification metrics

Flag and explore malicious records in test data

This acts as a mini Security Operations Center (SOC) dashboard powered by AI.

Features

Dataset Handling: Auto-loads UNSW-NB15 train/test splits or allows CSV uploads.

Model Training: Machine Learning pipeline with preprocessing, encoding, and scaling.

Evaluation Metrics: Accuracy, Precision, Recall, F1-score, Confusion Matrix, ROC Curve.

Attack Analysis: Flags malicious traffic records and visualizes attack distribution.

Interactive Dashboard: Built with Streamlit for real-time analysis.

Project Structure
cybersecurity-ai/
│── app.py                     # Main Streamlit dashboard
│── requirements.txt           # Dependencies
│── README.md                  # Documentation
│
├── data/                      # Dataset storage
│   ├── UNSW_NB15_training-set.csv
│   ├── UNSW_NB15_testing-set.csv
│   ├── NUSW-NB15_features.csv
│   └── UNSW-NB15_LIST_EVENTS.csv
│
├── utils/                     # Helper scripts
│   ├── __init__.py
│   ├── data_loader.py         # Load & preprocess dataset
│   ├── model.py               # Train & evaluate ML models
│   ├── visualizations.py      # Confusion Matrix & ROC plots
│   └── helpers.py             # (Future utils: scalers, encoders)
│
├── models/                    # Trained models (pickle format)
│   └── rf_model.pkl
│
├── notebooks/                 # Jupyter notebooks (EDA, testing)
│   └── exploratory_analysis.ipynb
│
├── logs/                      # Training logs
│   └── training.log
│
└── reports/                   # Saved visualizations & reports
    ├── confusion_matrix.png
    ├── roc_curve.png
    └── performance_report.txt

Dataset

We use the UNSW-NB15 Intrusion Detection dataset, created by the University of New South Wales, which contains modern network attack types.

Training set: UNSW_NB15_training-set.csv

Testing set: UNSW_NB15_testing-set.csv

Features: 49 attributes (protocol, service, src_bytes, dst_bytes, flags, etc.)

Target Label: label (0 = Normal, 1 = Attack)

More info: UNSW-NB15 Dataset

Tech Stack

Python 3.10+

Libraries: Streamlit, scikit-learn, Pandas, NumPy, Seaborn, Matplotlib, Joblib

ML Model: Random Forest Classifier (extensible to XGBoost, DL models)

Visualization: Streamlit interactive dashboard

Installation & Setup
1. Clone the Repository
cd cybersecurity-ai

2. Install Dependencies
pip install -r requirements.txt

3. Place Dataset

Download UNSW-NB15 dataset and place the CSVs inside the data/ folder:

UNSW_NB15_training-set.csv

UNSW_NB15_testing-set.csv

4. Run the App
streamlit run app.py

Example Outputs

Classification Report: Accuracy, Precision, Recall, F1

Confusion Matrix: Heatmap of correct vs incorrect classifications

ROC Curve: Area under curve (AUC) for model performance

Flagged Malicious Records: Interactive view of predicted attacks

Future Enhancements

Add KPI Metric Cards (Accuracy %, Precision %, Recall %) at the top.

Compare multiple models (RandomForest, XGBoost, Neural Networks).

Integrate real-time log streaming via Kafka.

Deploy to AWS/GCP/Azure for enterprise-ready IDS.

Expand dashboard with attack-type breakdowns.

Author

Abhinav Reddy Koyya
M.S. in Computer Science, NYIT
