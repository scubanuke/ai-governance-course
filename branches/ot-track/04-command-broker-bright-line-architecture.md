# Command Broker and Bright Line at the Architecture Level

> **Part of:** Branch / OT Track

Module 4 introduced the Command Broker as the human who authorizes what the Bright Line places above it. This unit makes it concrete: where the enforcement sits in a real control architecture, and the specific pattern that enforces it. For an OT practitioner this is the deliverable's teeth — the difference between a Bright Line described in a document and one a system is physically incapable of crossing.

## The boundary is architectural, not procedural

The Bright Line is a threshold on **actions**, not a boundary between layers. An action is above it when its incorrect performance could reach the facility's must-not-happen consequences, and the governing rule is absolute: *no above-line action executes without the Command Broker's authorization.* The critical word is *architectural.* The control system must be **incapable** of executing an above-line action from an in-scope component without that authorization — in the moment, a positive human confirmation that is local, auditable, and "not itself executable remotely or by another software component"; in advance, the Command Broker's authorization of a pre-authorized envelope, against which a verified gatekeeper admits each action (below). The AI has no wire to the setpoint, the valve, or the breaker for an above-line change. Defense by architecture means the protection does not depend on anyone following a procedure correctly under stress — it holds because the path does not exist.

Two things decide whether the rule reaches an action, and neither is the layer. **Scope:** the obligation reaches every component that does not meet the determinism carve-out — deterministic within a stated input bound *and* formally testable as deployed (**FD-LD** §4.3). Generative AI is the principal case, not the definition; a deterministic model never formally tested is in scope too. **Placement:** consequence, action by action (**FD-BL** §4.2, §4.3). An above-line action does not escape the rule because an in-scope component's contribution to it was indirect — but "materially influenced" decides whether the rule *reaches* an action already above the line, never whether it *is* above the line (**FD-BL-D1** §7).

The advisory/command seam is *where* enforcement is usually built — not what *defines* where the line falls. **FD-BL** §4.2 says it in terms: the seam "is a useful place to build enforcement; it is not the definition of the boundary." A single gate at the seam leaves above-line actions on the advisory side ungated, and gates below-line actions on the command side for nothing.

And the line is drawn by **consequence, not sophistication**: "sophistication does not govern; consequence governs." A crude dosing-adjustment AI at a water plant may sit above the line while a far more sophisticated data-center energy optimizer sits below it. What places an action above the line is the severity of what it could cause, exactly as the design basis has insisted since Module 2 — and the same system will usually produce actions on both sides of it.

## The Proposer–Gate pattern

The pattern that implements this cleanly is the **Proposer–Gate** architecture, and it is the unit's key construct. Two components sit on either side of the safety boundary:

The **proposer** is "a generative or otherwise complex, capable, and unverifiable component that generates a desired action." It may be opaque, probabilistic, and occasionally wrong. It holds **proposal authority and nothing more.**

The **gatekeeper** is "a simple, deterministic, formally verified governor that sits at the boundary and admits only the actions that fall within the pre-authorized envelope its verification covers, clamping or rejecting the rest." It holds **veto authority** and is the sole path by which any proposal reaches the process. (The pattern's name is older than the vocabulary: "Gate" in *Proposer–Gate* means this verified gatekeeper, not the Gate — the enforcement interlock that holds an above-line action until it is authorized.)

The elegance is what this does to the hard problem. Because the entire safety case lives in the small, verifiable gatekeeper, *the proposer's non-determinism becomes irrelevant to safety.* You no longer have to verify the unverifiable model; you only have to verify the gate. But the gatekeeper is not a second kind of broker. The Command Broker authorizes the pre-authorized envelope and accepts the proof that bounds it, discharging in advance; the gatekeeper then admits each action in the class. **The human discharges; the gatekeeper admits** (**FD-BR** §4.1, §4.2). What the gatekeeper stands in for is the Broker's *presence* at the moment of action, not the Broker's *judgment* — and the boundary it stands at is not the Bright Line, which stays a threshold on actions. (This is the runtime-assurance, or safety-filter, family — kin to simplex and shielding architectures.)

## Two conditions that make the gate real

A gatekeeper is only as good as two properties, and both are where naive implementations fail.

First, the monitor must be **complete and sound**: its set of admitted actions must be genuinely safe — and safety here is a function of "state, trajectory, and timing," not a static range. An action safe from one state is unsafe from another; safe at one rate is unsafe at another. A gate whose acceptance set has not been shown to be a subset of the truly-safe set, across all three, is — memorably — "a range check wearing the costume of a safety case."

Second, distinguish an action *within* the envelope from a change *to* the envelope. The gate disposes of in-envelope actions at runtime. But a request to change the envelope itself — the limits, the logic, the configuration — "must travel the same path as any other change to safety-grade logic: offline, through full requalification." This is also the anti-drift discipline: a frozen, verified gatekeeper does not drift, and live field learning is forbidden by construction. The model behind the gate may adapt all it likes; the gate does not change without going back through qualification.

## The human broker: qualification and accountability

Whether the Command Broker authorizes in the moment or in advance as the author of the envelope — one role in two modes, with the advance mode an endorsement within the one qualification (**FD-BL-D1** §7) — the person is not a formality. They must be qualified across technical process competency, authority clarity, situational awareness, and performance under degraded conditions (lost comms, manipulated inputs, elevated tempo, military action), and organizationally they must be independent of the function generating the proposal, with protected authority to reject and time enough to exercise it. Underneath sits the **accountability principle**: accountability rests with the named human who signs, and it is not transferred away from them — "there is no chair at Nuremberg for an organization." It rests with the asset owner-operator as well; the organization cannot take the individual's accountability, but it holds its own (**FD-BL** §4.5).

Which yields the warning to carry into any implementation: a Command Broker interface that routes AI recommendations through a human who rubber-stamps every output "is architecturally compliant and functionally worthless." The architecture creates the opportunity to say no; the qualified, empowered, accountable human is what makes the no real.

## For your capstone facility

For your facility's highest-criticality AI function, list its actions and place each on consequence, then draw the Proposer–Gate boundary for the above-line class you would discharge in advance: name the proposer, specify the pre-authorized envelope over state/trajectory/timing and the Command Broker who authorizes it, and identify what a "change to the envelope" would be and how it would be requalified offline. For the above-line actions authorized in the moment, state the broker's qualification and protected authority to reject. That drawing — boundary, envelope, change-path, accountable authority — is the architecture your OT deliverable has to show.

> **Author note:** the source Command Broker documents do not use an OSI 7-layer or Purdue reference model; this unit follows their advisory-layer / physical-command-layer (protection–control separation) framing instead. If you want an explicit OSI/Purdue mapping added, send the layer model you prefer and I'll fold it in.
