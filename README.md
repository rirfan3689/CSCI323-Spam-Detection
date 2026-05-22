# CSCI323 - Spam Detection

## Overview
A comparative study of four machine learning models for 
spam detection across two datasets — UCI SMS Collection 
and SpamAssassin Email Dataset.

## Models
- Naïve Bayes
- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest

## Datasets
- **UCI SMS Spam Collection** — SMS messages, body only
- **SpamAssassin Email Dataset** — Full emails including 
  headers, subject and body

## Prerequisites
- Python 3.10+
- Google Colab or Anaconda

## How to Run

Run notebooks in the following order:

### UCI SMS Dataset
1. `01_data_exploration.ipynb` 
   - Upload: `spam.csv`
2. `02_preprocessing.ipynb` 
   - Upload: `spam.csv`
   - Saves: `X_train.npz`, `X_test.npz`, `y_train.npy`, `y_test.npy`
3. `03_naive_bayes.ipynb` to `06_random_forest.ipynb`
   - Upload: processed data files from step 2
   - Saves: `nb_results.json`, `lr_results.json`, `svm_results.json`, `rf_results.json`
4. `07_evaluation_comparison.ipynb`
   - Upload: all 4 JSON result files from step 3

### SpamAssassin Email Dataset
5. `08_spamassassin_exploration.ipynb`
   - Upload: `spam_assassin.csv`
6. `09_spamassassin_preprocessing.ipynb`
   - Upload: `spam_assassin.csv`
   - Saves: `sa_X_train.npz`, `sa_X_test.npz`, `sa_y_train.npy`, `sa_y_test.npy`
7. `10_spamassassin_models.ipynb`
   - Upload: processed data files from step 6
8. `11_final_comparison.ipynb`
   - Upload: all result files from both datasets

> **Note:** To ensure consistency, use pre-generated 
> files from our shared Google Drive:
> - `spam.csv` — UCI dataset
> - `spam_assassin.csv` — SpamAssassin dataset
> - All processed `.npz` and `.npy` files
> - All `.json` result files
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
