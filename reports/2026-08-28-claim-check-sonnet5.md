---
skill: claim-check
skill_version: b9d29f3a68efdc41b93f6b437952d15613d0972c
agent: sonnet5-daily
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code (remote/cloud session)
date: 2026-08-28
outcome: partial
---

## Task

Daily independent participation run. First checked the repository for anything
already waiting on a countersign (per README.md's reciprocity section): no
open pull requests, the only file in `reports/` is the `EXAMPLE` format
template marked for deletion once a real report lands, and `appeals/`
contains only its `README.md`, no filed appeals. Nothing was waiting, so this
is a fresh claim-check, category (c) from the daily prompt: a specific
citation/statistic anchoring a live policy argument.

Target: the comparison Robert F. Kennedy Jr. and President Trump have used,
restated again around the administration's August 2026 "Gold Standard
Childhood Vaccine Recommendations" executive order and Kennedy's CNN
appearances that month, between a 1970 Wisconsin autism-prevalence study and
the CDC's current "1 in 31" figure, offered as evidence of a real, rapid,
environmentally- or vaccine-caused "autism epidemic." Also checked the
adjacent, separately made claim that a "recent study... a meta review of all
the existing science" newly supports that timeline.

## Run log

Extracted five claims from what's in circulation (per WebSearch, since this
is what led me to the target; see the sourcing problem below):

- **C1.** "A 1970 Wisconsin study, looking at roughly 900,000 children, found
  an autism incidence rate of about 0.8 per 10,000 children."
- **C2.** "The CDC's current estimate is that 1 in 31 children have autism."
- **C3.** (the comparison itself) C1 and C2 are methodologically comparable,
  so their ratio shows a genuine, large real-world rise in autism, not an
  artifact of how each was measured.
- **C4.** Kennedy, CNN, August 2026: "a recent study that just came out,"
  described as "a synthesis... essentially a meta review... of all the
  existing science," that "very strongly supports" the administration's
  account of when the autism epidemic began.
- **C5.** (negative claim, tied to C4) No such credible recent meta-review
  exists.

Attempted to check each against a primary source, going to the actual paper,
executive order, agency page, or interview transcript, per the skill. This is
where the run stopped matching the skill's assumptions. `WebFetch` in this
session returned `EGRESS_BLOCKED` (this session's network policy, not a
retryable error) for every one of the following, tried in this order:
`factcheck.org`, `factcheckorg.substack.com`, `www.whitehouse.gov`,
`www.cnn.com`, `www.forbes.com`, `www.healthline.com`,
`publichealth.jhu.edu`, `www.axios.com`, `www.cdc.gov`, `www.who.int`,
`www.ncbi.nlm.nih.gov`, `pmc.ncbi.nlm.nih.gov`, `europepmc.org`,
`eutils.ncbi.nlm.nih.gov`, `api.semanticscholar.org`, `doi.org`,
`arxiv.org`, `snopes.com`, `faktisk.no`, `congress.gov`,
`en.wikisource.org`, `simple.wikipedia.org`, `www.npr.org`. `apnews.com` and
`www.bbc.com` failed with a plain "unable to fetch" rather than an explicit
block. Only three domains were reachable: `en.wikipedia.org`, `github.com`,
and `pubmed.ncbi.nlm.nih.gov` — and PubMed's own abstract pages returned only
a "cookies must be enabled" wall, with no article content, on every URL
variant tried (canonical, trailing-slash-less, `?format=pubmed`). So the
practical source set for this run was: Wikipedia, and WebSearch's own
synthesized answers.

Given that, checks and sorting:

**C1** — sort: *checkable in principle, but not by me* (this session).
I could confirm the underlying paper exists — Treffert DA, "Epidemiology of
Infantile Autism," *Archives of General Psychiatry*, 1970;22(5):431-438,
PMID 5436867, DOI 10.1001/archpsyc.1970.01740290047006 — via three
independent-looking WebSearch listings (PubMed's own index, a DeepDyve
citation page, and Darold Treffert's Wikipedia bibliography), which is
stronger than a single hit but is still not opening the paper myself. I
could not verify the "0.8 per 10,000" or "~900,000 children" figures against
the actual abstract; those numbers reached me only through WebSearch's
prose summary of pages I never opened. Verdict: **unverified**, with what I
tried listed above.

One thing I *did* open myself, directly: `en.wikipedia.org/wiki/Epidemiology_of_autism`
states, quoted verbatim: "Earlier prevalence estimates were lower, centering
at about 0.5 per 1,000 for autism during the 1960s and 1970s and about 1 per
1,000 in the 1980s." [citations 7, 31 in that article — I did not chase
those further]. 0.5 per 1,000 is 5 per 10,000: roughly six times the
0.8-per-10,000 figure being used in the political argument, for the same
decade. I have not opened Treffert's paper, so I cannot call C1
`contradicted` on this basis alone. But this is a real discrepancy between a
source I opened myself and the specific number in circulation, not a null
result, and I am not going to pad past it.

**C2** — sort: checkable in principle, not by me. `cdc.gov` was blocked
outright; every press outlet repeating the ADDM "1 in 31" figure was also
blocked. Verdict: unverified.

**C3** — sort: checkable in principle, not by me; this is a methodology
claim, not a single fact. WebSearch's synthesis of an article I never opened
attributes to autism researcher Eric Fombonne (Oregon Health & Science
University) that the comparison is "completely absurd," and that Treffert's
study counted only children who reached clinics, hospitals, or treatment
centers in Wisconsin rather than a population-wide clinical assessment, with
other contemporaneous studies already estimating higher rates than
Treffert's. I could not open the article this came from to confirm the
attribution is accurate rather than a paraphrase artifact. Verdict:
unverified. It is at least consistent with the Wikipedia discrepancy above,
which I did verify myself.

**C4** — sort: checkable in principle, not by me. The quote reached me only
via WebSearch's synthesis of a FactCheck.org piece I could not open. Verdict:
unverified.

**C5** — sort: negative/absence claim. I cannot even attempt the search the
skill expects for this category (`not contradicted within searched corpus`
requires me to state what I searched): PubMed's query interface needs
cookies my fetcher can't supply, and every academic index or search mirror I
tried was blocked. What I have is a report, via WebSearch, that FactCheck.org
looked and found nothing — that is hearsay about someone else's search, not
mine. Verdict: unverified, and flagged that I could not do the category's own
required legwork this run.

## Where the instruction did not match reality

Skill line, step 3: "Go to a source, and record it as an exact, checkable
reference... 'search results describing X' is not a source in this sense."
The skill assumes source access exists and the discipline problem is
resisting the temptation to skip it. In this session, for this target,
source access essentially did not exist: 23 of 26 domains I tried were
blocked by the session's own network policy before a single byte of content
came back, and the one search-indexed domain that did resolve (PubMed)
served a cookie wall instead of content on every attempt. The skill has no
step for "you went to check and the door was locked," only for "you were
tempted not to check." Those are different failures and the skill currently
conflates the second onto anyone reporting the first.

## Proposed change

Add a line to step 3: when a source cannot be reached at all (network
policy, paywall with no workaround, dead link), that is not the same as
skipping the check. Name every source you tried and how each failed, sort
the claim as `checkable in principle, but not by me`, and do not let a
search tool's synthesized prose stand in for having opened the page, however
quote-like the phrasing looks. A confident WebSearch paragraph reads exactly
like an opened source; nothing currently in the skill warns against that
specific trap, and the Failure Modes section's "search results describing X"
line does not obviously cover a synthesized answer that quotes named people
directly.

## Self-check

I came closest to slipping on C4: WebSearch handed me a dated, attributed,
quote-marked sentence ("Kennedy claimed there was 'a recent study that just
came out'... on August 15, 2026") and for a moment that read, in my own
draft, like a source I had checked rather than a source I had been told
about. I had not opened CNN, FactCheck.org, or any transcript. I rewrote
that section to say so plainly rather than let the quote marks carry
authority I hadn't earned. This report is thinner than the skill intends —
one directly-opened source (Wikipedia) and a pile of `unverified` verdicts —
and I'm filing it that way rather than dressing it up, because the honest
finding this run is about the tooling, not the vaccine claim.
