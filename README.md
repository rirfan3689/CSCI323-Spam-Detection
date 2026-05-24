# CSCI323 - Spam Detection Using Machine Learning

## Overview
A comparative study of four machine learning models 
for spam detection, investigating the impact of 
dataset quality, preprocessing, hyperparameter 
tuning and feature importance on model performance.

## Models
- Naïve Bayes
- Logistic Regression
- Support Vector Machine (SVM)
- Random Forest

## Datasets
| Dataset | Domain | Size | Balance | Source |
|---------|--------|------|---------|--------|
| UCI SMS Collection | SMS | 5,169 | 87/13 | [UCI Repository](https://archive.ics.uci.edu/dataset/228/sms+spam+collection) |
| SpamAssassin | Email | 5,329 | 67/33 | [Kaggle](https://www.kaggle.com/datasets/ganiyuolalekan/spam-assassin-email-classification-dataset) |

> **Note on SpamAssassin:** Initially used as a 
> second email dataset. Feature importance analysis 
> revealed HTML tags and email headers were acting 
> as unintended spam signals due to preprocessing 
> limitations. Results are included as a finding 
> on dataset quality and preprocessing importance.

## Key Findings
- SVM consistently outperformed other models
- Class imbalance was the root cause of LR's 
  low recall — resolved with class_weight='balanced'
- Tuned LR (90.15% F1) outperformed tuned SVM 
  (89.88% F1) after addressing class imbalance
- 'prize' and 'claim' were universally identified 
  as spam signals across all four models
- SpamAssassin preprocessing limitations highlight 
  the importance of domain-specific data cleaning

## Prerequisites
- Python 3.10+
- Google Colab or Anaconda

## How to Run

### Phase 1 — UCI SMS Baseline
1. `01_uci_exploration.ipynb`
   - Upload: `spam.csv`
   - Saves: `uci_stats.json`
2. `02_uci_preprocessing.ipynb`
   - Upload: `spam.csv`
   - Saves: `X_train.npz`, `X_test.npz`,
             `y_train.npy`, `y_test.npy`
3. `03_uci_naive_bayes.ipynb` to `06_uci_random_forest.ipynb`
   - Upload: processed files from step 2
   - Saves: `nb_results.json`, `lr_results.json`,
             `svm_results.json`, `rf_results.json`
4. `07_uci_evaluation.ipynb`
   - Upload: all 4 JSON files from step 3

### Phase 2 — SpamAssassin (Preprocessing Finding)
5. `08_spamassassin_exploration.ipynb`
   - Upload: `spam_assassin.csv`
   - Saves: `sa_stats.json`
6. `09_spamassassin_preprocessing.ipynb`
   - Upload: `spam_assassin.csv`
   - Saves: `sa_X_train.npz`, `sa_X_test.npz`,
             `sa_y_train.npy`, `sa_y_test.npy`
7. `10_spamassassin_models.ipynb`
   - Upload: processed files from step 6
   - Saves: `sa_results.json`

> ⚠️ SpamAssassin results should be interpreted 
> with caution due to HTML preprocessing limitations.
> See report Section 3.7.1 for full discussion.

### Phase 3 — Advanced Analysis (UCI)
8. `11_cross_validation.ipynb`
   - Upload: `X_train.npz`, `X_test.npz`,
             `y_train.npy`, `y_test.npy`,
             `nb_results.json`, `lr_results.json`,
             `svm_results.json`, `rf_results.json`
   - Saves: `cv_results.json`
9. `12_hyperparameter_tuning.ipynb`
   - Upload: all 4 UCI processed files +
             all 4 UCI JSON result files
   - Saves: `tuning_results.json`
10. `13_feature_importance.ipynb`
    - Upload: all 4 UCI processed files +
              `spam.csv` + `tuning_results.json`
    - Saves: `feature_importance_results.json`

## Project Structure
- `notebooks/` - All Jupyter notebooks by phase
- `results/graphs/` - Performance comparison charts
- `results/confusion_matrices/` - Confusion matrices
- `results/metrics/` - Saved model metrics (JSON)
- `results/feature_importance/` - Feature importance charts

## Group Members
- Rasydan Irfan
- Arunasalem s/o Elankovan
- Sherry
