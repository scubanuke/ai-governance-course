# Progress Tracker — design seed (not yet functional)

> **Status:** placeholder for a future version. This is a design note, not a working feature.

## Intent

In v0.1 the course is a static repository; a learner tracks their own progress by working through the folders in order.

A later version is planned to become a **live form** that:

1. Captures the learner's sector at Module 0.
2. Records progress as they complete each module and unit.
3. On the learner's request, produces an **email** summarizing where they are in the course.

## Notes for that build

- Sector selection (Module 0) is the first captured field and keys the *In Your Sector* blocks and the capstone.
- Progress state maps cleanly onto the folder structure: core Modules 0–4, bridge Module 5, the chosen branch, and the capstone.
- The status email is generated on request, not pushed.
- Likely delivery: a small GitHub Pages front end over this same repository structure.
