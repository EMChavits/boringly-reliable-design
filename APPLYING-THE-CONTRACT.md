# Applying the Boringly Reliable Design Contract  
**Version:** 1.1.0  
**Status:** Locked  
**Companion to:** DESIGN-CONTRACT.md v1.1.0

---

## Purpose

This document provides **practical tests** for applying the Boringly Reliable Design Contract.

It is intended for:
- reviewing new designs,
- sense-checking existing systems,
- evaluating changes and feature requests,
- identifying unnecessary complexity.

This document is operational, not philosophical.

---

## How to Use This Document

For each design, implementation, or change:
- Walk through each section.
- Answer each question honestly.
- Treat any failed section as a design issue, not a documentation issue.

Passing the contract requires **substantive compliance**, not creative justification.

---

## 1. Technology Choice Test

Ask:
- Are all core technologies well understood and widely deployed?
- Are normal and failure behaviours predictable and documented?
- Would a competent maintainer recognise common faults?

**Fail if:**
- the design depends on immature standards,
- vendor churn,
- or undocumented behaviour.

---

## 2. Failure Behaviour Test

Ask:
- Are failures local rather than cascading?
- Is failure visible without deep log analysis?
- Does the system default to a safe or degraded state?

**Fail if:**
- faults can remain silent,
- or failure states are ambiguous.

---

## 3. Recovery and Reversibility Test

Ask:
- Can the system be restored using simple, repeatable steps?
- Is rollback clean and complete?
- Is recovery possible without vendor or cloud dependency?

**Fail if:**
- recovery requires ad-hoc fixes,
- manual state repair,
- or specialist intervention.

---

## 4. State Integrity Test

Ask:
- Is all persistent state explicit and inspectable?
- Is state factual rather than inferred?
- Is there a clear separation between raw data and interpretation?

**Fail if:**
- derived state is treated as truth,
- or hidden logic is embedded in state.

---

## 5. Complexity and Coupling Test

Ask:
- Does each component have a single, clear responsibility?
- Are dependencies explicit and minimal?
- Could components be removed or replaced without redesign?

**Fail if:**
- behaviour emerges from tight coupling,
- or responsibilities overlap.

---

## 6. Innovation Boundary Test

If innovation is introduced:
- Is it isolated from core functionality?
- Is failure acceptable and easily bypassed?
- Is the benefit proportionate to the added risk?

**Fail if:**
- innovation is mandatory for normal operation,
- or undermines core reliability.

---

## 7. Human-Centric Operation Test

Ask:
- Are names meaningful and unambiguous?
- Can status be understood at a glance?
- Is diagnostic information useful under pressure?

**Fail if:**
- interpretation requires prior knowledge,
- or routine operation demands explanation.

---

## 8. Deviation Test (Mandatory)

If any section fails:
- Is the deviation explicitly documented?
- Are risks clearly stated and accepted?
- Is scope limited and reversible?

**Fail if:**
- deviation is implicit,
- accidental,
- or justified only by convenience.

---

## Practical Rule of Thumb

> If a system requires explanation to defend its reliability, it likely violates the contract.

---

## Versioning and Alignment

This document is **locked at v1.1.0** and must be used alongside:
- DESIGN-CONTRACT.md v1.1.0

Both documents must be updated together.

---
