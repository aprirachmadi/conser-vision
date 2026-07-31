# Conser-Vision

A **camera-trap image classification** project for identifying animal species in wildlife imagery. Based on the [Conservision Practice Area](https://www.drivendata.org/competitions/87/competition-image-classification-wildlife-conservation/) competition on DrivenData — a practice competition using a real-world dataset of wildlife images from [Tai National Park](https://en.wikipedia.org/wiki/Ta%C3%AF_National_Park) in Côte d'Ivoire.

Camera traps let conservationists study and monitor ecosystems with minimal human interference, but they generate far more data than humans can review. This project applies computer vision to automate **species detection and identification** from camera-trap photos.

## What's in this repo

```text
conser-vision/
├── benchmark.ipynb               # End-to-end baseline: EDA, training, evaluation, submission
├── notebooks/
│   └── test-data.ipynb           # Data exploration notebook
├── tests/                        # Test suite
├── pyproject.toml                # Project configuration (uv, Python ≥ 3.10, CUDA 12.8)
├── uv.lock                       # Locked dependency resolution
└── README.md
```

## Task

Predict a **multi-label indicator vector** for each image — the species present among:

- `antelope_duiker`
- `bird`
- `blank` (no animal)
- `civet_genet`
- `hog`
- `leopard`
- `monkey_prosimian`
- `rodent`

## Getting started

### Requirements

- Python ≥ 3.10 (the project targets 3.10–3.13)
- PyTorch / torchvision (CUDA 12.8 build via uv's PyTorch index)
- `uv` (recommended) or pip

### Setup

```powershell
# Create the virtual environment and install dependencies
uv sync
```

### Data

Download the competition data from the [Data Download](https://www.drivendata.org/competitions/87/competition-image-classification-wildlife-conservation/data/) page on DrivenData. The archive contains:

```text
├── benchmark.ipynb
├── submission_format.csv
├── test_features/          # test images
├── test_features.csv
├── train_features/          # train images
├── train_features.csv
└── train_labels.csv         # multi-label species indicators
```

## Notebook workflow

`benchmark.ipynb` walks through the full modeling lifecycle:

1. Environment setup
2. Download the data
3. Explore the data (image and label distributions)
4. Split into train and evaluation sets
5. Build a PyTorch classification model
6. Train the model
7. Evaluate performance
8. Create a submission

## Tech stack

- **Python 3** + **PyTorch / torchvision**
- **pandas**, **matplotlib**, **Pillow**, **scikit-learn**, **tqdm**
- Managed with **uv**
