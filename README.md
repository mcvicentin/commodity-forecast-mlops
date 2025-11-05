# commodity-forecast-mlops
End-to-end MLOps pipeline for forecasting commodity returns using global financial data (LME, JPX, US, and FX).


## Overview
This repository implements a full machine learning lifecycle:
- Data ingestion and feature engineering (PySpark/Pandas)
- Model training and tracking (PyTorch + MLflow)
- Model serving via FastAPI + Docker
- Deployment on Render or Cloud Run
- Monitoring & drift detection (Evidently AI)


## Project structure
```
commodity-forecast-mlops/
│
├── data/
│   ├── raw/               # arquivos originais (train.csv, test.csv etc.)
│   └── processed/         # versões pós-ETL e feature engineering
│
├── notebooks/
│   └── 01_eda.ipynb       # análise exploratória inicial
│
├── src/
│   ├── data/
│   │   ├── load_data.py
│   │   └── preprocess.py
│   ├── features/
│   │   └── build_features.py
│   ├── models/
│   │   ├── train_model.py
│   │   └── evaluate.py
│   ├── api/
│   │   └── app.py
│   └── monitoring/
│       └── drift_report.py
│
├── tests/
│   └── test_api.py
│
├── mlflow/                # tracking de experimentos
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── .gitignore
├── requirements.txt
├── Dockerfile
├── Makefile
├── dvc.yaml
└── README.md

```
