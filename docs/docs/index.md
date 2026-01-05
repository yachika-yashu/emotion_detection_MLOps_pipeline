# Emotion detection pipeline using DVC documentation!

## Description

Emotion detection app that analyzes text to determine whether it conveys happiness or sadness. Primary goal is to integrate the **MLOps process** throughout the project lifecycle.

## Commands

The Makefile contains the central entry points for common tasks related to this project.

### Syncing data to cloud storage

* `make sync_data_up` will use `aws s3 sync` to recursively sync files in `data/` up to `s3://emotion detection/data/`.
* `make sync_data_down` will use `aws s3 sync` to recursively sync files from `s3://emotion detection/data/` to `data/`.


