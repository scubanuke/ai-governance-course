# OT Deliverable: Facility-Class and AI Design Bases

> **Part of:** Capstone / OT

This is the OT capstone. You will produce, for the facility you selected, **both** design bases as engineering artifacts — the facility-class design basis and the AI design basis — and show the Bright Line seam between them. A deliverable with a facility design basis but no AI design basis does not pass; the two-design-bases result is the thing the whole course was built to make you produce. Everything you learned in the OT branch (units 00–05) is a tool for this deliverable.

## Required components

**1. The facility-class design basis (FC-DB).** Derive the facility's class and its design basis using the method from Module 3 and OT unit 00. State the **consequence-anchored root** — the physical and operational must-not-happens — in concrete terms, and bound the **physical/operational adversary envelope** the facility is engineered to withstand. Make at least one bound *quantitative* in the sense of OT unit 00: a numeric target anchored to a standard you must already meet or an empirical event, with a stated acceptance criterion. If your sector has no prebuilt facility class, this is where you carve one, using the four-filter applicability gate to establish that your facility is in scope.

**2. The AI design basis (AI-DB).** For the AI operating in or over the facility, apply inherit-and-diverge. **Inherit** the FC-DB's consequences — the AI's failure matters because it can reach the same physical outcomes — and **extend** with any AI-specific consequences (loss of trustworthy state, integrity failures with no kinetic equivalent). Then bound the **AI-facing adversary envelope**: model manipulation, data poisoning, prompt injection, autonomy drift — an envelope entirely unlike the facility's physical one. Show explicitly that the consequence root is shared and the envelope diverges; that is the argument for why the AI needs its own design basis rather than being folded into the facility's.

**3. The Bright Line seam.** Draw the seam that joins the two. State where the **Bright Line** falls — the boundary, defined in the AI-DB, past which the AI's action could reach the inherited consequence — and make it *bright* (observably crossed or not). Place the AI in a **criticality tier** measured against the inherited consequences, and specify what the **Command Broker** must enforce at runtime to hold the line, at architecture level (the proposer–gate boundary, its tested envelope, and how a change to the envelope would be requalified offline).

## How to build it, and what "good" looks like

Work in the order the components are listed — the FC-DB first, because the AI-DB inherits its root. Resist the urge to start from the AI; an AI-DB built before its facility's consequences are named has nothing to inherit and usually re-invents a weaker anchor.

Bring the branch's assessment machinery to bear where it strengthens the artifact. Use **TAF tiering** (OT unit 01) to justify the criticality tier and the assessment depth it obligates. Use the **IEEE V&V** split (unit 02) to say which parts of the AI system are deterministic infrastructure you would formally verify and which are the cognitive layer you would assess statistically — and name the provenance and evidence you would require. Use the **62443 mapping** (unit 03) to position your design basis against the standard your sector already answers to, naming at least one foundational-requirement gap the AI's non-determinism opens. And where a consequence is severe enough, ask the **Local Sovereignty** question from unit 05: is there a minimal, passive, physically grounded backstop that would hold even if every digital system above it were compromised? A capstone that includes a credible Disruptor-style backstop for its worst consequence is the strongest form of this deliverable.

A strong OT capstone reads like something a reviewer could act on: the consequence is concrete, the two envelopes are genuinely different, the Bright Line is observable, the tier is justified rather than asserted, and the Command Broker is placed in a real architecture rather than described in the abstract.

## Common failure modes to avoid

The disqualifying failure is producing only the FC-DB and stopping — an admirable facility design basis with no AI design basis is exactly the incomplete answer the course exists to prevent. The next most common are subtler: re-inventing a fresh consequence anchor for the AI instead of inheriting the facility's; reusing the physical adversary envelope for the AI instead of bounding the real AI-facing one; and describing a Command Broker that quietly depends on the AI behaving correctly, which is no enforcement at all. Check your draft against each before you consider it done, then take it to the shared rubric.
