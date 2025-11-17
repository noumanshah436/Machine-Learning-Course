Here is a **simple, clear example** of how **entropy** is calculated in **Decision Trees (ID3 / C4.5)**.

---

# 🌳 **Decision Tree — Entropy Example**

Suppose you have the following dataset:

| Weather  | Play? |
| -------- | ----- |
| Sunny    | No    |
| Sunny    | No    |
| Overcast | Yes   |
| Rainy    | Yes   |
| Rainy    | Yes   |
| Rainy    | No    |

We want to calculate the **entropy of the target column ("Play?")**.

---

# Step 1: Count class frequencies

Target = **Play?**

```
Yes = 3
No  = 3
Total = 6
```

---

# Step 2: Entropy formula

$$
Entropy = - \sum p_i \log_2(p_i)
$$

Where ( p_i ) = class probability.

---

# Step 3: Compute probabilities

$$
p(Yes) = 3/6 = 0.5
$$
$$
p(No) = 3/6 = 0.5
$$

---

# Step 4: Apply entropy formula

$$
Entropy = -$$0.5 \log_2(0.5) + 0.5 \log_2(0.5)$$
$$

We know:

$$
\log_2(0.5) = -1
$$

So:

$$
Entropy = -$$0.5(-1) + 0.5(-1)$$
$$
$$
Entropy = -$$-0.5 - 0.5$$
$$
$$
Entropy = 1.0
$$

---

# ✅ **Entropy of the entire dataset = 1.0**

This means:

* Dataset is **perfectly impure**
* All classes are **equally mixed**
* Decision Tree must **split** to reduce uncertainty

---

# ⭐ Want a split example (e.g., entropy of "Weather" attribute)?

I can show you **entropy of Sunny / Overcast / Rainy** and also the **Information Gain** for the split.


Great — let’s compute **attribute entropies** and the **Information Gain** for splitting on **Weather**.

We use the same dataset:

| Weather  | Play? |
| -------- | ----- |
| Sunny    | No    |
| Sunny    | No    |
| Overcast | Yes   |
| Rainy    | Yes   |
| Rainy    | Yes   |
| Rainy    | No    |

We already computed:

### **Entropy(parent) = 1.0**

---

# 🌤️ Step 1: Split the data by **Weather**

## 1) **Sunny**

Rows:

| Sunny | No |
| ----- | -- |
| Sunny | No |
| Sunny | No |

Counts:

```
Yes = 0
No  = 2
```

Entropy:

$$
Entropy(Sunny) = -$$0 \log_2(0) + 1 \log_2(1)$$ = 0
$$

(Reason: all samples are “No” → perfectly pure)

---

## 2) **Overcast**

| Overcast | Yes |
| -------- | --- |

Counts:

```
Yes = 1
No  = 0
```

Entropy:

$$
Entropy(Overcast) = 0
$$

(Reason: perfectly pure)

---

## 3) **Rainy**

| Rainy | Yes |
| ----- | --- |
| Rainy | Yes |
| Rainy | No  |

Counts:

```
Yes = 2
No  = 1
Total = 3
```

Probabilities:

$$
p(Yes)=2/3,\quad p(No)=1/3
$$

Entropy:

$$
Entropy(Rainy) = -\left(\frac23 \log_2\frac23 + \frac13 \log_2\frac13\right)
$$

Compute:

$$
\frac23 \log_2\frac23 \approx 0.6667 \times (-0.585) = -0.39
$$
$$
\frac13 \log_2\frac13 \approx 0.3333 \times (-1.585) = -0.53
$$

$$
Entropy(Rainy) = -(-0.39 - 0.53) = 0.92
$$

---

# 🧮 Step 2: Compute Weighted Entropy After Split

Weights = proportion of rows.

```
Sunny:     2/6 = 0.33
Overcast:  1/6 = 0.17
Rainy:     3/6 = 0.50
```

Weighted entropy:

$$
Entropy_{after} = 0.33(0) + 0.17(0) + 0.50(0.92)
$$

$$
Entropy_{after} = 0.46
$$

---

# 🎯 Step 3: Information Gain

$$
IG(Weather) = Entropy(parent) - Entropy_{after}
$$

$$
IG = 1.0 - 0.46 = 0.54
$$

---

# ✅ Final Results

| Category             | Entropy  |
| -------------------- | -------- |
| Sunny                | 0        |
| Overcast             | 0        |
| Rainy                | 0.92     |
| **Weighted total**   | **0.46** |
| **Information Gain** | **0.54** |

---

# 🎉 Interpretation

* **Weather is a very good splitting attribute**, because:

  * It reduces entropy from **1.0 → 0.46**
  * Information Gain = **0.54** (high)
  * Sunny + Overcast become perfectly pure.

---

If you want, I can now show:

✅ Information Gain for other attributes (Temperature, Windy, etc.)
or
✅ Build the **entire decision tree** step-by-step.

Just tell me!
