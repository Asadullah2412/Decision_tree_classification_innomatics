# Decision Tree Practice Machine Learning Project

## Project Overview

This project focuses on understanding **Decision Trees** as a core machine learning algorithm, with emphasis on how model behavior changes when key hyperparameters are tuned. The goal is not to maximize performance, but to build intuition around **tree growth, overfitting, and generalization**. The project explores different split criteria and manually tunes regularization parameters to observe their practical impact on model complexity and performance.

---

## What is a Decision Tree?

A Decision Tree is a supervised learning algorithm that makes predictions by recursively splitting the data into smaller subsets based on feature values. At each node, the model selects a feature and split that best separates the target classes using a mathematical criterion. The final prediction is made at the leaf nodes based on the majority class (classification) or average value (regression).

Decision Trees are easy to interpret and work well with mixed data types, but they are highly prone to overfitting if not properly constrained.

---

## Split Criteria Used

Two common split criteria were explored:

* **Gini Impurity**: Measures the probability of incorrect classification. It is computationally efficient and commonly used.
* **Entropy (Information Gain)**: Measures disorder in the data and selects splits that provide maximum information gain.

In practice, both criteria produced very similar tree structures and performance, indicating that split criterion choice has minimal impact compared to controlling tree complexity.

---

## Key Hyperparameter Tuned: `min_samples_leaf`

The primary parameter tuned in this project is `min_samples_leaf`, which defines the **minimum number of samples required in a leaf node**. This parameter directly controls overfitting by preventing the tree from creating extremely small and specific leaf nodes.

### Effect of tuning `min_samples_leaf`

* **Low values (e.g., 1)** allow deep trees that tend to overfit
* **Moderate values (5–10)** balance bias and variance effectively
* **High values (20+)** simplify the model too much and may lead to underfitting

Increasing `min_samples_leaf` results in shallower trees, fewer leaf nodes, and smoother decision boundaries.

---

## Model Evaluation

The model was evaluated on a held-out test set to measure generalization performance. By manually experimenting with different values of `min_samples_leaf`, changes in accuracy and tree complexity were observed. The best performance was achieved when the tree was constrained enough to avoid memorization while still capturing meaningful patterns.

---

## Key Learnings

* Decision Trees can easily overfit if unconstrained
* Regularization parameters matter more than split criteria
* `min_samples_leaf` is an effective way to control model complexity
* Simpler trees often generalize better than very deep ones

---

## Conclusion

This practice project demonstrates that the real strength of Decision Trees lies in **how their growth is controlled**. While Gini and Entropy resulted in comparable performance, tuning `min_samples_leaf` had a significant impact on reducing overfitting and improving generalization. Understanding and tuning such parameters is essential before moving on to more complex ensemble models like Random Forests and Gradient Boosting.

---

> **Note:** This project is intended for learning and experimentation purposes, focusing on building intuition rather than optimizing production-level performance.
