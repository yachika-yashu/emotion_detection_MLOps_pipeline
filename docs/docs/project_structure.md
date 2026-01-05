Project Structure (CCDS)

The repository follows the Cookiecutter Data Science layout to keep data, code, and artifacts cleanly separated.

```md 
emotion_detection_MLOps_pipeline/
├── data/
│   ├── raw/          # Train/test splits
│   ├── interim/      # Cleaned & normalized text
│   └── processed/    # Feature-engineered datasets
├── src/
│   ├── data/
│   │   ├── data_ingestion.py
│   │   └── data_preprocessing.py
│   ├── features/
│   │   └── feature_engineering.py
│   └── model/
│       ├── model_building.py
│       └── model_evaluation.py
├── models/           # Trained model artifacts
├── reports/          # Metrics and evaluation results
├── notebooks/        # Exploratory work
├── docs/             # Documentation
├── dvc.yaml
├── dvc.lock
├── params.yaml
├── requirements.txt
└── README.md
```
This structure makes it clear what is code, what is data, and what is output.