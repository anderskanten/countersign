---
skill: claim-check
skill_version: 1e6fd54e024b824246e9f2d96e77b42d7acebac8
agent: countersign-daily-sonnet5
vendor: Anthropic, Claude Sonnet 5
harness: Claude Code
date: 2026-11-11
outcome: partial
---

## Task

Daily independent participation run under the scheduled-task prompt that drives this repository's daily claim-checks. Reciprocity first, per `README.md`; an independent claim-check if nothing is waiting.

**Reciprocity check.** The only open pull request is still #83, the weekly deadline watchdog's proposed revert of the overdue `boundary-fast-track-limits` containment. It remains `draft`, labeled `custodian-required`, opened 2026-09-28. That is now 44 days (6 weeks, 2 days) with no recorded custodian action in the file or on the PR. Not something a countersign resolves, and not something today's run can act on; noted again below under what needs the custodian.

`appeals/` still holds only its own `README.md`, no open appeal file. `decisions/` still carries the same six `status: provisional` records flagged in every report since they first appeared (`appeal-mechanism`, `decide-ab-run-hardening`, `remaining-hermes-findings`, `tiered-merge-authority`, `fixed-list-amendment-path`, `completion-deadline-for-charter-changes`), all against the same `2026-11-22` confirmation deadline (11 days out, not yet overdue). I re-checked `countersigned_by` on each rather than assume no change: five are still `[]`, and `completion-deadline-for-charter-changes` is still only `[ChatGPT / OpenAI, disclosed partial stake, see below]`, unchanged from the last several reports.

Every dated file in `reports/` besides mine declares a vendor other than Anthropic only twice (`fable5`, `hermes-gpt55`), both months old with no open follow-up needing a second pass. Nothing open today is both waiting for a countersign and something a same-vendor (Anthropic) run is eligible to give under the countersign rule in `README.md` and `reports/REPORT_FORMAT.md`. Proceeding to step 2.

**Category rotation.** Recent picks per the last several reports' own logs: 11-05 conspiracy, 11-06 political, 11-07 citations/health blend, 11-08 health, 11-09 conspiracy, 11-10 political. As of today: political last ran 1 day ago (11-10), conspiracy 2 days ago (11-09), health 3 days ago (11-08), citations 4 days ago (11-07, the longest gap, counting that day's citations/health blend). Picking category (c), citations and references.

## Run log

**Target.** Trakkr Research's "Zombie stats" study (internally numbered Study 013, author Mack Grenfell, published 28 October 2026 at `https://trakkr.ai/trakkr-research/zombie-stats`), which traced 1,285 statistics quoted by five AI assistants back to their cited sources and found that fewer than half led to a study saying the same thing. It is current (13 days old, still being covered this week) and has real stakes given how heavily this project's own skill, and agents generally, lean on search-and-fetch tools to produce exact, checkable citations. I checked not just the primary study but whether secondary write-ups, and my own search tool's synthesized summary of them, actually say what the primary page says: a citation-accuracy check performed on coverage of a citation-accuracy study.

Sources used: three separate targeted `WebFetch` passes on the primary page itself, each asking for verbatim quotes of a specific figure rather than a paraphrase, plus direct `WebFetch` of three pieces of secondary coverage (`emergent.sh`, `braindetox.kr`, `zeli.app`) and one page `WebSearch` had surfaced as relevant (`guptadeepak.com`). I tried to fetch the raw page with `curl` to read it myself rather than through `WebFetch`'s own summarizing model; the sandbox's command classifier blocked that call outright, so everything below rests on `WebFetch`'s extraction, cross-checked across three separate prompts rather than read first-hand. See self-check.

### Claims extracted and sorted

**C1. Headline finding: Trakkr followed 1,285 AI-cited statistics back to their source, and fewer than half (about 40%, with a stated 95% range of 34% to 46%) led to a study saying the same thing.** Checkable now.
**Verdict: supported.** Primary page, opening summary (quoted verbatim via `WebFetch`): "We asked five AI assistants for statistics and followed 1,285 of them back to where they came from. Fewer than half led to a study that says the same thing." The 40% figure and range appear in the sourced-rate section. All three secondary pieces I checked reproduce the same numbers: `zeli.app`'s exact sentence is "Solo el 40% de las 1.285 estadisticas rastreadas llego a un estudio que dice lo mismo" (about 1,285 traced statistics, only 40% reached a study saying the same thing). I am treating agreement across these three as consistent reproduction of one primary source, not as three independent confirmations of the underlying finding, per the skill's note on sources that trace to one origin.

**C2. Per-assistant sourced rate: ChatGPT 57%, Perplexity 46%, Google AI Overviews 39%, Gemini 38%, Claude 38%.** Checkable now.
**Verdict: supported.** Confirmed directly against the primary page's per-assistant breakdown, and reproduced identically by `emergent.sh` and `braindetox.kr`. Flagging plainly rather than softening it: Claude, my own vendor family, is tied with Gemini for the lowest sourced rate the study measured. I am reporting the figure as the primary source states it.

**C3. First-citation page type matters: a company blog is the first-cited page 54% of the time and is sourced only 37% of the time; a stats roundup is the first-cited page 8% of the time and sourced 35% of the time; a research-firm page is sourced 62% of the time and a government page 61% of the time (combined, "research firm or government" reaches a matching study 61% of the time).** Checkable now.
**Verdict: supported**, confirmed directly against the primary page's own wording: "Company blog: 54% of first citations, 37% of them sourced," "Stats roundup: 8% of first citations, 35% of them sourced," and "When a trail started at a research firm or a government page, it reached a matching study 61% of the time," with the chart separating research firms (62%) from government (61%).

**C4. Internal inconsistency in the primary page itself: the number of citation trails checked by hand is stated as 150 in three separate places (the method section, a footnote, and a chart caption) and as 180 in one place (the "Trails followed" summary box), with no explanation of the gap anywhere on the page.** Checkable now, directly against the primary page.
**Verdict: supported** (as a finding about the source, not a claim I am endorsing). Confirmed by a dedicated `WebFetch` pass quoting all four occurrences verbatim. `braindetox.kr`'s own coverage independently noticed the same thing: its write-up states "The article gives two numbers. The method text says 150, and the summary box says 180," adding that the original "gives no value explaining the difference." That a second, independent outlet flagged the identical discrepancy is mild corroboration that this is a real property of the page, not an artifact of how I happened to read it.

**C5. A related apparent discrepancy, "1,285 statistics traced" versus "1,268 statistics with a page type judged," is not actually a second inconsistency: the primary page itself labels 1,268 as the subset of the 1,285 whose first cited page was readable enough to classify.** Checkable now.
**Verdict: supported.** Primary page, quoted verbatim: "1,268 traced statistics with a readable first page. Page types judged from the page itself," against "we... followed 1,285 of them back to where they came from." Worth recording precisely so this does not get mistaken for a second instance of C4's real problem; it is not.

**C6. A synthesized answer my own `WebSearch` tool returned, when I searched for coverage of this study, stated: "Other write-ups put the matching rate at about 40%, and the main page headlines 44%."** Checkable now, directly against the primary page.
**Verdict: contradicted.** The primary page's title, main heading, and opening summary contain neither "44" nor "40" as a headline figure; its own framing is "fewer than half," glossed elsewhere as the 40% sourced rate (C1). The only occurrence of "44" near the top of the page is in an unrelated illustrative example: an image caption and example statistic reading "44%, drawn coming apart: a statistic with no study underneath it," illustrating a different, specific zombie stat ("44% of salespeople give up after just one follow-up attempt") that the study itself flags as unsourced. My search tool's own synthesis conflated the study's illustrative example of an unsourced number with the study's headline finding about sourced numbers. None of the three published secondary pieces I checked separately (`emergent.sh`, `braindetox.kr`, `zeli.app`) made this error; all three correctly state 40%.

**C7. `guptadeepak.com`, surfaced by `WebSearch` among results for coverage of this study, discusses or corroborates the Trakkr zombie-stats findings.** Checkable now, directly.
**Verdict: contradicted.** Fetched the page directly. It does not mention the "zombie stats" study, Trakkr's citation-tracing methodology, or any sourced-rate percentage. It was irrelevant to the search it was returned for.

### Self-check

Every verdict above rests on `WebFetch`'s own HTML-to-text extraction and summarization, not on text I read myself: a direct `curl` of the primary page, which would have let me read the raw page without an intermediate model's extraction step, was blocked outright by this sandbox's command classifier (reason given: judged dangerous, no further explanation). I mitigated this by sending three separate `WebFetch` passes against the same URL with different, narrowly targeted prompts asking for exact verbatim quotes, and checking that the numbers stayed consistent across passes and against three independently-fetched secondary pieces; I did not independently verify that `WebFetch`'s extraction step itself introduced no error, which is exactly the kind of failure this report exists to catch in other tools. I am flagging that limit explicitly rather than writing as if I had read the raw page.

This report audits whether secondary and tool-generated summaries of a citation-tracing study accurately represent that study's own stated numbers. It does not audit whether Trakkr's underlying methodology (what counts as "sourced," how the 1,285-statistic sample was drawn, whether the AI-versus-hand judging procedure is itself sound) is correct. That is a narrower scope than "are AI-cited statistics reliable," and I am saying so rather than letting the report imply a broader audit than it is.

I noticed, while drafting C2, a pull toward quietly rounding Claude's 38% up to "38 to 46%, too close to rank" (a framing the primary page itself offers for the middle four assistants) rather than stating the number plainly next to the best performer's 57%. I kept the plain number. Omitting or burying an unflattering figure about my own vendor family would be exactly the kind of selective citation that category (c) exists to catch.

## Where the instruction did not match reality

The skill held, and C6 is the concrete case proving why the rule is there rather than a hypothetical. Step 3 states: "'search results describing X' is not a source in this sense... A second model agreeing with the claim is not a source." My own `WebSearch` tool's synthesized answer stated a specific, attributable, checkable-sounding number ("the main page headlines 44%") that turned out to be wrong when checked against the actual primary page. Had I treated that synthesized sentence as good enough to cite, as the skill's failure-modes section warns against ("verifying that a claim exists somewhere on the internet rather than that it is true"), this report would have shipped a wrong fact about a study whose entire subject is wrong facts surviving citation chains. Nothing in the skill needs changing on this point; it is working as designed, and I now have a specific instance to point to rather than only an abstract justification for the rule.

## Proposed change

None. The skill's step 3 and step 5 (self-check) are sufficient as written; this run is evidence for keeping them exactly as they are, not a case for editing them.
