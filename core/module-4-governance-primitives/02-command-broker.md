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

## Enforcement scaled to the tier

The Command Broker is where the criticality tier from the last unit is cashed out. For a lowest-criticality system, the Broker may be light — a check, a mediation, a log. For a highest-criticality system, holding the Bright Line may demand the strongest available enforcement: independent interlocks, hard limits the AI cannot address, a control lock and an independent reset that no amount of model misbehavior can override. The tier sets the strength; the Broker delivers it. This is the sense in which the three primitives are one system rather than three ideas — the tier's number becomes the Broker's teeth.

*(In this framework the Command Broker carries a distinct identity — the CB family of instruments — and should not be confused with the separate communications design basis. It is an enforcement construct, not a communications one.)*

## Where this goes

With the Command Broker, the AI design basis has all three of its working parts, and the core of the course is complete: you can now name a consequence root, derive a design basis for a facility, recognize that the AI operating there needs its own, draw the Bright Line between them, tier its criticality, and specify what must enforce it in operation. The branches take this machinery deeper — the OT track builds the Command Broker and Bright Line at the architecture level and works the assessment tiering; the policy track analyzes what happens when this machinery is absent or defeated. The capstone makes you produce it. Everything from here uses what this module built.

## In your sector

For the Bright Line and criticality tier you have been developing, describe the Command Broker it would take to hold that line in live operation. What sits between your AI and the consequence? Is it independent of the AI, or does it quietly depend on the AI being well-behaved? Push on that last question — it is the one that most often reveals whether a Bright Line is really being enforced or only being described.
