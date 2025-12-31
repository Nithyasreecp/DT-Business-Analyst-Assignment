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

Automation is layered only after workflow stability.


## Conclusion

This system transforms patient communication from reactive WhatsApp handling into a structured, auditable, and scalable workflow that preserves care quality while protecting doctor time.
