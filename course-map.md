# Course Map — Design Basis for AI Governance

**Version 0.1.** This is the working syllabus. Move pieces around here; the folder skeleton mirrors it.

The through-line is the **method** — how a design basis is derived and how a facility class is carved. The energy, nuclear, and data-center material are worked examples hanging off that spine, not the only supported paths.

---

## Core — everyone walks this (sector-agnostic method)

### Module 0 — Orientation and the founding gap
The hook: the National Infrastructure Protection Plan never required any sector but nuclear to define a formal design basis. Most of critical-infrastructure protection has run without the discipline that makes safety engineering rigorous. **The learner picks their sector here**, and it threads through everything after.
Closes with: *In Your Sector.*

### Module 1 — What we're actually governing
The generative / agentic / autonomous taxonomy, and why conflating the three wrecks governance reasoning. The accessible on-ramp that grounds the vocabulary before the method arrives.
**Physically split:** a stable conceptual unit (autonomy crossing into safety-critical is *the* governance-relevant boundary) and a separate, dated snapshot unit holding current examples. See `CONVENTIONS.md`.
Closes with: *In Your Sector.*

### Module 2 — Consequence-driven thinking
The CCE / CIE lineage and the shift from vulnerability-first to consequence-first. The mental move everything downstream depends on.
Closes with: *In Your Sector.*

### Module 3 — Design basis methodology
The crown jewel. What a design basis is, borrowed from nuclear safety, and how you derive one: the consequence-anchored root and the bounded adversary envelope. DBA into DBA-MA. The module teaches the method, then instantiates it **twice**.
**The keystone unit — Two Design Bases:** a facility where AI operates has *two* design bases, not one. The facility-class design basis (FC-DB) and the AI design basis (AI-DB) inherit the same consequence root but diverge on the adversary envelope — which is exactly why the AI needs its own DB rather than being covered by the facility's. The seam between them is the Bright Line. This unit is written out, not stubbed.
Closes with: *In Your Sector.*

### Module 4 — The governance primitives (the AI-DB toolkit)
Reframed as the **machinery of the AI design basis**, all sitting on the Bright Line seam from Module 3. Bright Line Criteria (the seam itself), the three-tier criticality model (the AI-DB's severity scale, measured against inherited consequences), and the Command Broker (what enforces the Bright Line in operation). Not a grab-bag of primitives — the toolkit that builds and enforces the second design basis.
Closes with: *In Your Sector.*

---

## Bridge — everyone

### Module 5 — Sectors, applicability, and facility classes
What a facility class is and how one gets carved: the strategic-significance boundary and the four-filter applicability gate. Worked examples from the author's own carve-outs — LNG as a standing class, oil marine terminals on strategic significance, data centers as the newest. The open **OI-O5 / OI-G9** strategic-versus-deliverability question is presented here as a live example of the exact reasoning an advanced learner should practice. This is where the chosen sector stops being cosmetic and the learner maps their sector onto the method.

---

## Branch — pick one

### OT track
Design-basis derivation in depth and the assessment machinery: TAF tiering, IEEE V&V, 62443 mapping, Command Broker and Bright Line at the architecture level, and Local Sovereignty with the Aurora Disruptor as the canonical case. Prepares the learner to **produce a design basis or assessment**.

### Policy track
Consequence and governance analysis: the Democratic Safeguards material (Autonomous Influence Broker, AI-enabled market manipulation), the three deterrence forms, and the standards-gap argument. Prepares the learner to **produce a governance and consequence analysis**.

---

## Capstone — both branches, same target, both design bases

Pick a real facility in your sector. **Both design bases are required of both branches.** OT learners *derive* both the FC-DB and the AI-DB and show the Bright Line seam between them; policy learners *analyze* both — the facility's consequence set and the AI's inherited-plus-extended set — and the governance gap each implies. A capstone that produces only one design basis is the incomplete answer the course exists to prevent. A shared rubric gates on both-DBs-present, then grades the fundamentals — consequence-anchored root, inherit-and-diverge, bounded adversary envelope, criticality tiering — with the branch-specific deliverable on top.
