---
skill: claim-check
skill_version: 43c23b68b820d5d1df78bccece6987ed303c7543
agent: claude-sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (cloud scheduled session)
date: 2026-11-20
outcome: partial
---

## Task

Daily independent participation run under the scheduled-task prompt that
drives this repository's daily claim-checks. Reciprocity first, per
`README.md`; an independent claim-check if nothing is waiting.

**Reciprocity check.** The only open pull request is still #83, the
weekly deadline watchdog's proposed revert of the overdue
`boundary-fast-track-limits` containment (opened 2026-09-28, draft,
labeled `custodian-required`). It is now 53 days open with no recorded
custodian action in the file or on the PR. It touches `CHARTER.md`, so
per `CLAUDE.md` non-negotiable #2 I cannot merge or act on it beyond
noting it again here; it needs the custodian, not a countersign.

I also re-checked the six `decisions/` files still carrying
`status: provisional` with a confirmation deadline, since one of them
(`2026-08-23-fixed-list-amendment-path.md`) has a 2026-11-22 deadline
only two days out. Per `skills/decide`'s own rule, passing that date
does not auto-revert the text; it only triggers a scheduled check to
open a ratify-or-revert PR for the custodian, so nothing is due from a
countersign today, and no such PR exists yet. I am also not an eligible
countersigner for that specific decision regardless of timing: it is
the amendment path for charter section 9, and that decision's own text
explicitly excludes "a countersign the custodian personally solicited
from an AI model in a session the custodian controls," which is exactly
what this scheduled task is. Noting the deadline again rather than
attempting a countersign I am not positioned to give.

`appeals/` still holds only its own `README.md`, no open appeal file.
No skill has moved past `state: proposed` (checked all four
`skills/*/SKILL.md` directly), so the countersign-for-promotion
mechanism does not apply to anything right now. Of the reports filed
since the last several passes, all are this same scheduled task; nothing
open today is both waiting for a countersign and something I am
eligible to give under the countersign rule. Proceeding to an
independent claim-check per step 2.

**Category rotation.** Recent picks per the last several reports' own
logs: 11-14 political, 11-15 citations, 11-16 health, 11-17 conspiracy,
11-18 political, 11-19 citations. That is a clean four-category cycle
(political, citations, health, conspiracy); the next slot is health.
Picking category (b): a current health claim, specifically one that
sits on the boundary with pseudoscience, since the clearest currently-
circulating example I found straddles both.

## Target

The claim, posted on X by Alex Jones/Infowars and reported to have drawn
over 340,000 views, that "a real-world, peer-reviewed study found that
ivermectin and mebendazole caused cancer to completely disappear,
shrink, or stop spreading in 84.4% of patients within six months." The
underlying paper is "Real-World Clinical Outcomes of Ivermectin and
Mebendazole in Cancer Patients" (Hulscher, Pinsky, Thorp, McCullough, et
al.), first posted to Zenodo as a preprint on 2026-04-07 and later
published in *Anticancer Research*. This is current, not stale COVID-era
material: a follow-up literature-review paper from the same author group
("Combination Ivermectin and Mebendazole... 25 human cancer types") was
posted to Zenodo on 2026-10-19, and secondary reporting states The
Wellness Company (TWC), the telehealth company that sells the drug
combination and employs the paper's authors, continues to promote the
84.4% figure into the current period. This has real stakes: it is
actively used to market an off-label cancer treatment to patients
weighing it against, or alongside, conventional oncology care.

I attempted the journal's own article and retraction-notice pages
directly (`ar.iiarjournals.org`) four times, at different URLs
(`/content/46/6/3243`, `/content/46/10/5877.full.txt`,
`/content/anticanres/46/10/5877.full.pdf`). All four returned HTTP 403
to this session's fetch tool. I did not route around this with a
different user agent or tool; I used the fetchable sources below
instead and say plainly, as in the 2026-11-19 report, that this means my
strongest claims below rest on secondary reporting that itself quotes
the journal, not on text I read from the journal directly.

Fetched directly (not via search-tool synthesis):

- Science-Based Medicine, "Can Ivermectin and Mebendazole Treat Cancer?"
  (pre-retraction analysis), fetched 2026-11-20,
  `https://sciencebasedmedicine.org/can-ivermectin-and-mebendazole-treat-cancer/`
- Science-Based Medicine, "Retracted study of ivermectin and
  mebendazole for cancer removed by publisher," fetched 2026-11-20,
  `https://sciencebasedmedicine.org/retracted-study-of-ivermectin-and-mebendazole-for-cancer-removed-by-publisher/`
- Black Dot Research fact-check, fetched 2026-11-20,
  `https://blackdotresearch.sg/?p=16317` (dated 2026-08-20 on the page)
- Lead Stories fact-check, fetched 2026-11-20,
  `https://leadstories.com/hoax-alert/2026/04/fact-check-preprint-study-claiming-84-4-percent-clinical-benefit-ivermectin-mebendazole-cancer-treatment-not-proper-clinical-trial.html`
  (dated 2026-04-15)

Reached only through a WebSearch tool's own synthesis, not independently
fetched, and treated accordingly below as weaker: TechARP's retraction
coverage and its "25 cancers" follow-up piece (both returned 403 to
direct fetch), and claims about TWC's current website content.

## Claims and sorting

1. "A real-world, peer-reviewed study found" the 84.4% result — checkable
   now, in two parts: peer-review status, and whether "found" still
   holds given what happened to the paper afterward.
2. "Ivermectin and mebendazole caused cancer to completely disappear,
   shrink, or stop spreading in 84.4% of patients" — checkable now,
   against the study's own reported breakdown of that 84.4% figure.
3. The study had no control group — checkable now.
4. Outcomes were self-reported by patients, with no scans or blood tests
   ordered or reviewed to confirm them — checkable now.
5. Most patients were concurrently receiving conventional cancer
   treatment during the study period — checkable now.
6. All authors are affiliated with or salaried by The Wellness Company,
   which sells the exact drug combination studied — checkable now.
7. The journal retracted the paper outright (not merely flagged it) —
   checkable in principle; checkable by me only at one remove, since the
   journal's own notice was unreachable.
8. TWC continues to display the 84.4% figure and disputes the
   retraction — checkable in principle, not checkable by me in this run
   (I did not independently reach TWC's site).

## Checking the claims

**Claim 1: "peer-reviewed study... found."**

The paper's history has three distinct states, not one. It was first
posted to Zenodo on 2026-04-07 as an unreviewed preprint; Lead Stories'
2026-04-15 fact-check explicitly notes "the paper doesn't mention peer
review" at that stage, which was correct at the time. Science-Based
Medicine's retraction-coverage piece gives a timeline in which the paper
was subsequently peer-reviewed and published in *Anticancer Research*
(submitted 2026-04-08, accepted 2026-04-24, published 2026-05-27), then
received an Expression of Concern (dated either 2026-06-01 or
2026-06-09 depending on which part of the record SBM is citing, a
discrepancy SBM itself flags as unreconciled), then was retracted
outright around 2026-10-01 per SBM's account.

Verdict: **contradicted**, for a claim made or repeated now, in the
present tense, without qualification. The paper did briefly exist in
peer-reviewed form, so "peer-reviewed" was not fabricated out of
nothing, but presenting it today as live peer-reviewed support, with no
mention that the journal has since withdrawn it, misstates its current
status. **Supported only for a narrow historical window** (roughly
2026-05-27 to 2026-06-01), which is not the window this claim is
actually being used in.

**Claim 2: the 84.4% breakdown.**

Science-Based Medicine quotes the paper's own reported components
verbatim: "Clinical Benefit Ratio (CBR) (the sum of NED+Regression+Stable)
(84.4%)," broken out as "No current evidence of disease (NED) (32.8%)"
and "regressed (15.6%)," i.e. 48.4% combined, with the remaining 36
points coming from patients whose disease was merely "Stable" (not
progressing).

Read literally, the viral wording ("disappear, shrink, or stop
spreading") maps onto these three components reasonably well: NED =
disappear, regression = shrink, stable = stopped spreading. I did not
expect this going in; my first instinct was to call the composite
wording itself misleading, which the self-check below records. The
actual problem is not that the three-way description is invented, it is
that "stable" disease in patients who were simultaneously on
conventional treatment (claim 5) cannot be attributed to the two
repurposed drugs, and none of the three components was confirmed by
imaging or lab work (claim 4) rather than by patient self-report.

Verdict: **supported** for the literal composite ("84.4% disappeared,
shrank, or did not progress" is numerically what the paper's own table
says). **Unverified, trending toward unsupported**, for the implied
claim that the drugs caused this outcome, which is a separate claim the
184.4% figure alone cannot carry, addressed in claims 3-5.

**Claim 3: no control group.**

Science-Based Medicine states this as a direct quotation: "No control
group." It adds, also quoted directly: "Without a control group, it is
impossible to know if treatment with ivermectin/mebendazole influenced"
[outcomes]. Lead Stories independently quotes a named reviewer, Yang:
"There is no control group who didn't receive ivermectin and
mebendazole." Two independently-fetched sources, in their own words,
agree.

Verdict: **supported**.

**Claim 4: self-reported outcomes, no scans or blood tests.**

Science-Based Medicine, quoted directly: "TWC authors assessed cancer
status based solely on patient-reported data... No scans were ordered or
reviewed. No blood tests were ordered or reviewed." Lead Stories
independently quotes reviewer Yang: "All outcomes are self-reported,"
and separately quotes reviewer Meyerowitz-Katz confirming the surveys
were anonymous per the paper's own methodology section. Also relevant:
only 122 of the original 197 patients (61.9%) completed follow-up at
all, per Black Dot Research.

Verdict: **supported**.

**Claim 5: concurrent conventional treatment.**

Lead Stories, quoting the paper's own reported baseline figures: 42.1%
of patients had had or were having surgery, 31.5% had had or were having
chemotherapy, during the same six-month window the drug combination was
credited with the outcome. Science-Based Medicine corroborates in less
precise terms: "Most patients had already undergone conventional therapy
... Many continued to receive treatment during the 6 months of the
study."

Verdict: **supported**.

**Claim 6: conflict of interest.**

Science-Based Medicine, quoted directly: "All of the authors of the
paper are affiliated with and/or salaried by the Wellness Company,"
adding "This is disclosed openly" in the paper itself, and separately
naming Peter McCullough, MD, as TWC's "chief scientific officer." This
is a disclosed, not hidden, conflict, which the paper's own authors
acknowledged, but it is still a conflict worth stating alongside the
headline figure, since TWC sells the exact combination studied.

Verdict: **supported**.

**Claim 7: outright retraction.**

Science-Based Medicine states, in its own article title, "Retracted
study of ivermectin and mebendazole for cancer removed by publisher,"
and separately, quoting what it presents as the retraction notice's own
language: "methodological and analytical problems undermine the
reliability of its central clinical-benefit conclusions." This is a
named, identifiable secondary source directly stating retraction, not a
bare search-engine summary, and I fetched it myself rather than relying
on a tool's synthesis of it.

Verdict: **supported, but at one remove**. I could not reach
`ar.iiarjournals.org` directly in four attempts (see "Where the
instruction did not match reality"), so this rests on Science-Based
Medicine's account of the notice, not the notice itself. I am not
treating "one secondary source quoting a primary document" as
equivalent to having read the primary document, per the skill's own
distinction between a source and a description of a source.

**Claim 8: TWC continues to promote the figure and disputes retraction.**

Only reached through a WebSearch tool's synthesis, which I did not
independently verify by fetching TWC's own site. Per the same lesson
the 2026-11-19 report named (a tool's own synthesized summary is not a
source), I am not recording a verdict beyond: **unverified by me in
this run**, flagged rather than asserted, even though it is the detail
that would most directly establish this is still live, present-tense
circulation rather than an April 2026 episode that has since been
resolved and dropped. The 2026-10-19 follow-up Zenodo preprint from the
same author group, which I confirmed through two independently-reached
secondary sources describing it consistently, is what I am actually
relying on to establish currency, not the TWC-website claim.

## Where the instruction did not match reality

`skills/claim-check` step 3 asks for "an exact, checkable reference" and
treats "search results describing X" as insufficient. The one truly
primary source for this entire target, the journal's own article and
retraction-notice pages, returned HTTP 403 on every direct fetch attempt
I made (four, across three different URL paths on the same domain). This
is the same failure mode the 2026-11-19 report hit with a different
publisher's domain, which suggests this session's fetch tool is blocked
by a non-trivial share of news and journal publishers outright, not
occasionally. I did not attempt a workaround once blocked; I used
directly-fetched secondary sources that themselves quote the primary
document, and I have flagged every verdict above that rests on that
one-remove sourcing rather than silently upgrading it to a clean
`supported`.

Separately: my first read of claim 2 assumed the viral wording
("disappear, shrink, or stop spreading") was itself a misleading
compression of the 84.4% figure. Once I had the paper's own component
breakdown in hand, the literal wording turned out to track the
components reasonably well; the actual weakness is attribution (no
control group, concurrent treatment), not the three-way description.
I am recording this because the skill's step 5 self-check asks where I
would have written what sounded right rather than what I verified, and
this is exactly that: my first-pass framing would have overstated the
finding in the other direction.

## Proposed change

None. `skills/claim-check` step 3 already distinguishes a source from a
description of a source, and that distinction is what caught both my own
near-miss on claim 2 and the WebSearch-synthesis caveat on claim 8. I
have no concrete edit to propose from this run; the instruction held.

## Self-check

- The verdict I am least confident calling `supported` outright is
  claim 7 (retraction). It rests on one secondary source's account of a
  primary document I could not reach myself, however directly I quoted
  that secondary source. I labeled it "supported, but at one remove"
  rather than plain `supported` for this reason.
- I came closest to writing what sounded right, rather than what I had
  verified, on claim 2 on my first pass, before I had the paper's actual
  NED/regression/stable breakdown in hand. I recorded the correction
  above rather than quietly fixing my own framing and not mentioning it.
- Claim 8 is the one place I am confident I avoided repeating the
  2026-11-19 report's mistake: a WebSearch synthesis offered a specific,
  usable claim (continued TWC promotion), and I declined to record a
  verdict on it rather than fold an unverified search summary into
  `supported`.
- Reciprocity: as in every recent report, this is a solo Anthropic/Claude
  run with no second vendor currently available to countersign it. I
  also want to flag, beyond the routine note, that the approaching
  2026-11-22 deadline on `fixed-list-amendment-path` is a real,
  structurally important date (it is the provisional status of charter
  section 9's own amendment path), and that I am specifically not the
  participant who can resolve it, by the charter's own design. If no
  genuinely external, disinterested participant appears before then,
  that deadline will pass with the gap unresolved, same as it has every
  day I have checked it.
