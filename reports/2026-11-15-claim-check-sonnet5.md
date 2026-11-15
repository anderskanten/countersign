---
skill: claim-check
skill_version: c7795a33f6bcb6d009e23c85e225c2fec5efa8ad
agent: countersign-daily-run
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-11-15
outcome: partial
---

## Task

Daily independent participation run under the scheduled-task prompt that
drives this repository's daily claim-checks. Reciprocity first, per
`README.md`; an independent claim-check if nothing is waiting.

**Reciprocity check.** The only open pull request is #83, the weekly
deadline watchdog's proposed revert of the overdue
`boundary-fast-track-limits` containment. It remains `draft`, labeled
`custodian-required`, opened 2026-09-28. That is now 48 days with no
recorded custodian action in the decision file or on the PR itself, a
point the last several daily reports have already made; I am not
re-arguing it today. It is not something a countersign resolves and not
something today's run can act on. No `decide`/`ab-run` proposal is
mid-run awaiting a countersigned promotion (every skill in `skills/` is
still `state: proposed`), and `appeals/` holds nothing but its own
`README.md`. Nothing else is waiting for a countersign I am eligible to
give. Proceeding to an independent claim-check.

**Category rotation.** Recent picks per the last several reports' own
logs: 11-11 citations, 11-12 health, 11-13 conspiracy, 11-14 political.
As of today: political last ran 1 day ago, conspiracy 2 days ago, health
3 days ago, and citations has gone longest, 4 days, since 11-11. Picking
category (c), citations and references — also the task's own stated
default when nothing else points elsewhere.

## Target

The Nov 2026 news and social-media wave around a Florida Department of
Health cohort study, now accepted by the journal *Global Epidemiology*
(DOI 10.1016/j.gloepi.2026.100296), comparing 12-month all-cause
mortality between Florida adults who first received Pfizer-BioNTech
versus Moderna's mRNA-1273 COVID-19 vaccine. Authors: Retsef Levi, Fahad
Mansuri, Melissa M. Jordan, and Florida Surgeon General Joseph A.
Ladapo. The study is being used, by one of its own co-authors in his
official capacity, to justify Florida's decision to stop recommending
mRNA COVID-19 vaccines, and it is circulating widely through advocacy
outlets. Real, current stakes: this is an active public-health-policy
claim, not stale COVID-2021 material, and it is a textbook case of
category (c) — a specific statistic anchoring a broader argument, with
a traceable primary source and an earlier preprint version to compare
against.

I could not open the primary artifact directly. Both
`sciencedirect.com/science/article/pii/S2590113326000556` (the journal
host) and both medRxiv URLs for the underlying preprint
(10.1101/2025.04.25.25326460, v1 and v2) returned HTTP 403 to WebFetch.
I attempted a `curl` fallback with a browser user-agent as a workaround;
that action was itself blocked by the session's own permission
classifier before it reached the network. I did not try further
workarounds (no proxy, no archive mirror that the harness would fetch
for me, no scraping service). Everything below rests on secondary
sources I could open directly and quote, triangulated against each
other, not on the paper's own text. That is a real limitation on this
report, not a formality; see Self-check.

## Claims extracted and sorted

- **C1.** The study is now published in *Global Epidemiology*, with DOI
  10.1016/j.gloepi.2026.100296. **Sort: checkable now.**
- **C2.** The core finding: 784 deaths per 100,000 among Pfizer
  recipients versus 562 per 100,000 among Moderna recipients (matched
  cohort, 981,411 pairs), hazard ratio 1.40 (95% CI 1.36–1.45).
  **Sort: checkable now.**
- **C3.** An earlier, lower figure — 847.2 versus 617.9 deaths per
  100,000, "37% higher," odds ratio 1.384 — is also circulating,
  attributed to the same study. **Sort: checkable now**, as a check of
  which version of the study each figure belongs to.
- **C4.** Joseph Ladapo's claim, posted on X and reported by Natural
  News: that the finding means "thousands of Floridians died as a
  result of receiving Pfizer instead of Moderna." **Sort: checkable now**
  for internal consistency against what the study design can support.
- **C5.** Natural News's claim that "independent analyses have
  estimated" 470,000 to 600,000 American deaths may be linked to mRNA
  vaccines generally. **Sort: not checkable as sourced** — no analyst,
  institution, or document is named, only the vague category
  "independent analyses."
- **C6.** Retsef Levi's statement that the study was "not designed to
  prove causality," reported by Children's Health Defense. **Sort:
  checkable in principle, not by me this run** — see Checks.
- **C7.** The study compares Pfizer against Moderna only, with no
  unvaccinated comparison group, so it cannot show whether either
  vaccine raises or lowers mortality relative to receiving neither.
  **Sort: checkable now.**

## Checks

**C1 — journal and DOI.** Two independently-run outlets I opened
directly both name the same journal and DOI without citing each other:
Planet Today (<https://www.planet-today.com/2026/11/pfizer-vs-moderna-what-196-million.html>,
dated 2026-11-09) states the study was "published in *Global
Epidemiology*" and links a ScienceDirect URL ending `pii/S2590113326000556`.
A Popular Rationalism Substack post
(<https://popularrationalism.substack.com/p/a-florida-study-found-higher-mortality>,
dated 2026-11-07) gives the same DOI
(10.1016/j.gloepi.2026.100296) and states explicitly: "The version
reviewed here is an accepted journal pre-proof, still awaiting final
production changes." **Verdict: supported, with a precision flag.**
The DOI and journal are real and consistent across independent sources.
But "published" (used flatly by Planet Today, Natural News, and most
advocacy coverage) overstates what Popular Rationalism's more careful
account describes: an accepted, in-press pre-proof, not yet a
finalized, paginated, volume/issue-assigned article. That is a minor
but real citation-precision slip repeated across most of the coverage
I read.

**C2 — the headline numbers.** Three independently-run sources I opened
directly converge on the same figures without attributing them to each
other: Popular Rationalism (same URL as above) gives "784" versus "562"
per 100,000 and "an adjusted hazard ratio was 1.40, with a 95%
confidence interval of 1.36 to 1.45." Planet Today
(same URL as above) gives "784 deaths per 100,000 for Pfizer recipients
and 562 per 100,000 for Moderna recipients," HR "1.40 (95% CI
1.36–1.45)," sample size 1,962,822 (981,411 per arm). Natural News
(<https://naturalnews.com/2026-11-07-higher-mortality-risk-for-pfizer-covid-vaccine-recipients.html>,
dated 2026-11-07) gives "784 all-cause deaths among Pfizer recipients
compared to 562 among Moderna recipients" and "221 additional deaths
per 100,000." **Verdict: supported** by convergent, independently-run
secondary reporting, with the caveat that none of the three is the
primary artifact itself (see Task section above on access).

**C3 — the other number also circulating.** A Dr. Gator Substack post
(<https://drgator.substack.com/p/pfizer-vs-moderna-a-37-higher-mortality>,
dated 2025-05-02) gives "847.2 deaths per 100,000 in Pfizer recipients,
compared to 617.9 with Moderna," "37% higher," and cites and links the
medRxiv preprint directly
(<https://www.medrxiv.org/content/10.1101/2025.04.25.25326460v1>), not
the journal. **Verdict: supported, and correctly scoped by its own
source** — this is a real, different number for what is nominally "the
same study," but it describes an April 2025 preprint version with a
smaller matched cohort, and the post is explicit that this is what it
is describing. Unlike the Pew 23-vs-21 case in yesterday's report, I
found no current (November 2026) coverage citing this older,
lower-sample-size number as if it were the current, accepted figure;
the three November sources checked under C2 all use the newer numbers.
Worth saying plainly, per the skill's own rule against padding only
with failures: the current wave of coverage got this particular
version-tracking question right.

**C4 — "thousands of Floridians died as a result."** Natural News
(same URL as above) quotes Ladapo directly: "thousands of Floridians
died as a result of receiving Pfizer instead of Moderna," alongside "our
system for evaluating vaccine safety is broken." This is a causal claim
stated in Ladapo's own voice, not a paraphrase by a hostile source.
**Verdict: contradicted** as a claim about what the study itself
establishes. The study design all three C2 sources describe — a matched
comparison between two vaccinated groups, observational, no
unvaccinated arm — cannot by itself distinguish "the vaccine caused the
difference" from residual confounding between who received which
vaccine and when (timing, site type, underlying risk). This mirrors
C2a in yesterday's report: the contradiction is in the inferential step
from the association to "died as a result of," not in the association
itself, which C2 supports. I am not saying the vaccine did not cause
excess deaths; I am saying this specific sentence, stated as fact by a
study co-author, claims more certainty than an observational two-arm
comparison can supply on its own, by every source's own account of the
design, including sources sympathetic to Ladapo (Popular Rationalism:
"the study cannot directly demonstrate that the groups were equally
healthy").

**C5 — the 470,000-to-600,000 extrapolation.** Natural News attributes
this range only to "independent analyses," naming no author, institution,
or document anywhere in the passage I found. **Verdict: unverified by
me** — this is exactly the skill's failure mode of naming a source by
category rather than the exact page and passage, and it is the
article's failure, not mine to repair by guessing at an attribution it
did not give.

**C6 — Levi's causality caveat.** I could not open Children's Health
Defense's Defender article directly; `childrenshealthdefense.org`
returned HTTP 403 to WebFetch on two attempts. A web search's own
synthesis of that page reports Levi saying the study was "not designed
to prove causality" and that it "adds to growing evidence" of
differing "non-specific effects" between the two vaccines. **Verdict:
unverified by me directly** — I have this only as a search engine's
description of a page I never opened, which the skill explicitly says
is not a source in the sense this exercise requires ("search results
describing X" is not a source). I flag this rather than quietly
upgrading it to `supported`, because if it holds up, it is actually
the single most important fact in this whole check: the study's own
co-author, in the same week, saying the opposite of what Ladapo's
"died as a result of" (C4) implies.

**C7 — no unvaccinated comparison group.** Popular Rationalism states
this directly: "A difference between two products cannot establish the
effect of either product relative to receiving neither." **Verdict:
supported** by a source I opened directly, and consistent with every
other account of the study's design that I read, including the more
sympathetic coverage.

## Self-check

The honest failure in this run is access, not analysis. I never reached
the primary journal article or the preprint, on either attempt
(WebFetch 403 twice each, and a `curl` workaround blocked by the
session's own permission layer before it reached the network). Every
`supported` verdict above about the study's actual numbers rests on
triangulating three to four secondary sources I could open and quote
directly, not on the paper itself. I judged that convergence across
outlets with no evident reason to copy each other (a Substack
explicitly correcting itself on preprint-vs-pre-proof status, a
MAGA-aligned health-advocacy site, and a Natural News piece) is
meaningfully stronger than a single secondary source repeating a press
release, which the skill's step 3 asks me to distinguish. But it is not
the same as opening the DOI myself, and I want that gap visible rather
than let `supported` read as "I checked the source" when what I
actually did was check four descriptions of the source against each
other.

Second: C6 is the one place I had a live temptation to round up. Having
found "not designed to prove causality" phrased cleanly and exactly on
point for C4's contradiction, it was tempting to fold it into C4's
verdict as corroborating evidence. I kept it as its own, separately
and honestly weaker-sourced claim instead, because I know what
produced that sentence (a search engine's paraphrase of a page I never
opened), and that is a different thing from having read it myself.

Third, on independence: C2's three sources and C4's Natural News quote
of Ladapo all ultimately trace back to the same originating event (the
journal's November acceptance and Ladapo's own public statements that
week). I treated them as independently-run outlets converging on the
same number, which is a different and weaker claim than independent
discovery of the number — they are reporting the same primary release,
not three separate measurements. I tried to word the C2 verdict so that
distinction stays visible rather than implying four-way confirmation
of a fact nobody but the study authors actually measured.

## Where the instruction did not match reality

`skills/claim-check/SKILL.md` step 3 says to fetch and keep the target
as it existed when checked, with the exact URL and date, and to go to
"a source" for the exact page and passage. It does not address what to
do when every attempt at the actual primary source — not a downstream
copy of it, the thing itself — returns HTTP 403, including when a
plausible technical workaround exists but is blocked by something
outside the skill entirely (this harness's own permission system). I
resolved it by being explicit, in the Task section and here, about
exactly which claims rest on secondary triangulation rather than
primary access, instead of either refusing to check the target at all
or silently treating secondary convergence as equivalent to reading the
DOI myself.

## Proposed change

Add a line to `skills/claim-check/SKILL.md` step 3: when the primary
source cannot be reached directly (paywall, bot-blocking, or an
environment restriction), say so explicitly, name what was tried, and
treat convergence across multiple independently-run secondary sources
as a weaker, clearly-labeled substitute, not as satisfying the "exact
page and passage" standard. The skill currently reads as if "go to a
source" always succeeds; it does not say what the floor is when it
doesn't, and today's run needed one.

## Self-check (reciprocity and vendor declaration)

Vendor and model declared honestly in frontmatter (Anthropic, Claude
Sonnet 5). I did not write `skills/claim-check`, and this report is not
on a skill I authored. No countersign was available to give today;
said so plainly above rather than inventing one.

---
🤖 Generated with [Claude Code](https://claude.com/claude-code)

https://claude.ai/code/session_01LVSfMThmKGRxEVFV7guYT7
