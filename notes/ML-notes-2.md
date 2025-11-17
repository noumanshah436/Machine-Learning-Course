Good — here are 7 compact, fully worked numerical examples for the topics that commonly require calculations in an ML exam. I show each problem, then solve it step-by-step so you can copy the method in the exam.

⸻

1) Linear Regression (closed form)

Problem: Given points (1,2), (2,2), (3,4). Fit a line \hat y = w x + b using least squares (closed form).

Solution (step-by-step):
	1.	n=3. Compute means:
	•	\bar x = (1+2+3)/3 = 6/3 = 2.0.
	•	\bar y = (2+2+4)/3 = 8/3 = 2.6666666667 (keep 2.6667).
	2.	Compute numerator and denominator for slope w:
	•	Numerator =\sum (x_i-\bar x)(y_i-\bar y).
	•	For (1,2): (1-2)*(2-2.6667) = (-1)*(-0.6667) = 0.6667.
	•	For (2,2): (2-2)*(2-2.6667) = 0*(-0.6667)=0.
	•	For (3,4): (3-2)*(4-2.6667)=1*(1.3333)=1.3333.
	•	Sum = 0.6667 + 0 + 1.3333 = 2.0000.
	•	Denominator =\sum (x_i-\bar x)^2.
	•	For x=1: (1-2)^2 = 1.
	•	For x=2: (2-2)^2 = 0.
	•	For x=3: (3-2)^2 = 1.
	•	Sum = 1 + 0 + 1 = 2.
	•	So w = 2.0000 / 2 = 1.0.
	3.	Intercept b = \bar y - w \bar x = 2.6666667 - 1.0 * 2.0 = 0.6666667.

Answer: \hat y = 1.0 \,x + 0.6667.

⸻

2) Pearson Correlation (r)

Problem: Compute Pearson correlation r for the same points x=[1,2,3], y=[2,2,4].

Solution (step-by-step formula):
r=\dfrac{\sum (x_i-\bar x)(y_i-\bar y)}{\sqrt{\sum (x_i-\bar x)^2}\sqrt{\sum (y_i-\bar y)^2}}

We already computed numerator = 2.0000 and \sum(x_i-\bar x)^2 = 2.

Compute \sum (y_i-\bar y)^2:
	•	For y=2: (2-2.6667)^2 = (-0.6667)^2 = 0.444444.
	•	For y=2: same = 0.444444.
	•	For y=4: (4-2.6667)^2 = 1.3333^2 = 1.777777.
Sum = 0.444444 + 0.444444 + 1.777777 = 2.666665 (≈ 2.6667).

Denominator = \sqrt{2} * \sqrt{2.6667} = 1.41421356 * 1.633 = 2.3094 (approx).

So r = 2.0000 / 2.3094 = 0.8660 (approx).

Answer: r \approx 0.8660 (strong positive linear correlation).

⸻

3) Entropy and Information Gain (decision tree split)

Problem: Parent node has 6 examples: 4 positive (P) and 2 negative (N). A candidate split produces:
	•	Left child: 3 examples (3 P, 0 N).
	•	Right child: 3 examples (1 P, 2 N).
Compute parent entropy, children entropies, and information gain.

Solution (step-by-step):
Entropy formula for binary: H = -p\log_2 p - q\log_2 q where p = fraction positive.
	1.	Parent: p=4/6 = 0.6666667,\; q=2/6 = 0.3333333.
	•	H_{parent} = -(2/3)\log_2(2/3) - (1/3)\log_2(1/3).
	•	Numerically: (2/3)\log_2(2/3) ≈ 0.6667 * (-0.5850) = -0.3900 (note sign), and (1/3)\log_2(1/3) ≈ 0.3333 * (-1.5850) = -0.528333.
	•	So H_{parent} ≈ 0.9183 bits.
	2.	Left child (3P,0N): p=1,\; q=0 → H_{left} = 0 (pure).
	3.	Right child (1P,2N): p=1/3=0.3333,\; q=2/3=0.6667.
	•	H_{right} = same as parent if reversed = 0.9183 bits.
	4.	Weighted child entropy = (3/6)*H_{left} + (3/6)*H_{right} = 0.5*0 + 0.5*0.9183 = 0.45915.
	5.	Information Gain = H_{parent} - weighted = 0.9183 - 0.45915 = 0.45915 bits.

Answer: Parent entropy ≈ 0.9183 bits, Info Gain ≈ 0.4591 bits.

⸻

4) Confusion Matrix → Accuracy, Precision, Recall, F1

Problem: For a classifier: TP=40, FP=10, FN=5, TN=45. Compute Accuracy, Precision, Recall, F1.

Solution (step-by-step):
	•	Total = TP+FP+FN+TN = 40+10+5+45 = 100.

	1.	Accuracy = (TP+TN)/Total = (40+45)/100 = 85/100 = 0.85 (85%).
	2.	Precision = TP/(TP+FP) = 40/(40+10) = 40/50 = 0.8 (80%).
	3.	Recall = TP/(TP+FN) = 40/(40+5) = 40/45 ≈ 0.8889 (88.89%).
	4.	F1 = 2 * (precision*recall)/(precision+recall):
	•	precision*recall = 0.8 * 0.8888889 = 0.7111111
	•	sum = 0.8 + 0.8888889 = 1.6888889
	•	F1 = 2*0.7111111 / 1.6888889 = 1.4222222 / 1.6888889 ≈ 0.8421.

Answer: Accuracy 0.85, Precision 0.8, Recall 0.8889, F1 ≈ 0.8421.

⸻

5) KNN (distance & prediction)

Problem: Dataset points:
	•	(1,2) label A
	•	(2,2) label A
	•	(3,3) label B
	•	(3,4) label B
	•	(0,0) label A
Query point q=(2,3). Predict label for k=3 using Euclidean distance.

Solution (step-by-step distances):
Distance formula d=\sqrt{(x_q-x)^2+(y_q-y)^2}.
	1.	To (1,2): d=\sqrt{(2-1)^2+(3-2)^2}=\sqrt{1+1}=\sqrt{2}=1.4142.
	2.	To (2,2): d=\sqrt{(2-2)^2+(3-2)^2}=\sqrt{0+1}=1.0.
	3.	To (3,3): d=\sqrt{(2-3)^2+(3-3)^2}=\sqrt{1+0}=1.0.
	4.	To (3,4): d=\sqrt{(2-3)^2+(3-4)^2}=\sqrt{1+1}=\sqrt{2}=1.4142.
	5.	To (0,0): d=\sqrt{4+9}=\sqrt{13}=3.6056.

Sort distances: 1.0 → (2,2) A; 1.0 → (3,3) B; 1.4142 → (1,2) A; …
Top k=3 neighbors: labels = [A, B, A] → A appears 2 times, B appears 1 time.

Answer: Predicted label = A (majority among 3 nearest).

⸻

6) Logistic Regression — probability & loss

Problem: Logistic model with weights w=[1,\,-0.5], bias b=0.2. For input x=[2,1], and true label y=1: compute z, probability p=\sigma(z), and cross-entropy loss -[y\log p + (1-y)\log(1-p)].

Solution (step-by-step):
	1.	Linear score z = w_1 x_1 + w_2 x_2 + b = 1*2 + (-0.5)*1 + 0.2 = 2 - 0.5 + 0.2 = 1.7.
	2.	Sigmoid: p = 1/(1+e^{-z}) = 1/(1 + e^{-1.7}).
	•	e^{-1.7} ≈ 0.182683.
	•	So p ≈ 1/(1+0.182683) = 1/1.182683 ≈ 0.8455347.
	3.	Cross-entropy loss for y=1: -\log(p) = -\log(0.8455347) ≈ 0.1677860.

Answer: z=1.7,\; p\approx 0.8455, loss ≈ 0.1678.

⸻

7) Regularized (Ridge) loss — quick calc

Problem: Using the linear model from example (w=1.0, b≈0.6667) on dataset (1,2),(2,2),(3,4), compute MSE and then ridge objective \text{MSE} + \lambda w^2 with \lambda=1.

Solution (step-by-step):
	1.	Predictions:
	•	x=1 → \hat y = 1*1 + 0.6667 = 1.6667.
	•	x=2 → \hat y = 2.6667.
	•	x=3 → \hat y = 3.6667.
	2.	Squared errors:
	•	(2 - 1.6667)^2 = (0.3333)^2 = 0.111111.
	•	(2 - 2.6667)^2 = (-0.6667)^2 = 0.444444.
	•	(4 - 3.6667)^2 = (0.3333)^2 = 0.111111.
	•	Sum = 0.111111 + 0.444444 + 0.111111 = 0.666666.
	3.	MSE = sum / n = 0.666666 / 3 = 0.222222.
	4.	Ridge objective = MSE + λ·w^2 = 0.222222 + 1*(1.0^2) = 1.222222.

Answer: MSE ≈ 0.2222, ridge objective (λ=1) ≈ 1.2222.

⸻

How to use these in the exam
	•	If asked for a regression fit: follow example 1 (means → numerator/denominator → slope → intercept).
	•	If asked for correlation: compute numerator and both variances, then divide.
	•	If asked for information gain: always compute parent entropy, child entropies, weight by child sizes.
	•	For confusion-matrix-style questions: extract TP/FP/FN/TN then compute the metrics in the same order I used.
	•	For KNN: always compute Euclidean distances, sort, pick top k, majority vote.
	•	For logistic: compute z, then sigmoid, then loss if requested.

⸻

If you want, I can now:
	•	Generate 3 quick practice questions like the above (you try, I give answers), or
	•	Make a one-page printable sheet with these formulas + the solved examples.

Which would you prefer?