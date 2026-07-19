# Worked Example — The Northgate Control Center

> **Part of:** Resources — the course's persistent worked example
> This is the **spine of the course**: a single facility, introduced at orientation and carried unchanged all the way to the capstone. Unlike the water example — a compact, single-pass model answer in a *second* sector — Northgate accumulates. Each stage of the course adds exactly one artifact to a growing record, so a learner watches the method build on one facility rather than restarting each module. It doubles as the **instructor reference set**: the boxed artifacts show what a competent response to each stage looks like, and the capstone artifact (Stage 9) is calibrated to the standard a strong capstone submission should meet. The facility is fictional; the design-basis content is grounded in the bulk-electric sector framework, the tiered assessment model, and the Command Broker material.

---

## 0 — How to use this worked example

One facility is introduced early and then carried, unchanged, through every stage to the capstone. Each stage adds a single artifact to the growing record, and every later stage builds on the artifacts before it. By the capstone the reader is not assembling a case from scratch; they are completing a record they have watched accumulate.

The example is deliberately built around **one facility with three generative-AI functions at three different consequence levels**. That single design choice lets the same case illustrate the entire criticality spectrum — from an administrative function that may run with limited autonomy to a real-time function that sits firmly above the Bright Line — without ever changing facilities on the learner.

Two uses are intended. For the **student**, the narrative sections show how each new concept lands on a facility they already understand. For the **instructor**, the boxed artifacts are a reference set, and the capstone artifact is calibrated to what a strong submission should meet. A short instructor note closes the document.

**A note on vocabulary.** The course distinguishes the **Facility-Class Design Basis (FC-DB)** — the design basis for the physical facility and its conventional, deterministic control systems — from the **AI Design Basis (AI-DB)** — the design basis for the generative-AI layer whose behavior can be reshaped after deployment. Criticality is named by tier and by level: **Highest (Tier 1), Middle (Tier 2), and Lowest / Administrative (Tier 3).**

**A note on this facility.** Northgate is a *fictional, composite* facility used only for instruction. It is not modeled on, and does not represent, any real utility, control center, or generating station; any resemblance to a specific facility is unintended.

---

## Stage 1 — The facility *(Modules 0–1: pick a real facility; locate the autonomy boundary)*

Northgate Control Center is the operations center for the Northgate Transmission Company, a registered **Transmission Operator (TOP)** and **Balancing Authority (BA)** responsible for a 500 kV and 230 kV footprint spanning several load pockets and three interconnection ties. Northgate operates an Energy Management System (EMS) with SCADA telemetry, a state estimator and real-time contingency analysis, and the protection-coordination records for its substations. Its operators are NERC-certified System Operators working rotating shifts under a shift supervisor.

Northgate has procured a generative-AI operations advisor, **GridAssist**, and intends to deploy it across three functions:

- **F1 — Real-time switching and protection advisory.** During normal switching and during restoration after a disturbance, GridAssist drafts proposed switching orders and reviews protection-setting changes against the coordination study, presenting recommendations to the operator on shift.
- **F2 — Operational advisory.** GridAssist performs anomaly detection on telemetry and produces short-term load-forecast and outage-scheduling recommendations for the next-day plan.
- **F3 — Administrative support.** GridAssist drafts maintenance records, assembles compliance-evidence packages, and generates operator training content.

It is a good spine facility by the Module-0 tests: real and nameable, a genuine must-not-happen consequence, and an AI with a plausible path to that consequence. The three functions also let the same facility sit on *both* sides of the autonomy boundary from Module 1 — F1 crosses into safety-critical operation; F3 does not.

> **Artifact 1A — Facility profile (established in orientation).**
> **Facility:** Northgate Control Center (TOP/BA). **Controlled process:** bulk-electric transmission, 500/230 kV. **Deterministic infrastructure:** EMS/SCADA, state estimator, protective relaying, RTUs/PLCs at substations. **Human operators:** NERC-certified System Operators + shift supervisor. **GenAI under governance:** GridAssist, functions F1–F3.
> *This profile is the fixed reference for every later stage.*

---

## Stage 2 — The two design bases *(Module 3: consequence-anchored root; bounded adversary envelope; inherit-and-diverge)*

Module 3 establishes that Northgate needs **two** design bases, not one, and that they relate by **inherit-and-diverge**: the AI-DB inherits the facility's consequences from the FC-DB, then diverges in the adversary envelope it must withstand.

The **Facility-Class Design Basis** answers the classic question: what must this facility's protective systems withstand, at what consequence level, before we specify how? Its adversary and challenge envelope is the familiar one — physical, kinetic, operational, and conventional cyber.

> **Artifact 1B — FC-DB adversary / challenge envelope.**
>
> | Envelope class | Examples at Northgate | Governing discipline |
> |---|---|---|
> | Physical | Substation intrusion, sabotage of a 500 kV breaker | Design-Basis Analysis (DBA / DBA-MA) |
> | Kinetic / natural | Equipment failure, severe weather, a conductor fault | DBA / DBA-MA |
> | Operational | Switching misoperation, procedure violation, loss of situational awareness | DBA / DBA-MA |
> | Conventional cyber | SCADA malware, stolen operator credentials, an RTU/PLC firmware exploit | DBA / DBA-MA |
>
> **Consequence statement (inherited by the AI-DB):** a Northgate failure can produce a cascading wide-area outage, protective-system misoperation, major equipment damage, and personnel hazard during switching.

A deliberate point is made here, because it is the one first-time readers stumble on: **conventional cyber threats — SCADA malware, stolen credentials, a PLC exploit — live in the FC-DB, not in a third design basis of their own.** They belong with the facility class because conventional software behavior is *fixed once engineered*: it is bounded at deployment and stays bounded under the same DBA/DBA-MA discipline used for physical and operational threats. What the AI-DB exists to govern is the property those threats do not have — behavior that can be **reshaped after deployment without a code change.**

> **Artifact 1C — AI-DB adversary envelope (GridAssist).**
>
> | Envelope class | Examples at Northgate | Distinguishing property |
> |---|---|---|
> | Model manipulation | An adversarial prompt that induces a plausible but unsafe switching recommendation | Behavior reshaped at inference time |
> | Data poisoning | Corrupted historian or fine-tuning data biases GridAssist's coordination review | Behavior reshaped via training data |
> | Prompt injection | Malicious text in an ingested outage ticket or vendor manual redirects the model | Behavior reshaped via ingested content |
> | Autonomy drift | Operators come to rubber-stamp F1 output; advisory hardens into de-facto authority | Authority reshaped by use over time |
> | AI-native cognitive failure | Hallucinated device, stale-context switching order, reasoning-chain error in a coordination study | Non-determinism; response space not enumerable |

The **seam** between the two — everything the AI-DB inherits from the FC-DB, and the single axis on which it diverges (*deterministic-and-fixed-once-engineered* versus *adaptive-and-reshapable-after-deployment*) — is the concept the whole course is built to teach, and it is the thing the capstone will require the learner to demonstrate.

---

## Stage 3 — Cognitive failure modes on this facility *(methodology thread; developed in OT-02)*

The methodology applies the seven-part cognitive-error taxonomy to GridAssist. The value of doing it on Northgate is that the **same taxonomy produces very different stakes on F1 than on F3.**

> **Artifact 2 — Cognitive-error mapping (selected).**
>
> | Cognitive error | On F1 (switching / protection) | On F3 (documentation) |
> |---|---|---|
> | Factual error | Wrong device rating cited in a switching order → misoperation | Wrong date in a maintenance record → clerical fix |
> | Hallucination | A breaker or relay that does not exist is referenced in a step | A fabricated citation in a training slide |
> | Reasoning-chain failure | Coordination-study logic skips a contingency → miscoordination | Weak argument in a narrative → editorial fix |
> | Context misinterpretation | Applies a normal-config order during an abnormal switching state | Misreads the audience of a memo |
> | Knowledge-boundary violation | Advises outside its validated operating domain during restoration | Answers an HR question it should refuse |
> | Temporal-reasoning error | Uses a stale system state after topology changed | Cites a superseded procedure revision |
> | Compound / interaction error | Stale state + hallucinated device + skipped contingency compound into a cascading recommendation | Multiple small errors in a low-stakes draft |

The lesson the facility makes concrete: **the taxonomy does not change with consequence, but the acceptance criteria for each error type must** — and that is what the tiered model formalizes next.

---

## Stage 4 — Hybrid quality assurance on this facility *(methodology thread; developed in OT-03)*

Northgate makes the hybrid-QA split tangible. The **deterministic infrastructure layer** — EMS/SCADA, the state estimator, protective relays, RTUs — is bounded and amenable to the formal and conventional verification the facility already performs. The **cognitive AI layer** — GridAssist — is non-deterministic and cannot be exhaustively enumerated; it must be characterized empirically.

> **Artifact 3 — Hybrid QA layer split.**
>
> | Layer | Northgate elements | Assurance approach |
> |---|---|---|
> | Deterministic infrastructure | Protection logic, interlocks, EMS state estimator, RTU/PLC logic | Formal verification + conventional V&V; behavior fixed once engineered |
> | Cognitive AI | GridAssist F1–F3 recommendations | Empirical cognitive-error assessment, statistically bounded and scaled to tier; adversarial evaluation |
>
> **Governing rule:** formal methods verify the floor *beneath* the AI; they do not and cannot fully assure the AI layer. Neither approach alone is sufficient for a function above the Bright Line.

---

## Stage 5 — Tiered criticality classification *(Module 4: place the AI in a tier against inherited consequences)*

Now the three functions diverge. Each is classified by the **severity of the consequence a cognitive error could produce** — not by which security zone it happens to sit in.

> **Artifact 4 — Tier-classification worksheet.**
>
> | Function | Consequence of cognitive failure | Tier / level | 62443 SL | 61508 SIL | NERC CIP-002 | Bright Line |
> |---|---|---|---|---|---|---|
> | **F1** switching / protection | Cascading outage, protection misoperation, equipment damage, personnel hazard | Highest — Tier 1 | SL 3–4 | SIL 3–4 | High Impact | **Above** — Command Broker mandatory |
> | **F2** operational advisory | Economic loss, degraded service, bounded reliability impact | Middle — Tier 2 | SL 2 | SIL 1–2 | Medium Impact | **Above** — Command Broker mandatory |
> | **F3** administrative | Correctable inconvenience, rework | Lowest — Tier 3 | SL 1 | below SIL | Low Impact | **Below** — limited autonomy permitted with monitoring and human review |
>
> **Classification owner:** the Northgate Asset Owner/Operator, considering foreseeable misuse and scope creep — e.g., F2's outage-scheduling output being quietly relied upon to pre-stage F1 switching, which would pull it upward and require reassessment.

The worksheet is where a learner first sees that **one facility can legitimately span the whole spectrum**, and that the classification is a consequence judgment the AOO owns.

---

## Stage 6 — The Bright Line and the Command Broker *(Module 4: what enforces the line in operation)*

F1 is above the Bright Line, so it is governed by an **absolute constraint** rather than by graded acceptance criteria: GridAssist may analyze, synthesize, and recommend a switching order or a protection change — **it may not command one.** Every action that affects the controlled process passes through a human decision-maker who evaluates the recommendation and authorizes or rejects it.

> **Artifact 5A — Bright Line determination for F1.**
> Placement is assessed against F1's **inherent, unmitigated** ability to reach the cascading consequence — GridAssist's capacity to influence a switching or protection action *before any safeguard is added.* Because that inherent ability reaches a Highest-tier consequence, F1 is above the line. Critically, adding an independent backstop (operator verification, a protection interlock) **does not move F1 to Middle**: backstops are obligations that *flow from* the Highest-tier placement, never evidence that can reclassify F1 downward. This closes the loophole in which a team could build a safeguard and then argue for reduced assurance.

The human who stands in that position is the **Command Broker**. At Northgate it is the certified System Operator on shift, backed by the shift supervisor — but the certification alone is not the qualification. The Command Broker function adds specific competencies and, crucially, the authority and the disposition to reject GridAssist when it is wrong.

> **Artifact 5B — Command Broker specification for F1.**
> **Who:** the on-shift NERC-certified System Operator, with a documented Command Broker qualification; the shift supervisor as escalation.
> **Competencies:** recognition of the AI-DB failure modes in Artifact 1C; ability to independently reconstruct a switching or coordination decision without relying on GridAssist; awareness of automation complacency as a personal failure mode.
> **Authority:** explicit, exercised authority to reject or override any GridAssist recommendation, with no adverse consequence for a well-reasoned rejection.
> **Currency:** a recurring adversarial tabletop program that injects hallucinated devices, stale-state orders, and manipulatively-framed-but-accurate recommendations.
> **Decision-context record (retained for every intervention):** governing policy invoked, the inherited consequence at stake, the triggering condition, and the rationale for authorizing or rejecting — so that a reviewer can later understand *why* the Broker acted, not merely that they did.

The decision-context record is included deliberately: it is what makes the Broker's judgment **auditable and defensible**, and it is the mechanism the course leans on where a consequence cannot be reduced to a purely deterministic check — an accurate recommendation framed to induce an unsafe decision, for example.

---

## Stage 7 — Sector application *(Module 5 / bridge: map the tiered result into the sector's vocabulary)*

The bridge maps Northgate's tiered result into the **bulk-electric regulatory vocabulary** without changing the underlying consequence logic.

> **Artifact 6 — Regulatory mapping for Northgate.**
> **F1 →** NERC CIP-002 High Impact BES Cyber System; real-time obligations under the TOP and IRO standard families. **F2 →** Medium Impact. **F3 →** Low Impact. Command Broker qualification hooks into **CIP-004** personnel-and-training requirements; provenance and procurement obligations for GridAssist hook into the AOO's existing supply-chain and **CIP-013** machinery.
> *The point to extract:* the **tier drives the obligation set; the CIP category is the vocabulary it is expressed in.**

---

## Stage 8 — Track divergence *(OT track and Policy track — same facility)*

The shared core ends here and the two tracks diverge — but on the **same facility**, which is what lets a policy learner and an OT learner discuss Northgate across the table.

> **Artifact 7A — OT-track deliverable for Northgate.**
> The engineering package: the completed FC-DB and AI-DB (Artifacts 1B/1C), the hybrid-QA assessment (Artifact 3), tier acceptance criteria (Artifact 4), the Bright Line determination and Command Broker interface specification (Artifacts 5A/5B), and the provenance-documentation requirements GridAssist's vendor must satisfy.

> **Artifact 7B — Policy-track deliverable for Northgate.**
> The governance package: the duty-of-care argument for qualifying the Command Broker before any regulator requires it; the insurability case for characterized-and-auditable risk; procurement and provenance requirements; the NERC standard mapping (Artifact 6); and a **deployment-model note.** The last matters at Northgate specifically: whether GridAssist is consumed as a commercial AI-as-a-Service offering or is self-hosted and locally tuned changes *where* the provenance and lifecycle-assurance obligations sit — self-hosting **relocates** them onto Northgate rather than removing them.

---

## Stage 9 — Capstone (both design bases required) *(the gate the shared rubric grades)*

The capstone asks the learner to produce, for Northgate, an integrated governance record that satisfies **both** design bases and, above all, addresses the **seam** between them. It is not sufficient to write a strong FC-DB and gesture at the AI, or to write a sophisticated AI-DB that forgets the facility whose consequences it inherits. Both are required, and the relationship between them is the graded object.

> **Artifact 8 — Capstone deliverable structure (and the acceptance gate).**
> A complete Northgate submission contains:
> 1. the **FC-DB** with its consequence envelope;
> 2. the **AI-DB** with its adversary envelope, shown *inheriting* the FC-DB consequences and *diverging* on the deterministic-versus-reshapable axis;
> 3. a **tier classification** for each GridAssist function with rationale and a scope-creep watch;
> 4. a **Bright Line determination** assessed on inherent capability, with backstops named as obligations rather than reclassification levers;
> 5. a **Command Broker specification** including the decision-context record; and
> 6. the **track-appropriate** governance or engineering artifacts.
>
> **The gate:** a submission that addresses only one design basis — however sophisticated — does not pass. Demonstrating the inherit-and-diverge relationship *at the seam* is the practical demonstration of mastery the course is built to produce.

---

## Instructor note

The worked example is calibrated so that **Stage 9 is what a strong submission looks like** and Stages 1–8 are the scaffolding a learner should be able to reconstruct on a new facility of their own. The most common failure mode to watch for is exactly the one the capstone gate is designed to catch: a learner treats one design basis as sufficient — usually a confident FC-DB with the AI-DB reduced to a paragraph, occasionally the reverse from a policy-leaning learner. When that happens, return them to Stage 2 and Artifact 1C, because the miss is almost always **at the seam** rather than in either design basis taken alone.

Two further calibration points. First, the tier worksheet (Artifact 4) is where most classification disputes surface; encourage learners to argue *consequence, not security zone*, and to defend the scope-creep column explicitly. Second, the Bright Line determination (Artifact 5A) is where the sharpest learners will try to argue a backstop down into a lower tier; that argument should be marked wrong every time, because permitting it would let a facility engineer its way out of the assurance its inherent consequences demand.

---

## What this shows an instructor *(the same five checks the shared rubric applies)*

- **Both design bases present** — the gate: an answer that stops at the FC-DB (harden the control center) and never builds the AI-DB for GridAssist has missed the point, exactly as the rubric says.
- **Consequence-anchored root** — look for a one-sentence, concrete must-not-happen ("a cascading wide-area outage from a bad F1 switching action"), not a category ("a cyber incident").
- **Inherit-and-diverge** — look for the AI-DB inheriting the outage consequence and diverging to a model-manipulation / data-poisoning / autonomy-drift envelope, not reusing the physical one.
- **Bright Line and tier** — look for an observable line (F1 may recommend but not command) and tiers justified by *reach to the consequence* (F1 Highest, F2 Middle, F3 Lowest), not asserted.
- **Enforcement** — look for a Command Broker independent of the AI: a qualified operator with real authority to reject and a retained decision-context record, not a human who merely watches a screen.

The same five checks work whether the learner picked a substation, an LNG terminal, a water plant, or a data center. The sector changes; the method — and the way you grade it — does not.

---

## Further reading

- **Bulk-electric / energy sector framework (DBA-EN-SF)** — the sector application this facility is drawn from, including the bulk-electric consequence profiles and NERC mapping. *(Series document; see the modules.)*
- **ISA Parent Framework / Tiered Assessment Framework** — the tiered assessment model, cognitive-error taxonomy, hybrid-QA methodology, and the Bright Line and Command Broker definitions the worked example instantiates. *(Series document; see the modules.)*
- **Command Broker Implementation Guide** — competency, qualification, and tabletop-program detail behind Artifact 5B. *(Series document; see the modules.)*
- **NERC CIP-002** — BES Cyber System categorization, the vocabulary Artifact 6 maps into. See [`reading-list.md`](reading-list.md).
- **U.S.–Canada Power System Outage Task Force, *Final Report on the August 14, 2003 Blackout*** — the canonical cascading-failure case that motivates F1's Highest-tier placement.

---

*Changelog*

- *v1.0 — Added as the course's persistent worked example (R-01), threaded Modules 0–1 → capstone. Reconciled from the Northgate drop-in draft. Companion to the water-treatment worked example, which remains the compact second-sector model answer.*
