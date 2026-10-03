# IEEE V&V Framework

> **Part of:** Branch / OT Track

TAF told you how deeply to assess. This unit is about what "assessment" even means when the thing under test is a generative model — and why the verification standards OT already trusts do not reach it. It follows the IEEE V&V framework for cognitive behaviors in generative AI, and its central claim is uncomfortable: the discipline that makes safety software trustworthy assumes something generative AI does not provide.

## The assumption that breaks

Every established verification and validation standard — IEEE 1012, IEC 61508, ISA/IEC 62443 — rests on one shared premise: **software is deterministic.** Same inputs, same outputs. That premise is what lets formal verification work at all: model checking, theorem proving, exhaustive state-space analysis can prove a requirement is met "with mathematical certainty" precisely because the behavior is fixed and enumerable.

Generative AI violates the premise. Its outputs are non-deterministic and emergent — "the same prompt can produce different outputs across execution cycles" — and its failures are *cognitive*: hallucinations, reasoning errors, context misinterpretation, knowledge-boundary failures. Force such a system into a formal-verification framework and you do not get assurance; you get, in the source's phrase, "illusory assurance." That is the danger this unit exists to prevent: a model that has passed a verification regime it was never actually susceptible to.

## Split the system before you test it

The resolution is not to abandon formal methods but to aim them correctly, by splitting the system into two layers. The **infrastructure layer** — operating system, protocols, I/O, input validation, output boundary checks, safety interlocks, logging — is deterministic and should be formally verified exactly as before. The **cognitive layer** — the generative functions doing reasoning, synthesis, and interpretation — is non-deterministic and must be assessed statistically instead. The assignment rule is sharp: *any component whose behavior cannot be exhaustively characterized through formal methods belongs to the cognitive layer, regardless of its functional role.* A retrieval-augmented system splits cleanly this way — the retrieval mechanics are infrastructure; the reasoning over what was retrieved is cognitive.

This hybrid split is the practical heart of the framework: prove what you can prove, and assess — rigorously, statistically — what you cannot. And the split has a dependency that is easy to miss: the layers are stacked, not side by side. "A formally verified protection algorithm running on an unverified operating system with potential vulnerabilities creates a weak foundation, undermining application-level assurances." Verifying the cognitive layer is worthless if the deterministic layer beneath it was never verified at all — both halves have to hold.

## What cognitive assessment produces

For the cognitive layer, verification-by-proof is replaced by a disciplined evidence-generating process, tuned by error class. Safety-critical error-class work demands exhaustive **domain characterization** — because AI behavior outside its characterized domain is simply unassessed and therefore unreliable — followed by structured-scenario, adversarial red-team, and regression testing, conservative quantitative acceptance criteria with justified confidence levels, and near-real-time monitoring of every output for inconsistency, confidence-uncertainty mismatch, and physical-constraint violations. Lower-severity classes keep the same shape at calibrated rigor, shifting to trend-based monitoring and periodic audits.

The evidence this yields — logged outputs, scenario results, acceptance-criteria records, monitoring flags, and crucially **system provenance documentation** (base model identity and version, fine-tuning records, guardrail characterization, configuration control) — is what stands in for a proof. It does not demonstrate the model cannot err. It demonstrates a characterized, monitored, traceable baseline that a regulator can have confidence in. That reframing — from proof of correctness to evidence of characterized reliability — is the mental shift the unit is teaching.

## What "assessing the cognitive layer" might actually mean

Statistical assessment is not the end of the story — it is the near-term stand-in while better methods are built. The foundational work behind this framework (the Hybrid Formal Methods "Grand Challenge") names four candidate techniques for putting real verification pressure on the cognitive layer, and they are worth knowing because they mark where the field is trying to go. **Probabilistic verification** bounds the probability of an unsafe output rather than proving it impossible — for example, demonstrating an unsafe action stays below one in a million. **Hybrid logic systems** combine deterministic proof with probabilistic reasoning so a mostly-deterministic architecture can still carry a formal argument. **New property-specification languages** let you state cognitive requirements precisely enough to test against — "within the 95th percentile of expert human decisions" rather than "behaves reasonably." And **compositional verification** propagates statistical assurances about the cognitive component through the deterministic architecture around it, so a bounded-confidence claim about the model becomes a system-level claim. None of these is mature; the honest framing is the one the source uses — hybrid approaches trade "absolute certainty for bounded confidence appropriate to the system's capabilities and risks." That trade, not a proof, is the realistic target.

## Policy and architecture are different objects

The framework draws a line OT engineers should keep crisp. The Bright Line is a threshold on **actions**, placed on the consequence of each one; the criticality band of the application sets how rigorously it is assessed, and does not decide which actions need a human. The Command Broker is the role that authorizes the above-line actions, and the architecture makes that non-negotiable: the control system is incapable of executing an above-line action without the authorization, so the AI "analyzes, recommends, and explains" and a human authorizes. Defense is architectural, not procedural — the next unit builds it. And note the carve-out that keeps the framework honest: a component that is deterministic within a stated input bound **and** formally testable as deployed is outside the Command Broker obligation (**FD-LD** §4.3). The carve-out is a property test, not a pass for "deterministic ML": a deterministic model never formally tested is in scope, and a carved-out component is not thereby below the line. The obligation targets behavior not bounded by proof, of which generative AI is the principal case — not "AI." (This summary follows the IEEE V&V Cognitive AI Framework at V1.4, which conformed its §5 to the October 2026 Edition of the Foundational Definitions.)

## Where it sits among standards

This framework did not appear from nowhere. It is the formalization of an earlier call to arms — the Hybrid Formal Methods white paper and its "Grand Challenge," which argued that five decades of industrial control had always produced quality-assurance methods to match each new technology *before* wide deployment, and that generative AI broke the pattern by deploying ahead of any verification framework. That gap — "50 years of proven quality assurance methods for traditional software in safety-critical applications; exactly zero mature, standardized frameworks for verifying the cognitive components of GenAI systems" — is the founding gap from Module 0 in its engineering form, and it is the root this V&V unit grows from.

This is positioned as the natural next chapter of IEEE 1012 rather than a repudiation of it: the three-error-class cognitive taxonomy lines up with 1012's integrity levels, the safety-critical error class aligns with the highest functional-safety integrity levels, and the whole approach operationalizes the govern/map/measure/manage structure of the NIST AI risk-management framework. It is complementary to 62443, which handles external compromise but not internal cognitive reliability — the seam the next unit takes up directly.

## For your capstone facility

For your facility's AI, perform the split: list what belongs to the infrastructure layer (and can be formally verified) and what belongs to the cognitive layer (and must be statistically assessed). Then, for one cognitive function, state the domain you would characterize, the tests you would run, and the provenance you would record. That triple — domain, tests, provenance — is the V&V evidence package your OT deliverable will need to stand behind.

---

*Changelog*

- *2026-07-31 — Reconciled to the Consequence-Severity vocabulary: the cognitive taxonomy is the three **error classes** (safety-critical / quality-of-service / compliance), retiring "Tier 1/2/3."*
