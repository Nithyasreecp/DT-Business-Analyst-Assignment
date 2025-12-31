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
