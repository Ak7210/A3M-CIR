# A3M-CIR

A3M-CIR: An Attention-Aware Adversarial Masking Based Self-Supervised Chemometric Framework for Robust Infrared Spectral Analysis

This repository provides the complete pipeline used in our work, including data scraping, data preprocessing, model pretraining, and model finetuning. The code is organized to allow users to reproduce the full data preparation and training workflow described in the paper.

---

## Paper

This repository accompanies the research paper:

A3M-CIR: An Attention-Aware Adversarial Masking Based Self-Supervised Chemometric Framework for Robust Infrared Spectral Analysis

The implementation provided here allows users to reproduce the experiments and training procedures described in the paper.

---

## Overview

The repository contains scripts and notebooks used to collect datasets, preprocess the collected spectra, and train the proposed model.

The workflow begins with scraping the raw datasets. After data collection, preprocessing scripts convert the raw data into a structured format suitable for model training. The processed data can then be used for model pretraining and finetuning.

---

## Repository Structure

The repository consists of the following major components.

### Data Scraping

The repository includes scraping codes that were used to collect the raw spectral datasets. These scripts download and organize the datasets required for the experiments.

The scraped data serves as the input for the preprocessing stage.

---

### Data Preprocessing

After scraping the raw datasets, preprocessing is performed to convert the data into a format suitable for training.

The preprocessing stage includes three files.

#### nist.ipynb

This notebook preprocesses the NIST dataset and converts the raw spectral data into the format required for model training.

#### sdbs.ipynb

This notebook preprocesses the SDBS dataset and prepares it for use in the training pipeline.

#### smarts.py

This script generates and processes SMARTS related representations that are required for the training framework.

These preprocessing files transform the raw scraped data into structured datasets that can be directly used during model training.

---

## Model Pretraining

The repository provides the code required to pretrain the model described in the paper.

The pretraining process uses the processed datasets generated during the preprocessing stage. To run the pretraining pipeline, users only need to provide the path to the training data files and configure the training parameters according to the values described in the paper.

---

## Model Finetuning

The repository also includes code for finetuning the pretrained model.

Finetuning allows the pretrained model to adapt to specific datasets and evaluation tasks. To perform finetuning, users need to provide the paths to the training dataset, validation dataset, and testing dataset.

All parameters should be set according to the configuration described in the paper to reproduce the reported results.

---

## Usage Workflow

The recommended workflow for using this repository is as follows.

Step 1  
Run the scraping scripts to collect the raw spectral datasets.

Step 2  
Run the preprocessing notebooks and scripts to convert the raw data into structured datasets.

Step 3  
Run the pretraining code using the processed datasets.

Step 4  
Run the finetuning code by providing the paths to the training, validation, and testing datasets and configuring the parameters according to the paper.

---

## Notes

Users only need to update the dataset file paths and configure the parameters according to the paper. The rest of the pipeline is already implemented in the provided scripts.

This repository is designed to make the data preparation and model training process easy to reproduce.
