# A3M-CIR

## A3M-CIR: An Attention-Aware Adversarial Masking Based Self-Supervised Chemometric Framework for Robust Infrared Spectral Analysis

This repository provides the complete implementation of **A3M-CIR**, a self-supervised chemometric framework for **robust infrared (IR) spectral analysis**.

The repository contains the full pipeline used in the paper, including:

- Data scraping
- Data preprocessing
- Model pretraining
- Model finetuning

The codebase is organized to allow researchers to **reproduce the full data preparation and training workflow** described in the paper.

---

# Paper

This repository accompanies the research paper:

**A3M-CIR: An Attention-Aware Adversarial Masking Based Self-Supervised Chemometric Framework for Robust Infrared Spectral Analysis**

If you use this repository in your research, please cite the paper.

---

# Requirements

- **Python >= 3.9**
- Conda or virtual environment recommended
- **PyTorch**

---

# Repository Structure

```
A3M-CIR/
│
├── scraping/
│   ├── sdbs_data/
│   │   └── CSV files containing molecule details
│   │
│   ├── nist_data/
│   │   └── CSV files containing molecule details
│   │
│   ├── sdbs.ipynb
│   └── nist.ipynb
│
├── preprocessing/
│   ├── nist.ipynb
│   ├── sdbs.ipynb
│   └── smarts.py
│
├── pretraining_code.ipynb
│
├── finetuning_code.ipynb
│
└── README.md
```

---

# Data Collection

The **scraping** directory contains scripts and metadata used to collect spectral datasets.

### Contents

**sdbs_data/**  
Contains CSV files with molecule information collected from the **SDBS database**.

**nist_data/**  
Contains CSV files with molecule information collected from the **NIST database**.

**sdbs.ipynb**  
Notebook used to scrape infrared spectral data from the **SDBS database**.

**nist.ipynb**  
Notebook used to scrape infrared spectral data from the **NIST database**.

These scripts download and organize the raw spectral datasets used for the experiments.

---

# Data Preprocessing

The **preprocessing** directory contains scripts used to convert scraped data into a format suitable for model training.

### Files

**nist.ipynb**  
Preprocesses the scraped NIST spectral data and converts it into the required training format.

**sdbs.ipynb**  
Preprocesses the scraped SDBS spectral data.

**smarts.py**  
Contains definitions of **chemical functional groups using SMARTS (SMiles ARbitrary Target Specification) strings**.  
These SMARTS patterns are used to identify functional groups in molecules and generate structural representations used during preprocessing and model training.

After preprocessing, the datasets are converted into **structured datasets ready for model training**.

---

# Installation

We recommend creating a dedicated environment before running the code.

### Create Environment

```
conda create -n a3m_cir python=3.9
conda activate a3m_cir
```

*(Python version must be **>= 3.9**)*

---

# Model Pretraining

The repository includes a **Jupyter Notebook** for pretraining the A3M-CIR model using the processed datasets.

### Pretraining Notebook

```
pretraining_code.ipynb
```

Open the notebook and run the cells sequentially to perform model pretraining.

Before training, configure the **dataset paths and training parameters** according to the setup described in the paper.

---

# Model Finetuning

The repository also includes a **Jupyter Notebook** for finetuning the pretrained model.

Finetuning allows the model to adapt to specific datasets and evaluation tasks.

### Finetuning Notebook

```
finetuning_code.ipynb
```

Open the notebook and run the cells sequentially to perform finetuning.

Before running the training cells, configure:

- Training dataset path
- Validation dataset path
- Testing dataset path

All hyperparameters should follow the configuration described in the paper.

---

# Usage Workflow

To reproduce the full pipeline, follow these steps:

### Step 1 — Data Scraping

Run the scraping notebooks to collect spectral datasets.

```
scraping/sdbs.ipynb
scraping/nist.ipynb
```

### Step 2 — Data Preprocessing

Convert raw scraped data into structured datasets.

```
preprocessing/sdbs.ipynb
preprocessing/nist.ipynb
```

### Step 3 — Model Pretraining

Run the pretraining notebook to train the self-supervised model.

```
pretraining_code.ipynb
```

### Step 4 — Model Finetuning

Run the finetuning notebook to evaluate and adapt the pretrained model.

```
finetuning_code.ipynb
```

---

# Dataset Sources

The datasets used in this work are obtained from:

- **NIST Chemistry WebBook**
- **SDBS (Spectral Database for Organic Compounds)**

Please refer to the respective databases for their licensing and usage policies.

---

# Reproducibility

To reproduce the results reported in the paper:

- Use the preprocessing pipeline provided in this repository
- Use the same hyperparameters described in the paper
- Run the provided notebooks for pretraining and finetuning

---
