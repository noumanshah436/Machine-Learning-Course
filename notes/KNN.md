Here is a clear explanation of the **KNN (k-Nearest Neighbors)** example and how the prediction is made step by step.

---

# 🎯 **Goal**

We have a dataset of 5 labeled points:

| Point | Coordinates | Label |
| ----- | ----------- | ----- |
| P1    | (1,2)       | A     |
| P2    | (2,2)       | A     |
| P3    | (3,3)       | B     |
| P4    | (3,4)       | B     |
| P5    | (0,0)       | A     |

We want to classify a **query point**:

$$
q = (2,3)
$$

Using **k = 3** nearest neighbors.

---

# 📌 **Step 1: Compute Euclidean distances**

Distance formula:

$$
d = \sqrt{(x_q - x)^2 + (y_q - y)^2}
$$

We compute the distance from q = (2,3) to each point:

---

### **1️⃣ Distance to point (1,2), label A**

$$
d = \sqrt{(2-1)^2 + (3-2)^2}
$$
$$
= \sqrt{1 + 1} = \sqrt{2} \approx 1.4142
$$

---

### **2️⃣ Distance to point (2,2), label A**

$$
d = \sqrt{(2-2)^2 + (3-2)^2}
$$
$$
= \sqrt{0 + 1} = 1.0
$$

---

### **3️⃣ Distance to point (3,3), label B**

$$
d = \sqrt{(2-3)^2 + (3-3)^2}
$$
$$
= \sqrt{1 + 0} = 1.0
$$

---

### **4️⃣ Distance to point (3,4), label B**

$$
d = \sqrt{(2-3)^2 + (3-4)^2}
$$
$$
= \sqrt{1 + 1} = 1.4142
$$

---

### **5️⃣ Distance to point (0,0), label A**

$$
d = \sqrt{(2-0)^2 + (3-0)^2}
$$
$$
= \sqrt{4 + 9} = \sqrt{13} \approx 3.6056
$$

---

# 📌 **Step 2: Sort distances by closeness**

| Point | Distance   | Label |
| ----- | ---------- | ----- |
| (2,2) | **1.0**    | A     |
| (3,3) | **1.0**    | B     |
| (1,2) | **1.4142** | A     |
| (3,4) | 1.4142     | B     |
| (0,0) | 3.6056     | A     |

The **3 nearest neighbors** (k=3) are:

1. **(2,2) — A**
2. **(3,3) — B**
3. **(1,2) — A**

---

# 📌 **Step 3: Majority vote among neighbors**

Labels among the top 3:

$$
$$A, B, A$$
$$

Count them:

* A = 2
* B = 1

**Majority label = A**

---

# 🎉 **Final Prediction**

$$
\boxed{\text{Predicted label for } q = A}
$$

---

# 🧠 **Why this result?**

* KNN simply looks at which class is more common among the closest points.
* The query point is closer to points labeled **A**.
* Even though there is one B point nearby, **A appears more frequently** among the 3 closest neighbors.

---

If you want, I can also show:

* the same example with different k values
* how KNN decision boundaries look
* Python code implementing this example.
