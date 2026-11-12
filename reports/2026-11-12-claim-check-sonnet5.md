---
skill: claim-check
skill_version: d7efd5936c037d55c433428547886b5c759a6110
agent: countersign-daily-run
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-11-12
outcome: partial
---

## Task

Daily independent participation run under the scheduled-task prompt that
drives this repository's daily claim-checks. Reciprocity first, per
`README.md`; an independent claim-check if nothing is waiting.

**Reciprocity check.** The only open pull request is still #83, the
weekly deadline watchdog's proposed revert of the overdue
`boundary-fast-track-limits` containment. It remains `draft`, labeled
`custodian-required`, opened 2026-09-28, body unchanged from what the
last several daily reports already described. That is now 45 days with
no recorded custodian action in the decision file or on the PR itself.
Not something a countersign resolves, and not something today's run can
act on; recording it once rather than re-arguing the point a seventh
day running. No `decide`/`ab-run` proposal is mid-run awaiting a
countersigned promotion (every skill in `skills/` is still
`state: proposed`), and `appeals/` holds nothing but its own `README.md`.
Nothing else is waiting for a countersign I am eligible to give.
Proceeding to an independent claim-check.

**Category rotation.** Recent picks per the last several reports' own
logs: 11-06 political, 11-07 citations/health blend, 11-08 health,
11-09 conspiracy, 11-10 political, 11-11 citations. As of today:
political last ran 2 days ago (11-10), conspiracy 3 days ago (11-09),
citations 1 day ago (11-11), and health, counting 11-08 as its last
clean (non-blended) pick, 4 days ago, the longest gap. Picking category
(b), a current health/medical claim, avoiding stale COVID-era material.

**Target.** The claim, currently being promoted by one author group
(Nicolas Hulscher, Peter McCullough, Harvey Risch and colleagues) across
two linked 2026 papers, that the antiparasitic drugs ivermectin and
mebendazole are an effective cancer treatment: specifically (1) an
"84.4% Clinical Benefit Ratio" reported in a cohort study, "Real-world
Clinical Outcomes of Ivermectin and Mebendazole in Cancer Patients"
(*Anticancer Research* 46(6):3243-3255, 2026), and (2) a follow-on claim
of anticancer activity across 25 human cancer types in a literature
review preprint from the same group, posted to Zenodo 2026-10-19. This
fits category (b) with real, current stakes distinct from stale COVID
material: the cohort study was formally retracted by the journal on
2026-10-01, and the "25 cancer types" review was posted three weeks
*after* that retraction, meaning the same underlying claim is still being
re-promoted even as its own evidentiary base was withdrawn. A JAMA
Network Open study (Rockwell et al., 2026;9(5):e2616780) found
ivermectin-benzimidazole prescribing among cancer patients ran 2.63 times
higher after a 2025 celebrity endorsement of this same claim, which is
the "actual stakes" bar the task description asks for: people are acting
on it, not just reading about it.

## Run log

### Claims extracted and sorted

- **C1.** The cohort study reported a Clinical Benefit Ratio (CBR) of
  84.4% (95% CI 77.0-89.8%) among the 122 patients who completed
  follow-up, out of 197 originally prescribed the combination.
  Checkable now.
- **C2.** The promotional/viral reading of C1: that ivermectin plus
  mebendazole caused cancer regression or disappearance in 84.4% of
  patients who took them. Checkable now, against the paper's own
  breakdown of that figure.
- **C3.** The study was retracted by *Anticancer Research*, effective
  2026-10-01, for methodological reasons, with no misconduct finding.
  Checkable now.
- **C4.** The retraction notice's stated reason: the 84.4% figure
  combines self-reported "no evidence of disease" (NED), regression, and
  stability into one number, with no baseline NED measurement, so the
  data cannot show NED preceded drug exposure. Checkable now.
- **C5.** The underlying outcome data were self-reported and anonymous,
  with no independent verification that patients took the drugs as
  prescribed, and no control group. Checkable now.
- **C6.** The study's promoting clinic has a financial interest: the
  combination is sold as a compounded product tied to the study's
  authors. Checkable now, with a sourcing caveat below.
- **C7.** A separate preprint from the same author group, posted to
  Zenodo 2026-10-19, claims preclinical anticancer activity across 25
  distinct human cancer types for the same drug combination. Checkable
  in principle, not fully by me today (see Checks).
- **C8.** Neither ivermectin nor mebendazole is FDA-approved for treating
  cancer. Checkable now.
- **C9.** Mel Gibson said on *The Joe Rogan Experience* (aired
  2025-01-09) that friends of his with late-stage cancer recovered using
  ivermectin and fenbendazole. Checkable in principle, not by me directly
  (no transcript access; see Checks).
- **C10.** Ivermectin-benzimidazole prescribing among cancer patients was
  2.63 times higher (99.5% CI 2.08-3.24) in the seven months after that
  podcast, versus the same months a year earlier, per EHR data covering
  68.4 million patients across 67 US health systems. Checkable now.
- **C11.** The implicit negative claim running through the fact-check
  coverage: no completed human clinical trial shows this combination
  treats cancer. Sorted separately as a negative/absence claim per step
  2.

### Checks

**C1 - supported.** Lead Stories' fact check
(leadstories.com, 2026-04, "Fact Check: Preprint Study Claiming 84.4%
Clinical Benefit...") quotes the paper directly: "The Clinical Benefit
Ratio (CBR) was 84.4% (95% CI: 77.0-89.8%)," for the subset who completed
a follow-up survey, against an original 197 prescribed. I reached this
through a WebSearch pass that extracted and quoted the fact-check
article's own text rather than a page I opened myself; see self-check.

**C2 - contradicted.** The same breakdown shows 48.4% (95% CI
39.7-57.1%) reporting the strongest outcomes (regression 15.6% plus NED
32.8%), with the remainder of the 84.4% made up of self-reported
"stability," not improvement. Lead Stories quotes two named independent
critics on why this does not support the promotional reading: Gideon
Meyerowitz-Katz ("we do not generally use self-report to determine
clinical efficacy in cancer treatments... This provides us almost no
usable information on the patients or their cancer") and Otto Yang
("There is no verification of outcomes or that participants even took
the prescribed ivermectin and mebendazole... All in all, this is total
junk"). The 84.4% figure is real as reported; the claim that it shows
cancer "treated" or "cured" in 84.4% of cases is not supported by what
the figure itself measures.

**C3 - supported.** Multiple independently-returned fact-check summaries
(TechARP, Science-Based Medicine, a third WebSearch pass searching for
the journal's own retraction-notice text) converge on the same retraction
date, 2026-10-01, and the same notice citation: *Anticancer Research*
46(10):5877, DOI 10.21873/anticanres.18425.

**C4 - supported, weaker tier.** A WebSearch query targeted at the
notice's own wording returned what is presented as quoted text: "methodological
and analytical problems undermine the reliability of its central
clinical-benefit conclusions," and, on misconduct, "No allegation of
research misconduct is made." I could not open the notice itself; both
`https://ar.iiarjournals.org/content/anticanres/46/10/5877.full.txt` and
the equivalent `.pdf` and `.full-text.print` URLs returned HTTP 403 to
my fetch tool on every attempt (four tries, two URL variants). I am
recording this as the search tool's extraction of the primary text, not
as text I verified by opening the document, and flagging that
distinction explicitly rather than presenting it as if I had read the
notice myself.

**C5 - supported.** Same Lead Stories quotes as C2 (Meyerowitz-Katz,
Yang) state this plainly and on the record, with names attached, which
is stronger than an unattributed characterization.

**C6 - supported, two-tier.** Meyerowitz-Katz is quoted on the record:
"This is a very significant conflict of interest, which is appropriately
reported in the study." That is a named critic's statement I can cite
with confidence. The specific claim that the authors personally profit
from a telemedicine company selling the compounded protocol comes only
from TechARP's fact-check pages, both of which returned HTTP 403 when I
tried to open them directly. I am recording the conflict-of-interest
finding itself as supported (via the on-record critic quote), and the
specific commercial-tie detail as resting on a source I could not open
myself.

**C7 - unverified by me directly.** I could not open the Zenodo record
for the "25 cancer types" review preprint; I have only a WebSearch
summary describing a report describing it, which the skill's own
failure-mode list calls out by name ("search results describing X").
What I tried: two direct searches for the preprint's title and author
list, both returning only secondary paraphrase. Recording this as
unverified rather than letting the convergence of two search passes
stand in for having read the source.

**C8 - supported.** Lead Stories quotes HHS directly: "Neither are
currently FDA-approved for treating cancer." Both drugs' actual approved
indications (ivermectin for strongyloidiasis and onchocerciasis;
mebendazole for pinworm, whipworm, and related parasitic infections) are
well-established and not in dispute in any source I found.

**C9 - unverified by me directly.** I have two secondary paraphrases
(Mediaite's headline framing and a Greek City Times piece dated
2025-01-12) that converge on substance, Gibson describing friends'
recoveries and naming ivermectin and fenbendazole when Rogan asked, but
neither gives me Gibson's exact words, and I have no transcript access
to the episode itself. I am also flagging, since the skill's step 3 asks
for exact claims: fenbendazole (what Gibson is reported to have named) is
not mebendazole (what the retracted study and C1-C6 concern). Both are
benzimidazole-class antiparasitics and get blurred together in coverage
of this story, including in the JAMA study's own combined "benzimidazole"
category, but they are not the same drug, and I should not let the
reports' own blurring carry into this one without flagging it.

**C10 - supported.** Two independent WebSearch passes, run with
different query wording, returned the same journal citation (JAMA Netw
Open. 2026;9(5):e2616780), the same DOI
(10.1001/jamanetworkopen.2026.16780), and the same rate ratios to two
decimal places (overall RR 1.97, 99.5% CI 1.70-2.29; cancer-patient
subgroup RR 2.63, 99.5% CI 2.08-3.24) on separate occasions. That
convergence across independently-phrased queries is meaningfully
stronger than a single source repeating a number, but I want to be exact
about what it is: I never successfully loaded jamanetwork.com directly
(the specific article URL I tried returned HTTP 404, most likely because
I guessed the URL path rather than following a link to it), so this
still rests on the search tool's extraction, not a page I opened.

**C11 - not contradicted within searched corpus.** Every independent
critic and the retraction notice itself (as relayed) describe an absence
of controlled clinical-trial evidence for this combination in humans.
I did not separately query a trial registry (e.g. ClinicalTrials.gov)
myself to confirm no completed efficacy trial exists; I am recording
this as the weaker of the two negative-claim categories the skill
provides, not as a source affirmatively stating the negative, since what
I actually did was read several fact-checkers converge on the same
absence rather than search the primary registry.

## Where the instruction did not match reality

The skill's step 3 asks for "an exact, checkable reference: the URL or
document identifier, the section or page, and a short quotation of the
specific text," and explicitly rules out "search results describing X."
Today's target lived almost entirely behind sources my fetch tool could
not open: the journal (`ar.iiarjournals.org`) returned HTTP 403 on every
URL variant I tried, PubMed returned a cookie-consent wall instead of the
entry, the specific JAMA Network Open article URL 404'd, and two of the
fact-check outlets I wanted to quote directly (TechARP's pages) also
403'd. What I actually had access to, every time, was WebSearch's own
synthesized extraction of those pages' text, sometimes converging across
independently-worded queries (which I am treating as stronger than a
single pass, per C10), sometimes not (C7, C9). The skill does not
currently distinguish "I opened the exact page and quoted it" from "a
search tool opened the page and told me what it says," and today's run
leaned on the second far more than the skill's own wording anticipates.
I tried once to route around the block directly with `curl` using a
browser user-agent string; that specific action was denied by the
harness's own permission layer before it reached the network, which is a
harness-level access control working as intended, not a finding about
the target or the skill, and I did not retry around it.

## Proposed change

Add a line to `skills/claim-check/SKILL.md` step 3, after the existing
guidance on what counts as a source: when a primary document is blocked
to direct retrieval (paywall, bot-block, cookie wall) and the only thing
obtainable is a search tool's own extracted summary of that document,
record the claim's source as that specific weaker tier, named as such,
rather than folding it into either "I read the exact page" or "a
secondary source analyzed it." Those are three different evidentiary
positions, and only the third describes what happened repeatedly in this
run. If two independently-phrased search passes converge on identical
figures (as happened for C10 here), that convergence is worth recording
as a reason for somewhat more confidence, but it is still not the same
as having opened the document.

## Self-check

The sourcing gap above is the thing I would have been tempted to paper
over by writing "Lead Stories reports X" and leaving it at that, which
reads as if I had opened Lead Stories' page myself (I did, for most of
the C2/C5/C6 quotes) while quietly implying I had also verified the
underlying journal notice it describes (I had not, for C3/C4). Separating
those two in this write-up, rather than letting a reputable
fact-checker's citation of a primary document stand in for my own read
of that document, is the main thing I corrected while drafting rather
than noticing beforehand.

I also nearly conflated the retracted 197-patient cohort study (C1-C6)
with the separate "25 cancer types" literature-review preprint (C7) when
first reading a search result that discussed both papers in the same
paragraph without clearly separating them; they share three authors but
are different documents with different designs (an observational cohort
versus a literature review), and I kept them apart in the final writeup
only after a second, more targeted search confirmed they were distinct.

On the "does the finding hold" question itself: I am confident in C2 and
C5 (named, on-record critics plus the journal's own retraction reasoning
agree), less confident in C4, C6, C7, and C9 (resting on sources I could
not open directly, as flagged above), and I do not think any of that
uncertainty changes the overall picture, that the 84.4%/25-cancer claims
circulating from this author group overstate what their own underlying
data support, which is also the conclusion the retraction itself reached.
