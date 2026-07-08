# The Bounded Adversary Envelope

> **Part of:** Core / Module 3

The root tells you what must not happen. It does not yet tell you what you are defending against, and without that second move a design basis is only half built. This unit is the second move: bounding the adversary. It is the move that most distinguishes a design basis from ordinary risk work, and the one people find hardest to accept, because it requires stating plainly what you will *not* defend against.

## The move: bound, don't chase

An **adversary envelope** is the explicitly bounded set of adversary capabilities and conditions a design is engineered to defeat. It is stated in advance and in specifics: what the adversary is assumed to know, to have, to be able to do — the resources, access, skill, and persistence the design will withstand. Everything inside the envelope, the design must defeat. Everything outside it is named as outside: acknowledged, but explicitly beyond the design basis.

This is the nuclear discipline of the Design Basis Threat: rather than an endless catalog of everything a bad actor might conceivably attempt, the facility defines a bounded, characterized adversary and engineers to defeat it. The bound is not an admission of weakness. It is the precondition for rigor.

## Why bounding is what makes the discipline work

Recall the failure of vulnerability-first thinking from Module 2: the threat list never ends, so effort spreads thin and the argument for adequacy can never close. An unbounded adversary is undesignable and untestable. You cannot build to defeat "anything," and you certainly cannot demonstrate that you have. The moment you bound the adversary, three things become possible that were impossible before.

You can **design** to a target, because the requirement is now finite and specific. You can **test and demonstrate**, because "does the design defeat *this* defined adversary?" is a question with an answer, where "is the design secure against everything?" never was. And you can **audit and argue**, because a bounded envelope is a claim on the record that a reviewer can examine, challenge, and hold you to. The bounded envelope is what turns protection from an open-ended aspiration into a closed, defensible engineering case. That is why the discipline is tractable and testable at all — the bound is the source of both.

## Drawing the envelope honestly

The envelope is a judgment, and like the root it can be drawn badly in two opposite directions. Draw it too small and you manufacture false assurance: the design defeats a weak assumed adversary and everyone relaxes, while the real threat walks around it. Draw it too large and you are back to chasing everything, and the discipline collapses into the unbounded problem you were trying to escape. The skill is in placing the boundary where it is both defensible and useful — strong enough to matter, bounded enough to build to.

Two disciplines keep it honest. First, **characterize, don't gesture**: state the adversary's assumed capabilities concretely enough that someone could disagree with a specific line, not just a vibe. Second, **name what is outside**. A design basis that never says what it excludes is hiding its own boundary. The threats beyond the envelope — the beyond-design-basis events — should be written down as excluded, on purpose, so the residual risk is visible rather than pretended away. Stating what you do not defend against is not a weakness of the method; it is the most honest thing the method does.

## Where the two design bases part

The root, you saw, is shared: the AI inherits the facility's must-not-happen consequences. The envelope is where they diverge — and this unit is where you can now see why. The facility's adversary envelope is physical, kinetic, and operational. The AI's is nothing like it: model manipulation, data poisoning, prompt injection, adversarial inputs, autonomy drift. Same root consequence, entirely different set of ways to reach it, therefore an entirely different envelope. A facility hardened against every threat in its physical envelope can still be driven into its own forbidden outcome through an envelope its design basis never examined — the AI's. That gap, between a shared root and two different envelopes, is precisely the argument the keystone unit makes. You now have both halves of it.

## In your sector

For the root you sharpened in the last unit, sketch a first adversary envelope: name, in specifics, the capabilities you would engineer a facility in your sector to withstand — and then, just as deliberately, name one thing you would place *outside* the envelope. Notice how much harder and more honest the second half is. That honesty is the discipline this unit is really teaching.
