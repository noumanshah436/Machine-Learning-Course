Perfect 👍
Let’s now do **Hierarchical Clustering using COMPLETE LINKAGE** on the **same data points**, step by step, very clearly.

---

## Same Data Points (2-D)

| Point | (x, y) |
| ----- | ------ |
| A     | (1, 1) |
| B     | (2, 1) |
| C     | (4, 3) |
| D     | (8, 8) |
| E     | (9, 8) |

---

## What is Complete Linkage? (Key Rule ⭐)

> **Distance between two clusters = maximum distance between any pair of points across the clusters**

Mathematically:
$$
d(C_i, C_j) = \max_{x \in C_i,; y \in C_j} d(x,y)
$$

This favors **compact, tight clusters**.

---

## Step 1: Pairwise Distance Matrix

Using Euclidean distance:

| Pair | Distance         |
| ---- | ---------------- |
| A–B  | √1 = **1**       |
| A–C  | √13 ≈ **3.61**   |
| A–D  | √98 ≈ **9.90**   |
| A–E  | √113 ≈ **10.63** |
| B–C  | √8 ≈ **2.83**    |
| B–D  | √85 ≈ **9.22**   |
| B–E  | √100 = **10**    |
| C–D  | √41 ≈ **6.40**   |
| C–E  | √50 ≈ **7.07**   |
| D–E  | √1 = **1**       |

---

## Step 2: Start with Individual Clusters

Initial clusters:
[
{A}, {B}, {C}, {D}, {E}
]

---

## Step 3: First Merge (Smallest Distance)

Smallest distance = **1**

* Merge **A & B**
* Merge **D & E**

New clusters:

* **C₁ = {A, B}**
* **C₂ = {C}**
* **C₃ = {D, E}**

---

## Step 4: Update Distances (Complete Linkage)

Now compute **maximum distance** between clusters.

---

### Distance: `{A,B}` – `{C}`

Distances:

* A–C = 3.61
* B–C = 2.83

Complete linkage:
[
\max(3.61,;2.83) = \boxed{3.61}
]

---

### Distance: `{A,B}` – `{D,E}`

Distances:

* A–D = 9.90
* A–E = 10.63
* B–D = 9.22
* B–E = 10

Complete linkage:
[
\max(9.90,;10.63,;9.22,;10) = \boxed{10.63}
]

---

### Distance: `{C}` – `{D,E}`

Distances:

* C–D = 6.40
* C–E = 7.07

Complete linkage:
[
\max(6.40,;7.07) = \boxed{7.07}
]

---

## Step 5: Second Merge

Smallest updated distance = **3.61**

* Merge **{A,B} & {C}**

Clusters now:

* **C₁ = {A, B, C}**
* **C₂ = {D, E}**

---

## Step 6: Final Merge (Optional)

Compute distance between final clusters using **complete linkage**.

Distances:

* A–D = 9.90
* A–E = 10.63
* B–D = 9.22
* B–E = 10
* C–D = 6.40
* C–E = 7.07

Complete linkage:
[
\max = \boxed{10.63}
]

* Merge at distance **10.63**

---

## Dendrogram (Conceptual)

```
           ┌──── A
       ┌───┤
       │   └──── B
   ┌───┤
   │   └──────── C
───┤
   │       ┌──── D
   └───────┤
           └──── E
```

(Cut height differs from single linkage)

---

## Cutting the Dendrogram (Important ⭐)

If we cut at distance **< 7**:

* **Cluster 1** → {A, B, C}
* **Cluster 2** → {D, E}

Same final clusters as single linkage here, **but merge heights are different**.

---

## Why Complete Linkage is Better Than Single (Intuition)

| Single Linkage    | Complete Linkage  |
| ----------------- | ----------------- |
| Uses min distance | Uses max distance |
| Causes chaining   | Avoids chaining   |
| Loose clusters    | Compact clusters  |

---

## One-Line Exam Answer ⭐

> In complete linkage hierarchical clustering, clusters are merged based on the maximum pairwise distance between their points, producing compact clusters and avoiding chaining.

---

If you want next:

* **Average linkage on same data**
* **Side-by-side table (single vs complete vs average)**
* **Ward’s method with variance explanation**
* **When hierarchical beats K-Means (theory + example)**
