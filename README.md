# Oasis Infobyte internship — ML and data analysis notebooks

This repository preserves notebooks from an early data science internship and documents subsequent improvements.

## Notebooks

| File | Purpose | Status |
| --- | --- | --- |
| `IRIS_dataset_internship.ipynb` | Original Iris classification notebook | Historical; contains evaluation leakage |
| `iris_classification_reproducible.ipynb` | Rebuilt Iris KNN/SVC evaluation with stratified holdout and training-only cross-validation | Updated; results must be run locally |
| `Spam_detection_internship.ipynb` | SMS spam classification | Historical; vectorizer fitted before split |
| `Unemployement.ipynb` | Exploratory analysis of 2020 unemployment data | Historical; needs cleanup |

## Run the improved Iris notebook

1. Use Python 3.10+ and create a virtual environment.
2. Install dependencies: `pip install -r requirements.txt`.
3. Open `iris_classification_reproducible.ipynb` with Jupyter or VS Code and run all cells.

The improved notebook uses the **Iris dataset bundled with scikit-learn**, so no external CSV is required. It reports results only when executed. The original notebook loaded `/content/iris.csv`, which is not committed here; the improved notebook is **not** a reproduction of the original experiment or its scores.

## Evaluation protocol

The improved Iris workflow makes a stratified 80/20 train/test split with a fixed random seed, uses 5-fold cross-validation and preprocessing pipelines on the training set, and reports held-out accuracy, macro F1, and confusion matrices. No claims of deployment or production performance are made.

## Next improvements

- Correct leakage and evaluate spam-class precision/recall in the SMS notebook.
- Clean the unemployment notebook, document data provenance, and correct unsupported interpretations.
- Add repeatable automated tests and CI once shared helpers are extracted.
