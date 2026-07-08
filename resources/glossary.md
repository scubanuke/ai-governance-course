# Glossary

One entry per key term, plain-language first. Terms are defined as the course uses them; where a term has a specific instrument or standard behind it, that is noted.

- **Design basis (DB)** — a written, bounded, consequence-anchored commitment to what a system is engineered to withstand. It names the consequences that must not happen and the bounded set of conditions the system is built to survive, and it serves as the yardstick every adequacy argument is measured against. Borrowed from nuclear safety engineering.

- **Consequence-anchored root** — the specific, concrete outcome that must not happen, stated in the system's own terms, from which the whole design basis is derived. The fixed point everything else traces back to.

- **Bounded adversary envelope** — the explicitly stated set of adversary capabilities and conditions a design is engineered to defeat — and, just as explicitly, what falls outside it. Bounding the adversary (rather than chasing every threat) is what makes the discipline tractable and testable.

- **DBA / DBA-MA** — *Design Basis Accident* is the classic nuclear instantiation: postulated accidents (equipment failure, natural hazard) the plant's safety systems must bring to a safe state. *Design Basis Accident — Military Action* is this work's extension of the same method to deliberate adversary action, including cyber and kinetic/military threats.

- **Facility-class design basis (FC-DB)** — the design basis for the facility or facility class; anchors on physical/operational must-not-happens, bounds a physical/kinetic/operational adversary.

- **AI design basis (AI-DB)** — the design basis for the AI operating in or over the facility; *inherits* the FC-DB's consequence root (and may extend it), but bounds a distinct adversary envelope — model manipulation, data poisoning, prompt injection, autonomy drift. The reason the AI is not covered by the facility's DB.

- **Inherit-and-diverge** — the relationship between the two design bases: shared consequence root, different adversary envelope. The keystone result of the course.

- **Design basis vs. risk management** — they differ in epistemology, not rigor. Risk management works against a threat envelope it never formally bounds; a design basis formally bounds the envelope and carries a forcing function that triggers review when a threat exceeds it. Without that function, risk assumptions drift silently.

- **Bright Line** — the boundary, defined in the AI-DB, past which the AI's action could reach the facility's must-not-happen consequences; the seam where the AI design basis fastens to the facility's. Must be *bright* — observably crossed or not. (Written as two words, no hyphen, in the architectural-boundary sense.)

- **Three-tier criticality model** — the AI-DB's severity scale: how much the AI's failure matters, measured against the inherited consequences. Structured as the SIL-equivalent (functional-safety Safety Integrity Level analog) for AI; higher tier means greater reach to worse consequences and correspondingly greater assurance obligations.

- **Command Broker (CB-)** — the construct that enforces the Bright Line in live operation, mediating every AI command before it can reach the controlled system. Made trustworthy by independence from the AI, determinism/verifiability, and minimality. Distinct from the CDB- communications design basis.

- **Proposer–Gate pattern** — the runtime architecture that realizes the Command Broker: an unverifiable *proposer* (the AI) holds proposal authority only, while a simple, deterministic, formally verified *gatekeeper* holds veto authority and is the sole path to the process. The safety case lives entirely in the gatekeeper.

- **Facility class** — a carved category of facilities alike enough in consequence and adversary profile that a single design basis can serve the whole category. Justified by the strategic-significance boundary.

- **Strategic-significance boundary** — the line a category of facility crosses when its systematic loss would reach a national or systemic consequence, justifying elevation to a standing facility class.

- **Four-filter applicability gate** — the test for whether the (military-action) design basis applies to a specific facility: geolocation relative to defense-critical loads, position in strategic transport corridors, substitutability, and adversary targeting logic. Disjunctive for a positive determination (any one filter puts a facility in scope); cumulative and documented for a negative one; built to fail toward inclusion. (Author's Section 1.4 / OI-8 gate, canonicalized in DBA-MA-AF.)

- **TAF (Tiered Assessment Framework)** — the procedure that proportions assessment depth to criticality, assessing the cognitive-layer errors of generative AI. Uses two orthogonal scales: criticality level (Highest/Mid/Lowest) and assessment tier (safety-critical / quality-of-service / compliance).

- **Local Sovereignty** — a protective function maintained independent of the digital infrastructure it protects: colocated with the asset, operating on physical principles, unreachable through the adversary's channels. Embodied by the Aurora Disruptor.

- **Aurora Disruptor** — a passive, analog protective device that blocks Aurora-style attacks on rotating machinery using only physical inputs (grid frequency and its rate of change); the canonical hardware embodiment of Local Sovereignty and the Bright Line. Deployed at scale in Operation Rockridge.

- **Generative / agentic / autonomous AI** — generative *produces* outputs; agentic *acts* toward a goal across steps; autonomous acts *without a human in the loop*. The governance-relevant boundary is where an autonomous system crosses into safety-critical reach.

- **Autonomous Influence Broker (AIB)** — an AI system (or coordinated network) that detects, amplifies, and directs influence at scale with enough autonomy that no human authorizes its specific outputs; operates via an aggregate→profile→generate→deliver pipeline. The policy branch's canonical threat.

- **Influence Broker** — the governance remedy to the AIB: a mandatory human gate interposed between the generation and delivery stages, architecturally non-bypassable, which also restores accountability. The information-domain analog of the Command Broker.

- **Aggregation Threshold** — the point at which an AI's synthesis of individually innocuous, legally obtained data crosses into functional mass surveillance; the trigger condition for an Influence Broker mandate.

- **Three forms of deterrence** — *punishment* (attack will be attributed and punished), *denial* (attack will not succeed against a hardened target), and *resilience* (system recovers faster than the campaign can sustain). Denial is the form design-basis standards most directly produce.

- **Founding gap** — the course's premise: no critical-infrastructure sector but nuclear was ever required to define a formal design basis, leaving most of critical-infrastructure protection without the discipline that makes safety engineering rigorous — a gap that turns acute once autonomous AI enters these systems.

- **CCE / CIE** — *Consequence-driven Cyber-informed Engineering* (the acute, consequence-first methodology formalized at Idaho National Laboratory) and *Cyber-Informed Engineering* (the broader design philosophy of building cyber-consequence reasoning into engineering from the start). The lineage this course's method stands on.
