# The Command Broker

> **Part of:** Core / Module 4 — the AI design basis's toolkit

The Bright Line is drawn at design time. The criticality tier is assigned at design time. But a facility runs in real time, with a live AI issuing real commands, and a boundary that exists only on paper enforces nothing. This unit is the primitive that makes the Bright Line hold while the system is running. It is the **Command Broker**, and it is the runtime half of the AI design basis.

## What the Command Broker is

The **Command Broker** is the construct that sits between the AI and the functions it can act on, and mediates every command the AI issues before that command reaches the controlled system. It checks each proposed action against the Bright Line criteria, and it does not pass an action that would cross the line. Where the Bright Line defines the boundary and the criticality tier says how firmly it must be held, the Command Broker is what actually stands at the boundary during operation and keeps it intact.

Put the three primitives together and the module resolves into a single mechanism. The Bright Line is *where* the seam is. The criticality tier is *how much* the seam matters. The Command Broker is *how the seam is held* while the facility runs. That is the AI-DB's toolkit, complete: a boundary, a measure, and an enforcer.

## What makes a Command Broker trustworthy

An enforcer that can be reasoned around, talked past, or corrupted along with the thing it governs is not an enforcer. Three properties are what give the Command Broker its force.

**Independence.** The Command Broker must not depend on the AI behaving correctly. If the same model that might drift, be manipulated, or be poisoned is also the thing deciding whether its commands are safe, there is no enforcement — only the AI grading its own homework. The Broker has to be a separate authority, outside the AI's reach, precisely so that an AI operating *past* its Bright Line still cannot get its command through.

**Determinism and verifiability.** The Broker's decisions must be legible and checkable — ideally simple enough that its behavior can be verified across the full range of commands it might see. It enforces; it does not itself reason probabilistically about intent. The point of moving enforcement out of the AI is defeated if the enforcer is just a second opaque model. A Command Broker should be the kind of thing you can prove correct, not merely hope is correct.

**Minimality.** The Broker should do one job — hold the Bright Line — and do it in as small, inspectable, and hard-to-subvert a form as possible. Every additional responsibility is additional surface for the enforcement to fail. Its legitimacy comes from being narrow.

## Mechanism and accountability: who — or what — can be the Broker

A reader who has absorbed the three properties will notice something, and the sharpest students ask it out loud: nothing in *independence*, *determinism and verifiability*, or *minimality* says the Broker must be human. The properties describe what the enforcement must **do**, not what it must **be** — and that is deliberate. Where a consequence reduces to a checkable physical or operational constraint, the enforcing mechanism can be an interlock, a hard limit, a few lines of inspectable logic, or in principle any constrained automation that meets the three tests. That implementation-neutrality is a feature: it is what lets the Broker's teeth scale from a log entry to a hardware lock. But it invites the obvious challenge — if the Broker is defined by function rather than by implementation, what stops a *sufficiently constrained AI agent* from occupying the role?

The answer is that the Command Broker is two things wearing one name — a **mechanism** and an **accountable authority** — and only the first is implementation-neutral. The mechanism enforces. The authority *answers for* the enforcement: it holds the duty of care, it is the party a reviewer, a regulator, or a board of inquiry addresses when something goes wrong, and it is the entity whose judgment the decision-context record exists to make defensible. Accountability is not a capability you can satisfy by adding constraints; it requires a party that can bear an obligation and be answerable for an outcome. An AI cannot occupy that seat, so it cannot *be* the Broker — even where it runs part of the Broker's machinery.

That dissolves the apparent paradox rather than legislating around it. The three properties were never a sufficient *definition* of the Broker; they are the test the **mechanism** must pass. A constrained automation can perform bounded, verifiable enforcement wherever the consequence is checkable. What it cannot do is be accountable. So the rule the framework states plainly is this:

> **Even where broker functions are automated, ultimate accountability remains tied to a named human decision-maker or governance authority; and where a consequence cannot be reduced to a deterministic check, that accountability is non-delegable.**

The next section is where the second clause earns its keep. Arbitration between two valid design-basis claims is exactly the case a mechanism cannot discharge on its own — there is no check to run, only a judgment to own — which is why the party that owns it has to be one that can be held to account.

## Enforcement is the easy half: the Broker as arbiter

Everything above describes the Broker as a gate — a thing that stops a command. That is the clean case, where the AI proposes an action that is simply forbidden and the answer is no.

The hard case is the one Module 3 left you with. The two design bases are **co-equal** at the seam: the AI-DB inherits the facility's consequences but not its authority, and neither basis settles a conflict by outranking the other. So what happens when both have a legitimate claim on the same decision — when the AI-DB says *act*, for reasons that are correct within its own basis, and the FC-DB says *that action moves the facility toward a must-not-happen*?

A gate cannot answer that. A gate only knows forbidden and permitted. What the situation requires is **arbitration**: a resolution between two valid claims, made at the moment of the decision.

> **The Command Broker is the arbiter of design basis collisions.**

This is the Broker's deeper job, and it is why the construct exists at all rather than being replaced by a rulebook. The nuclear precedent discharges the same obligation through a review board that convenes on a Tuesday and reconciles safety against security before a change is made *(see Module 3, unit 05, and Course Note M03-CN-01)*. That model holds when changes are discrete, planned, and known in advance. It fails when the collision surfaces at runtime, at machine speed, in the instant the system is being asked to act. The Broker is the runtime discharge of an interface duty the nuclear world discharges on human time.

Two consequences follow, and they should govern how you design one.

**The arbitration rule must be written down before it is needed.** A Broker that decides collisions ad hoc is not an arbiter; it is a second opaque model. The resolution must be deterministic, stated in the AI-DB, and traceable back to the consequence root — which is exactly what makes the Bright Line more than a slogan.

**Not every collision is resolved in the facility's favor.** Co-equal means co-equal. Where the AI-DB has *extended* the consequence set with something the physical basis never contemplated — an integrity consequence, a loss of trustworthy state — the Broker may hold a line the FC-DB never drew. Deference to the physical basis is a design choice you make deliberately, on the record, for stated reasons. It is not a law of nature, and a framework that assumes it has quietly reintroduced the hierarchy Module 3 spent a unit dismantling.

## Enforcement scaled to the tier

The Command Broker is where the criticality tier from the last unit is cashed out. For a lowest-criticality system, the Broker may be light — a check, a mediation, a log. For a highest-criticality system, holding the Bright Line may demand the strongest available enforcement: independent interlocks, hard limits the AI cannot address, a control lock and an independent reset that no amount of model misbehavior can override. The tier sets the strength; the Broker delivers it. This is the sense in which the three primitives are one system rather than three ideas — the tier's number becomes the Broker's teeth.

*(In this framework the Command Broker carries a distinct identity — the CB family of instruments — and should not be confused with the separate communications design basis. It is an enforcement construct, not a communications one.)*

## Where this goes

With the Command Broker, the AI design basis has all three of its working parts, and the core of the course is complete: you can now name a consequence root, derive a design basis for a facility, recognize that the AI operating there needs its own, draw the Bright Line between them, tier its criticality, and specify what must enforce it in operation. The branches take this machinery deeper — the OT track builds the Command Broker and Bright Line at the architecture level and works the assessment tiering; the policy track analyzes what happens when this machinery is absent or defeated. The capstone makes you produce it. Everything from here uses what this module built.

## In your sector

For the Bright Line and criticality tier you have been developing, describe the Command Broker it would take to hold that line in live operation. What sits between your AI and the consequence? Is it independent of the AI, or does it quietly depend on the AI being well-behaved? Push on that last question — it is the one that most often reveals whether a Bright Line is really being enforced or only being described.
