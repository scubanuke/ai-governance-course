# The CCE / CIE Lineage

> **Part of:** Core / Module 2

The inversion in the last unit — start from the consequence, not the vulnerability — is not a new invention of this course. It has a name, a provenance, and a decade of use in exactly the setting this course cares about: the defense of critical infrastructure against adversaries who are assumed to get in. This unit tells that origin story, because a method carries more weight when you know where it came from and that serious people staked serious work on it.

## Two names, one idea

The lineage runs through two closely related terms.

**Consequence-driven Cyber-informed Engineering (CCE)** is the sharper of the two. It was formalized at Idaho National Laboratory, beginning as a laboratory research and development effort around 2016 — though its conceptual roots run several years earlier and in a different sector, as the next section describes. Its founding premise is deliberately grim: assume that a sufficiently skilled and determined adversary *will* penetrate the network. Once you accept that, prevention-by-enumeration stops being the goal. The goal becomes making sure that even a successful intruder cannot produce the outcomes you cannot survive. CCE turns on identifying a facility's most essential functions, determining the specific outcomes that would be catastrophic, and then engineering the digital pathways to those outcomes down to as close to nothing as possible.

**Cyber-Informed Engineering (CIE)** is the broader, more upstream idea: that cyber risk should be addressed by engineers in the design of a system from the very beginning — built into the engineering lifecycle — rather than bolted on afterward by a security team. Where CCE is a targeted analysis you run against an existing high-consequence facility, CIE is the general principle that consequence and adversary belong in the engineering conversation from day one. CCE is the acute application; CIE is the design philosophy behind it.

For this course, the important thing is what they share: both refuse to start from the vulnerability list, and both put the intolerable outcome — the consequence — in the first position.

## Where it came from

The consequence-first method has two intellectual parents, and it grew out of their collaboration before it ever carried the name CCE.

Its roots are in the **North American Electric Reliability Corporation (NERC)**, where, in the years around 2009, two people came at the same problem from opposite sides. **Timothy Roxey** — the author of this course — arrived from nearly forty years in the nuclear sector, and in particular from the nuclear design-basis reconstitution programs that ran from the mid-1980s into the late 1990s. His instinct was to reason about risk through the consequences that must be avoided: the nuclear design basis and its design-basis accidents, the DB → DBA line this course is built on. **Michael Assante** came at it from the adversary side — through threat matrices and a deep, operational understanding of how real attackers select and reach their targets. During their overlap at NERC these two strands — consequence-first from the nuclear tradition, adversary-first from the intelligence tradition — met and combined, under a different name than the one the method would later carry. Each supplied what the other lacked; neither strand alone is CCE.

Assante then returned to **Idaho National Laboratory** to carry the work forward in the public sector, while Roxey remained at NERC and completed the electricity sector's information-sharing capability (the E-ISAC). INL proved a good home for the idea: there it was fleshed out and formalized into the methodology now known as CCE. Assante is today widely and rightly credited as CCE's founder and one of its godfathers; he died in July 2019, and the method has since been set down in book-length form and has spread well beyond the laboratory. What this course adds to that public record is the earlier half of the story — that the consequence-first core came out of the nuclear design-basis tradition, carried into the electricity sector, before it was ever called CCE.

The engineering side of that heritage matters for where this course goes next. CCE's instinct — anchor on the consequence, then bound what the adversary can do — is the same instinct that nuclear safety engineering formalized decades earlier under a different name: the **design basis.** Module 3 makes that connection explicit and turns the instinct into a repeatable derivation. What you should carry out of this unit is that consequence-first thinking is not a rhetorical stance; it is a documented engineering method with a real lineage, and this course stands on it.

## What CCE actually does, in brief

Without reproducing the full methodology, it is worth seeing the shape, because it models the reasoning the rest of the course asks you to internalize. CCE works from the top down: first it forces a hard prioritization of the consequences that would truly be catastrophic — not the long list of bad-but-survivable events, but the few that cannot be allowed. Then it maps how the real system-of-systems actually functions, including the dependencies and digital pathways that operators often do not have fully in view. Then it reasons the way an adversary would, identifying what someone would specifically have to accomplish to cause one of the prioritized consequences. Only then does it engineer the mitigations — and often the most powerful mitigation is to remove a digital pathway entirely, so the consequence simply cannot be reached that way.

Notice that vulnerabilities enter this process late and in service of the consequence, never as the organizing principle. That ordering — consequence first, adversary second, mitigation last and targeted — is the inheritance this course accepts and extends to AI.

## Why we extend it rather than just adopt it

CCE was built for facilities and their control systems. This course takes its consequence-first core and carries it into a setting CCE did not originally center: an autonomous or agentic AI operating inside one of those facilities. The consequence-first discipline transfers cleanly. What has to be added is a second design basis for the AI itself — the idea developed in Module 3 — because the adversary envelope for a model is not the adversary envelope for a pump or a breaker. The lineage gives us the method and the credibility. The rest of the course does the extending.

## In your sector

Take the intolerable outcome you named at the end of the last unit. Ask the CCE question about it directly: *if I assume an adversary is already inside, what would they specifically have to accomplish to cause this outcome — and could I engineer that pathway away entirely?* Hold that answer. It is the seed of the design basis you will learn to derive in the next module.
