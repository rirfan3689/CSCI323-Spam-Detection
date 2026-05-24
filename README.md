# CSCI323 - Spam Detection Using Machine Learning

## Overview
A comparative study of four machine learning models 
for spam detection across multiple datasets, 
investigating the impact of dataset quality, 
preprocessing and hyperparameter tuning on model 
performance.

## Models
- Naïve Bayes
- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest

## Datasets
| Dataset | Domain | Size | Balance |
|---------|--------|------|---------|
| UCI SMS Collection | SMS | 5,169 | 87/13 |
| SpamAssassin | Email | 5,329 | 67/33 |
| Enron Spam | Email | 33,716 | 51/49 |

> **Note on SpamAssassin:** This dataset was 
> initially used as a second email dataset. 
> However, feature importance analysis revealed 
> that inline HTML tags and email headers were 
> acting as unintended spam signals due to 
> preprocessing limitations. Results are included 
> as a finding on the importance of dataset 
> quality and preprocessing. Enron was subsequently 
> used as a cleaner alternative.

## Prerequisites
- Python 3.10+
- Google Colab or Anaconda

## How to Run

### Phase 1 — UCI SMS Baseline
Run in order:
1. `01_uci_exploration.ipynb` — Upload: `spam.csv`
2. `02_uci_preprocessing.ipynb` — Upload: `spam.csv`
   - Saves: `X_train.npz`, `X_test.npz`, 
             `y_train.npy`, `y_test.npy`
3. `03_uci_naive_bayes.ipynb` to `06_uci_random_forest.ipynb`
   - Upload: processed files from step 2
   - Saves: `nb_results.json`, `lr_results.json`,
             `svm_results.json`, `rf_results.json`
4. `07_uci_evaluation.ipynb`
   - Upload: all 4 JSON files from step 3

### Phase 2 — SpamAssassin (Preprocessing Finding)
5. `08_sa_exploration.ipynb` — Upload: `spam_assassin.csv`
6. `09_sa_preprocessing.ipynb` — Upload: `spam_assassin.csv`
   - Saves: `sa_X_train.npz`, `sa_X_test.npz`,
             `sa_y_train.npy`, `sa_y_test.npy`
7. `10_sa_models.ipynb`
   - Upload: processed files from step 6
   - Saves: `sa_results.json`

> ⚠️ SpamAssassin results should be interpreted 
> with caution due to HTML preprocessing limitations.
> See report Section 4.6 for full discussion.

### Phase 3 — Enron Email Baseline
8. `11_enron_exploration.ipynb` — Upload: `enron_spam_data.csv`
9. `12_enron_preprocessing.ipynb` — Upload: `enron_spam_data.csv`
   - Saves: `enron_X_train.npz`, `enron_X_test.npz`,
             `enron_y_train.npy`, `enron_y_test.npy`
10. `13_enron_models.ipynb`
    - Upload: processed files from step 9
    - Saves: `enron_results.json`

### Phase 4 — Advanced Analysis
11. `14_cross_validation.ipynb`
    - Upload: UCI + Enron training files
12. `15_hyperparameter_tuning.ipynb`
    - Upload: UCI + Enron processed files + JSON results
13. `16_feature_importance.ipynb`
    - Upload: all processed files + raw CSV files
14. `17_neural_network.ipynb`
    - Upload: UCI + Enron processed files
15. `18_final_comparison.ipynb`
    - Upload: all JSON result files

> **Note:** Pre-generated processed files and 
> results are available on Google Drive for 
> consistency:
> 📁 Google Drive:
> 1. Dataset: https://drive.google.com/drive/folders/1r_E9ehREhlj2Ru8vNGiMpM_Vgk6NmDR-?usp=drive_link
> 2. Code Output: https://drive.google.com/drive/folders/187_7veGTZ1chYtzgBRdeXbSS1bePYrq0?usp=drive_link

## Project Structure
- `notebooks/` - All Jupyter notebooks by phase
- `results/` - Pre-generated graphs and metrics

## Key Findings
- SVM consistently outperformed other models
- Class imbalance significantly impacts LR recall
- Dataset quality and preprocessing critically 
  affect model interpretability
- SpamAssassin HTML preprocessing revealed 
  importance of domain-specific data cleaning
   - Upload: all result files from both datasets

## Group Members
- Rasydan Irfan
- Arun
- Sherry
  
## Project Structure
- `notebooks/` - Jupyter notebooks for each model
- `results/` - Pre-generated graphs and confusion matrices
