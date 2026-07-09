# Design Basis for AI Governance
## Reviewer's Preview — v1.0 (complete course)

*A self-paced course in consequence-anchored governance for critical infrastructure.*
Timothy E. Roxey, Eclectic Technologies

---

## What you're looking at, and what I'd value from you

This is a complete, self-paced course that teaches a method — the engineering **design basis**, borrowed from nuclear safety — applied to the governance of AI in critical infrastructure. It lives on GitHub as self-taught modules.

I've pulled together just enough here to convey the layout and the pedagogical intent, not the finished content. Most modules are still scaffolding; one is written out so you can judge depth and voice. What I'd most value your eyes on:

- Is the **architecture** sound as a learning progression — core, then a branch, then an applied capstone?
- Are the **learning objectives** the right targets, and are they pitched at the right level?
- Does the **two-design-bases** distinction (the intellectual core, in Module 3 below) land clearly, or does it need more scaffolding before students meet it?
- Is the **capstone** rigorous enough to be worth a student's time, and is the "both design bases required" gate the right bar?

## The premise

Most of critical-infrastructure protection has operated without a formal design basis. The National Infrastructure Protection Plan never required any sector but nuclear to define one. The course exists to close that gap — to teach any practitioner, in any sector, to reason about a facility the way a design-basis engineer would: start from the consequence that must not happen, bound the adversary, and tier criticality. The student supplies the sector; the course supplies the method.

## How the course is structured

```
   Module 0  ─ Orientation + pick your sector
      │
   [ CORE ]   Modules 1–4  (everyone, sector-agnostic method)
      │
   [ BRIDGE ] Module 5  (sectors, applicability, facility classes)
      │
      ├──►  OT track      (produce a design basis / assessment)
      └──►  Policy track  (produce a consequence & governance analysis)
      │
   [ CAPSTONE ] one facility in the student's sector — same target, branch-specific deliverable
```

Three design choices worth flagging:

**Sector is chosen up front and threads through everything.** Each core module ends with a short *In Your Sector* reflection, so the student is applying the method to their own sector from Module 1 — not waiting until the end. A student whose sector has no prebuilt instruments (water, comms, transportation, health, finance) walks the same core and their capstone becomes *derive the facility class for my sector*, which is the more valuable outcome anyway.

**One method, two branches, same capstone target.** The OT and policy branches analyze the *same* facility; only the deliverable differs. OT produces a design basis; policy produces a consequence-and-governance analysis.

**The course teaches two design bases, not one** — see Module 3. This is the distinction the whole course turns on, and the capstone won't pass without both.

## The learning arc

The full set of module objectives, so you can see the progression:

### Core

**Module 0 — Orientation and the Founding Gap.** Explain the founding gap; select a sector and assess whether a design-basis discipline exists in it; state what the course will ask them to produce.

**Module 1 — What We're Actually Governing.** Distinguish generative, agentic, and autonomous AI, and why conflating them corrupts governance reasoning; locate the boundary where autonomy crosses into safety-critical operation; recognize that boundary as the course's target.

**Module 2 — Consequence-Driven Thinking.** Contrast vulnerability-first and consequence-first reasoning; trace the CCE / CIE lineage and its engineering provenance; reframe a sector problem in consequence-first terms.

**Module 3 — Design Basis Methodology.** Define and derive a design basis; explain DB → DBA → DBA-MA; **distinguish the two design bases (facility-class and AI) and the inherit-the-root / diverge-on-the-envelope relationship**; identify the Bright Line as the seam between them.

**Module 4 — The Governance Primitives (the AI-DB toolkit).** Explain Bright Line Criteria as the seam; place an AI system in a criticality tier measured against inherited consequences; describe how the Command Broker enforces the Bright Line in operation.

### Bridge

**Module 5 — Sectors, Applicability, and Facility Classes.** Define a facility class and the strategic-significance boundary; apply the four-filter applicability gate; map the student's own sector onto the method; reason about a genuinely open question (OI-O5 / OI-G9) without a supplied answer.

### Branches

**OT track.** Derive both design bases as engineering artifacts; apply TAF tiering, IEEE V&V, and 62443 mapping; place the Bright Line and Command Broker in a real architecture; explain Local Sovereignty through the Aurora Disruptor case.

**Policy track.** Produce a consequence-and-governance analysis addressing both design bases; analyze AI-enabled influence and market-manipulation cases; apply the three deterrence forms; argue the standards gap for a sector.

### Capstone

For a real facility, produce both design bases (OT) or a governance analysis reckoning with both (policy); demonstrate inherit-and-diverge on a real target; meet the shared rubric's both-DBs-present gate.

---

## A module in depth: the two design bases

*This is the one place I've written the content out, because it's the distinction the course turns on and the part I'd most want your reaction to. It sits at the end of Module 3.*

By this point a student knows what a design basis is: a discipline that anchors on the consequences that must not happen and bounds the adversary you will defend against. This unit makes a claim that is easy to miss and expensive to get wrong: **in any facility where AI operates, there are two design bases, not one.** Same method, two artifacts.

**The facility-class design basis (FC-DB)** governs the facility. Its consequence anchor is physical and operational — the releases, failures, and losses that must not happen. Its adversary envelope is physical, kinetic, and operational.

**The AI design basis (AI-DB)** governs the AI operating in or over that facility. It is a design basis in exactly the same sense, but its object is the model, not the machinery.

The reason the AI cannot simply be folded into the facility's design basis is this: **the two share a consequence root but diverge on the adversary envelope.** The AI-DB *inherits* the facility's must-not-happen consequences — the AI's failure matters precisely because it can reach the physical consequence set the FC-DB already named — and may *extend* that set with consequences the physical basis never contemplated (an integrity consequence, an influence consequence, a loss of trustworthy state with no kinetic equivalent). But the AI's adversary envelope is a different animal: model manipulation, data poisoning, prompt injection, autonomy drift — the moment the agentic system crosses into safety-critical territory. A facility hardened against every physical threat in its envelope can still be driven into its own forbidden consequences through an envelope its FC-DB never examined.

Same consequence root, different adversary envelope, different reachability — therefore two design bases.

The two meet at a seam with a name: the **Bright Line** — the boundary, defined in the AI-DB, that keeps the AI from reaching the consequences the FC-DB says must not happen. Read that way, the governance primitives of Module 4 are not a grab-bag; they are the machinery of the second design basis. Criticality tiering is *how much does this AI's failure matter, measured against the inherited consequences.* The Command Broker is what enforces the Bright Line in live operation.

| | Facility-class DB (FC-DB) | AI design basis (AI-DB) |
|---|---|---|
| Object | the facility / facility class | the AI operating in it |
| Consequence anchor | physical & operational must-not-happens | **inherited** from FC-DB; may extend |
| Adversary envelope | physical, kinetic, operational | model, data, prompt, autonomy |
| Key boundary | the facility threat envelope | the **Bright Line** — seam to the FC-DB |

---

## How students are assessed

The capstone asks the student to pick a real facility in their sector. Both branches analyze the same facility; the deliverable differs. Crucially, **both design bases are required of both branches** — OT *derives* the FC-DB and the AI-DB and shows the Bright Line between them; policy *analyzes* both and the governance gap of each. A capstone that produces only one design basis does not pass, regardless of how well that one is done. That gate is deliberate: producing an FC-DB and calling it finished is exactly the incomplete answer the course exists to prevent.

A shared rubric checks the both-DBs gate first, then grades the fundamentals: consequence-anchored root, the inherit-and-diverge relationship, bounded adversary envelopes correctly distinguished, criticality tiering against inherited consequences, and genuine sector fit.

---

## The questions I'd value your feedback on

1. Does the progression hold — is there a rung missing between the core method (Modules 2–3) and asking a student to *produce* a design basis at the capstone?
2. Are the learning objectives measurable enough to build assessments around, or too abstract?
3. Is the two-design-bases distinction clear on first read, or does it need a worked example before the abstract statement?
4. Is a single self-paced course trying to serve both OT and policy audiences a strength or a fault line? Would you split them?
5. What would you need to see before you'd consider using a module like this in your own teaching?

*Thank you for reading a work in progress. Every one of these decisions is still movable.*
