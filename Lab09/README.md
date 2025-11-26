# Solution subpoint b

Posterior distribution $n$ is a compromise between our prior knowledge and the likelihood of the observed data.

### The Effect of $Y$ (Observed Buyers)
There is a strict logical constraint: **$n$ must be greater than or equal to $Y$**. You cannot have 10 buyers if only 5 people entered the store.
* **When $Y$ is small (e.g., 0):** The posterior remains close to the prior (around 10), though slightly shifted downwards because seeing 0 buyers suggests slightly lower traffic.
* **When $Y$ is large (e.g., 10):** The posterior is pushed strictly to the right. The probability of $n < 10$ becomes zero. The distribution centers on values significantly higher than the prior mean of 10.

### The Effect of $\theta$ (Conversion Probability)
$\theta$ acts as a scaling factor connecting total visitors to buyers ($Y \approx n \times \theta$).
* **High $\theta$ (0.5):** If 50% of people buy, and we observed $Y=10$, we likely had about $n=20$ visitors. The data is "trustworthy," so the posterior is tighter and closer to $Y$.
* **Low $\theta$ (0.2):** If only 20% of people buy, and we observed $Y=10$, we likely had a massive number of visitors (approx $n=50$). However, since our prior strongly suggests $n \approx 10$, the posterior becomes a "tug-of-war." It will be pulled upward by the data but held back by the prior, resulting in a **wider (more uncertain) posterior** distributed between the prior mean and the likelihood estimate ($Y/\theta$).


# Solution subpoint d

### 1. Posterior Distribution for $n$ ($P(n | Y, \theta)$)
* **What it represents:** The probability distribution of the **latent parameter** (the unobserved total number of customers on that specific day).
* **Uncertainty:** This reflects our "epistemic" uncertainty—we don't know the true value of $n$, so we assign probabilities to likely values based on the evidence.

### 2. Predictive Posterior for $Y^*$ ($P(Y^* | Y)$)
* **What it represents:** The probability distribution of **future observable data** (how many buyers we might see if we re-ran the day under the same conditions).
* **Difference:** The predictive posterior is **wider** (has higher variance) than the posterior for $n$.
* **Why?** It includes two sources of uncertainty:
    1.  **Parameter Uncertainty:** We aren't sure what $n$ is (from step 1).
    2.  **Sampling Uncertainty:** Even if we knew $n$ perfectly, the number of buyers is random (Binomial noise).
