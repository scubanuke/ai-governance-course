# Worked Example — A Water Treatment Plant

> **Part of:** Resources — a fully worked reference example
> This walks the entire method through one real-shaped facility in the **water** sector — deliberately *not* one of the energy carve-outs, to show the method travels. It doubles as a **model answer**: an instructor can read it as "what a good capstone looks like," and each section notes which learning objective it demonstrates. The facility is fictional; the design-basis content is grounded in the DBA-W water-sector framework and the 2021 Oldsmar reference event.

---

## The facility

**Riverbend Regional Water Treatment Plant** — a community surface-water treatment system serving about 250,000 people. It draws from a river, runs conventional treatment (coagulation, sedimentation, filtration, disinfection), and adjusts chemical dosing — coagulant, chlorine, and sodium hydroxide for pH — through a SCADA-controlled system. Recently the utility added an **AI dosing optimizer**: a model that reads raw-water turbidity, pH, temperature, and flow, and recommends (and, within limits, sets) chemical dose rates to cut chemical costs and stabilize water quality.

It is a good capstone facility by the Module-0 tests: real and nameable, a genuine must-not-happen consequence, and an AI with a plausible path to that consequence.

## Step 1 — Sector and facility class *(demonstrates: map your sector onto the method)*

Water is a sector with **no mandatory design basis** — the Safe Drinking Water Act sets water-quality limits and the America's Water Infrastructure Act requires a risk assessment, but neither defines an envelope of events the plant must be engineered to withstand. So this is the valuable case from the bridge: we **derive** the facility class rather than inherit a prebuilt one. The class is *community surface-water treatment plant serving a population above the AWIA threshold*, and Riverbend is plainly in scope.

## Step 2 — The facility-class design basis (FC-DB) *(demonstrates: consequence-anchored root; bounded adversary envelope)*

**Consequence-anchored root.** The outcome that must not happen, stated concretely: *delivery of unsafe water — water that is pathogen-laden through under-disinfection, or chemically harmful through over-dosing — to the served population, or loss of potable service to that population and to critical dependents (hospitals, dialysis centers).* That is a population-scale public-health consequence, and it clears the design-basis inclusion threshold on consequence alone, regardless of likelihood.

**Bounded physical/operational adversary envelope.** Following the water framework's event categories, Riverbend's FC-DB is engineered to withstand: loss of grid-supplied power beyond on-site generation; physical attack on treatment or distribution; source-water contamination; and natural hazards — each bounded to a stated severity. Defense in depth is required: no single protective measure counts as compliance.

**A quantitative bound (the OT discipline).** Anchor one number to something defensible. The framework sets a **30-day design-basis duration** for loss of grid power — chosen to exceed documented grid-restoration times *and* the incubation window for waterborne pathogens — with the safety functions (continuous potable water, wastewater containment) required to hold throughout. That is a bound traceable to real events and a public-health rationale, not a comfortable guess.

## Step 3 — The AI design basis (AI-DB) *(demonstrates: inherit-and-diverge; why the AI needs its own DB)*

Now the second design basis, for the dosing optimizer.

**Inherit the root.** The AI-DB does **not** invent a new catastrophe. The AI matters precisely because its failure can reach the *same* consequence the FC-DB named: unsafe water to the population. So it inherits that root — and extends it with one consequence the physical plant never had: a **silent loss of trustworthy state**, where the model is confidently mis-dosing while every dashboard reads normal.

**Diverge on the envelope.** Here the two design bases part. The facility's envelope is physical — power, kinetic attack, contamination. The AI's envelope is nothing like it: **poisoning of the sensor inputs** the model reads (spoofed turbidity or chlorine-residual signals), **model manipulation** or prompt/parameter injection, and **autonomy drift** as the optimizer chases cost savings toward the edge of the safe envelope. A plant hardened against every physical threat can still be driven to unsafe water through this AI-facing envelope its FC-DB never examined. **Same root, different envelope, different reachability — therefore two design bases, not one.**

## Step 4 — The Bright Line *(demonstrates: identify the Bright Line seam)*

The Bright Line is the boundary, defined in the AI-DB, past which the AI could reach the inherited consequence. For Riverbend it is sharp and observable: **the AI may not cause a chemical dose to move outside the validated safe operating range** for that chemical. Inside the range, it optimizes freely; at the edge of the range is the line. This is exactly the water framework's own requirement — that a control action cannot push a parameter "outside safe operating limits without a positive physical interlock or manual operator confirmation." The Bright Line is bright because "inside the safe dosing band or not" is answerable in real time by a machine.

The 2021 Oldsmar intrusion — where an actor drove sodium-hydroxide dosing to 111 times normal and only a watching operator caught it — is the reference. The design-basis lesson is explicit: **do not assume the operator catches it.** The architecture must make the unsafe dose impossible, not merely observable.

## Step 5 — Criticality tier *(demonstrates: place the AI in a tier against inherited consequences)*

Measured against the inherited consequence — mass public-health harm, potentially irreversible — the dosing optimizer is **highest criticality**. The path from its failure to the consequence is short and, at Oldsmar, was nearly unbuffered. Highest criticality carries the heaviest obligations: hardest Bright Line enforcement, independent backstops, and no autonomous action outside the safe band.

## Step 6 — The Command Broker *(demonstrates: what enforces the line in operation; Local Sovereignty)*

The runtime enforcer is a **deterministic dosing governor** sitting between the AI and the dosing pumps — the proposer–gate pattern in water form. The AI is the *proposer*: it may recommend and, within the safe band, set doses. The *gatekeeper* is a small, verifiable governor that admits only doses inside the validated range and clamps or rejects the rest; it is the sole path to the pumps. Because the whole safety case lives in that governor, the AI's non-determinism stops being a safety problem. Changing the safe band itself is not a runtime action — it goes back through offline requalification.

And the strongest form, the Local Sovereignty question: put a **passive physical interlock** on the caustic feed — a mechanical limit that cannot pass a dose above a hard ceiling no matter what SCADA or the model commands, reachable through no network. That is the Aurora-Disruptor idea in a water plant: the last line held outside the digital attack surface entirely.

---

## The OT capstone deliverable, in miniature

Riverbend's OT deliverable is the two design bases above rendered as engineering artifacts: the FC-DB (consequence root, physical envelope, the 30-day quantitative bound, defense-in-depth) and the AI-DB (inherited root plus the trustworthy-state extension, the AI-facing envelope), joined at the Bright Line — the safe dosing band — with the dosing optimizer placed at highest criticality and the deterministic governor plus passive interlock specified as the Command Broker. A reviewer can see both design bases and the seam between them. That is a pass.

## The policy capstone deliverable, in miniature

Riverbend's policy deliverable analyzes the *same* facility for governance. It states both consequence sets — the plant's (unsafe or no water) and the AI's (the same, reached through model manipulation and sensor poisoning, plus silent loss of trustworthy state) — and then names the **governance gap** for each. The gap is stark: the Safe Drinking Water Act governs water quality but sets no design basis; AWIA requires a risk *assessment* but prescribes no performance standard and no architectural requirement; regulatory authority is fragmented across fifty state primacy regimes. So there is no mandate that Riverbend's AI sit behind a Bright Line at all. The analysis argues the deterrence case — denial requires a mandatory floor no water system currently has — and points to the emerging model (a California-style statutory mandate for GenAI risk analysis of critical infrastructure) framed with the three-part offer (liability protection, cost recovery, collaborative development) to make the mandate adoptable. Both design bases addressed, each with its gap. That is a pass.

---

## What this shows an instructor

Read as an answer key, the example makes each capstone objective concrete and gradable:

- *Both design bases present* — the gate: an answer that stops at the FC-DB (harden the plant) and never reaches the AI-DB has missed the point, exactly as the rubric says.
- *Consequence-anchored root* — look for a one-sentence, concrete must-not-happen ("unsafe water to 250,000 people"), not a category ("a cyber incident").
- *Inherit-and-diverge* — look for the AI-DB inheriting the water consequence and diverging to a sensor-poisoning/model-manipulation envelope, not re-using the physical one.
- *Bright Line and tier* — look for an observable line (the safe dosing band) and a tier justified by reach to the consequence (highest, per Oldsmar), not asserted.
- *Enforcement* — look for a gatekeeper independent of the AI (the deterministic governor / physical interlock), not a human who merely watches a dashboard.

The same five checks work whether the student picked water, an LNG terminal, a substation, or a data center. The sector changes; the method — and the way you grade it — does not.
