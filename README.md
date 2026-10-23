<div align="center">

# scikit-playground

**Linear vs quadratic discriminant analysis on synthetic Gaussian data, with decision boundaries and covariance ellipses (April 2021).**

[![Python](https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-LDA%20%C2%B7%20QDA-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![matplotlib](https://img.shields.io/badge/matplotlib-%3C3.8-11557C?style=flat-square)](#-requirements)

</div>

## 🔎 What it shows

`linear-quadratic-discriminant.py` draws one figure with four panels:

| | Linear Discriminant Analysis | Quadratic Discriminant Analysis |
|:---|:---:|:---:|
| **Same covariance** for both classes | panel 1 | panel 2 |
| **Different covariances** | panel 3 | panel 4 |

Each panel shows:

- 300 points per class (seed 0): correctly classified points as dots and misclassified ones as crosses.
- The class-1 probability as a red–blue background, with the 0.5 decision boundary in white.
- The class means as yellow stars, and each class's covariance as an ellipse spanning two standard deviations.

LDA uses a single shared covariance (`solver="svd"`), so its boundary is a straight line; QDA uses one covariance per class, so its boundary can curve.

## 🧰 Requirements

The script uses two matplotlib calls that no longer exist in current releases:

- `plt.cm.register_cmap` was removed in matplotlib 3.9.
- Passing the ellipse angle positionally to `Ellipse` stopped working in matplotlib 3.8.

Install a matplotlib older than 3.8 to run the file unchanged:

```bash
git clone https://github.com/mavasbel-legacy/scikit-playground.git
cd scikit-playground
python -m pip install numpy scipy scikit-learn "matplotlib<3.8"
python linear-quadratic-discriminant.py
```

The figure opens in a window; nothing is saved to disk.

## 📚 Source

The script is the scikit-learn 0.24.1 gallery example [*Linear and Quadratic Discriminant Analysis with covariance ellipsoid*](https://github.com/scikit-learn/scikit-learn/blob/0.24.1/examples/classification/plot_lda_qda.py), with its module docstring removed. scikit-learn is distributed under the [BSD 3-Clause license](https://github.com/scikit-learn/scikit-learn/blob/0.24.1/COPYING).

---

<div align="center">
<sub>Part of <a href="https://github.com/mavasbel-legacy">mavasbel-legacy</a> · <a href="https://github.com/mavasbel">Marco Vásquez Beltrán</a></sub>
</div>
