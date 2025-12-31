# Task 1: Clinic Inventory Statistical Audit

## Objective

Design daily, lightweight statistical checks that detect sales-entry errors and inventory mismatches early, without full reconciliation and without increasing doctor workload.


## 1. Where Inventory Errors Are Most Likely to Occur

Based on real clinic workflows, inventory errors typically occur at the following points:

### a. Sales Entry Errors
- Medicine dispensed but not entered due to patient rush
- Wrong unit entered (1 strip instead of 1 tablet)
- Confusion between similar medicine names or strengths

### b. Purchase Entry Errors
- Free quantities not entered
- Partial deliveries recorded as full deliveries
- Delayed bill entry causing temporary mismatches

### c. Stock Adjustments
- Expired or damaged stock removed physically but not updated in the system
- Emergency dispensing with an “entry later” approach

### d. Shift Changes
- Morning and evening staff assuming each other’s entries
- Closing stock assumed instead of physically verified

These errors are unintentional but recurring, making them ideal for pattern-based detection.


## 2. Daily Statistical / Randomized Micro-Audit Design

All checks are designed to run daily in under 15 minutes.

### a. High-Frequency SKU Check (Pareto-Based)
- Identify top 10 medicines by daily sales frequency
- Daily statistical check:


- Small variance is acceptable; repeated deviation is flagged

**Reason:**  
Most entry errors occur in fast-moving medicines, not rare items.

---

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

---

### d. Strip vs Tablet Ratio Monitoring

For medicines sold in both forms:
- Track daily tablet-to-strip sales ratio
- Sudden deviation from historical pattern indicates a probable entry error

 
 ## 3. How These Checks Improve Staff Compliance & SOP Discipline

- Small, daily checks reduce fear compared to monthly audits.
- Random sampling prevents selective compliance.
- Pattern-based flags encourage correction without blame.
- Doctor involvement is eliminated, preserving authority and focus.


