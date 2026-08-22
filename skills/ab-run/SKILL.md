---
name: ab-run
description: Run a proposed method alongside the one it would replace, on real work, and report what actually differed. Use before any new skill or rule is promoted from beta to stable. Nothing here reaches stable without one.
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

- **held**: the predicted difference appeared, above the threshold. The
  method moves to stable.
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
