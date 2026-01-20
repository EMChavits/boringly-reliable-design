# BORINGLY-RELIABLE Design Contract

This repository contains the **canonical, versioned BORINGLY-RELIABLE design contract** and its companion application guidance.

The contract defines how to design systems intended to function as **long-lived, dependable infrastructure**, where predictability, diagnosability, and recoverability take precedence over novelty or feature richness.

---

## Contents

- **DESIGN-CONTRACT.md**  
  The binding design contract. Defines the principles, obligations, and non-goals required for borningly reliable systems.

- **APPLYING-THE-CONTRACT.md**  
  Practical guidance and operational tests for applying the contract to new designs, changes, and existing systems.

- **CHANGELOG.md**  
  Explicit, versioned record of intentional changes to both core documents.

---

## Intended Use

These documents are intended to be used as:

- governing design input for software, automation, and infrastructure projects
- a structured lens for sense-checking existing systems and proposed changes
- shared context for AI-assisted development and code review
- a guardrail against accidental complexity and feature creep

They are **not** intended as a general-purpose software methodology or a substitute for domain-specific requirements.

---

## Versioning and Authority

- The design contract and application guidance always share the **same version number**.
- Only changes recorded in `CHANGELOG.md` are authoritative.
- Each version is considered **locked** once published.

Consumers of the contract should assess systems against the version in force at the time the system was designed.

---

## Scope and Philosophy

The BORINGLY-RELIABLE design contract assumes that:

- systems exist to serve people, not to showcase technical capability
- failures are inevitable and must be obvious, local, and recoverable
- innovation belongs at the edges, not at the core

Where a choice exists, reliability wins.

---

## Status

Current version: **v1.1.0**

---

