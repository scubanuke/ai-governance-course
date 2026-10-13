# The Command Broker

> **Part of:** Core / Module 4 — the AI design basis's toolkit

The Bright Line is drawn at design time. The criticality band is assigned at design time. But a facility runs in real time, with a live AI issuing real commands, and a boundary that exists only on paper enforces nothing. This unit is about what makes the Bright Line hold while the system is running. At its center is the **Command Broker**: the qualified human who authorizes what the AI may do across the line.

## What the Command Broker is

The **Command Broker** is a role, not a device. It is the qualified human who gives the authorization the Bright Line requires before an above-line action may execute. It is not an office, a job title, a software component, or a procedure telling an operator to click "confirm." The Foundational Definitions hold this definition once, in FD-BR (*The Broker*), and pair the Command Broker with exactly one line: the industrial Bright Line of FD-BL (*The Bright Line*).

The Broker does not hold the line alone. Holding a Bright Line in live operation takes three things, and it helps to keep them apart:

**The Line** places the obligation. An action the AI proposes is placed above or below the Bright Line on its own consequence, and an above-line action requires human authorization before it executes.

**The Gate** enforces the obligation. It is the architecture that makes the control system *incapable* of executing an above-line action without that authorization. It sits between the AI and the functions the AI can act on, and nothing the AI does can get an above-line command past it unauthorized.

**The Broker** authorizes. The Gate never authorizes and never stands in for the Broker; it only holds the action until the authorization is given.

Upstream of all three sits the consequence classifier, which decides for each action whether it is above or below the line. An action reaches the Gate and the Broker only once it has been placed above it.

Put the module's primitives together and they resolve into a single system. The Bright Line is *where* the seam is. The criticality band is *how much* the seam matters. The Gate and the Command Broker are *how the seam is held* while the facility runs: a mechanism that cannot be talked past, and a qualified human who answers for what goes across.

## Why the Broker is a human

The Command Broker is not there because consequential actions ought to have a human somewhere in the loop. It is there to supply judgment where proof is unavailable. It is compensation for unverifiability.

That explains an asymmetry that would otherwise look arbitrary. A reactor trip, a protective relay operation or an automatic load shed performs an action of the highest consequence with no Command Broker at all. Those actions are not below the line. They are outside the obligation because a deterministic protective function's behavior is bounded by proof: what it will do is known before it does it. Judgment is not required where proof is available.

A generative or learned AI is the opposite case. What it will propose cannot be known in advance, and nothing about its behavior is bounded by proof. Where proof cannot be had, a qualified human has to supply the judgment that proof would have supplied. That is the whole of the Command Broker's purpose, and it is the test any proposed alternative has to meet.

## What makes the Gate trustworthy

An enforcer that can be reasoned around, talked past, or corrupted along with the thing it governs is not an enforcer. Three properties give the Gate its force.

**Independence.** The Gate must not depend on the AI behaving correctly. If the same model that might drift, be manipulated, or be poisoned is also the thing deciding whether its commands get through, there is no enforcement, only the AI grading its own homework. The Gate has to sit outside the AI's reach, so that an AI operating *past* its Bright Line still cannot get its command through.

**Determinism and verifiability.** The Gate's behavior must be legible and checkable, simple enough that it can be verified across the full range of commands it might see. It enforces; it does not reason probabilistically about intent. The point of moving enforcement out of the AI is defeated if the enforcer is a second opaque model. A Gate should be the kind of thing you can prove correct, not merely hope is correct.

**Minimality.** The Gate should do one job, hold above-line actions until they are authorized, and do it in as small, inspectable, and hard-to-subvert a form as possible. Every additional responsibility is additional surface for the enforcement to fail. Its legitimacy comes from being narrow.

To these the definition adds one requirement that is easy to miss: the obligation is architectural, not procedural. The Gate must not be defeasible by a configuration change, a software update, or a system integration, and a procedure instructing an operator to confirm does not discharge it.

## What makes the Broker's authorization count

The Gate's properties are properties of a mechanism. They do not make anyone accountable, and they do not tell you whether an authorization means anything. Those are questions about the Broker, and the Foundational Definitions answer them directly.

**Substantive and attributable.** An authorization is *substantive* when the Broker has the information, competence, time and authority to withhold it on the merits. It is *attributable* when it resolves to a named, qualified individual and can be reconstructed from the record. An operator who approves a stream of prompts faster than they could read them gives authorizations that are neither.

**Competence belongs to the line.** A Command Broker must be competent in process and control consequence: able to evaluate what an incorrect setpoint or control action could cause. That competence is specific to the industrial Bright Line and does not transfer. Each Bright Line has exactly one Broker role, and holding one Broker role does not qualify a person for another.

**Accountability stays with people.** Accountability for an authorized action rests with the named Command Broker and with the asset owner-operator. A supplier may build and operate the Gate; a supplier may not hold the accountability, and no software component holds it.

## Can automation stand in for the Broker?

The sharpest students ask this out loud. If the Gate can be verified, why not let a sufficiently constrained AI agent authorize as well?

The answer has two parts. An AI cannot *be* the Broker, because the Broker is defined by judgment and accountability, and neither is a capability you can add by constraining a system. But for a narrow class of actions, the Broker does not have to be *present* at the moment of action.

The governing instrument is the determination FD-BL-D1 (*Mode of Discharge*). It allows the Command Broker to discharge the authorization *in advance* rather than in the moment, if and only if three conditions all hold. R1: the whole safety case lives in a formally verified gatekeeper that the proposing AI can neither modify nor bypass. R2: the gatekeeper's acceptance set is proven safe over state, trajectory and rate, so that *which* action is chosen, and not merely *whether* it is allowed, is bounded. R3: no change *to* the pre-authorized envelope, or to the gatekeeper's configuration, limits or logic, is ever discharged in advance.

Under those conditions the human authorization is not skipped. It is relocated in time. The Command Broker authorizes the envelope and accepts the proof that bounds it, and the verified gatekeeper then admits each action inside it at runtime. What the gatekeeper substitutes for is the Broker's *presence* at the moment of action, not the Broker's *judgment*, which was exercised when the envelope and its proof were accepted. Anything outside the envelope, and every change to the envelope itself, comes back to the Broker in the moment. In the definitions' terms, the Command Broker is *partially substitutable*. The OT track builds this architecture in detail as the Proposer–Gate pattern.

## Enforcement is the easy half: the Broker as arbiter

Everything above is about holding a forbidden action until someone with standing says yes or no. That is the clean case.

The hard case is the one Module 3 left you with. The two design bases are **co-equal** at the seam: the AI-DB inherits the facility's consequences but not its authority, and neither basis settles a conflict by outranking the other. So what happens when both have a legitimate claim on the same decision — when the AI-DB says *act*, for reasons that are correct within its own basis, and the FC-DB says *that action moves the facility toward a must-not-happen*?

A gate cannot answer that. A gate only knows held and released. What the situation requires is **arbitration**: a resolution between two valid claims, made at the moment of the decision.

> **The Command Broker is the arbiter of design basis collisions.**

This is the Broker's deeper job, and it is the clearest case of judgment where proof is unavailable: there is no check to run, only a decision to own. The nuclear precedent discharges the same obligation through a review board that convenes on a Tuesday and reconciles safety against security before a change is made *(see Module 3, unit 05, and Course Note M03-CN-01)*. That model holds when changes are discrete, planned, and known in advance. It fails when the collision surfaces at runtime, at machine speed, in the instant the system is being asked to act. The Broker is the runtime discharge of an interface duty the nuclear world discharges on human time.

Two consequences follow, and they should govern how you design for it.

**The arbitration rule must be written down before it is needed.** An arbiter who decides collisions ad hoc leaves nothing a reviewer can check the decision against. The rule must be stated in the AI-DB and traceable back to the consequence root. Where the rule settles a class of collision outright, it can be built into the Gate. Where it cannot, the Broker decides on the merits against the stated rule, and the decision is attributable. That is what makes the Bright Line more than a slogan.

**Not every collision is resolved in the facility's favor.** Co-equal means co-equal. Where the AI-DB has *extended* the consequence set with something the physical basis never contemplated, such as an integrity consequence or a loss of trustworthy state, the Broker may hold a line the FC-DB never drew. Deference to the physical basis is a design choice you make deliberately, on the record, for stated reasons. It is not a law of nature, and a framework that assumes it has quietly reintroduced the hierarchy Module 3 spent a unit dismantling.

## Enforcement scaled to the band

The criticality band from the last unit is cashed out here. For a lowest-criticality system, the Gate may be light: a check, a mediation, a log. For a highest-criticality system, holding the Bright Line may demand the strongest available enforcement: independent interlocks, hard limits the AI cannot address, a control lock and an independent reset that no amount of model misbehavior can override. The band sets the strength of the Gate and the weight of what the Broker is asked to authorize. This is the sense in which the module's primitives are one system rather than separate ideas: the band's demand becomes the Gate's teeth.

*(In this framework the Command Broker carries a distinct identity, the CB family of instruments, and should not be confused with the separate communications design basis. It is an authorization role, not a communications construct.)*

## Where this goes

With the Gate and the Command Broker, the AI design basis has all its working parts, and the core of the course is complete. You can now name a consequence root, derive a design basis for a facility, recognize that the AI operating there needs its own, draw the Bright Line between them, band its criticality, and specify the Gate that enforces the line and the Broker who authorizes across it. The branches take this machinery deeper. The OT track builds the Gate, the Proposer–Gate pattern and the Bright Line at the architecture level and works the TAF assessment; the policy track analyzes what happens when this machinery is absent or defeated. The capstone makes you produce it. Everything from here uses what this module built.

## In your sector

For the Bright Line and criticality band you have been developing, name the Command Broker who would authorize across it: what role holds it, and is that person competent in the consequence? Then describe the Gate. What sits between your AI and the consequence, and is it independent of the AI, or does it quietly depend on the AI being well-behaved? Push on that question; it is the one that most often reveals whether a Bright Line is really being enforced or only being described. Finally, ask whether any class of your above-line actions could be discharged in advance, and what proof that would take.

---

*Changelog*

- *2026-10-13 — Conformed to the October 2026 Edition of the Foundational Definitions: FD-BR (The Broker) and FD-BL-D1 (Mode of Discharge). The Command Broker is now the qualified human role, and the three properties (independence, determinism and verifiability, minimality) are properties of the Gate. Added why the Broker is a human, what makes an authorization count, and advance discharge. The arbiter result is unchanged.*
- *2026-07-31 — Reconciled to the Consequence-Severity vocabulary: "criticality tier" → **criticality band** throughout. Method unchanged.*
