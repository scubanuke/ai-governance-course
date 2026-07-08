# The Two Design Bases

> **Part of:** Core / Module 3
> This unit is written out rather than stubbed, because it carries the distinction the whole course turns on.

By now you know what a design basis is: a discipline that anchors on the consequences that must not happen and bounds the adversary you will defend against. This unit makes a claim that is easy to miss and expensive to get wrong: **in any facility where AI operates, there are two design bases, not one.** They are produced by the same method. They are not the same artifact, and doing one does not do the other.

## The two

**The facility-class design basis (FC-DB).** This governs the facility, or the class of facilities. Its consequence anchor is physical and operational — the releases, failures, and losses that must not happen at the plant, the terminal, the substation. Its adversary envelope is physical, kinetic, and operational: the bounded set of physical and operational threats the facility is engineered to withstand. This is the DBA / DBA-MA line you've been building toward.

**The AI design basis (AI-DB).** This governs the AI system operating in or over that facility. It is a design basis in exactly the same sense — same method, same two moves — but its object is the model, not the machinery.

## Why two, and not one bigger one

Here is the part to teach hard, because it is the reason the AI cannot simply be folded into the facility's design basis:

**The two design bases share a consequence root but diverge on the adversary envelope.**

The AI-DB *inherits* the facility's must-not-happen consequences. The AI's failure matters precisely because it can reach into the physical consequence set the FC-DB already named. So you do not invent a fresh consequence anchor for the AI — you inherit the facility's and ask how the AI can reach it. The AI-DB may also *extend* that set with consequences the physical design basis never contemplated: an integrity consequence, an influence consequence, a loss of trustworthy state that has no kinetic equivalent.

But the adversary envelope is a different animal entirely. The facility's envelope is physical and kinetic. The AI's envelope is model manipulation, data poisoning, prompt injection, and autonomy drift — the moment the agentic system crosses into safety-critical territory, which is the boundary you met back in Module 1. A facility hardened against every physical threat in its envelope can still be driven straight into its own forbidden consequences through an adversary envelope its FC-DB never looked at.

That divergence is the whole argument. **Same consequence root, different adversary envelope, different reachability — therefore two design bases.**

## The seam between them has a name

The two design bases are not independent. They meet at a seam, and in this framework the seam has a name: the **Bright Line.** The Bright Line is the boundary, defined in the AI-DB, that keeps the AI from being able to reach the consequences the FC-DB says must not happen. It is where the second design basis is fastened to the first.

Everything you will meet in Module 4 sits on this seam. **Criticality tiering** is simply the question *how much does this AI's failure matter, measured against the inherited consequences?* The **Command Broker** is the construct that enforces the Bright Line in live operation. Read that way, Module 4 is not a grab-bag of governance primitives — it is the machinery of the second design basis.

## The two, side by side

| | Facility-class design basis (FC-DB) | AI design basis (AI-DB) |
|---|---|---|
| **Object** | the facility / facility class | the AI operating in or over it |
| **Consequence anchor** | physical & operational must-not-happens | **inherited** from the FC-DB; may **extend** with AI-specific consequences |
| **Adversary envelope** | physical, kinetic, operational | model manipulation, data poisoning, prompt injection, autonomy drift |
| **Primary instruments** | DBA / DBA-MA | Bright Line, criticality tiering, Command Broker |
| **Key boundary** | the facility threat envelope | the **Bright Line** — the seam back to the FC-DB |

## What this means for the rest of the course

- **Module 4** is the AI-DB's toolkit. Every primitive there lives on the Bright Line seam.
- **The branches** each work both design bases in their own idiom — the OT track *derives* them; the policy track *analyzes* them.
- **The capstone requires both.** A facility-class design basis with no AI design basis is precisely the incomplete answer this course exists to prevent. If a student hands in one DB, they have missed the point of the two.

## In your sector

Name one must-not-happen consequence for a facility in your sector. That is your FC-DB anchor. Now ask: through what AI-facing path — a manipulated model, poisoned data, a drifting autonomous agent — could that same consequence be reached? That path is what the AI-DB exists to bound. Hold both; you will need them at the capstone.
