# Reproducing the Project

Clone the repository and run:

```
git clone https://github.com/yachika-yashu/emotion_detection_MLOps_pipeline.git
cd emotion_detection_MLOps_pipeline
dvc pull
dvc repro
```

This fetches the correct data and artifacts and rebuilds the full ML pipeline end-to-end.