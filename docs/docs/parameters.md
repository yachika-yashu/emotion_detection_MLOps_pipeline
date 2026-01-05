# Parameter Management

All tunable values are stored in params.yaml. This allows experiments to be rerun without touching code.

Example:
```
data_ingestion:
  test_size: 0.2


feature_engineering:
  max_features: 50


model_building:
  n_estimators: 25
  learning_rate: 0.1
```

Changing any parameter automatically triggers only the affected pipeline stages when running dvc repro.