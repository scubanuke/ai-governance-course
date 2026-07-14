# Course Notes

The supporting-reference apparatus for the course.

A reading list is a burden handed to the student: a pile of documents and no instruction about what to take from them. A **Course Note** is the alternative — an excerpt placed *in context*, under the heading it serves, with a short account of what it establishes and where the AI case departs from it. It is the handout a professor gives out when the material is too new to have a textbook.

Notes are numbered by module (`M03-CN-01`), anchored to a specific unit and heading, and cross-linked from the module text. They are not woven into the modules: the module carries the frame and the argument; the Note carries the source. The full convention — including the seven required fields and the rule that excerptability is a selection criterion — is in [`CONVENTIONS.md`](../../CONVENTIONS.md).

## The collection

| Note | Anchors to | Source |
|---|---|---|
| [`M03-CN-01`](M03-CN-01-safety-security-interface.md) — Safety/Security Interface | Core / Module 3 · unit 05 · *Precedent: make the interface itself the governed object* | 10 CFR 73.58; NRC RG 5.74 |

## Template

Copy this shape. If a Note cannot fill field 6, it does not belong in the course.

```markdown
# Course Note M<NN>-CN-<NN> — <Short Title>

**Anchor** — <module / unit / heading it attaches to>

**Source and locator** — <full citation, precise locator, durable link:
.gov URL, Git mirror, or DOI — never a cloud-drive link>

**Provenance and use** — <published | prepublication | working note> ·
<public domain | licensed | CHARACTERIZE ONLY>

---

**Excerpt** — <verbatim and bounded>

> ...

*(Where reproduction is not permitted, replace this field with a
**Characterization**: what the clause requires, in our own words, with the
clause number so the learner can go read it.)*

---

**What it establishes** — <what the source settled, inside its own domain,
on its own terms. No editorializing yet.>

---

**Where the AI case departs** — <the payload. What has no counterpart on the
AI side, what breaks when the concept is carried across, and what the course
therefore has to construct.>

---

**Carry-forward** — <one sentence the learner takes into the next section,
phrased so it can be checked against the capstone rubric.>
```
