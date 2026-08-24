---
name: ab-run
description: Run a proposed method alongside the one it would replace, on real work, and report what actually differed. Use before any new skill or rule is promoted from beta to stable. Nothing here reaches stable without one.
state: proposed
---

# A/B run

Nothing goes straight to stable. Every new method runs in beta against
the one it would replace, on real work, until a stated end condition is
reached.

The purpose is not to confirm the new version. It is to find out whether
the difference is real or whether you are reading a story into noise.
Both of us are very good at the second thing.

## States

- `proposed`: written, not run
- `beta`: running alongside the incumbent
- `stable`: the beta ended and the evidence held
- `superseded`: replaced, kept in history

There is no path from `proposed` to `stable`.

## Evidence must match the exact version being promoted

A report names a `skill_version` (the commit SHA it was actually run
against). Promotion evidence, the qualifying reports and the beta run,
must all name the same `skill_version` as the one being promoted to
`stable`. If the skill file changes materially after reports were
filed, whether to fix something a reporter found or for any other
reason, the candidate resets to `proposed`, and old reports against the
prior version do not count toward the new one. Two real reports on
version A do not make version B stable; that is laundering evidence
across a revision, not carrying it forward. Write the exact
`skill_version` being promoted into the decision or report that
promotes it.

## Before you run anything

Write these down and commit them. Changing them after you have seen
results invalidates the run, and doing that quietly is a method failure
under the charter.

1. **What you expect to differ.** Specifically. "Better decisions" is not
   a prediction. "Fewer decisions reopened within ten rounds" is.

2. **How you will measure it.** Participants choose their own measures;
   this skill does not prescribe them. But a measure someone else could
   apply to the same runs and get the same answer, without knowing which
   version they were looking at.

3. **The end condition.** A number of runs or a date. Not "a while", not
   "until it seems settled". Beta with no end condition is beta forever,
   and it will be ended by whoever gets impatient first.

4. **How small a difference still counts.** Below this, the result is
   inconclusive. Decide the threshold before you know which way it fell.

5. **Minimum run count for the claim being made.** A handful of easy
   cases does not support "this is generally better." State how many
   real, paired runs the claim needs before it can be tested at all,
   and do not promote on fewer than that, even if every one of them
   went the challenger's way.

6. **Whether the metric can be scored blind.** Where it can, the person
   or model scoring an individual run should not know which version
   produced it until after scoring. Where genuinely impossible, say so
   and say why, rather than skipping it silently.

7. **Someone to review whether the metric actually measures the
   promised improvement**, chosen before results exist, ideally someone
   who did not write the proposal. A metric can be met honestly while
   testing the wrong thing; that is a design flaw in the run, not a
   result.

## Running

- Same questions to both versions where possible. Different questions
  make the comparison worthless.
- Do not stop early because the new version is winning. That is the
  single most common way a run produces a false result.
- Do not stop early because it is losing either. File the loss.
- Log every run, including the ones that were messy or aborted. A run
  log with no failures in it has usually been curated.

## Outcomes

Three are permitted, and all three are reported the same way.

- **held**: the predicted difference appeared, above the threshold, at
  or above the minimum run count committed to beforehand, with the
  size of the difference stated alongside how confident that size is
  (not just a direction). The method moves to stable.
- **reverted**: it was worse. Back to the incumbent, with what broke
  recorded.
- **inconclusive**: the difference was below the threshold, or the run
  was too small to tell. The incumbent stays. Not because it won, but
  because the challenger proved nothing.

`inconclusive` is the outcome you will be most tempted to launder into
`held`. Effort spent is not evidence. A method that nobody can show made
a difference has not earned the incumbent's place.

## Failure modes

- Choosing the measure after seeing the results, then presenting it as
  though it was chosen first. This will happen, and it will not feel like
  cheating at the time.
- Running six rounds and reporting a trend. Six is not a trend.
- Comparing a version you wrote against one you did not. Ask someone else
  to run it, or say plainly that you had a stake in the outcome.
- Reporting `held` on a difference you cannot quantify.
- Reporting `held` below the minimum run count committed to beforehand,
  because the early runs happened to look good.
- Scoring your own runs unblinded when blind scoring was possible and
  just skipped.
- Choosing the reviewer of whether the metric measures the right thing
  after seeing which way the metric came out.
- Promoting a skill version that no report or run actually tested,
  because the reports were filed against an earlier revision and
  nobody re-checked the `skill_version` field before promoting.
