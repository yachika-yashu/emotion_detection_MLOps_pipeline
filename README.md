
# Emotion Detection – Reproducible ML Pipeline with DVC

## Project Overview

This project builds an **Emotion Detection machine learning pipeline** that classifies text into **happiness** or **sadness**.  
The primary objective is to demonstrate a **complete MLOps workflow**, covering experimentation, pipeline orchestration, reproducibility, and version control.

The project starts with notebook-based experimentation and evolves into a **production-style ML pipeline** using:

- Python
    
- DVC (Data Version Control)
    
- Git
    
- Cookiecutter Data Science (CCDS) structure
    

The pipeline is fully reproducible using `dvc repro`.

---

## Project Structure (CCDS)

````md
```text
emotion_detection_MLOps_pipeline/
├── data/
│   ├── raw/
│   ├── interim/
│   └── processed/
├── src/
│   ├── data/
│   │   ├── data_ingestion.py
│   │   └── data_preprocessing.py
│   ├── features/
│   │   └── feature_engineering.py
│   └── model/
│       ├── model_building.py
│       └── model_evaluation.py
├── models/
├── reports/
├── notebooks/
├── docs/
├── dvc.yaml
├── dvc.lock
├── params.yaml
├── requirements.txt
├── README.md
└── .gitignore

````
This project follows the **Cookiecutter Data Science (CCDS)** convention to ensure separation of concerns and long-term maintainability.

---

## ML Pipeline Stages

### 1. Data Ingestion

- Loads the dataset from a remote source
    
- Filters required sentiments
    
- Splits data into train and test sets
    
- Outputs stored in `data/raw/`
    

### 2. Data Preprocessing

- Text normalization:
    
    - Lowercasing
        
    - Stopword removal
        
    - Lemmatization
        
    - URL, punctuation, and number removal
        
- Outputs stored in `data/interim/`
    

### 3. Feature Engineering

- TF-IDF vectorization
    
- Configurable feature size via `params.yaml`
    
- Outputs stored in `data/processed/`
    

### 4. Model Building

- Trains a Gradient Boosting classifier
    
- Hyperparameters controlled via `params.yaml`
    
- Model saved to `models/model.pkl`
    

### 5. Model Evaluation

- Computes Accuracy, Precision, Recall, and AUC
    
- Metrics saved to `reports/metrics.json`
    

---

## Parameter Management (`params.yaml`)

All tunable parameters are centralized:

`data_ingestion:   test_size: 0.2  feature_engineering:   max_features: 50  model_building:   n_estimators: 25   learning_rate: 0.1`

This enables controlled experimentation without modifying code.

---

## DVC Pipeline

Each pipeline stage is defined using `dvc stage add`.  
Example:

`dvc stage add -n data_ingestion \ -d src/data/data_ingestion.py \ -o data/raw \ -p data_ingestion.test_size \ python src/data/data_ingestion.py`

To reproduce the full pipeline:

`dvc repro`

DVC automatically tracks:

- Data
    
- Model artifacts
    
- Metrics
    
- Pipeline dependencies
    

---

## Version Control Strategy

- **Git** → source code, configuration, documentation
    
- **DVC** → datasets, pipeline outputs, trained models
    

This ensures full experiment traceability and reproducibility.

---

## Reproducing the Project
```
git clone https://github.com/yachika-yashu/emotion_detection_MLOps_pipeline.git
cd emotion_detection_MLOps_pipeline
dvc pull
dvc repro
```

📘 Project Documentation   👉 [https://yachika-yashu.github.io/emotion_detection_MLOps_pipeline](https://yachika-yashu.github.io/emotion_detection_MLOps_pipeline/)

