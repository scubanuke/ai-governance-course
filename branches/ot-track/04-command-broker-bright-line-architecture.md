# Command Broker and Bright Line at the Architecture Level

> **Part of:** Branch / OT Track

Module 4 introduced the Command Broker as the runtime enforcer of the Bright Line. This unit makes it concrete: where the boundary sits in a real control architecture, and the specific pattern that enforces it. For an OT practitioner this is the deliverable's teeth — the difference between a Bright Line described in a document and one a system is physically incapable of crossing.

## The boundary is architectural, not procedural

The Bright Line, realized, is "the boundary between the advisory layer and the physical command layer," and the governing rule is absolute: *nothing crosses it without passing through a human Command Broker.* The critical word is *architectural.* The control system must be **incapable** of executing an AI-originated physical command without a positive human confirmation that is local, auditable, and "not itself executable remotely or by another software component." The AI has no wire to the setpoint, the valve, or the breaker. Defense by architecture means the protection does not depend on anyone following a procedure correctly under stress — it holds because the path does not exist.

And the line is drawn by **consequence, not sophistication**: "sophistication does not govern; consequence governs." A crude dosing-adjustment AI at a water plant may sit above the line while a far more sophisticated data-center energy optimizer sits below it. What places a system above the line is the severity of what it could cause, exactly as the design basis has insisted since Module 2.

## The Proposer–Gate pattern

The pattern that implements this cleanly is the **Proposer–Gate** architecture, and it is the unit's key construct. Two components sit on either side of the safety boundary:

The **proposer** is "a generative or otherwise complex, capable, and unverifiable component that generates a desired action." It may be opaque, probabilistic, and occasionally wrong. It holds **proposal authority and nothing more.**

The **gatekeeper** is "a simple, deterministic, formally verified governor that sits at the boundary and admits only the actions that fall within its tested envelope, clamping or rejecting the rest." It holds **veto authority** and is the sole path by which any proposal reaches the process.

The elegance is what this does to the hard problem. Because the entire safety case lives in the small, verifiable gatekeeper, *the proposer's non-determinism becomes irrelevant to safety.* You no longer have to verify the unverifiable model; you only have to verify the gate. This is the OT realization of what the Command Broker does — the human broker and the deterministic gatekeeper are the same idea in different substrates, and the boundary each holds is the Bright Line. (This is the runtime-assurance, or safety-filter, family — kin to simplex and shielding architectures.)

## Two conditions that make the gate real

A gatekeeper is only as good as two properties, and both are where naive implementations fail.

First, the monitor must be **complete and sound**: its set of admitted actions must be genuinely safe — and safety here is a function of "state, trajectory, and timing," not a static range. An action safe from one state is unsafe from another; safe at one rate is unsafe at another. A gate whose acceptance set has not been shown to be a subset of the truly-safe set, across all three, is — memorably — "a range check wearing the costume of a safety case."

Second, distinguish an action *within* the envelope from a change *to* the envelope. The gate disposes of in-envelope actions at runtime. But a request to change the envelope itself — the limits, the logic, the configuration — "must travel the same path as any other change to safety-grade logic: offline, through full requalification." This is also the anti-drift discipline: a frozen, verified gatekeeper does not drift, and live field learning is forbidden by construction. The model behind the gate may adapt all it likes; the gate does not change without going back through qualification.

## The human broker: qualification and accountability

Where the enforcer is a human Command Broker rather than a deterministic gate — the required architecture above the Bright Line for generative systems — the person is not a formality. They must be qualified across technical process competency, authority clarity, situational awareness, and performance under degraded conditions (lost comms, manipulated inputs, elevated tempo, military action), and organizationally they must be independent of the function generating the proposal, with protected authority to reject and time enough to exercise it. Underneath sits the **accountability principle**: accountability is personal and non-transferable, resting with the named human who signs — "there is no chair at Nuremberg for an organization."

Which yields the warning to carry into any implementation: a Command Broker interface that routes AI recommendations through a human who rubber-stamps every output "is architecturally compliant and functionally worthless." The architecture creates the opportunity to say no; the qualified, empowered, accountable human is what makes the no real.

## For your capstone facility

For your facility's highest-criticality AI function, draw the Proposer–Gate boundary explicitly: name the proposer, specify the gatekeeper's tested envelope over state/trajectory/timing, and identify what a "change to the envelope" would be and how it would be requalified offline. If a human broker holds the line instead, state their qualification and their protected authority to reject. That drawing — boundary, envelope, change-path, accountable authority — is the architecture your OT deliverable has to show.

> **Author note:** the source Command Broker documents do not use an OSI 7-layer or Purdue reference model; this unit follows their advisory-layer / physical-command-layer (protection–control separation) framing instead. If you want an explicit OSI/Purdue mapping added, send the layer model you prefer and I'll fold it in.
