# Design Basis for AI Governance
### A self-paced course in consequence-anchored governance for critical infrastructure

**Version 1.0 — complete course**
Author: Timothy E. Roxey, Eclectic Technologies

---

## What this is

A self-paced set of instruction modules that teaches a method, not a catalog. The method is the engineering **design basis** — the discipline nuclear safety has used for decades — applied to the governance of AI in critical infrastructure. By the end you should be able to take a real facility in your own sector and reason about it the way a design-basis engineer would: starting from consequence, bounding the adversary, and tiering criticality.

Most of critical-infrastructure protection has operated without this discipline. The course exists to close that gap, one sector at a time, with you supplying the sector.

## How the course is shaped

You walk a common **core**, cross a **bridge** where your chosen sector stops being cosmetic, then pick **one branch** and finish with a **capstone** on a facility you choose.

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
   [ CAPSTONE ] one facility in your sector — same target, branch-specific deliverable
```

## How to use it

1. **Start at Module 0** and pick your sector. That choice threads through everything after it. You do not need a facility class to already exist for your sector — the method teaches you to derive one.
2. **Walk the core in order** (Modules 1 → 4). Each core module ends with a short **In Your Sector** reflection so you are working with your own sector from the very first module, not waiting until the end.
3. **Cross the bridge** (Module 5). Here you learn what a facility class is and how one gets carved, using worked examples from the energy sector, then map your own sector onto the method.
4. **Pick one branch.** OT if you want to *produce* a design basis or assessment; Policy if you want to *produce* a governance and consequence analysis. Same body of ideas, different lens.
5. **Do the capstone.** Choose a real facility in your sector. Both branches analyze the *same* target; the deliverable differs by branch. A shared rubric grades the fundamentals.

## Who this is for

Senior technical staff, policy practitioners, and engineers working in or around critical infrastructure who need to reason rigorously about AI in operational and institutional settings. The core assumes general technical literacy; the branches go deeper in their respective directions.

## A note on the sector question

When you pick your sector at Module 0, the course does not require that prebuilt facility-class instruments already exist for it. The energy, nuclear, and data-center material in this course are **worked examples**, not the only supported paths. If your sector is water, communications, transportation, health, or finance, you walk the same core, study the energy carve-outs as models, and your capstone becomes *derive the facility class for a facility in my sector*. That is the more valuable outcome, and it is what the method is actually for.

## Status and roadmap

This is **v1.0**, a complete static repository — every core module, the bridge, both branches, and the capstone are fully written, with a glossary and reading list in `resources/`. Sector selection and progress are handled by reading the routing above and working through the folders in order.

A later version is planned to become a **live form** that gathers a student's progress and, on request, produces an email summarizing where they are in the course. The seed for that lives in [`resources/progress-tracker.md`](resources/progress-tracker.md). It is a design placeholder for now, not a working feature.

## Repository layout

| Path | Contents |
|---|---|
| [`course-map.md`](course-map.md) | The full syllabus — every module and unit |
| [`CONVENTIONS.md`](CONVENTIONS.md) | Authoring conventions: the recurring block, the Module 1 split, naming, versioning |
| `core/` | Modules 0–4, the sector-agnostic method |
| `bridge/` | Module 5, sectors and facility classes |
| `branches/ot-track/` | The operational-technology branch |
| `branches/policy-track/` | The policy branch |
| `capstone/` | The applied final project and shared rubric |
| `resources/` | Glossary, reading list, a fully worked example (water), progress-tracker seed |

---

*Design basis is the discipline that makes safety engineering rigorous. This course argues it should make AI governance rigorous too.*

---

## Publish on GitHub Pages

This repository includes a lightweight site (`index.html`) that renders the modules in the browser with a sidebar for navigation. It reads the same Markdown files as their single source of truth — edit a `.md` file and the site reflects it, with no build step.

To publish:

1. Push this repository to GitHub.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, choose the `main` branch and the `/ (root)` folder, and save.
4. After a minute, the site is live at `https://<your-username>.github.io/<repo-name>/`.

The `.nojekyll` file tells Pages to serve the files directly. The site loads content over HTTP, so it displays on the published URL (or any local web server), not by double-clicking `index.html` on your desktop.
