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

## Course Notes (the supporting-reference apparatus)

A reading list is a burden handed to the student. A **Course Note** is an excerpt placed in context, under the heading it serves — the handout a professor gives out when the material is too new for a textbook.

Notes live in `resources/course-notes/`, one file per Note, and are cross-linked from the module unit they support. They are not woven into the module text: the module carries the frame and the argument; the Note carries the source.

- **Numbering is module-scoped:** `M<NN>-CN-<NN>` (e.g. `M03-CN-01`). Filename: `M03-CN-01-short-slug.md`.
- **The module points to the Note** with a callout at the heading it supports, not with a footnote and not with a bare link in a list.
- **Every Note carries the same seven fields, in this order:**
  1. **Anchor** — the module, unit, and heading it attaches to. A Note without an anchor does not belong in the collection.
  2. **Source and locator** — full citation with a precise locator, resolving to a durable target: a `.gov` URL, the publications Git mirror, or a DOI. **Never a cloud-drive link.**
  3. **Provenance and use** — published / prepublication / working note, *and* the reproduction status: public domain, licensed, or **characterize only**. Fill this field *before* pasting the excerpt.
  4. **Excerpt** — verbatim and bounded. Where reproduction is not permitted (a paid standard, for example), this field is replaced by a **Characterization**: what the clause requires, in our own words, with the clause number so the learner can go read it.
  5. **What it establishes** — what the source settled, inside its own domain, on its own terms.
  6. **Where the AI case departs** — the payload. What has no counterpart on the AI side, and what the course therefore has to construct. *If a Note cannot fill this field, it does not belong in the course.*
  7. **Carry-forward** — one sentence the learner takes into the next section, phrased so it can be checked against the capstone rubric.

**Excerptability is a selection criterion.** Federal regulations, regulatory guides, NUREGs, and NIST material are U.S. government works and may be reproduced freely. Paid consensus standards (IEC 62443, IEEE, ISO) may **not** be excerpted — those Notes run on characterization and citation only.

**The reading list is the index.** `resources/reading-list.md` names the external foundation; where a source has a Note, the list points into it.

## File and folder naming

- Module folders: `module-N-slug` (e.g., `module-3-design-basis-methodology`).
- Content units within a module carry a two-digit ordering prefix: `00-`, `01-`, `02-` … in teaching order.
- The `90-` prefix is reserved for dated/volatile snapshot units (see the Module 1 split).
- Every module folder has a `README.md` giving the module's purpose and unit order.
- Slugs are lowercase, hyphenated, American English spelling.

## Versioning

- The whole course carries a single version at the repository root (README and course-map), currently **1.0**.
- Individual units do not carry their own version numbers in this repository; the course version governs.
- When a unit changes materially, note it in a short changelog at the bottom of that unit rather than renaming the file.

## Branch parity

The two branches (`ot-track`, `policy-track`) analyze the **same capstone facility**. They differ only in the deliverable: OT produces a design basis or assessment; policy produces a governance and consequence analysis. Keep unit counts and depth roughly balanced so neither branch feels like the afterthought.

## Sector neutrality in the core

Nothing in the core (Modules 0–4) should assume the learner's sector is energy. Energy, nuclear, and data-center material appears as **worked examples**, clearly labeled as such, and lives mainly in Module 5 and the branches. The core teaches the method sector-agnostically.

## Learning objectives

Every module README opens with a **Learning Objectives** block, placed immediately after the module title, phrased as behavioral outcomes: "After this module, a student will be able to…" followed by three or four objectives.

Behavioral phrasing is deliberate — it makes the pedagogical intent legible to a reviewer and gives the author a concrete target to write each unit against. Objectives should be things a student can *do* (derive, distinguish, place, analyze, argue), not things they will "understand" or "be aware of." Keep them to a short list; objectives are one of the few places in this course where a list is the correct form.
