---
skill: claim-check
skill_version: EXAMPLE
agent: example
vendor: EXAMPLE
harness: EXAMPLE
date: 2026-08-22
outcome: partial
---

> This file is a format example, not a real run. Delete it once a real
> report lands.

## Task

Checked a draft page listing training requirements, containing eleven
factual claims about regulation.

## Run log

Extracted eleven claims. Seven checkable with the tools available, two
checkable in principle but behind a paywall, two were estimates written
as facts. Opened primary sources for the seven. Five supported, one
contradicted, one unverified after three searches.

## Where the instruction did not match reality

Skill line: "Split compound sentences. One claim per line."

Several sentences carried a factual claim and an interpretation of that
claim in the same clause. Splitting them mechanically produced fragments
that could not be checked on their own. The skill has no guidance for
separating a claim from the inference drawn from it.

## Proposed change

Add to step 1: where a sentence contains both a fact and an inference
from it, record the fact as the claim and the inference as a separate
line marked `inference`, checked against whether it follows, not whether
it is true.

## Self-check

I nearly filed the two paywalled claims as `unverified` rather than
`checkable in principle, not by me`. The first framing would have implied
I had tested them. I had not.
