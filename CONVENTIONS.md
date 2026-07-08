# Authoring Conventions

These conventions keep the repository predictable as content gets authored. They encode the structural decisions made during course design.

## The "In Your Sector" recurring block

Every **core module** (0 through 4) ends with a short reflection block named **In Your Sector**. It is the same block, same name, same shape, every time — so the learner recognizes it and the repository reads consistently.

Each core module folder contains an `in-your-sector.md` file. The block is short by design: it asks the learner to take what the module just taught and say something concrete about the sector they picked at Module 0. This keeps the chosen sector alive from the very first module rather than dormant until Module 5.

A reusable template lives at `resources/in-your-sector-template.md`. Each module's instance is filled from it.

## The Module 1 split

Module 1 is **physically split into two files** so annual upkeep never touches the durable core:

- `00-concept-autonomy-boundary.md` — the **stable** conceptual unit. Carries the durable claim: autonomy crossing into safety-critical is the governance-relevant boundary. This should rarely change.
- `90-snapshot-2026-examples.md` — the **dated snapshot** unit. Holds the current (2026) generative/agentic/autonomous examples. The `90-` prefix marks it as the volatile, refresh-on-a-cycle unit.

The concept file **references** the snapshot; it does not weave the examples in. Annual review edits only the snapshot. This rule generalizes: any unit that will age faster than the method gets a `90-` sibling so the core stays clean.

## File and folder naming

- Module folders: `module-N-slug` (e.g., `module-3-design-basis-methodology`).
- Content units within a module carry a two-digit ordering prefix: `00-`, `01-`, `02-` … in teaching order.
- The `90-` prefix is reserved for dated/volatile snapshot units (see the Module 1 split).
- Every module folder has a `README.md` giving the module's purpose and unit order.
- Slugs are lowercase, hyphenated, American English spelling.

## Versioning

- The whole course carries a single version at the repository root (README and course-map), currently **0.1**.
- Individual units do not carry their own version numbers in this skeleton; the course version governs.
- When a unit changes materially, note it in a short changelog at the bottom of that unit rather than renaming the file.

## Branch parity

The two branches (`ot-track`, `policy-track`) analyze the **same capstone facility**. They differ only in the deliverable: OT produces a design basis or assessment; policy produces a governance and consequence analysis. Keep unit counts and depth roughly balanced so neither branch feels like the afterthought.

## Sector neutrality in the core

Nothing in the core (Modules 0–4) should assume the learner's sector is energy. Energy, nuclear, and data-center material appears as **worked examples**, clearly labeled as such, and lives mainly in Module 5 and the branches. The core teaches the method sector-agnostically.

## Learning objectives

Every module README opens with a **Learning Objectives** block, placed immediately after the module title, phrased as behavioral outcomes: "After this module, a student will be able to…" followed by three or four objectives.

Behavioral phrasing is deliberate — it makes the pedagogical intent legible to a reviewer and gives the author a concrete target to write each unit against. Objectives should be things a student can *do* (derive, distinguish, place, analyze, argue), not things they will "understand" or "be aware of." Keep them to a short list; objectives are one of the few places in this course where a list is the correct form.
