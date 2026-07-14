# Merging the Two Design Bases

> **Part of:** Core / Module 3
> This unit answers the question the previous one raises and does not settle: two design bases exist, but how are they developed together, and what happens when they collide?

The previous unit left you with two design bases and a seam. That is a description of an architecture. It is not yet a method for building one. Two bases that meet at a seam can still be developed by different people, on different schedules, toward different objectives — and if they are, the seam is where the whole thing fails.

This unit is about making them row in the same direction.

## Why neither basis can simply win

The previous unit ended on a distinction worth pressing: the AI design basis inherits the facility's **consequences**, not its **authority**. Take that seriously and the easy resolutions close off one by one.

The easy resolution is a hierarchy. Put one basis over the other, and every collision at the seam has an answer: the senior document wins. It is tidy, it is what most organizations will reach for, and it does not work in either direction. If the FC-DB is superior, then the facility's design basis governs the AI — but the FC-DB was written against a physical, kinetic adversary envelope, by engineers who never contemplated model manipulation or autonomy drift. It cannot govern a system whose behavior it does not describe and whose failure modes it never enumerated. Asserting its primacy does not make it competent over the AI; it only makes the AI's real risks unowned.

Now run it the other way. If the AI-DB is superior, it governs a facility it does not own, in which it has no licensing standing, against consequences it did not originate. That is worse.

So the correct statement is the one your reviewers will press you on, and you should have it ready:

> **The AI design basis inherits the facility's consequences. It does not sit beneath the facility's authority. At the seam, the two bases are co-equal, and neither can resolve a conflict by outranking the other.**

Which leaves the obvious question. If neither wins, what settles it?

## Precedent: make the interface itself the governed object

The move you need has been made before, in a regulated setting, under conditions close enough to be instructive.

> **Worked example — nuclear.** *This example is drawn from nuclear power regulation. If your sector is water, communications, transportation, health, or finance, read it as a model of the reasoning, not as a rule that binds you. The pattern is what transfers.*
>
> **See Course Note M03-CN-01 — Safety/Security Interface (10 CFR 73.58).**

A nuclear power plant carries two mature design bases at once. A **safety** basis, anchored on radiological consequence and engineered against accident. A **security** basis, anchored on sabotage and engineered against a bounded adversary. They are developed by different organizations, reviewed by different regulators, and they routinely conflict: a door locked for security is a door that slows an operator; a barrier that stops an intruder can obstruct an emergency response.

Faced with two co-equal bases in one facility, the regulator did not pick a winner. It made **the interface itself** the regulated object. The licensee carries an affirmative obligation to assess and manage the potential for adverse effects on safety and security before implementing changes to plant configurations, facility conditions, or security. Where conflicts are found, the licensee must communicate them and take compensatory or mitigative action. The implementing guidance is deliberately unglamorous: the interface is discharged through the institutions the plant already runs — review boards, configuration management, work planning, corrective action.

That is the pattern, and it is the answer to the "neither is superior" problem:

**You do not merge two design bases by reconciling them philosophically. You merge them by making the seam a thing somebody owns, with a duty to look for conflict before acting and a fallback for when conflict cannot be removed.**

## Where the AI case departs

The precedent gets you the shape. It does not get you the mechanism, because three things about AI break the model that discharges it.

**Cadence.** The nuclear interface obligation operates on *changes*, and it assumes a change is a discrete, planned, reviewable event — a modification a review board can convene against. A model update, a retraining cycle, a revised prompt or policy, a system whose behavior shifts under a drifting input distribution: none of these arrive as a change ticket. The AI-DB moves at a cadence the review-board model was never built to track.

**Discovery point.** The precedent finds conflict *before implementation*. The AI case surfaces much of its conflict **at runtime**, in the instant the system is being asked to act. Pre-implementation review remains necessary. It has stopped being sufficient.

**Reach.** The precedent has an accountable licensee who owns the configuration it is held to. In the AI case the operator is still accountable — the duty does not evaporate because one side of the conflict now originates in a model — but its **reach** is gone. The operator is answerable for a design basis partly authored elsewhere: a training corpus it did not assemble, weights it cannot inspect, a release cadence it does not set. Accountability without control is the structural mismatch that has no analogue in the nuclear precedent.

Each of these is a live regulatory gap, and the policy track takes them up as such. Here, treat them as design requirements. Any merge mechanism you build has to work at machine cadence, at runtime, and across an authorship boundary you do not control.

## The arbiter: what the Command Broker is for

Those three requirements have a single answer in this framework, and you have already met its name.

The **Bright Line** says where authority changes hands — it is the boundary, defined in the AI-DB, past which the AI must not be able to reach the FC-DB's forbidden consequences. But a boundary is a declaration. It does not decide anything.

The **Command Broker is the arbiter of design basis collisions.** When both bases have a legitimate claim on the same decision — the AI-DB says act, the FC-DB says that action approaches a must-not-happen — the Broker is what resolves it, at the speed the decision is actually being made, without either basis outranking the other. It is the runtime discharge of the same obligation the nuclear precedent discharges through a review board convening on a Tuesday.

Read the whole framework through this unit and it reorganizes itself. The two design bases are the *what*. The Bright Line is the *where*. The Command Broker is the *how*, at the moment it matters. Module 4 is not a toolkit of governance primitives. It is the machinery of a managed interface.

## Making the merge operational

A managed interface that exists only as an architectural principle will not survive contact with a procurement department. Here is where it actually lives, and this is the part to take into your capstone.

**At acquisition.** When an operator buys AI-enabled equipment for a consequential facility, it executes an acceptance test plan — a documented quality-assurance regime, in regulated sectors a matter of legal diligence rather than good practice. That plan has to be written **against something**. It is written against the AI design basis. So are the requirements the procurement engineers place into the contract.

**On change.** The contract carries the re-test trigger: when the supplier makes a change significant enough to move the model's version by an integer rather than a decimal point — a substantive revision, not a patch — a reduced acceptance test plan fires. What it tests against is, again, the AI-DB.

**At runtime.** Between declared changes lies the residue the trigger cannot see: in-place updates, refreshed corpora, silent drift. That residue is the second, independent argument for the Broker. What cannot be caught at acceptance must be arbitrated in operation.

Notice what has happened to the AI design basis in the course of that paragraph. It is no longer a governance artifact that sits in a binder. It is **the source document for the purchase order** — the thing the contract requirements are derived from, the spine of the acceptance test plan, and the baseline any deviation is measured against.

This has a consequence for how you write one, and the capstone rubric holds you to it:

> **An AI design basis written in prose principles cannot generate an acceptance test plan.** If your AI-DB says the system *shall behave safely*, the procurement engineer has nothing to put in a contract and the test engineer has nothing to test. Every clause has to be written so that it yields a verifiable acceptance criterion. A design basis that cannot be procured against is not yet a design basis.

That is the strongest reason to write one that this course can offer. Not that governance is virtuous. That you cannot buy the equipment without it.

## What is not settled here

Be honest about the edges, because your reviewers will find them.

The acceptance-test route works where the operator has leverage over its supplier. It reaches less well through the sub-tier — the model provider sitting underneath your vendor, who will not negotiate terms with a single buyer and whose update cadence is set globally. And contract is not regulation: a flow-down clause binds whoever you had the market power to bind, while a statutory duty binds everyone. Whether the AI case needs a reporting duty on model suppliers to critical infrastructure — a genuine obligation rather than a negotiated one — is an open policy question, and the policy track is where you argue it.

Name the gap. Do not paper over it. A design basis that states what it cannot yet bound is doing its job; one that pretends to completeness is not.

## In your sector

Take the FC-DB anchor and the AI-facing path you named in the previous unit. Now find the collision: a moment when the AI, doing exactly what it was fielded to do, would push the facility toward that must-not-happen consequence — and both bases have a defensible claim.

Answer three questions about it. *Who owns the seam* — which named role in your organization is obliged to notice this conflict before it happens? *Where is it caught* — at acceptance, at a declared change, or only at runtime? *What arbitrates* — and if the answer is "a person, eventually," ask whether the decision will wait for one.

---

*Changelog — added in response to reviewer comment that the merge of the two design bases needed its own treatment: neither basis is superior, both are necessary, and cross-purpose development is the failure mode.*
