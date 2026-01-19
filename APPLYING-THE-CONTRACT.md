# Applying the BORINGLY-RELIABLE Design Contract

**Version:** 1.0.0  
**Status:** Stable  
**Last updated:** 2026-01-19

---

## Purpose

This document explains **when and how** to apply the BORINGLY-RELIABLE design contract in practice.

It complements `DESIGN-CONTRACT.md` by describing:

- the correct timing for adopting the contract  
- how to transition from exploration to commitment  
- how to apply the contract to new projects  
- how to use the contract to sense-check and simplify existing systems  
- how to avoid common misapplications of the contract  

This document is **platform agnostic** and applies to any software or system design context.

---

## Relationship to the Design Contract

- `DESIGN-CONTRACT.md` defines **what the contract is** and **what it demands**.
- This document defines **when the contract applies** and **how it should be used**.

The two documents are intended to be read together and kept **version-aligned**.

---

## Why Timing Matters

The BORINGLY-RELIABLE design contract is intentionally **restrictive**.

Applied correctly, it produces systems that are calm, predictable, and low-maintenance.  
Applied incorrectly, it can inhibit learning and prematurely constrain design.

Understanding *when* to apply the contract is therefore as important as understanding *what* the contract requires.

---

## The Three Development Phases

### Phase 1 — Exploration (Contract does NOT apply)

**Purpose:** learning and discovery

Characteristics of this phase include:

- experimentation with ideas and features  
- temporary heuristics and assumptions  
- verbose or diagnostic-heavy logging  
- rapid iteration and change  
- acceptance that many ideas will be discarded  

Examples of appropriate Phase 1 activity:

- testing combinations of signals or inputs  
- exploring monitoring thresholds or alerting strategies  
- learning a new protocol or API  
- validating feasibility of an approach  
- identifying failure modes  

**Rules in this phase:**

- nothing is promised  
- nothing is frozen  
- nothing is considered stable  
- correctness is secondary to understanding  

Applying the BORINGLY-RELIABLE contract during this phase is **incorrect** and counterproductive.

---

### Phase 2 — Convergence (Contract used as a filter)

**Purpose:** reduction and selection

This phase begins once sufficient understanding has been gained and the problem space is clearer.

Characteristics include:

- deliberate rejection of fragile or complex ideas  
- identification of mechanisms that are genuinely reliable  
- documentation of assumptions and constraints  
- explicit definition of non-goals  
- narrowing scope intentionally  

In this phase, the contract is not yet enforced, but it is used as a **filter**.

Typical questions asked at this stage include:

- Which features rely on inference rather than formal signals?  
- Which behaviours introduce ambiguity or hidden failure modes?  
- Which ideas add long-term maintenance burden?  
- Which mechanisms remain predictable over time?  

Most candidate features should be rejected at this stage.

---

### Phase 3 — Commitment (Contract fully applies)

**Purpose:** long-term stability

This phase begins when the system is ready to prioritise predictability over flexibility.

Characteristics include:

- explicit scope and behavioural guarantees  
- stable semantics  
- documentation treated as binding  
- resistance to incremental feature creep  
- deliberate, versioned change  

Once a system enters Phase 3:

- the BORINGLY-RELIABLE contract becomes enforceable  
- deviations are treated as design violations  
- scope expansion requires explicit version boundaries  
- stability takes precedence over novelty  

This is the correct point at which a project should declare adherence to the BORINGLY-RELIABLE design contract.

---

## Using the Contract for New Projects

For new projects, the recommended approach is:

1. Begin in Phase 1 without applying the contract.  
2. Explore freely and document findings.  
3. Transition consciously into Phase 2.  
4. Reject aggressively using the contract as a filter.  
5. Adopt the contract only when ready to commit to stability.  

The contract is adopted **after learning**, not before.

---

## Using the Contract to Sense-Check Existing Projects

The BORINGLY-RELIABLE contract may be applied retroactively to reassess existing systems.

This process is not refactoring for optimisation.  
It is **design realignment**.

### Recommended sense-check approach

1. Re-read `DESIGN-CONTRACT.md` in full.  
2. Identify areas that raise concern, such as:
   - background activity  
   - inferred states or health indicators  
   - adaptive or self-healing behaviour  
   - unexplained complexity  
3. For each area, choose one outcome:
   - **Keep** — explicitly reaffirm as contract-compliant  
   - **Remove** — delete cleanly and intentionally  
   - **Quarantine** — document as legacy or non-core  
4. Update documentation **before** modifying code.  
5. Prefer removal over replacement.  

Reduction of capability is an acceptable and often desirable outcome.

---

## Common Failure Modes

### Applying the contract too early

Results in:
- constrained thinking  
- incomplete understanding  
- brittle designs  

---

### Treating the contract as guidance rather than obligation

Results in:
- negotiation of constraints  
- gradual scope creep  
- erosion of guarantees  

---

### Mixing exploration and commitment

Results in:
- confusion about intent  
- inconsistent behaviour  
- unclear expectations  

The contract must be either *fully applied* or *not applied at all*.

---

## Relationship to Documentation

Once the contract is adopted:

- documentation becomes authoritative  
- comments preserve intent and guarantees  
- behaviour must match documented expectations  
- undocumented behaviour is considered a defect  

Accuracy of explanation is prioritised over brevity.

---

## Relationship to Change

Under the BORINGLY-RELIABLE contract:

- change is permitted  
- change must be deliberate  
- change must be documented first  
- change may require a version boundary  

Stability is protected by process, not inertia.

---

## Indicators That a System Is Ready for the Contract

A system is typically ready to adopt the contract when:

- the problem domain is well understood  
- core mechanisms are known to be reliable  
- feature additions are becoming marginal  
- maintenance burden is a concern  
- predictability is valued over flexibility  

If these indicators are not met, adoption should be delayed.

---

## Closing Statement

The BORINGLY-RELIABLE design contract is not intended to limit creativity.

It is a **commitment mechanism** that preserves clarity, reduces long-term effort, and prevents systems from becoming fragile through incremental compromise.

Applied at the correct stage, it transforms experience into structure and judgement into policy.
