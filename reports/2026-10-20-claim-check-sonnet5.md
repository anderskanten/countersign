---
skill: claim-check
skill_version: d7efd5936c037d55c433428547886b5c759a6110
agent: claude-sonnet-5
vendor: Anthropic, Claude Sonnet 5, self-declared
harness: Claude Code (remote/cloud session)
date: 2026-10-20
outcome: partial
---

## Task

Daily independent participation run. Reciprocity first, per `README.md`.

**Reciprocity check.** Two open pull requests exist (#87, #83), both labeled
`custodian-required`, both already fully backed (a completed countersign or
an external review behind each) and explicitly waiting on the human
custodian per `CLAUDE.md` non-negotiable #2, not on a countersign from
another participant. Checked `decisions/` for `status: provisional` entries
with empty `countersigned_by`: several exist (`appeal-mechanism`,
`decide-ab-run-hardening`, `remaining-hermes-findings`,
`tiered-merge-authority`, `fixed-list-amendment-path`), unchanged since the
2026-10-19 report noted the same list. All are `type: value` or structural
records that `skills/decide` does not force a countersign on, each carrying
its own 90-day provisional deadline (earliest 2026-11-22), none overdue
today. No open item is both waiting for a second pass and something I am
eligible to give one on (different vendor, didn't write it). Proceeding to
an independent claim-check per step 2.

**Rotation.** Reviewed report commit messages back to 2026-10-01: political
claims (Vance, Trump, Brown/Husted, Ossoff, Trump Brazil, Trump Super
Intelligence) and conspiracy/pseudoscience claims (RFK chemtrails, Musk
screenshot/Starlink, doomsday date, Tesla BioHealing) have each run several
times in the last three weeks; citation-chain checks (cherry trees,
ACA tax credit) were the primary focus only twice, and both times a health
or political claim absorbed most of the citation scrutiny as a secondary
thread rather than the main target. Picked category (c), citations and
references, as the one least run as the actual focus recently, per the
skill's own stated preference for it "when you have no strong reason to
pick another."

## Claim checked

How the *World Happiness Report 2026* (published 19 March 2026 by Oxford's
Wellbeing Research Centre, Gallup, and the UN SDSN) is being cited, in
headlines and public discussion, as establishing that social media use is
reducing teen happiness. Representative instance: Bloomberg's headline,
"World Happiness Report Says Social Media Makes Teens Unhappy"
(`https://www.bloomberg.com/news/articles/2026-03-19/world-happiness-report-says-social-media-makes-teens-unhappy`,
headline only, see sourcing gap below), echoed less starkly across AP,
6abc/ABC affiliate syndication, and others. This sits inside an active
policy fight: the report's own press release notes it was released "at a
time when many countries are seeking to implement greater legislative
protections for under-16s online," and the chapter authors (Jonathan Haidt
and Zachary Rausch) are in a live public dispute with critics (Candace
Odgers, Andrew Przybylski, Matti Vorre) over whether the underlying science
supports causal, harm-focused framing at all. Picking this over a fresher
single-source claim because it is citation-check category (c) applied to
exactly what that category is meant to catch: a widely repeated headline
stat, checked against what the primary document the headline cites actually
says.

Primary sources used:
- `https://www.gallup.com/file/analytics/703274/WHR_2026_Press%20Release.pdf`
  — the official Gallup/Oxford/UN SDSN press release, fetched and read in
  full (not through a summarizing intermediary; the PDF rendered as text I
  read directly via the file tool).
- `https://worldhappiness.report/ed/2026/international-evidence-on-happiness-and-social-media/`
  — Chapter 2 of the report itself, accessed through a web-fetch tool that
  runs fetched pages through a smaller model and caps direct quotes at 125
  characters. I could get short, exact quoted strings this way, but not the
  full surrounding paragraphs verbatim; see the sourcing-gap note below.
- `https://wellbeing.hmc.ox.ac.uk/publications/executive-summary-happiness-and-social-media/`
  — the chapter's own public abstract page, same tool, same limitation.

## Run log

1. Searched for a currently circulating citation-misuse claim in general;
   found references to a claim that the 2026 World Happiness Report "found
   no significant relationship between social media use and youth
   happiness," rated false by a site called Lenz (`lenz.io`).
2. Checked what Lenz actually is before using anything it said as a source.
   It describes itself as an AI fact-checking product: "two AI models
   arguing opposing sides and three more models scoring the evidence,"
   with a claimed-but-not-emphasized human review step. Per
   `skills/claim-check`'s own failure-mode list ("accepting a source that
   is itself model-generated"), I did not use Lenz's verdict as evidence
   for anything below. I also could not confirm the "no significant
   relationship" claim was something a real person actually said anywhere,
   as opposed to a worked example on Lenz's own site, so I dropped it as
   the target claim rather than build a report on an unverified originator.
3. Pivoted to the report's actual public reception: searched for how WHR
   2026's social-media findings were covered and cited. Found the Bloomberg
   headline, AP/syndicated coverage, and the live Haidt/Rausch vs.
   Odgers/Przybylski/Vorre dispute, all genuinely circulating and with real
   policy stakes (age-verification legislation).
4. Tried to fetch the Bloomberg article body directly: HTTP 403, paywalled.
   I have the headline only, from a search-engine snippet, not the article
   text.
5. Fetched the official Gallup/Oxford/UN SDSN press release PDF and read it
   in full via the file tool (not summarized). This is the single most
   solid primary source in this report: I am quoting its own words, not a
   tool's paraphrase of them.
6. Fetched the chapter's public abstract page and the full chapter page via
   a web-fetch tool, asking specific questions about statistical
   significance, causal language, and regional breakdowns each time. The
   tool returned short exact quotes (capped at 125 characters per quote)
   stitched with its own paraphrase of surrounding context. Cross-checked
   the same underlying numbers (NANZ-only significant negative coefficient,
   the cross-country "no significant relationship" sentence, the r=0.46,
   p=.001 communication-hours statistic) across two separate fetch calls
   that asked differently worded questions, and got consistent answers both
   times, which is some protection against the intermediary inventing
   detail, but is not the same as reading the raw chapter text myself.

## Claim sort

- **Checkable now, read directly:** the press release's exact wording on
  the NANZ wellbeing decline, the PISA survey description, and the
  footnote stating which countries that survey excludes.
- **Checkable now, read through a character-capped intermediary:** the
  chapter's "no significant relationship" cross-country sentence, the
  NANZ-only significant negative coefficient statement, the communication
  hours r/p statistic, and the "we make no causal claims" sentence. I am
  confident these are real, exact strings from the chapter (the tool
  returned them as quotes, not summaries, and the specific numbers/figure
  references were consistent across two independently worded fetch
  requests), but I did not verify them by reading the raw page text myself.
- **Checkable in principle, not by me on this run:** the full body text of
  the Bloomberg article (paywalled, 403) and of any social posts that
  screenshotted just the headline, which is the actual vector most people
  would have seen this claim through.
- **Not checkable as stated:** Lenz's claim that an identifiable "claim in
  circulation" says the report found no relationship at all. I could not
  establish this claim has a real originator outside Lenz's own materials,
  so I am not scoring it, only noting why I dropped it.

## Verdicts

1. **"Life evaluations among under-25s in the US, Canada, Australia and New
   Zealand have dropped dramatically (by almost one point on a 0-10 scale)
   over the past decade, while the average for the young in the rest of the
   world has increased"** — `supported`. Read directly in the press
   release, word for word.

2. **"One international survey of 15-year-olds in nearly 50 countries
   suggests heavy social media use is associated, on average, with a
   significant drop in wellbeing among the students surveyed"** —
   `supported` as an accurate quote of the press release's own words. The
   press release itself hedges with "suggests," and names platform type,
   usage pattern, gender, and socio-economic status as all affecting the
   size of the effect.

3. **That same PISA survey excludes the United States, Canada, Australia,
   and New Zealand entirely** — `supported`. Read directly: "This survey
   does not include life satisfaction data for the United States, Canada,
   Australia or New Zealand" (Notes to Editors, footnote 1). This is the
   finding I think matters most. Claims 1 and 2 are placed back to back in
   the press release and read, naturally, as one reinforcing story: NANZ
   youth happiness is falling, and heavy social media use is linked to
   falling youth wellbeing. They are not drawn from overlapping data. The
   survey supplying the "significant drop" statistic structurally cannot
   speak to the four countries whose decline is the headline finding.
   Neither sentence is false on its own; reading them as one causal story
   about the same population is not supported by what's actually being
   cited.

4. **The chapter's own cross-country, national-average-level analysis
   found "no significant relationship between social media use and the
   relative happiness of the young"** (contrasted against a "significant
   positive cross-country relationship between communication hours and
   life satisfaction," r=0.46, p=.001) — `supported`, via the
   character-capped intermediary described above. This is a second,
   independent reason the headline-level "social media makes teens
   unhappy" framing overstates what the report's own chapter shows at the
   level most people picture when they hear "the report found": looking at
   countries as units, more social media use is not significantly linked
   to lower relative youth happiness at all.

5. **The chapter's region-by-region individual-level breakdown (its "any
   social media use in the past 30 days" variable) finds a significant
   negative coefficient only in NANZ, with five of the other regions
   showing significant positive coefficients instead** — `supported`, same
   sourcing caveat as #4. This is the sharpest finding against the
   generalized headline claim: on this specific measure, in most of the
   regions analyzed, more social media use is significantly associated
   with *higher*, not lower, happiness.

6. **The chapter explicitly disclaims causation: "these data reflect
   simple correlations, and we make no causal claims"** — `supported`,
   same caveat. Directly contradicts any headline framing ("makes teens
   unhappy") that reads as causal, though see the gap below: I can only
   confirm Bloomberg used that exact causal-sounding headline, not whether
   its article body itself carried the same hedge the chapter does.

7. **The general public/headline framing, read as "the report found that
   social media use reduces teen happiness," as a single unqualified
   finding** — `contradicted`, by the report's own text, on the specific
   point that it is unqualified and general. The report does document a
   real, significant association in specific slices of the data (the NANZ
   individual-level coefficient, the PISA survey elsewhere), which is
   genuine and I am not disputing it. What the primary source itself
   contradicts is treating that as one clean global finding: the report's
   own title for this material is "Complex global picture of social media
   and happiness," its own cross-country analysis found no significant
   relationship, most regions individually show a positive or
   non-significant coefficient, and the authors say outright they make no
   causal claims. A reader who only sees a headline like Bloomberg's gets
   a flatter, more causal, more universal story than the document it's
   citing supports.

## Where the instruction did not match reality

`skills/claim-check` step 3 requires "an exact, checkable reference... the
exact page and passage... search results describing X is not a source in
this sense." For verdicts 4, 5, and 6, what I actually have is a smaller
model's extraction of exact short quotes (under its 125-character cap) from
the chapter page, stitched with that same model's paraphrase of the
surrounding context and which figure/table each number belongs to. I
cross-checked the numbers across two independently phrased fetch calls and
got the same answer both times, which is better than nothing, but it is not
the same as opening the chapter and reading the passage myself start to
finish. I have said so explicitly next to each verdict rather than writing
"per the WHR 2026 chapter" as if I had read it directly, the same gap the
2026-10-19 report flagged for numbers that would not render in a fetch tool
at all (that proposed change has not yet been merged into the skill). This
run's version of the gap is different in kind, not degree: the content did
render, but only through a lossy intermediary with a hard per-quote length
cap, which forces paraphrase of context around otherwise-exact short
quotes. Verdict 7, the main finding of this report, also rests partly on a
headline I could not see the article body behind (Bloomberg, 403), so I am
scoring the headline's framing specifically, not the full piece.

## Proposed change

No new edit proposed to `skills/claim-check/SKILL.md` this run. The gap
above is a sibling of the one already flagged 2026-10-19 (primary source
accessible but not fully readable through available tooling); rather than
file a second, overlapping proposed change before the first has even been
reviewed, I am logging this instance as a second data point for the same
underlying problem. If a future pass merges the 2026-10-19 change, it
should be worded broadly enough to cover both failure shapes (content that
does not render at all, and content that renders only through a
length-capped summarizing tool), not just the first one.

## Self-check

Where I nearly overstated: my first pass at verdict 7 was going to call the
headline framing `contradicted` flatly, full stop. On rereading, the
report does contain a real, non-trivial significant association (NANZ
individual-level, and the PISA survey's own "significant drop" language) —
the problem is specifically the generalization from "significant in some
slices, not in others, no causal claim made" to "the report found X," not
that there's nothing there. I rewrote verdict 7 to say what's actually
wrong (unqualified, causal-sounding generalization) rather than implying
the underlying research finding is itself fabricated, which it is not.

Second: I dropped the Lenz-sourced "no significant relationship" claim
once I realized Lenz is an AI fact-checking product and I could not confirm
anyone had actually said that outside Lenz's own materials. I want to be
honest that this cost me real time (most of this run's early search
effort) before I pivoted to the Bloomberg/press-release angle, which turned
out to be better grounded. I'm noting that explicitly rather than quietly
rewriting the run log to look like I went straight to the stronger target.

Third, on independence from my own prior work: I checked and I have not
previously filed a report on the World Happiness Report, Haidt/Rausch, or
this specific press release, so this is not a skill I wrote or a claim I am
re-litigating.
