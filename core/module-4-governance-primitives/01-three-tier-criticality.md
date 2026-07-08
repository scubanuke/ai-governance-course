# The Three-Tier Criticality Model

> **Part of:** Core / Module 4 — the AI design basis's toolkit

The Bright Line tells you *where* the AI must not go. This unit tells you *how much it matters* — and therefore how much rigor the AI's design and enforcement must carry. It is the AI-DB's severity scale: a three-tier criticality model that grades an AI system by the consequence it can reach, and assigns obligations to match.

## Severity measured against inherited consequences

The move that makes this scale disciplined rather than arbitrary is where it takes its measurement from. An AI system's criticality is **not** a property of the AI in isolation — not its size, its autonomy, or its sophistication. It is measured against the **inherited consequences**: how severe is the facility's must-not-happen outcome that this AI, by crossing its Bright Line, could reach? A dazzlingly capable model with no path to a serious consequence is low criticality. A modest model that can reach a catastrophic outcome is high criticality. The consequence root, inherited from the FC-DB, is the ruler. The AI is measured against it.

This is the same logic that functional safety has used for decades. In that world, a function is assigned a Safety Integrity Level — a SIL — according to the severity of what happens if it fails, and the SIL then dictates how much assurance the function must be built and proven to. The three-tier criticality model is the SIL-equivalent for AI: the tier is set by the consequence reachable across the Bright Line, and the tier then dictates the obligations. Borrowing the structure keeps this course connected to established engineering practice rather than inventing a scale from nothing.

## The three tiers

The model sorts AI systems into three bands by their relationship to the Bright Line and the consequence beyond it.

**Highest criticality** is an AI whose failure or subversion can reach a must-not-happen consequence directly — it sits right at the Bright Line, with a short, unbuffered path to the consequence root. These systems carry the heaviest obligations: the strongest assurance, the hardest Bright Line enforcement, and independent backstops that do not themselves depend on the AI behaving correctly.

**Middle criticality** is an AI that can move a facility *toward* a serious consequence but is separated from it by intervening barriers — other controls, human checkpoints, physical limits — that must also fail for the consequence to occur. Real obligations attach, scaled to how much of the distance to the consequence the AI can actually close.

**Lowest criticality** is an AI with no credible path across a Bright Line to a must-not-happen consequence — advisory and generative systems whose outputs are mediated by a human or an independent system before anything irreversible can occur. The obligations are correspondingly light. This is where most AI belongs, and saying so is part of the model's value: it keeps scarce assurance effort concentrated where the consequences actually live.

The exact boundaries between tiers are drawn per domain, but the ordering principle never changes: **higher tier means greater reach to worse consequences, and greater reach obligates greater rigor.**

## How to place a system

Placing an AI in a tier is a reachability question, and you already have the tools to answer it. Take the consequence root. Trace the AI-facing paths to it — the same paths the Bright Line is drawn across. Ask how severe the reachable consequence is and how direct the path: how many independent barriers stand between this AI's failure and the consequence, and how much does the AI's own action erode them? The severity of the consequence and the directness of the reach together fix the tier. Placement is not a vibe or a vendor claim; it is derived from the design basis, and it can be shown and defended.

## Where this feeds

The tier is not an end in itself — it is an instruction to the rest of the system. It tells the Command Broker in the next unit how hard the Bright Line has to be held for this system. And it is the seed of the assessment machinery the OT branch develops as **TAF tiering**, where this criticality model becomes an operational procedure for classifying and treating systems. Carry the tier forward; it is the AI-DB's statement of how much is at stake.

## In your sector

For the facility, consequence, and Bright Line you have been building, place your AI: highest, middle, or lowest criticality? State the reason in terms of reach — how severe the consequence it can touch, and how many independent barriers sit between the AI and that consequence. Notice that the honest answer sometimes lowers the tier (the barriers are real) and sometimes raises it (the barriers turn out to depend on the AI itself). That second discovery is one this module especially wants you to be able to make.
