## Causal Inference Analysis

To explore how different indicators were connected during the COVID-19 recovery, I started by creating a **correlation heatmap**. One of the strongest relationships I found was between **vaccination rates and unemployment** — provinces with higher percentages of fully vaccinated people tended to have lower unemployment. 

But since correlation doesn’t always mean causation, I used a causal inference tool called **DoWhy** to test if this relationship was actually causal.

### Research Question

**Does increasing the percentage of people fully vaccinated lead to lower unemployment?**

- **Treatment Variable:** `percent_fully_vaccinated`
- **Outcome Variable:** `Unemployment Rate (%)`
- **Controls:** `Total healthcare spending`, `Public Health`, `Administration`, and `COVID-19 Response Funding`

After building a causal graph and running a **backdoor-adjusted linear regression**, the model showed:

> 📉 A **1% increase** in full vaccination leads to a **0.043% decrease** in unemployment, on average.

---

### Refutation Tests

To make sure the result was trustworthy, I ran two refutation tests:

- **Random Common Cause Refuter**  
  ➤ After adding a fake random confounder, the new effect stayed nearly the same: **–0.0434**, with a **p-value of 0.98**.

- **Data Subset Refuter**  
  ➤ Even when using a random slice of the data, the effect still held: **–0.0436**, with a **p-value of 0.94**.

---

### Conclusion

These results suggest that the relationship between vaccination and unemployment is **causal and stable**, not just a coincidence or driven by random variation. Overall, the analysis supports the idea that **higher full vaccination rates helped reduce unemployment** during the pandemic.
