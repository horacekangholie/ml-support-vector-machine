# 📘 Support Vector Machine (SVM)

## 📌 Introduction

**Support Vector Machine (SVM)** is a powerful **supervised learning algorithm** used for both **classification and regression** tasks. It works by finding the optimal hyperplane that maximally separates data points of different classes in a **high-dimensional space**.

For non-linearly separable data, SVM uses the **kernel trick** to transform data into a higher-dimensional space where a linear separator may exist.

## ⚙️ What the Model Does

SVM aims to:

- Maximize the **margin** between the nearest points (support vectors) of different classes.
- Use different **kernel functions** to handle linear and nonlinear classification.

Key idea:

$f(x) = \text{sign}(w \cdot x + b)$


In nonlinear cases:

$f(x) = \text{sign}(\sum \alpha_i y_i K(x_i, x) + b)$


## 🚧 Limitations

| Limitation                             | Description |
|----------------------------------------|-------------|
| Computationally Intensive               | Slow for large datasets. |
| Requires Careful Kernel Selection       | Incorrect kernel choice can lead to poor performance. |
| Poor Performance with Overlapping Classes | Not ideal when classes are not well-separated. |
| Difficult to Interpret                 | Especially with nonlinear kernels. |

---

## 🔧 Common Parameters, Attributes, and Methods

### Parameters (in `sklearn.svm.SVC`)

| Parameter         | Description |
|------------------|-------------|
| `C`               | Regularization parameter. Smaller values create a wider margin but allow more misclassifications. |
| `kernel`          | Type of kernel function: `'linear'`, `'poly'`, `'rbf'`, `'sigmoid'`. |
| `degree`          | Degree of polynomial kernel (if `kernel='poly'`). |
| `gamma`           | Kernel coefficient for `'rbf'`, `'poly'`, and `'sigmoid'`. |
| `probability`     | Whether to enable probability estimates via cross-validation. |

### Attributes (after fitting)

| Attribute          | Description |
|-------------------|-------------|
| `support_vectors_` | Support vectors found during training. |
| `dual_coef_`       | Coefficients of the support vector in the decision function. |
| `intercept_`       | Constant in the decision function. |
| `n_support_`       | Number of support vectors per class. |

### Methods

| Method             | Description |
|-------------------|-------------|
| `fit(X, y)`        | Train the model. |
| `predict(X)`       | Predict class labels. |
| `decision_function(X)` | Distance of samples to the separating hyperplane. |
| `score(X, y)`      | Return accuracy score. |

---

## 📏 Evaluation Metrics

Same metrics as for other classifiers:

| Metric     | Description |
|------------|-------------|
| **Accuracy**   | Fraction of correct predictions. |
| **Precision**  | Proportion of predicted positives that are correct. |
| **Recall**     | Proportion of actual positives correctly predicted. |
| **F1 Score**   | Harmonic mean of precision and recall. |
| **ROC-AUC**    | Measures model’s ability to distinguish between classes (especially useful for binary classification). |

---

## 💡 Example Use Case

- Handwritten Number Prediction
- Salary Prediction

[Demo code](/notebooks/svm.ipynb)
