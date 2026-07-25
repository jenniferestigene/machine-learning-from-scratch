# Machine Learning From Scratch

Classical machine learning algorithms implemented from scratch in NumPy, applied to real biological data.

Built with my personal interest in exploring the intersection of machine learning and computational biology.

## Approach

Every notebook follows the same structure: implement the algorithm's core math directly in NumPy (no `sklearn.linear_model`, no `.fit()` shortcuts), train it on a real biological dataset, then validate the result against the equivalent scikit-learn implementation to confirm correctness.

All nine notebooks use the [Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic) dataset — real fine-needle aspirate measurements from 569 breast tumor biopsies, loaded directly via `sklearn.datasets.load_breast_cancer()`. Using one consistent real dataset across every algorithm makes the results directly comparable to each other, notebook to notebook.

## Results

| Algorithm | Task | Result | vs. scikit-learn |
|---|---|---|---|
| [Linear Regression](linear_regression.ipynb) | Predict tumor concavity from compactness | w=1.3331, b=-0.0503 | Exact match |
| [Logistic Regression](logistic_regression.ipynb) | Malignant/benign classification | 94.55% accuracy | Matches (94.55%) |
| [K-Nearest Neighbors](k_nearest_neighbors.ipynb) | Malignant/benign classification | 97.37% accuracy | Exact match |
| [Decision Tree](decision_tree.ipynb) | Malignant/benign classification | 91.23% accuracy | Close (89.47%) |
| [Naive Bayes](naive_bayes.ipynb) | Malignant/benign classification | 93.86% accuracy | Exact match |
| [Random Forest](random_forests.ipynb) | Malignant/benign classification | 94.74% accuracy | Exact match |
| [Support Vector Machine](support_vector_machine.ipynb) | Malignant/benign classification | 93.32% accuracy | Close (94.55%) |
| [Principal Component Analysis](principal_component_analysis.ipynb) | Dimensionality reduction | 63.24% variance retained (2 components) | Exact match |
| [K-Means](k_means.ipynb) | Unsupervised clustering | 91.04% agreement with real diagnosis | Exact match |

Where results are "close" rather than "exact," it's expected as those algorithms (decision trees, SVM) involve optimization or tie-breaking procedures that can legitimately converge to slightly different, comparably good solutions rather than one guaranteed answer.

## Running locally

```bash
git clone https://github.com/jenniferestigene/machine-learning-from-scratch.git
cd machine-learning-from-scratch
pip install -r requirements.txt
jupyter notebook
```

No external downloads needed — every notebook loads its dataset directly through scikit-learn.

## License

MIT — see [LICENSE](LICENSE).