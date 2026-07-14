# Shared Capstone Rubric

> **Part of:** Capstone

This rubric grades both branches on the same fundamentals, then adds branch-specific criteria on top. The point is that an OT derivation and a policy analysis of the same facility are held to a common standard on the *method* — the two deliverables look different, but they are judged first on the same core. Use it as a self-check before you consider your capstone finished, and as the standard a reviewer would apply.

Grade in three passes, in order: the gate, the shared fundamentals, then the branch-specific criteria. A deliverable that fails the gate is not scored further.

## Pass 1 — Gating requirement: both design bases

Before anything else is scored, the deliverable must address **both** design bases — the facility-class design basis (FC-DB) and the AI design basis (AI-DB). A capstone that addresses only one does not pass, regardless of how well that one is done. This is the single non-negotiable, because the two-DB distinction is what the course exists to teach.

- **OT:** are **both** DBs derived, with the Bright Line seam shown between them?
- **Policy:** does the analysis reckon with **both** DBs and the governance gap of each?

If the answer is no, the deliverable is returned at the gate. Nothing below is evaluated until both design bases are present.

## Pass 2 — Shared fundamentals (both branches)

These are the method itself, and they are scored identically for OT and policy.

- **Consequence-anchored root** — is each design basis anchored on a concrete consequence that must not happen, stated in the facility's own terms rather than as a vague category or a risk score?
- **Inherit-and-diverge** — does the AI-DB correctly *inherit* the facility's consequence root and *diverge* on the adversary envelope, rather than re-inventing the anchor or reusing the physical envelope? This is the most common place strong-looking work quietly fails.
- **Bounded adversary envelope** — is each adversary bounded rather than chased, with what is *outside* the envelope named on purpose, and are the two envelopes (physical vs. AI-facing) correctly distinguished?
- **Criticality tiering** — is the AI placed in the right tier, *measured against the inherited consequences*, with the tier's obligations actually followed rather than asserted?
- **The managed seam** — is the relationship between the two design bases handled as a *managed interface* rather than a hierarchy? A deliverable that resolves every collision by declaring one basis superior has not done the work. Look for three things: a named owner of the seam, a stated point at which conflict is detected (acceptance, declared change, or runtime), and an arbiter for collisions that surface too fast for human review.
- **Sector fit** — does the work reflect the learner's real, named facility and sector, rather than a generic template that could be pasted onto any facility?

## Pass 3 — Branch-specific criteria

Scored on top of the shared fundamentals, appropriate to the deliverable form.

**OT branch — derivation and architecture.**

- **Derivation rigor** — is the FC-DB genuinely *derived* (class carved or applied, consequence root and envelope established) rather than described, and is at least one bound made quantitative — a numeric target anchored to a standard or an empirical event, with a stated acceptance criterion?
- **Adversary-aware bounds** — does the derivation account for an adversary who has read the design basis (calibrating around a published recovery bound), not just for accidents and equipment failure?
- **V&V evidence** — is the AI system split into a formally verifiable infrastructure layer and a statistically assessed cognitive layer, with the required domain characterization, tests, and provenance named?
- **Architectural placement** — are the Bright Line and Command Broker placed in a real architecture (a proposer–gate boundary with a tested envelope and an offline requalification path for envelope changes), and is the enforcement independent of the AI behaving correctly?
- **Procurability** — could a procurement engineer write a contract from this AI-DB, and a test engineer write an acceptance test plan against it? Every clause must yield a verifiable acceptance criterion. An AI-DB written in prose principles — *the system shall behave safely* — gives the contract nothing to require and the test nothing to check. A design basis that cannot be procured against is not yet a design basis. A stated re-test trigger for supplier model changes is a mark of distinction.
- **Standards positioning** — is the design basis mapped against 62443, naming at least one foundational-requirement gap the AI's non-determinism opens? A credible Local Sovereignty backstop for the worst consequence is a mark of distinction.

**Policy branch — governance and standards.**

- **Governance-gap identification per DB** — for *each* design basis, is a specific missing governance, standards, or deterrence posture named, rather than a single generic gap covering both?
- **Argue-from-the-technology** — are conclusions derived from the technology's characteristics (so they cannot be dismissed as political preference), and is the architectural-over-contractual ordering respected for high-consequence uses?
- **Deterrence reasoning** — are all three forms (punishment, denial, resilience) assessed, and does the analysis apply the "least-hardened facility" test to show whether the sector's current posture actually deters?
- **Standards implication** — are findings sorted into process gaps and authority gaps, and is any proposed mandate framed to be adoptable (liability protection, cost recovery, collaborative development)?
- **Interface-gap reasoning** — does the analysis reckon with what the operator is accountable for but cannot reach — a model whose corpus, weights, and release cadence are authored outside the fence line — and say whether contract alone can close it, or whether a statutory duty on suppliers is required?
- **Responsible use of cases** — are contested or alleged real-world cases handled as analytic scenarios, not verdicts?

## What a passing capstone demonstrates

Read the whole rubric backward and it says one thing: the learner can take a real facility, name what must not happen, derive or analyze the two design bases that keep it from happening, show the Bright Line between them, say who owns the seam and what arbitrates when the two bases collide, and say what enforcement or governance must hold that line. A capstone that does this — for a real facility, in the learner's own sector, addressing both design bases — is the course achieving exactly what it set out to do at Module 0.
