# Module 3 — Design Basis Methodology

## Learning Objectives

After this module, a student will be able to:

- Define a design basis and derive one from a consequence-anchored root and a bounded adversary envelope.
- Explain the DB → DBA → DBA-MA progression.
- Distinguish the two design bases — facility-class (FC-DB) and AI (AI-DB) — and explain the inherit-the-root / diverge-on-the-envelope relationship between them.
- Identify the Bright Line as the seam that connects the two.
- Reconcile the two design bases as a managed interface rather than a hierarchy, and locate the arbitration point at which their collisions are settled.


The crown jewel. What a design basis is, borrowed from nuclear safety, and how you derive one — the consequence-anchored root and the bounded adversary envelope. DBA into DBA-MA.

This module teaches design basis as a **method**, then instantiates it **twice**: once for the facility (the FC design basis) and once for the AI operating in it (the AI design basis). The two-design-bases distinction is the keystone of the whole course — a student who leaves thinking there is only one design basis has missed the point.

## Units, in order

1. `00-what-is-a-design-basis.md` — the concept, from nuclear safety
2. `01-consequence-anchored-root.md` — anchoring on consequence
3. `02-bounded-adversary-envelope.md` — bounding the adversary
4. `03-db-to-dba-to-dba-ma.md` — design basis to DBA to military-action DBA
5. `04-two-design-bases.md` — **the FC design basis and the AI design basis: inherit the consequence root, diverge on the adversary envelope** *(written out, not stubbed)*
6. `05-merging-the-two-design-bases.md` — **how the two are developed together and what arbitrates when they collide: the managed interface, not a hierarchy** *(written out, not stubbed)*
7. `in-your-sector.md` — closing reflection

## Note to the author

Unit 04 is the seam that connects this module to Module 4 (the AI design basis's toolkit) and sets the two-DB requirement the capstone enforces. Units 00–03 build the method; unit 04 is where it gets used twice. Keep the *inherit-and-diverge* relationship loud: shared consequence root, different adversary envelope, therefore two design bases.

Unit 05 is where the architecture becomes a method. Unit 04 says the two bases meet; unit 05 says how they are built together and what settles it when they collide. Two things must not drift: *inheritance is of consequence, not authority* (say it in 04, build on it in 05), and the **Command Broker is the arbiter of design basis collisions** — the runtime discharge of an interface obligation the nuclear precedent discharges through a review board. Unit 05 also carries the operational payoff the course had been leaving implicit: the AI-DB is the source document from which the contract requirements and the acceptance test plan are derived. That claim propagates into the capstone rubric — an AI-DB that cannot generate an acceptance test plan is not yet a design basis.
