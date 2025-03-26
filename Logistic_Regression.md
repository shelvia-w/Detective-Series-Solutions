
# 🧠 Logistic Regression Quiz Answers

---

## ❓ Question 1:
**If a suspect has a very high “z” score from the linear combination, what happens to their probability after applying the sigmoid function? And why is that useful?**

**✅ Answer:**
When the linear score \( z \) is very high, the sigmoid function:

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

outputs a value close to **1**. This means the model is highly confident the input belongs to class **1**.  
Similarly, a very low \( z \) results in a probability close to **0**. This behavior is useful because it bounds probabilities between 0 and 1 and provides a smooth confidence curve.

---

## ❓ Question 2:
**Suppose the model gives a suspect a probability of 0.8, and you use 0.5 as your threshold. But your boss says we need to be more cautious and reduce false positives. What can you do?**

**✅ Answer:**
Two ways to reduce false positives (accusing innocent people):

1. **Increase the decision threshold** (e.g., from 0.5 to 0.7 or 0.8), so only higher-confidence predictions are classified as “guilty.”
2. **Add regularization** (like L2) to reduce the magnitude of weights, making the model less overconfident and helping it generalize better, especially when features are noisy or weak.

---

## ❓ Question 3:
**Why do we prefer log loss over mean squared error (MSE) in logistic regression? What would go wrong if we used MSE instead?**

**✅ Answer:**
We prefer **log loss** (binary cross-entropy):

\[
\text{LogLoss} = -\left[ y \cdot \log(p) + (1 - y) \cdot \log(1 - p) \right]
\]

Because:

- It heavily penalizes **confident wrong predictions** (e.g., predicting 0.01 when the true label is 1)
- It matches the probabilistic interpretation of logistic regression (based on likelihood maximization)
- It leads to **better gradients** and faster, more stable learning

If we used MSE:

\[
\text{MSE} = (y - p)^2
\]

- The gradients would be small near 0 or 1 → **slow learning**
- It doesn't penalize confident errors as strongly
- It assumes linear errors, which isn't aligned with how probabilities behave
