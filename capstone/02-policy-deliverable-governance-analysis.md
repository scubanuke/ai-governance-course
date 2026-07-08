# Policy Deliverable: Consequence and Governance Analysis (Both Design Bases)

> **Part of:** Capstone / Policy

This is the policy capstone. You will produce, for the facility you selected, a consequence-and-governance analysis that reckons with **both** design bases — the facility's own consequence set and the AI's inherited-plus-extended set — and identifies the governance gap each implies. An analysis that addresses only the facility and ignores the AI (or the reverse) does not pass; reckoning with both is the non-negotiable the course was built around. Everything from the policy branch (units 00–04) is a tool for this deliverable.

## Required components

**1. The facility's consequence set (FC-DB view).** State what must not happen at this facility — the physical and operational consequences — and describe the physical/operational adversary envelope the facility's design basis bounds. You are not deriving the engineering artifact here (that is the OT branch); you are analyzing the consequence and threat picture rigorously enough to reason about governance.

**2. The AI's consequence and adversary set (AI-DB view).** Lay out the consequences the AI inherits from the facility, plus any it extends — integrity, influence, loss of trustworthy state — and the distinct AI-facing adversary envelope (model manipulation, data poisoning, prompt injection, autonomy drift). Make the argument explicitly: *why does the AI need its own design basis rather than being covered by the facility's?* The answer — shared consequence root, divergent adversary envelope — is the analytic core of the deliverable.

**3. The governance gap.** For **each** design basis, state what governance, standards, or deterrence posture is missing today and what your analysis implies should exist. This is where you connect to the standards-gap argument from policy unit 04: is there a mandatory design-basis requirement for this facility, or only voluntary practice? What would close the gap, and how would compliance be verified?

## How to build it, and what "good" looks like

Lead with the method from policy unit 00: argue from the technology's characteristics, not from values, so your conclusions cannot be dismissed as preferences. Run the five-step chain on your facility — two-layer decomposition, verification gap, consequence tiering, Bright Line, broker-and-audit — and let the consequence do the arguing.

Then bring the branch's cases and frameworks to bear where they fit your facility. If your facility touches opinion, information, or population-scale decisions, use the **Autonomous Influence Broker** analysis (unit 01) — locate the equivalent of the Aggregation Threshold and specify an Influence Broker gate. If it touches a market, use the **market-manipulation** analysis (unit 02) — name the consequential action that belongs behind a Bright Line and the accountability anchor whose duty to detect makes inaction the liability. Assess the facility's **deterrence** posture across all three forms from unit 03 — punishment, denial, resilience — and apply the "least-hardened facility" test: could an adversary shop for the gap? Then make the **standards** argument from unit 04, sorting what you find into process gaps (closable administratively) and authority gaps (needing statute), and framing any mandate with the three-part offer — liability protection, cost recovery, collaborative development — that makes it adoptable.

A strong policy capstone reads like something a legislator or regulator could act on: each recommendation names the consequence it addresses, the boundary it draws, and how compliance would be verified; the two design bases are genuinely distinguished; and the governance gap is specific to this facility and sector, not a generic complaint. Where you reference contested or alleged real-world cases, handle them as your source material does — as analytic scenarios, not verdicts.

## Common failure modes to avoid

The disqualifying failure is analyzing only the facility's physical consequences and never reckoning with the AI (or the reverse) — the incomplete answer the course exists to prevent. Beyond that: treating the AI-DB view as a restatement of the facility's rather than showing the divergent envelope; recommending contractual or training-level safeguards for a high-consequence use when only an architectural one would hold; and identifying a gap without specifying whether it is a process gap or an authority gap, which leaves a policymaker without an actionable next step. Check your draft against each, then take it to the shared rubric.
