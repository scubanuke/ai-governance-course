# Select Your Facility

> **Part of:** Capstone

This is where everything you have carried since Module 0 comes to rest on a single, real target. You picked a sector at the start; you mapped it onto the method at the bridge; you chose a branch. Now you choose the **one facility** you will apply the whole method to. Both branches — OT and policy — analyze the *same* facility; only the deliverable differs. Choose well, because you will live inside this choice for the rest of the capstone.

## What makes a good capstone facility

A workable facility sits between two failure modes. Too **trivial**, and the method has nothing to bite on — there is no must-not-happen consequence worth a design basis, and the exercise becomes a paperwork drill. Too **unbounded**, and you cannot finish — "the electric grid" or "the financial system" is not a facility, it is a sector, and it has no single design basis you could actually derive. Aim for the middle: a facility concrete enough to name and bounded enough to analyze in the time you have.

Three tests tell you that you have found it.

**It is real and nameable.** A specific plant, terminal, station, control center, clearing system, or data center — one you can picture and, ideally, one whose real characteristics you know. Abstraction is where design-basis reasoning dies; a named facility keeps you honest.

**It has a genuine must-not-happen consequence.** There is an outcome at this facility that would be catastrophic and, ideally, irreversible — a release, a loss of an essential service, a break in institutional trust. If you cannot state that consequence in one concrete sentence, the facility is too trivial for the capstone. This sentence is the consequence-anchored root you built toward in Module 3, and it is the anchor for everything that follows.

**An AI plausibly operates in or over it.** The course exists for the facility where AI touches a safety-critical function. Your facility needs a real or realistic AI presence — an optimizer, a controller, an advisory system, an autonomous agent — with some path toward that must-not-happen consequence. If no AI could plausibly reach the consequence, there is no second design basis to build, and the capstone loses its point.

## One facility, both design bases

Whichever branch you are on, hold the course's central result in view from the moment you choose: the facility where an AI operates has **two** design bases, and your capstone must address both. Pick a facility rich enough to support that. You will need to be able to name the facility's own physical or operational consequences *and* to reason about how the AI operating there could reach them through a different, AI-facing adversary envelope. A facility with a real consequence but no meaningful AI, or an interesting AI with no serious consequence, will strand you with only half a capstone.

## If your sector has no prebuilt facility class

Recall the promise from Module 0 and the bridge: you do not need a facility class to already exist for your sector. If one does, your capstone applies and tailors it. If none does — the common and more valuable case — your capstone *is* the carve: derive the facility class for your chosen facility from the consequence root up, using the energy examples as models. That is not a lesser path. It is the method doing exactly what it was built to do, and it makes for the stronger capstone.

## Write down your selection

Before moving to your branch's deliverable, commit the choice to paper:

- **The facility:** the specific, named facility (and its sector).
- **The must-not-happen consequence:** the one concrete sentence that will anchor both design bases.
- **The AI in play:** what AI operates in or over the facility, and the rough path by which its failure or subversion could reach the consequence.
- **Inherit or derive:** whether a facility class already exists for this category, or you will derive one.

That four-part statement is the shared foundation of both the OT and the policy deliverables. Take it into whichever unit matches your branch — `01-ot-deliverable-design-basis.md` or `02-policy-deliverable-governance-analysis.md` — and build.
