# Bright Line Criteria

> **Part of:** Core / Module 4 — the AI design basis's toolkit

Read this whole module as one thing: the machinery of the second design basis. Module 3 left you with two design bases — the facility's (FC-DB) and the AI's (AI-DB) — sharing a consequence root and meeting at a seam. This unit names and builds that seam. It is the **Bright Line**, and it is where the AI design basis fastens to the facility's.

## What the Bright Line is

The **Bright Line** is the boundary, defined inside the AI-DB, that the AI must not cross because crossing it puts the AI within reach of the facility's must-not-happen consequences. It is drawn at exactly the reachability seam you identified in Module 3: on the near side, the AI's actions cannot arrive at the consequence root; on the far side, they can. The Bright Line is the line between those two territories, made explicit and committed to in advance.

This is why the module insists these primitives are not a grab-bag. The Bright Line is the seam itself. Everything else in the AI-DB toolkit is defined relative to it: the criticality tiers measure how much is at stake on the far side of it, and the Command Broker is what holds it in live operation. Build the Bright Line correctly and the rest of the toolkit has a place to attach. Draw it wrong and nothing downstream can be right.

## Why it belongs to the AI-DB but points at the FC-DB

The Bright Line is defined in the AI's design basis, yet it is anchored on the facility's consequences. That double character is the whole point. The FC-DB names what must not happen — the physical, operational consequence root. The AI-DB then asks: *through what AI-facing paths could the AI reach that root?* The Bright Line is drawn across those paths. It is the AI-DB's boundary, but it is meaningless except in reference to the FC-DB's consequences. This is, concretely, what "the second design basis fastens to the first" means: the Bright Line is the fastener.

Because it is anchored on the shared consequence root, the Bright Line inherits the discipline you already learned. Its placement is derived, not guessed — you trace the reachability from the AI to the inherited consequences and draw the line where reach begins.

## Why it must be *bright*

The name is a requirement, not a decoration. A Bright Line must be **bright**: unambiguous enough that, at any moment in operation, you can tell whether it has been crossed. This is what separates it from an ordinary risk threshold. Risk thresholds are graded and fuzzy — "elevated," "high," a score creeping upward — and in live operation a fuzzy boundary is unenforceable, because no one can say for certain, in the moment, which side of it the system is on. The Bright Line is deliberately the opposite: a boundary defined by explicit **criteria** — specific, pre-committed conditions and authorities whose crossing is legible in real time. It should be as close to binary as the domain allows: crossed or not crossed, with as little interpretation as possible standing between the two.

Brightness is what makes the seam *governable*. A boundary you cannot reliably observe being crossed cannot be enforced, tiered, or audited. The criteria are what make the line bright, and the brightness is what makes the next two units possible.

## What this sets up

You now have the seam. The two units that follow live on it. The **criticality tiers** ask how much rigor the far side of this particular Bright Line demands, measured against the severity of the consequence it guards. The **Command Broker** is the construct that stands at the line during operation and keeps it from being crossed. Hold the Bright Line as the fixed reference for both: one measures against it, the other enforces it.

## In your sector

For the facility and consequence you carried out of Module 3, try to state a Bright Line in a single, observable criterion — a specific action, authority, or condition such that crossing it would put an AI within reach of that consequence. Then test it for brightness: could an operator, or a machine, tell in the moment whether it had been crossed? If the answer is "not quite," keep sharpening — the difficulty of making the line bright is exactly the work this unit is teaching.
