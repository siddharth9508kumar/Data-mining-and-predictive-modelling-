# Data Mining and Predictive Modelling

Lab notebooks and assignments for the **Data Mining and Predictive Modelling (DMPM)** course. The repository walks through the core data-mining workflow in Python: descriptive statistics, data visualization, preprocessing, statistical testing, association rule mining, classification, and clustering.

Each notebook is self-contained and focuses on one topic, usually with a small worked example and printed results.

## Contents

| Notebook | Topic | What it covers |
|---|---|---|
| `DMPM_Lab02_Assignment01_2026-07-11.ipynb` | Descriptive statistics | Mean, median, mode, standard deviation and variance, computed both with NumPy/SciPy and by hand without library functions |
| `DMPM_Exp03_2026-08-08.ipynb` | Data visualization | Matplotlib (line, scatter, bar, pie, histogram, box plot) and Seaborn (displot, boxplot, histplot, barplot, scatterplot, heatmap, pairplot) |
| `DMPM_Lab04_2026-09-04.ipynb` | Normalization and correlation analysis | Min-max, z-score and decimal-scaling normalization; chi-square test of independence with a hypothesis-test conclusion |
| `dmpm exp 6,7,8.ipynb` | Classification and clustering | **Exp 6:** Decision Tree · **Exp 7:** KNN classifier · **Exp 8:** K-Means and K-Medoids clustering |
| `dmpm-lab (11_09_26).ipynb` | Frequent pattern mining | Apriori and FP-Growth with association rule generation |

## Topics in detail

### Descriptive statistics
Central tendency and spread on a small numeric list, implemented twice: with `numpy` / `scipy.stats`, and manually with plain Python, so the two approaches can be compared.

### Data visualization
A tour of the standard plot types in Matplotlib and Seaborn, with a short note on when each one is useful.

### Normalization and chi-square test
Three rescaling methods applied to `[10, 20, 30, 40, 50]`:

- Min-max normalization (rescales to the range 0 to 1)
- Z-score normalization
- Decimal scaling

The same notebook runs a chi-square test on an hours-studied versus marks table and interprets the p-value against a 0.05 significance level.

### Decision Tree (Exp 6)
A `DecisionTreeClassifier` (Gini criterion, `max_depth=4`) that predicts iris species from a large, synthetic iris-style dataset. Identifier and non-numeric columns are dropped, the target is label-encoded, and data is split 80/20. The notebook reports accuracy and a classification report and plots the fitted tree.

### KNN classifier (Exp 7)
A K-Nearest Neighbors model (k = 3) on a breast cancer diagnosis dataset (benign vs. malignant) with standardized features. On the 114-sample test set it reaches **95.61% accuracy**, with precision/recall of 0.97/0.96 for benign and 0.93/0.95 for malignant.

### K-Means and K-Medoids (Exp 8)
Both algorithms are run on the scaled iris-style data with K = 3. The notebook uses the elbow method (WCSS for K = 1 to 10) to choose K, compares the two methods with the silhouette score, and visualizes the clusters in 2D using PCA.

### Apriori and FP-Growth
Both algorithms run on a five-transaction market-basket dataset (Bread, Milk, Diaper, Beer, Eggs, Cola) with `min_support = 0.6` and `min_confidence = 0.7`. They find the same frequent itemsets and rules. The strongest rule is `Beer → Diaper` (confidence 1.00, lift 1.25).

## Tech stack

- Python 3
- NumPy, pandas, SciPy
- Matplotlib, Seaborn
- scikit-learn, scikit-learn-extra (for K-Medoids)
- mlxtend (for Apriori, FP-Growth and association rules)
- Jupyter / Google Colab

## Getting started

1. Clone the repository:

   ```bash
   git clone https://github.com/siddharth9508kumar/Data-mining-and-predictive-modelling-.git
   cd Data-mining-and-predictive-modelling-
   ```

2. Install the dependencies:

   ```bash
   pip install numpy pandas scipy matplotlib seaborn scikit-learn scikit-learn-extra mlxtend jupyter
   ```

3. Launch Jupyter and open any notebook:

   ```bash
   jupyter notebook
   ```

   The notebooks also run on [Google Colab](https://colab.research.google.com/) without any local setup.

## Datasets

Most notebooks use small inline datasets and run as-is. Two notebooks load CSV files that are **not included in this repository**:

| File | Used in | Purpose |
|---|---|---|
| `iris_large_dataset.csv` | Exp 6 (Decision Tree), Exp 8 (Clustering) | Iris-style dataset with a `Species` target |
| `KNNAlgorithmDataset-selected-columns.csv` | Exp 7 (KNN) | Breast cancer features with a `diagnosis` target (`M` / `B`) |

The notebooks read these from `/content/` (the Google Colab working directory). To run them, upload the files to Colab, or change the `pd.read_csv(...)` paths to point to your local copies.

## Repository structure

```
.
├── DMPM_Lab02_Assignment01_2026-07-11.ipynb
├── DMPM_Exp03_2026-08-08.ipynb
├── DMPM_Lab04_2026-09-04.ipynb
├── dmpm exp 6,7,8.ipynb
├── dmpm-lab (11_09_26).ipynb
└── README.md
```

## Author

**Siddharth Kumar** — [@siddharth9508kumar](https://github.com/siddharth9508kumar)
