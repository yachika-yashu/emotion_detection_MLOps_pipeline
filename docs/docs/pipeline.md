# ML Pipeline Stages

The pipeline is composed of five deterministic stages, each implemented as an independent script and tracked by DVC.

## 1. Data Ingestion

- Loads the raw dataset from a remote source

- Filters only happiness and sadness labels

- Converts labels to binary format

- Performs train/test split

- Outputs written to data/raw/

## 2. Data Preprocessing

- Normalizes text data

- Steps include lowercasing, stopword removal, lemmatization, and noise removal

- Cleaned text stored in data/interim/

## 3. Feature Engineering

- Converts text into numerical features using TF-IDF

- Feature size controlled through parameters

- Outpu- ts written to data/processed/

## 4. Model Building

- Trains a Gradient Boosting classifier

- Hyperparameters are externally configurable

- Trained model saved as models/model.pkl

## 5. Model Evaluation

- Computes Accuracy, Precision, Recall, and AUC

- Metrics stored in reports/metrics.json