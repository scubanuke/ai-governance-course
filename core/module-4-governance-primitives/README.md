# Module 4 — The Governance Primitives

## Learning Objectives

After this module, a student will be able to:

- Explain Bright Line Criteria as the seam between the two design bases.
- Place an AI system in a criticality tier measured against inherited consequences.
- Describe how the Command Broker enforces the Bright Line in live operation.


**Read this module as the toolkit of the AI design basis.** In Module 3 you learned that a facility where AI operates has two design bases — the facility's (FC-DB) and the AI's (AI-DB) — meeting at a seam called the Bright Line. Everything in this module lives on that seam. These are not a grab-bag of governance ideas; they are the machinery that builds and enforces the second design basis.

- **Bright Line Criteria** — the boundary in the AI-DB that keeps the AI from reaching the consequences the FC-DB says must not happen.
- **The three-tier criticality model** — how much the AI's failure matters, measured against the inherited consequences. This is the AI-DB's severity scale.
- **The Command Broker** — the construct that enforces the Bright Line in live operation.

## Units, in order

1. `00-bright-line-criteria.md` — the seam between the two design bases
2. `01-three-tier-criticality.md` — SIL-equivalent AI tiering, measured against inherited consequences
3. `02-command-broker.md` — enforcing the Bright Line in operation
4. `in-your-sector.md` — closing reflection
