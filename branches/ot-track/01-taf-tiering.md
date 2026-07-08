# TAF Tiering

> **Part of:** Branch / OT Track

Module 4 gave you the three-tier criticality model as the AI design basis's severity scale. This unit turns that scale into a working assessment procedure: the **Tiered Assessment Framework (TAF)**, which decides *how much scrutiny* an AI system must undergo and proportions assessment effort to consequence. If the criticality tier says how much is at stake, TAF says how hard you look — and proves you looked.

## What TAF assesses, and what it does not

TAF is precise about its scope, and the precision is the first lesson. It assesses **cognitive errors in generative AI** deployed in control environments — the emergent, non-deterministic failures that formal methods cannot catch. It deliberately does *not* cover the deterministic **infrastructure layer** of a system, because that layer is already amenable to formal verification (the next unit's subject). TAF is the cognitive-layer half of a hybrid quality-assurance approach: formal verification below, cognitive-error assessment above. Point TAF at the right layer — the part of the system whose behavior you cannot exhaustively prove.

## Two three-part scales that are not the same scale

The most common mistake with TAF is collapsing two distinct axes, so hold them apart deliberately.

The first axis is **criticality level** — Highest, Mid-Level, Lowest — set by consequence severity and mapped onto each sector's existing regulatory classification (nuclear Safety-Related, or the electric sector's High / Medium / Low-Impact cyber-system tiers). This is the same consequence-anchored scale from Module 4, and it drives a hard deployment rule: **fully autonomous generative AI is prohibited at both Highest and Mid-Level criticality.** Above that Bright Line, generative AI may only advise — it "cannot directly command changes to setpoints, valve positions, or other process control parameters"; a human Command Broker makes and executes the decision. Only at Lowest criticality is bounded autonomy permitted.

The second axis is **assessment tier** — Tier 1 safety-critical errors, Tier 2 quality-of-service errors, Tier 3 compliance-driven errors — a taxonomy of *what kind of cognitive error* you are testing for. These two axes are **orthogonal**: the criticality level says how autonomous the system may be and how rigorously to assess it; the assessment tier says which class of error the assessment is hunting. A Highest-criticality system gets rigorous assessment across all three tiers; a Lowest-criticality one may need only light Tier 1 work. Keep the names straight and the framework is clear; conflate them and it collapses.

## How tier drives depth

The operating principle is proportional allocation: acceptance-criteria severity, monitoring intensity, and reassessment frequency all scale with criticality. At the top, the numbers get demanding. Hallucination tolerance for safety-critical deployment "should approach zero" — otherwise every AI claim needs independent external verification, which reduces the AI to a hypothesis generator. Factual accuracy for critical parameters is expected around 99% or better; below roughly 95% the framework questions whether the system adds value at all. Safety-critical validation is held to 95%+ statistical confidence, monitored in near-real-time, and may warrant annual reassessment. Commission errors — confidently wrong outputs — are treated as more dangerous than omission errors, where the system flags its own gap. Lower down the criticality scale, the same categories are assessed with lighter cadence and trend-based rather than continuous monitoring.

Notice this is the design-basis logic again, applied to assessment: consequence sets the bar, and effort concentrates where the consequence lives, rather than spreading evenly across every system that happens to contain AI.

## Why it slots into existing regimes

TAF is built to codify into the frameworks OT practitioners already answer to, not to replace them. Its criticality levels map onto the electric sector's High/Medium/Low cyber-system impact tiers and the nuclear safety classifications; its rigor is pitched to be "comparable to Class 1E systems" or protective-relay logic at Tier 1; and it cross-walks to functional-safety integrity levels, where autonomous generative AI lands as prohibited at the highest levels. There is a sector variant for water, and a variant aligned to the electric-reliability regime — the same framework instantiated per sector, exactly as the applicability gate was. That portability is deliberate: TAF is meant to be the assessment procedure a regulator can adopt, not just an idea.

## For your capstone facility

For the AI in your capstone facility, do the two-axis placement explicitly. First, which criticality level — and therefore, is autonomy even permitted, or does the Bright Line force a Command Broker? Second, across which assessment tiers must you test it, and to what acceptance numbers? Write those down; that pairing — deployment constraint plus assessment obligation — is the core of the OT assessment deliverable, and TAF is how you defend it.
