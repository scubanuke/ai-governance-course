# The Consequence-Anchored Root

> **Part of:** Core / Module 3

The last unit said a design basis makes two moves: anchor on consequence, then bound the adversary. This unit is the first move, in full. It is the more important of the two, because everything else in the design basis is derived from it. Get the root right and the rest has something true to grow from. Get it wrong and you will build a rigorous defense of the wrong thing.

## The root, and why it is a root

A design basis begins at the consequence — the specific outcome that must not happen — and treats it as the fixed point from which the entire structure descends. This is the direct continuation of Module 2: consequence-first thinking, now made into the load-bearing element of an engineering method rather than just a stance. The consequence is not one input among many. It is the **root**: the thing every later decision traces back to and is justified by.

The metaphor is exact, and it has a practical form worth seeing. Picture the analysis as a tree with the consequence at the root and the ways to reach it branching upward — an attack tree read in the disciplined direction. Conventional security builds such trees from the bottom up, starting from vulnerabilities and asking what they might lead to, and drowns in branches. The design-basis discipline builds from the root down: fix the intolerable consequence first, then enumerate only the paths that actually reach *it.* The reciprocal relationship matters — the consequence at the root is what tells you which branches are worth drawing at all. A path that cannot reach the root consequence is, for this analysis, not on the tree. That is how a method that could sprawl infinitely stays finite: the root prunes it.

## Constructing the root well

Because everything depends on it, naming the root is the highest-leverage act in the whole method, and it is easy to do badly. Three disciplines make the difference.

**State it concretely, in the system's own terms.** The root is not "a cyber incident" or "a safety event" or a risk rated high. It is a specific physical or institutional outcome a domain expert would recognize instantly: this containment breached, this supply lost to this population for this long, this control surrendered, this trust irreversibly broken. Vagueness at the root propagates into vagueness everywhere, and a vague design basis defends nothing in particular.

**Prioritize ruthlessly.** Most bad outcomes are survivable; a few are not. The root is reserved for the few that cannot be allowed — the ones whose occurrence would be catastrophic and, often, irreversible. This is the hard consequence prioritization that consequence-driven engineering insists on: not the long list of things you would prefer to avoid, but the short list of things that must not happen. A design basis anchored on twenty consequences is anchored on none.

**Anchor on the consequence, not the cause.** The root is defined by *what must not happen,* independent of how it might be brought about. This is what lets a single root stand firm while the causes below it change. An accident, a cyber intrusion, and a deliberate attack may all reach the same forbidden outcome; the outcome is the stable thing, and anchoring there is what makes the design basis durable against threats no one has thought of yet.

## The root is shared

One property of the root matters so much that this module's keystone is built on it, so meet it here. In a facility where AI operates, the consequence root is **shared.** The facility has its must-not-happen outcomes; the AI operating inside it does not get a fresh, separate set of catastrophes to worry about — its failures matter precisely because they can reach *the same* physical outcomes the facility already named. The AI's design basis therefore *inherits* the facility's root rather than inventing its own. It may extend the root with new kinds of consequence the physical world never had — a loss of trustworthy state, an integrity failure with no kinetic equivalent — but the physical root is common ground. Hold that; the keystone unit turns it into the reason there must be two design bases and not one.

## In your sector

Return to the must-not-happen outcome you have been carrying. Now sharpen it into a root: state it in one concrete sentence a domain expert in your sector would immediately recognize, with no reference to how it might be caused. If you can write that sentence, you have a root. If you cannot yet — if it keeps coming out as a category of event rather than a specific outcome — that difficulty is the real work of this module, and it is worth staying with.
