Law of Large Numbers – Simulation in Python
Introduction

The Law of Large Numbers (LLN) states that as the sample size increases, the sample mean converges to the true population mean.
In this project, I simulate coin tosses and show how probability estimates stabilize when sample size grows.

Concept

Layman’s View: The more data you collect, the closer your averages get to the “real truth.”

Technical Definition: For independent, identically distributed random variables with expected value μ,


⚙️ Methodology

Generate a large population of coin tosses (fair coin → p=0.5).

Draw random samples of different sizes (n=10, 50, 100, 500, 1000, 2000).

For each sample size, repeat multiple trials and record the probability of heads.

Compute:

Mean probability

Standard deviation (variability across trials)

Visualize how estimates converge with error bars.

💻 Code Snippet
sample_sizes = [10, 50, 100, 500, 1000, 2000]
means, stds = [], []

for n in sample_sizes:
    mean_est, std_est = estimate_prob(df, n, trials=100)
    means.append(mean_est)
    stds.append(std_est)

plt.errorbar(sample_sizes, means, yerr=stds, fmt='o-', capsize=5, label='Estimated Probability of Head')
plt.axhline(0.5, color='red', linestyle='--', label='True Probability (0.5)')
plt.xlabel('Sample Size')
plt.ylabel('Estimated Probability')
plt.title('Law of Large Numbers with Error Bars')
plt.legend()
plt.show()

Visualization

Figure: Probability Estimates with Error Bars

<img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/29d2305e-d694-4f66-ab02-9627c876a022" />

Small samples → wide variability (big error bars).

Large samples → stable around 0.5.

🔑 Key Takeaways

Statistical Insight: Larger sample sizes reduce variance, making estimates more reliable.

Business Impact: Small experiments (low users) → noisy & risky. Large experiments → stable and trustworthy results.

Practical Use: This principle underlies A/B testing, surveys, and model evaluation.

🛠️ Skills Demonstrated

Probability & Statistics (LLN, variance, convergence)

Simulation with Python (NumPy, Pandas)

Data Visualization (Matplotlib with error bars)

Communicating statistical intuition clearly

🚀 Next Steps

This project is part of my Probability & A/B Testing learning series.
Next: [Central Limit Theorem Simulation →](link to CLT project once uploaded)
