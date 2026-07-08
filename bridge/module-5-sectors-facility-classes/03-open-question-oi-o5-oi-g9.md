# Open Question: Strategic Significance vs. Deliverability (OI-O5 / OI-G9)

> **Part of:** Bridge / Module 5
> This unit is different from the others. It does **not** hand you a resolved answer, because the question it raises is genuinely open in the framework itself — tracked as an unresolved parent-level issue in the oil and gas series (OI-O5 / OI-G9). Your job here is not to learn the answer. It is to practice reasoning inside a question that does not yet have one. That is the skill an advanced practitioner actually needs.

## The tension

You have now seen two different ways a facility earns its place inside a design basis. The applicability gate makes them explicit. One is **strategic significance**: the facility matters because of *where it sits and whom it serves* — a defense-critical load, a strategic corridor, a position an adversary would target in a pattern attack (filters 1, 2, and 4). The other is **deliverability consequence**: the facility matters because of *what its loss does to supply* — how much throughput or buffer it provides and how poorly that function can be substituted (filter 3, and the storage-and-supply reasoning behind it).

Most of the time these point the same way, and the question never surfaces. The open question is what to do when they **diverge** — and for marine terminals and LNG facilities, they diverge often.

## Where marine and LNG make it sharp

Consider two facilities that pull the axes apart.

An **LNG import terminal** may carry enormous deliverability consequence — it is the backup supply that covers a pipeline outage, days-to-weeks of buffer, the high-deliverability capacity a grid leans on during a cold-snap emergency — while sitting nowhere near a defense-critical corridor. Its importance is almost entirely a *deliverability* consequence, not a strategic-position one.

A **marine terminal** can present the mirror image: sited on a strategic corridor or coastline that gives it clear strategic significance, yet highly substitutable, so that its loss is absorbed quickly by rerouting and alternate supply. Its importance is almost entirely a *strategic-significance* consequence, with modest deliverability weight.

Both are plausibly in scope. But they are in scope for opposite reasons, and that is where the architecture has to make a choice it has not yet made.

## Why it is genuinely unresolved

The applicability gate handles this cleanly for the *in-or-out* question: it is disjunctive, so either axis alone brings a facility into scope, and the divergence causes no trouble at the applicability level. The open question lives one level up, at the **parent-level definition of the class itself**: when you carve a facility class and set its consequence anchor, do you define the class primarily on strategic significance, primarily on deliverability consequence, or on some principled combination — and what do you do when weighting one over the other changes which facilities are core members versus edge cases?

This matters because the consequence anchor set at the class level propagates into everything downstream — the design basis, the tiering, the assessment. Anchor the class on strategic significance and the LNG deliverability buffer looks peripheral; anchor it on deliverability consequence and the strategically sited but substitutable marine terminal looks peripheral. The two framings produce different classes, different core members, and different design bases. There is no obviously correct choice, which is precisely why it remains an open issue rather than a settled convention.

## How to reason about it (without resolving it)

Do not reach for a verdict. Instead, practice the moves an advanced practitioner makes when standing inside an open question like this:

Notice, first, that the disagreement is not about facts but about **which consequence axis is primary** — a definitional choice, not a measurement. Ask what each framing optimizes for and what it neglects: strategic-significance framing protects against the adversary's targeting logic but can under-weight quiet supply dependencies; deliverability framing protects continuity of supply but can under-weight facilities an adversary would hit for strategic effect even if the grid could route around them. Then ask the design-basis question the whole course has trained you to ask: *which framing more faithfully anchors on the consequences that must not happen?* — and notice that even that question can be answered two ways depending on whether the must-not-happen consequence is framed as "loss to a strategic adversary" or "loss of supply to the population."

The mark of competence here is not picking a side. It is being able to hold both framings, state precisely what turns on the choice, and reason about the trade cleanly enough that a decision — when someone finally makes it — can be made with eyes open.

## In your sector

Look for the same fault line in your own sector. Is there a facility whose importance rests mainly on *where it sits and whom it serves*, and another whose importance rests mainly on *what its loss does to supply*? If you can find both, you have located your sector's version of this open question — and reasoning about it, without rushing to resolve it, is exactly the advanced skill this unit exists to build.
