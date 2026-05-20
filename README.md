# CSCI323 - Spam Email Detection

## Overview
A machine learning project to detect spam emails using multiple baseline models.

## Models
- Naïve Bayes
- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest

## Prerequisites
- Python 3.10+
- Google Colab or Anaconda
- Download dataset from: https://archive.ics.uci.edu/dataset/228/sms+spam+collection
- Rename downloaded file to `spam.csv`

## How to Run
Run notebooks in the following order:

1. `01_data_exploration.ipynb` 
   - Upload: `spam.csv`
   
2. `02_preprocessing.ipynb` 
   - Upload: `spam.csv`
   - Saves: `X_train.npz`, `X_test.npz`, `y_train.npy`, `y_test.npy`

3. `03_naive_bayes.ipynb` to `06_random_forest.ipynb`
   - Upload: `X_train.npz`, `X_test.npz`, `y_train.npy`, `y_test.npy`
   - Saves: `nb_results.json`, `lr_results.json`, `svm_results.json`, `rf_results.json`

4. `07_evaluation_comparison.ipynb`
   - Upload: all 4 JSON result files from step 3

> **Note:** To ensure consistency, you may use the pre-generated 
> files from our shared Google Drive instead of generating your own:
> - `spam.csv` — original dataset
> - `X_train.npz`, `X_test.npz`, `y_train.npy`, `y_test.npy` — preprocessed data from step 2
> - `nb_results.json`, `lr_results.json`, `svm_results.json`, `rf_results.json` — model results from step 3
>
> 📁 Google Drive:
> 1. Dataset: https://drive.google.com/drive/folders/1r_E9ehREhlj2Ru8vNGiMpM_Vgk6NmDR-?usp=drive_link
> 2. Code Output: https://drive.google.com/drive/folders/187_7veGTZ1chYtzgBRdeXbSS1bePYrq0?usp=drive_link

## Group Members
- Rasydan Irfan
- Arun
- Sherry
  
## Project Structure
- `notebooks/` - Jupyter notebooks for each model
- `results/` - Pre-generated graphs and confusion matrices
