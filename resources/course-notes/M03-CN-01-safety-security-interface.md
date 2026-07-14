# Course Note M03-CN-01 — Safety/Security Interface

**Anchor** — Core / Module 3, unit `05-merging-the-two-design-bases.md`, §*Precedent: make the interface itself the governed object*

**Source and locator** — 10 CFR 73.58, "Safety/security interface requirements for nuclear power reactors," U.S. Nuclear Regulatory Commission. Implementing guidance: Regulatory Guide 5.74, Rev. 1, "Managing the Safety/Security Interface."

**Provenance and use** — Published federal regulation and public regulatory guidance. A federal regulation is a government edict and carries no copyright. Reproduce freely and verbatim.

---

**Excerpt** — 10 CFR 73.58:

> (b) The licensee shall assess and manage the potential for adverse effects on safety and security, including the site emergency plan, before implementing changes to plant configurations, facility conditions, or security.
>
> (d) Where potential conflicts are identified, the licensee shall communicate them to appropriate licensee personnel and take compensatory and/or mitigative actions to maintain safety and security under applicable Commission requirements.

Paragraph (c) casts the scope deliberately wide: physical modifications, procedural changes, changes to operator actions or security assignments, maintenance, system reconfiguration, access changes, and changes to the security plan itself.

---

**What it establishes**

A regulator confronting two mature, co-equal design bases in a single facility — safety and security — declined to resolve the tension by declaring one dominant. It made the **interface** a regulated object. The safety basis does not subordinate the security basis, nor the reverse. Instead the licensee carries an affirmative obligation: look for conflict before acting, surface it when found, compensate when it cannot be eliminated.

RG 5.74 supplies the machinery, and the machinery is ordinary. Plant review boards, configuration management, work planning and control, corrective action programs. The interface is discharged through institutions the plant already runs, not through a new bureaucracy invented for the purpose.

This is the precedent that defeats the objection that two design bases in one facility must eventually collapse into a hierarchy. They need not. They require a managed seam, an assignable duty to assess before change, and a fallback when the seam binds.

---

**Where the AI case departs**

*Cadence.* The rule operates on changes and assumes the licensee knows when one occurs — a discrete, planned, reviewable event. Model updates, retraining cycles, revised prompts, behavioral drift under distributional shift: these are not events a review board can convene against.

*Discovery point.* The rule finds conflict before implementation. AI collisions surface at runtime, in the instant the system is asked to act. Pre-implementation review remains necessary and stops being sufficient. This is the seat of the Command Broker.

*Reach, not ownership.* The tempting claim is that the AI case has no licensee. It does — in critical infrastructure the operator is right there, already carrying interface duties, and nothing exempts a conflict merely because one side of it now originates in a model. The departure is narrower and sharper: the obligation extends to the AI system, but the operator's **reach** does not. A plant modification is something the licensee designed and can un-design. A model's behavior is shaped by a corpus it did not assemble, weights it cannot inspect, and a release cadence set outside the fence line by parties owing no duty to the interface. The nuclear licensee owns the configuration it is held to. The AI operator does not. That mismatch between accountability and control has no analogue in the precedent.

---

**Carry-forward**

The merge of the facility-class and AI design bases is a **managed interface**, not a hierarchy. Neither basis is superior; what keeps them pulling in the same direction is an affirmative, assignable duty to detect conflict and act on it. Where the nuclear precedent discharges that duty through periodic human review of discrete changes, the AI case must discharge it, in part, through arbitration at decision speed.
