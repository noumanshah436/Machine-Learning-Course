Here is the cleanest, simplest, exam-ready cheat sheet for your ML mid-term.
It covers all topics you listed, written as if you know nothing, and in a way that will help you solve paper questions tomorrow.

⸻

📘 MACHINE LEARNING MID-TERM CHEAT SHEET

⸻

🔹 1. Basics of ML

Machine Learning = Making computers learn patterns from data without being explicitly programmed.

Goal:
Use data → learn a model → make predictions.

⸻

🔹 2. Introduction

ML types:
	1.	Supervised Learning – has labels
	2.	Unsupervised Learning – no labels
	3.	Reinforcement Learning – learn by rewards

⸻

🔹 3. Supervised Learning

Data includes input X and output Y.

Examples:
	•	Predict house price
	•	Classify email as spam or not

Two types:
	•	Regression → continuous output (price, temperature)
	•	Classification → discrete output (0/1, spam/not spam)

⸻

🔹 4. Unsupervised Learning

Data has only input X, no labels Y.

Goal:
	•	Find structure/patterns

Examples:
	•	Clustering (K-means)
	•	Dimensionality reduction (PCA)

⸻

🔹 5. Reinforcement Learning

An agent learns by:
	•	Taking actions
	•	Receiving rewards/punishments
	•	Improving policy over time

Example: Chess AI, Self-driving.

⸻

🔹 6. Encoding for Categorical Data

Machines only understand numbers → convert categories to numbers.

Two common methods:

1. One-Hot Encoding

Red → [1,0,0]
Blue → [0,1,0]
Green → [0,0,1]

2. Label Encoding

Red → 0
Blue → 1
Green → 2

⸻

🔹 7. Models and Parameters

Model: A function that maps input → output
Parameters: Values learned during training (weights, bias)

Example linear model:
y = w x + b
Here w and b are parameters.

⸻

🔹 8. Loss Function

Loss = How wrong the model is on training data.

Examples:
	•	MSE (Mean Squared Error) → regression
	•	Cross-entropy loss → classification

⸻

🔹 9. Risk of a Model

Two types:
	1.	Empirical Risk (Training Loss)
Loss calculated only on training data.
	2.	True Risk (Generalization Error)
How model performs on unseen data.

Goal: low true risk.

⸻

🔹 10. Optimization

Process of finding the best parameters to minimize loss.

Most common: Gradient Descent

Steps:
	1.	Compute gradient
	2.	Update parameter:
\theta = \theta - \alpha \frac{dL}{d\theta}

⸻

🔹 11. Machine Learning Pipeline

Typical pipeline:
	1.	Collect data
	2.	Clean data
	3.	Encode features
	4.	Split train/test
	5.	Train model
	6.	Evaluate model
	7.	Deploy

⸻

🔹 12. Machine Learning for Prediction

We learn a function:
\hat{y} = f(x)
Goal: Predict output for new unseen input.

⸻

🔹 13. Linear Function

A linear function looks like:
f(x) = w x + b

Can draw a straight line on a graph.

⸻

🔹 14. Choice of Loss Function

Depends on problem:
	•	Regression → MSE
	•	Classification → Cross entropy
	•	Outliers present → MAE (L1 loss)

⸻

🔹 15. Linear Regression Algorithm

Goal: find best line through data.

Model:
\hat{y} = w x + b

Loss: MSE
L = \frac{1}{n} \sum (y - \hat{y})^2

Optimization: Gradient descent.

⸻

🔹 16. Alternative Loss Functions
	•	MAE (L1 Loss): robust to outliers
	•	Huber Loss: combination of MSE + MAE
	•	Log-cosh

⸻

🔹 17. Pearson Correlation

Measures linear relationship between two variables.

Range:
	•	+1 → perfect positive
	•	0 → no relation
	•	-1 → perfect negative

Formula:
r = \frac{cov(X,Y)}{\sigma_x \sigma_y}

⸻

🔹 18. Quadratic Feature Map

Transforms input into non-linear features.

Example:
Original feature: x
Quadratic map: [x, x^2]

Allows linear models to fit curved patterns.

⸻

🔹 19. Bias–Variance Tradeoff

Bias = error from wrong assumptions (model too simple)
Variance = model too sensitive to noise (overfitting)

Goal: find balance.
	•	High bias → Underfitting
	•	High variance → Overfitting

⸻

🔹 20. Training Data vs Test Data

Training data: used to learn model
Test data: used to evaluate performance (never used in training)

⸻

🔹 21. Regularization

Used to reduce overfitting.

Types:
	•	L1 Regularization (Lasso) → makes weights sparse
	•	L2 Regularization (Ridge) → reduces weight size

Loss becomes:

L_{\text{reg}} = L + \lambda ||w||

⸻

🔹 22. Cross Validation

Most common: k-fold cross validation

Steps:
	1.	Split data into k parts
	2.	Train on k-1 parts
	3.	Test on the left-out part
	4.	Repeat k times
	5.	Take average score

Purpose: better estimate of true performance.

⸻

🔹 23. Logistic Regression

Used for binary classification.

Model:
p = \frac{1}{1 + e^{-wx+b}}

Loss used: Log loss / Cross entropy

Output: probability (0 to 1)

⸻

🔹 24. Confusion Matrix

	Predicted +	Predicted -
Actual +	TP	FN
Actual -	FP	TN


⸻

🔹 25. Accuracy, Precision, Recall

Accuracy
\frac{TP+TN}{Total}

Precision (How many predicted positives are correct)
\frac{TP}{TP+FP}

Recall (How many actual positives detected)
\frac{TP}{TP+FN}

⸻

🔹 26. KNN Model (K-Nearest Neighbors)

Lazy learning model.

Steps:
	1.	Calculate distance to all points
	2.	Pick k nearest
	3.	Take majority vote (classification)
or average (regression)

Distance usually: Euclidean.

⸻

🔹 27. Decision Trees

Tree-like model that splits data based on questions.

Example:
Is temperature > 25?
→ Yes → Hot
→ No → Cold

Advantages:
	•	Easy to interpret
	•	Handles non-linear data

⸻

🔹 28. Impurity Function

Measures how “mixed” a node is.

Common impurity measures:

1. Entropy

H = -\sum p \log_2(p)

Range:
	•	0 → pure
	•	High → mixed

2. Gini Impurity

G = 1 - \sum p^2

⸻

🔹 29. Information Gain

Used in decision trees for choosing the best split.

Information\ Gain = Entropy(parent) - \text{Weighted Entropy(children)}

Higher IG = better split.

⸻

⭐ Your Exam Strategy

If short-questions come → write definitions.
If numerical → practice:
	•	Confusion matrix
	•	Accuracy/precision/recall
	•	Entropy + Information Gain calculation
	•	Pearson correlation
	•	Linear regression prediction