Great 👍
Let’s do a **complete 2-D numerical example of K-Means**, step by step, with **actual calculations**.

---

## Problem Setup (2-D Data)

We have **6 points in 2-D space**:

| Point | (x, y) |
| ----- | ------ |
| A     | (1, 1) |
| B     | (1, 2) |
| C     | (2, 1) |
| D     | (8, 8) |
| E     | (9, 8) |
| F     | (8, 9) |

We want **K = 2 clusters**.

---

## Step 1: Initialize Centroids

Choose two initial centroids randomly:

* **Centroid C₁ = (1, 1)**
* **Centroid C₂ = (8, 8)**

---

## Step 2: Assign Points to Nearest Centroid

We use **Euclidean distance**:

$$
d((x,y),(a,b)) = \sqrt{(x-a)^2 + (y-b)^2}
$$

---

### Distance Calculations

#### Point A (1,1)

* To C₁:
  $$
  \sqrt{(1-1)^2 + (1-1)^2} = 0
  $$
* To C₂:
  $$
  \sqrt{(1-8)^2 + (1-8)^2} = \sqrt{98} \approx 9.9
  $$
  ✅ Assign to **C₁**

---

#### Point B (1,2)

* To C₁:
  $$
  \sqrt{(1-1)^2 + (2-1)^2} = 1
  $$
* To C₂:
  $$
  \sqrt{(1-8)^2 + (2-8)^2} = \sqrt{85} \approx 9.2
  $$
  ✅ Assign to **C₁**

---

#### Point C (2,1)

* To C₁:
  $$
  \sqrt{(2-1)^2 + (1-1)^2} = 1
  $$
* To C₂:
  $$
  \sqrt{(2-8)^2 + (1-8)^2} = \sqrt{85} \approx 9.2
  $$
  ✅ Assign to **C₁**

---

#### Point D (8,8)

* To C₁:
  $$
  \sqrt{(8-1)^2 + (8-1)^2} = \sqrt{98} \approx 9.9
  $$
* To C₂:
  $$
  \sqrt{(8-8)^2 + (8-8)^2} = 0
  $$
  ✅ Assign to **C₂**

---

#### Point E (9,8)

* To C₁:
  $$
  \sqrt{(9-1)^2 + (8-1)^2} = \sqrt{113} \approx 10.6
  $$
* To C₂:
  $$
  \sqrt{(9-8)^2 + (8-8)^2} = 1
  $$
  ✅ Assign to **C₂**

---

#### Point F (8,9)

* To C₁:
  $$
  \sqrt{(8-1)^2 + (9-1)^2} = \sqrt{113} \approx 10.6
  $$
* To C₂:
  $$
  \sqrt{(8-8)^2 + (9-8)^2} = 1
  $$
  ✅ Assign to **C₂**

---

### Clusters After Assignment

* **Cluster 1**: A(1,1), B(1,2), C(2,1)
* **Cluster 2**: D(8,8), E(9,8), F(8,9)

---

## Step 3: Update Centroids (Mean of Points)

### New Centroid C₁

$$
x = \frac{1 + 1 + 2}{3} = \frac{4}{3} \approx 1.33
$$
$$
y = \frac{1 + 2 + 1}{3} = \frac{4}{3} \approx 1.33
$$

$$
\boxed{C₁ = (1.33,;1.33)}
$$

---

### New Centroid C₂

$$
x = \frac{8 + 9 + 8}{3} = \frac{25}{3} \approx 8.33
$$
$$
y = \frac{8 + 8 + 9}{3} = \frac{25}{3} \approx 8.33
$$

$$
\boxed{C₂ = (8.33,;8.33)}
$$

---

## Step 4: Re-assignment Check

If we recompute distances using new centroids:

* Points A, B, C are still closer to **C₁**
* Points D, E, F are still closer to **C₂**

👉 **No change in cluster assignment**

---

## Step 5: Convergence

Since clusters didn’t change, **K-Means converges**.

---

## ✅ Final Result

### Final Clusters

* **Cluster 1** → (1,1), (1,2), (2,1)
* **Cluster 2** → (8,8), (9,8), (8,9)

### Final Centroids

* **C₁ ≈ (1.33, 1.33)**
* **C₂ ≈ (8.33, 8.33)**

---

## Exam Tip (Very Important ⭐)

* Assignment step → **distance minimization**
* Update step → **mean of cluster**
* Objective function minimized:
  $$
  \sum_{i=1}^{k} \sum_{x \in C_i} ||x - \mu_i||^2
  $$

---

If you want next:

* **Same example with WCSS calculation**
* **Graphical intuition**
* **Why K-Means fails on non-spherical data**
* **Comparison with hierarchical clustering**

Just tell me 👍
