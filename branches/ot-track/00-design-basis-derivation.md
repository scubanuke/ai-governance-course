# Design Basis Derivation in Depth

> **Part of:** Branch / OT Track
> This is the spine of the OT branch. The core taught you *what* a design basis is; here you learn to *produce* one to engineering standard — the work an OT practitioner actually delivers.

Module 3 gave you the two moves: anchor on consequence, bound the adversary. That is enough to reason. It is not yet enough to build. A design basis that an operator, a regulator, or an adversary can take seriously has to become **quantitative** — numeric bounds, stated acceptance criteria, and a repeatable way to test them. This unit walks that step, following the method used in the electric-sector quantitative design basis (the DBA-ES-MA-QB), so you can produce the artifact rather than merely describe it.

## Framework and quantification are two documents, on purpose

The first thing to internalize is a division of labor. The qualitative framework — the architecture, the facility classes, the adversary characterization — is one instrument. The quantitative design basis is a separate one that "does not amend the framework; it supplies the numerical bounds and operational acceptance criteria" that make the framework enforceable. As the source puts it: *the framework establishes architecture; the quantitative basis establishes quantitative bounds and operational requirements.* Together they are the complete design basis.

Keep them separate in your own work. The framework answers *what are we protecting and against whom.* The quantitative basis answers *exactly how much, by when, and how do we know it held.* Blur them and you get a document that sounds rigorous and specifies nothing.

## Anchoring the numbers to something defensible

The move that makes a bound "quantitative" is not picking a number — it is anchoring the number to an external standard or an empirical record so it can be defended. The worked example is the control-coordination timing metric, with its two calibration thresholds. The upper bound on the first, roughly thirty minutes, is not chosen for comfort: it is anchored to the reliability standard's own notification window, so that a slower value would make the coordinator non-compliant with an obligation it already carries — "analytically incoherent." The second threshold, on the order of hours, is anchored to the empirical cascade record — the 2003 Northeast blackout's roughly ninety minutes from initiating event to cascade, the 2011 Southwest event's minutes to widespread shedding, the gas-electric cascade of Winter Storm Uri. The resulting bound is "a ceiling, not a target."

That is the discipline: every number traces to a standard you must already meet or an event that already happened. And the bounds differentiate by facility scale — a large balancing authority carries tighter timing than a small one — because a defensible design basis reflects the real consequence, not a single convenient figure.

## Where the adversary re-enters the arithmetic

Here is the move that separates a safety design basis from a DBA-MA one. Once your timing bound is written down, assume the adversary reads it. An attacker who knows the recovery must complete within a stated window can calibrate an attack — for instance, degrading control-system availability — to simply *outlast* that window. The source's blunt conclusion: an adversary who cannot be dislodged within the recovery bound "has, by design, achieved a [severe] consequence" through cyber means alone. So the acceptance criterion must change: recovery has to execute *against active adversarial persistence*, not merely against equipment that failed and stayed failed. The number that was safe against accidents is not automatically safe against an adversary who has read it.

## The stress-test methodology

The quantitative basis is validated by a repeatable five-step stress test: extract the governing timeline or bound; surface the assumptions baked into it; test those assumptions against pattern-attack conditions (coordinated multi-facility combinations, not single failures); determine where and by how much they break; and state the corrected design-basis requirement. Running it surfaces the finding that matters most for OT practitioners: under coordinated attack, "the consequence is not additive — it is multiplicative." Two facilities lost together are worse than the sum of each lost alone, because their recovery paths depend on shared, scarce resources.

Which is the last piece of realism: the numbers have to account for **concurrent demand** on finite spares. When restoration leans on long-lead components — extra-high-voltage transformers at eighteen-to-twenty-four months, converter transformers at twelve-to-eighteen, large turbine rotors past two years — a design basis that assumes each facility can independently draw a spare is fiction under a pattern attack. And a mitigation you have specified but never exercised does not count: *channels that are installed but untested are not a design-basis asset.*

## For your capstone facility

Take the facility-class design basis you will build in the capstone and push one consequence all the way to a number. State the bound, name the standard or event you anchored it to, then ask the adversary question: could an attacker who read this bound calibrate around it? Rewrite the acceptance criterion to survive that. You have now done, in miniature, exactly what the quantitative design basis does at sector scale — and it is the deliverable the OT branch is preparing you to produce.
