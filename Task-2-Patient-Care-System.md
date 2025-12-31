## 2. Daily Statistical / Randomized Micro-Audit Design

All checks are designed to run daily in under 15 minutes.

### a. High-Frequency SKU Check (Pareto-Based)
- Identify top 10 medicines by daily sales frequency
- Daily statistical check:


- Small variance is acceptable; repeated deviation is flagged

**Reason:**  
Most entry errors occur in fast-moving medicines, not rare items.



### b. Random SKU Sampling
- Each day, randomly select 3–5 medicines
- Physically count and compare with system stock
- Track deviation trend, not one-time mismatch

**Reason:**  
Randomization prevents selective compliance and builds discipline.



### c. Anomaly & Trigger-Based Flags

Automatically flag when:
- Stock becomes negative
- Same medicine is manually adjusted multiple times per week
- Sales quantity suddenly spikes compared to recent average

These are signals of workflow issues, not reconciliation failures.



### d. Strip vs Tablet Ratio Monitoring

For medicines sold in both forms:
- Track daily tablet-to-strip sales ratio
- Sudden deviation from historical pattern indicates a probable entry error
