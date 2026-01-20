# Boringly Reliable Design Contract  
**Version:** 1.1.0  
**Status:** Locked  
**Applies to:** Apps, drivers, services, automations, and supporting infrastructure  
**Scope:** Platform-agnostic

---

## Purpose

This design contract defines the principles required to build systems that are **boringly reliable**.

Systems governed by this contract are expected to function as **everyday infrastructure**, not experiments. They must behave predictably, fail honestly, and remain understandable and recoverable over long periods of time, including by maintainers who did not originally design them.

This contract prioritises operational reliability over novelty, flexibility, or feature richness.

---

## Core Principles

### 1. Reliability Over Novelty

This contract deliberately prioritises **stability, predictability, and operational clarity** over innovation or feature density.

Where a design choice exists, preference is given to technologies, patterns, and behaviours that are:
- well understood,
- behaviourally stable over time,
- easy to reason about during normal operation and failure,
- recoverable without specialist knowledge.

Innovation is not excluded, but it must be **explicitly constrained**. New or complex mechanisms are acceptable only where:
- failure is local rather than systemic,
- failure is immediately visible,
- recovery is straightforward and reversible.

Systems covered by this contract are intended to function as infrastructure. As such, long-term maintainability, diagnosability, and trustworthiness take precedence over abstraction or theoretical elegance.

Any deviation from this principle must be intentional, justified, and accompanied by a clear statement of risk.

---

### 2. Explicitness Over Cleverness

System behaviour must be obvious from the code and configuration.

- State must be explicit, named, and observable.
- Behaviour must not rely on undocumented side effects or implicit assumptions.
- Hidden coupling and emergent behaviour are prohibited.

If behaviour requires explanation to be trusted, it violates this principle.

---

### 3. Factual State Only

Systems must represent **observed or reported reality**, not inferred or speculative interpretations.

- Derived, synthetic, or convenience state is discouraged.
- Where interpretation is unavoidable, it must be clearly labelled as such.
- Raw signals and factual attributes take precedence over abstractions.

This ensures downstream consumers can make informed decisions without inheriting hidden logic.

---

### 4. Honest Failure

Failures must be:
- local,
- visible,
- understandable.

Systems must not:
- fail silently,
- mask faults,
- or degrade into ambiguous states.

A failure that is obvious is preferable to one that is hidden but partially functional.

---

### 5. Simple Recovery

Recovery paths must be:
- documented,
- repeatable,
- non-destructive.

A system should be restorable after failure, restart, or misconfiguration without requiring:
- specialist tools,
- vendor intervention,
- or manual state surgery.

If recovery is fragile or ad-hoc, the design is non-compliant.

---

### 6. Minimal and Stable Dependencies

Dependencies must be:
- necessary,
- explicit,
- stable over time.

Avoid:
- transitive complexity,
- volatile external services,
- unnecessary layers of abstraction.

Each dependency increases the system’s operational surface area and must earn its place.

---

### 7. Human-Centric Operation

Systems exist to serve people, not the other way around.

- Naming must be meaningful to humans.
- Status and health must be understandable at a glance.
- Diagnostics should prioritise clarity over completeness.

A system that cannot be reasoned about while tired or under pressure is not acceptable.

---

## Deviation Policy

Deviation from this contract is permitted only when:
- it is explicit,
- the risks are clearly documented,
- the scope is limited,
- and the deviation is reversible.

Implicit or accidental deviation is not acceptable.

---

## Non-Goals

This contract does not aim to:
- maximise features,
- adopt new standards early,
- optimise for theoretical purity,
- or impress with complexity.

Its goal is trust.

---

## Versioning and Change Control

This contract is **locked at v1.1.0**.

Future changes must:
- increment the version,
- document rationale,
- and preserve backward interpretability.

Existing systems should be assessed against the version under which they were created.

---
