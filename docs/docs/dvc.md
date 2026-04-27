# DVC Pipeline & Reproducibility

Each pipeline stage is registered using dvc stage add, defining:

- Dependencies (code and data)

- Outputs

- Parameters

Once defined, the entire workflow can be reproduced using:

`dvc repro`

### DVC tracks:

- Intermediate datasets

- Trained models

- Evaluation metrics

This guarantees that results are reproducible across machines and time.