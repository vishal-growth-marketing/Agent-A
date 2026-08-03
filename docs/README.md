# Agent-A Documentation

Welcome to the Agent-A documentation.

This directory explains how Agent-A is designed, how it executes work, and the principles that govern every decision.

Unlike the root `README.md`, which introduces the project, these documents explain the architecture, workflow, philosophy, and design decisions behind the system.

---

## Documentation

### Architecture

**File:** `architecture.md`

Learn how Agent-A is structured, including Governance, Orchestrators, Skills, and the overall execution model.

---

### Workflow

**File:** `workflow.md`

Understand how work moves through Agent-A, from Market Research to final release, including responsibilities and handoffs between every role.

---

### Philosophy

**File:** `philosophy.md`

Learn the principles behind Agent-A, including Human-Governed AI, evidence-based decision making, and why specialists outperform general-purpose agents.

---

### Design Principles

**File:** `design-principles.md`

Understand the engineering principles used throughout the repository, including ownership, consistency, governance, and explicit responsibility boundaries.

---

### Glossary

**File:** `glossary.md`

Definitions for the terminology used across Agent-A, including Skills, Orchestrators, Governance, Execution, Positioning, Strategic Drift, GEO, EEAT, and more.

---

### Frequently Asked Questions

**File:** `faq.md`

Answers to common questions about Agent-A's architecture, workflow, contribution model, and design decisions.

---

## Documentation Principles

Every document in this directory should:

- Explain the system, not individual implementations.
- Avoid duplicating information from Governance, Orchestrators, or Skills.
- Use consistent terminology from the Glossary.
- Reflect the Constitution and Execution documents.
- Help contributors understand **why** Agent-A is designed the way it is.

---

## Repository Structure

```text
README.md
    │
    ▼
docs/
    │
    ▼
governance/
    │
    ▼
orchestrators/
    │
    ▼
skills/
```

Each layer has a different responsibility:

| Layer | Responsibility |
|--------|----------------|
| README | Introduces Agent-A |
| Documentation | Explains the system |
| Governance | Defines rules and standards |
| Orchestrators | Coordinate decision-making |
| Skills | Execute specialized work |

Documentation exists to help contributors understand the system before extending or modifying it.
