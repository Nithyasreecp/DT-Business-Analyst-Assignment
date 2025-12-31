# Task 2: Patient Care & Communication System Design

## Objective

Design a simple, scalable patient care and follow-up communication system that automates routine interactions, reduces WhatsApp chaos, and minimizes doctor cognitive load while preserving care quality.

---

## 1. Patient Message Classification Framework

Patient messages are classified based on decision complexity and risk.

### a. Fully Automated Messages
Examples:
- Appointment reminders
- Lab report availability notifications
- Post-visit care instructions
- Medicine refill reminders

These messages are consistent across patients and do not require clinical judgement.

---

### b. Human-in-the-Loop (Staff Managed)
Examples:
- Clarification on dosage timing
- Routine symptom updates
- Follow-up scheduling questions

Staff respond using predefined templates and escalate only when necessary.

---

### c. Doctor Escalation Only
Examples:
- New or worsening symptoms
- Adverse drug reactions
- Emergency indicators

Only summarized, decision-ready cases reach the doctor.

## 2. Google Sheets–Based Control System

### Sheet 1: Patient Communication Log
Tracks all interactions and ownership.

| Patient ID | Visit Date | Message Type | Category | Status | Owner | Escalated |
|-----------|------------|--------------|----------|--------|-------|-----------|

---

### Sheet 2: Automation Rules
Defines which messages are triggered automatically.

| Trigger Event | Message Template | Timing | Channel |
|--------------|------------------|--------|---------|
| Visit End | Care Instructions | Immediate | WhatsApp |
| Lab Ready | Report Notification | Auto | WhatsApp |
| Post-Visit | Follow-up Check | +3 Days | WhatsApp |

---

### Sheet 3: Doctor Escalation View
Filtered view showing:
- Patient summary
- Staff notes
- Exact decision required

Doctor interaction time per case is minimized.


## 3. Doctor Cognitive Load Minimization

- Doctor is removed from routine messaging
- Only exceptions reach the doctor
- No message scrolling or context reconstruction
- Decisions are made from structured summaries

This preserves doctor focus and authority.


## 4. Optional Automation Layer

If required, Google Apps Script can monitor Sheet updates and:
- Trigger WhatsApp/SMS APIs
- Update message status automatically
- Generate daily summary reports for doctors


# Task 1: Daily Clinic Inventory Micro-Audit

## Objective
Design a daily micro-audit routine that detects sales-entry errors early, improves billing discipline, and prevents month-end inventory shocks without consuming doctor time.

---

## Daily Micro-Audit Checklist (20–30 mins/day)

### STEP 1 — Identify High-Risk Medicines (One-Time Setup)

High-risk medicines are selected based on:
- High daily sales volume
- Similar or confusing name variations
- Frequent prescription by the doctor
- Higher value per unit

**High-Risk List Example**

| Medicine (Master) | Why High Risk |
|-------------------|--------------|
| Dolo 650 | High volume + multiple name variations |
| Azithromycin 500 | Abbreviations commonly used |
| Pantoprazole 40 | Prescribed frequently |

⏱ Time: ~30 minutes (one-time)

---

### STEP 2 — Daily Name-Variation Check (10 mins/day)

**What is done:**
- Filter sales register for high-risk medicines only
- Group similar entered names manually or visually

**Example Mapping**

| Entered Name Variants | Mapped To |
|----------------------|-----------|
| Dolo / Dolo kind / Dolo 650 | Dolo 650 |
| Azithro 500 / Azithromycin | Azithromycin 500 |

**What is flagged:**
- New or unusual name variants
- Misspellings not seen earlier

**Action:**
- Add variant to mapping list
- Inform billing staff to use standard name

---

### STEP 3 — Daily Usage Reasonableness Check (10 mins/day)

For each high-risk medicine:

**Expected Closing Stock = Opening Stock + Purchases − Total Sales**

Compare expected vs actual closing stock.

**Tolerance:** ±2%

**Example**

| Medicine | Expected | Actual | Difference | Action |
|--------|---------|--------|------------|--------|
| Dolo 650 | 1,460 | 1,440 | −20 | Review sales entries |

Focus is on **patterns**, not perfect matching.

---

### STEP 4 — Random Bill Spot Check (5–10 mins/day)

**What is done:**
- Randomly select 3–5 bills involving high-risk medicines
- Verify:
  - Medicine name matches master
  - Quantity is reasonable vs prescription

**Why random:**
- Staff never knows which bill is checked
- Improves attention and double-checking behavior

**Outcome:**
- Errors logged
- No punishment — only correction

---

## Weekly Checklist (15 mins/week)

### STEP 5 — Pattern Tracking

Maintain a simple error log.

| Date | Medicine | Error Type | Repeated? |
|------|---------|------------|-----------|
| Aug 1 | Dolo 650 | Name variation | Yes |
| Aug 3 | Dolo 650 | Wrong quantity | No |

**Decision Rules:**
- Same error ≥3 times → staff retraining
- Multiple medicines affected → SOP update

---

## Doctor Escalation Rules

Doctor involvement only when:
- Financial impact is material
- Error pattern persists despite correction
- Inventory issue affects patient treatment availability

All routine corrections are handled by the analyst and staff.

---

## Conclusion

This daily micro-audit system creates early visibility into errors, improves staff discipline through small consistent checks, and prevents month-end inventory shocks while fully protecting doctor time.


Automation is layered only after workflow stability.


## Conclusion

This system transforms patient communication from reactive WhatsApp handling into a structured, auditable, and scalable workflow that preserves care quality while protecting doctor time.
