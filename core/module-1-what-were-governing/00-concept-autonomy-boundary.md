# The Autonomy Boundary

> **Part of:** Core / Module 1 — stable concept unit
> Current, dated examples live in the companion file `90-snapshot-2026-examples.md`. This unit stays deliberately example-light so it does not age.

Before you can govern something, you have to say what it is. Much of the confusion in AI governance comes from a single word doing too much work: "AI" gets used for a chatbot drafting an email and for a self-directed system reaching into a live control loop, as if they posed the same problem. They do not. This unit sorts the field into three categories — generative, agentic, and autonomous — and then makes the one distinction the rest of the course depends on: the point where autonomy crosses into safety-critical operation. That crossing, not "AI" in the abstract, is the governance-relevant boundary.

## Three categories, not one

**Generative AI produces.** Given a prompt, it returns content — text, code, an image, a prediction, a recommendation. It does not act on the world; it hands an output to a human or a system that decides what to do next. Its influence is entirely mediated by whoever consumes what it produces. A generative model is a very capable advisor with no hands.

**Agentic AI acts.** It is given a goal, and it plans and takes a sequence of steps toward that goal — calling tools, querying systems, chaining decisions, adjusting as it goes. The defining change from generative is *agency over a workflow*: it does not just answer, it pursues. An agent can still operate under human oversight, and often nominally does, but the unit of behavior is now a multi-step course of action rather than a single reply.

**Autonomous AI acts without a human in the loop.** It is agentic behavior with the supervision removed: the system initiates and sustains action on its own authority, deciding and executing without a person authorizing each step. Autonomy is not a fourth kind of intelligence; it is agentic capability operating with the human moved from *in* the loop to, at best, *on* the loop — watching — or out of it entirely.

These are not sharp bins, and a single deployed system can shade from one into the next as oversight is loosened. That is exactly why the categories matter: the governance question is not which label a system wears, but *how far along this progression it sits and what it can reach from there.*

## Why conflating them corrupts governance

Treat all three as "AI" and you make two opposite errors at once. You over-govern the harmless — wrapping a document-summarizing generative tool in controls meant for a system that can move a physical process — and you under-govern the dangerous, waving through an autonomous agent because "it's just AI, like the chatbot." Both errors come from reasoning about the technology instead of about its **agency and its reach.**

The distinction that survives is not generative-versus-the-rest for its own sake. It is this: risk in this course is a function of *how much independent authority a system has* and *what consequences it can reach with that authority.* A generative model with no path to a critical function is a low-consequence problem no matter how capable it is. An autonomous agent with authority over a safety-critical function is the problem the whole course is built for — even if it is, in raw capability, less impressive than the chatbot.

## The boundary that matters

Here is the durable claim, the one meant to outlast every example: **the governance-relevant boundary is the point where an autonomous system crosses into safety-critical operation.**

Locate the three categories against it. Generative AI sits well back from the boundary; its outputs reach consequences only through a human or system that acts on them, and that intermediary is where governance has traditionally lived. Agentic AI moves toward the boundary — it takes actions, so the question becomes what its actions can touch. Autonomous AI crosses the boundary at the moment it holds unsupervised authority over a function whose failure reaches a consequence that must not happen. That is the line. On the near side, an AI's mistakes are recoverable through the human or system standing between it and the world. On the far side, the AI can drive a facility toward its own forbidden outcomes with no one in the path.

Two things determine which side a system is on: **autonomy** (can it act without a human authorizing the step?) and **safety-critical reach** (can that action arrive at a must-not-happen consequence?). Neither alone crosses the line. High autonomy over something trivial is a nuisance, not a hazard. Deep reach into a critical function under tight human control is ordinary, well-understood engineering. It is the *combination* — self-directed action with a path to catastrophe — that defines the boundary this course exists to govern.

## Where this points

You have now met, in plain form, the line the rest of the course sharpens into a tool. In Module 3 you will learn that a facility's must-not-happen consequences are named by its design basis, and that the AI operating there needs its own. In Module 4 the boundary gets an operational name — the **Bright Line** — and a mechanism that enforces it. For now, hold the concept: what we are governing is not "AI." It is the crossing, by a self-directed system, into territory where it can cause what must not be allowed to happen.

For current examples of each category and where today's systems sit relative to this boundary, see the dated snapshot beside this unit. The examples will change. The boundary will not.

## In your sector

Think of one place in your chosen sector where software already touches a critical function. Ask the two boundary questions of it: *can it act without a human authorizing the step, and can that action reach an outcome that must not happen?* Wherever both answers trend toward yes, you have found the exact spot the rest of this course is going to teach you to govern.
