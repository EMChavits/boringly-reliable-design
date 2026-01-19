# Changelog  
## BORINGLY-RELIABLE Design Contract

This changelog records **intentional changes** to the BORINGLY-RELIABLE design contract
and its companion document, `APPLYING-THE-CONTRACT.md`.

It exists to make evolution of the contract explicit and traceable.

---

## Versioning Policy

The design contract follows conservative semantic versioning:

- **Patch (x.y.Z)** — clarifications only; no change in obligations  
- **Minor (x.Y.0)** — additive refinements that tighten or clarify constraints  
- **Major (X.0.0)** — substantive changes that may invalidate existing compliant systems  

Both core documents always share the **same version number**.

---

## v1.0.0 — 2026-01-19

### Added
- Initial publication of the BORINGLY-RELIABLE design contract
- Explicit definition of the contract as binding rather than advisory
- Core principles prioritising determinism, minimal surface area, and explicit scope
- Feature acceptance and exclusion rules
- Diagnostics philosophy based on observation rather than interpretation
- Conservative versioning model

### Added (Application Guidance)
- Three-phase development model (Exploration → Convergence → Commitment)
- Explicit guidance on when *not* to apply the contract
- Method for applying the contract to existing systems
- Common failure modes when misapplying the contract
- Indicators for readiness to adopt the contract

### Notes
- This version establishes the baseline contract.
- No prior versions exist.
- All future changes must be recorded here.
