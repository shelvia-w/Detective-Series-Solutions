# 🧠 k-Nearest Neighbors Quiz Answers

---

## ❓ Question 1:
**Suppose you had chosen k = 1 instead of k = 5, and the nearest person was Mira. Would relying on just one neighbor always be the best choice for finding Casey's community? Why might using k = 5 give a better recommendation?**

**✅ Answer:**

Using **k = 1** means the recommendation depends entirely on a single person - Mira, in this case. While Mira may be a good match, relying on just one person can be risky because it doesn't capture the broader social context. For instance, even though Mira shares interests like reading and jogging, she might mostly hang out with the Fitness Club, which is full of extroverted people who love parties and loud music - none of which match Casey’s preferences.

Using **k = 5** allows you to see a **pattern** across multiple similar people. If three (Mira, Theo, and Aria) out of five people that share interests with Casey are attending a Book Club, it's a stronger signal that Casey would fit in there.

---

## ❓ Question 2:
**Suppose the town has 1,000 people, but only 10 of them are bookworms like Casey, while the rest are mostly into coffee shop hopping and socializing. If you had chosen `k = 100`, would Casey still be matched with similar people? Why or why not?**

**✅ Answer:**

No, because the majority of the 100 neighbors would likely be people who are not similar to Casey. This means the "majority vote" might favor the dominant group (coffee shop lovers), not the bookworms.  
In cases of **imbalanced populations**, using a smaller k helps prevent Casey from being outvoted by unrelated groups.

---

## ❓ Question 3:
**One of the interest features—like jogging distance—is a number (in km), while the others—like liking books or cats—are yes/no values. How might this imbalance affect your KNN result? What could you do to make the model's "judgment" fairer?**

**✅ Answer:**

Jogging distance could **dominate** the distance calculation because it's a continuous numerical feature, while others are binary (no: 0 or yes: 1). This makes the model overly sensitive to jogging and less sensitive to shared interests like reading or liking cats. 
To fix this, you can **normalize** or **standardize** all features (ensures that it lies between 0 and 1) so that each one contributes fairly to the distance calculation, ensuring no single feature unfairly skews the results.

---
