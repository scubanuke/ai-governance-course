# Producing a Consequence and Governance Analysis

> **Part of:** Branch / Policy Track
> This is the spine of the policy branch — the analytic method a policy practitioner follows, parallel to the OT branch's derivation unit. Where the OT track produces an engineering artifact, this track produces a governance analysis. The method underneath is the same one you learned in the core.

The policy practitioner faces a trap the OT engineer does not: governance arguments are easy to dismiss as values dressed up as analysis. Say "AI should be constrained in elections" and half the room hears a political preference. This unit teaches the move that escapes the trap — the analytic method behind the Democratic Safeguards work — and it is, at bottom, the design-basis method pointed at institutions instead of machinery.

## Argue from the technology, not from values

The foundational move is to derive every constraint from **what the technology actually is**, so that the conclusion "cannot be dismissed as a political preference because it does not originate in one." You are not asserting that autonomous AI in a high-consequence setting is *bad*; you are showing that its own inherent characteristics force a particular governance boundary, whatever your politics. This is why the analysis is called consequence-and-governance rather than advocacy: the consequence does the arguing.

That reframing is also the "middle ground" thesis. When the method was applied to the standoff over military AI, the resolution was "not a negotiated compromise between contractual positions" but "an engineered solution that satisfies both parties' legitimate requirements because it is derived from the technology itself." A governance analysis worth the name produces that kind of result — a boundary both sides can accept because neither side authored it.

## The five-step chain

The method runs as a chain you can apply to any AI-in-society question, and it will look familiar because it is the core method in governance dress.

First, **decompose into two layers.** Every deployment has a deterministic infrastructure layer (data pipelines, access controls — formally verifiable) and a non-deterministic cognitive layer (reasoning, inference, content generation — not verifiable in advance). Second, state the **verification gap**: because the cognitive layer is non-deterministic, "no pre-deployment testing regime can prove the absence of failure modes in scenarios not yet encountered." Testing shows behavior in the cases you tried; it cannot bound the cases you did not. Third, **tier by consequence** — sort applications by severity so you apply proportional rigor rather than uniform restriction. Fourth, **draw the Bright Line**: for the highest-consequence tier, non-verifiability plus irreversible harm forces an architecturally enforced boundary above which the AI may not act autonomously. Fifth, **specify the broker and the audit**: interpose a mandatory human authority — architecturally, not procedurally — and prove the boundary holds by independent audit of the deterministic layer.

You have seen every one of these steps. They are Modules 1 through 4, restated for an audience of legislators rather than engineers.

And they apply twice. The policy analyst, like the OT engineer, must reckon with **both design bases** from Module 3 — the facility's own must-not-happen consequences (the FC-DB) and the AI's inherited-plus-extended set (the AI-DB). A governance analysis that addresses only the facility's physical consequences and ignores what the AI can reach, or vice versa, is the incomplete answer this course exists to prevent. Your analysis has to name both consequence sets and the governance gap each implies.

## Why "architectural" is the load-bearing word

The single most important claim to carry into any governance analysis is the ordering of safeguards: **architectural beats weight-level beats contractual.** Contractual terms can be renegotiated. Training-level constraints (RLHF and the like) can be fine-tuned away or elicited around. Only architecture "holds regardless of any party's preferences." A governance analysis that recommends a contractual or training-based safeguard for a high-consequence use has recommended something that dissolves under political or market pressure. The February 2026 episode in which contractual AI safeguards proved renegotiable is the cautionary case: *contractual safeguards are not architectural safeguards, and only architectural safeguards survive.*

## Turning the analysis into governance

The final discipline is what makes this a policy deliverable rather than an essay: each governance ask must be written so it "can be translated into an engineering specification" and "independently audited and verified." When the method was applied to democratic process, it produced an integrated architecture of concrete, auditable components — a statutory aggregation threshold, a standards-and-certification body, a human-broker mandate, graduated penalties — not a list of aspirations. That is the standard your analysis is held to: every recommendation should name the consequence it addresses, the boundary it draws, and how compliance would be verified.

## For your capstone analysis

Take your capstone facility or sector and run the chain once, out loud: name the highest-consequence outcome, state why the cognitive layer cannot be verified against it, place the Bright Line, and specify the human broker and the audit that enforces it. Then convert one recommendation into an auditable requirement — consequence, boundary, verification. That conversion is the heart of the policy deliverable this branch is preparing you to produce.
