# Deadline watchdog: run log

Weekly, Mondays 07:00 UTC. Model: Claude Sonnet 5. Read-only unless a
deadline is overdue; it never merges a provisional decision itself.

Since 2026-08-25 it runs three checks:

1. Boundary/emergency-action deadlines (`CHARTER.md` section 9).
2. Charter completion deadline, 30 days (`CHARTER.md` section 10).
3. Provisional-decision confirmation deadline, 90 days (`skills/decide`).

Run 2026-08-24 predates checks 2 and 3.

| Run date | Checks | Overdue | Action taken |
|---|---|---|---|
| 2026-08-24 | 1 | none | none |
| 2026-08-31 | 1, 2, 3 | none | none |
| 2026-09-07 | 1, 2, 3 | none | none |
| 2026-09-14 | 1, 2, 3 | none | none |
| 2026-09-28 | 1, 2, 3 | check 1 | PR #83 opened, custodian-required |

## Entries

### 2026-08-24 (check 1 only)

Read all 9 decision files. One boundary action with a stated deadline:
`2026-08-22-boundary-fast-track-limits.md`, due 2026-09-22, not yet
passed. Nothing overdue. No PR, issue or comment opened.

### 2026-08-31

Check 1: same single deadline, 2026-09-22, 22 days out. Check 2: five
decisions carry quoted charter text and a countersign; in every case the
text is already present verbatim in the live `CHARTER.md`, so all were
skipped. Check 3: five provisional decisions carry the explicit
deadline 2026-11-22; a sixth, `completion-deadline-for-charter-changes`,
computes to about 2026-11-23. None overdue. No action.

### 2026-09-07

Same result. Check 2 additionally noted that
`external-review-as-disinterested-countersign.md` is not eligible
because `countersigned_by` is empty and status is `open`. No action.

### 2026-09-14

Same result. Check 1: deadline 2026-09-22 now 8 days out. Check 3: six
provisional decisions, all about two months from their deadlines. No
action.

### 2026-09-28

Check 1: the 2026-09-22 deadline on
`decisions/2026-08-22-boundary-fast-track-limits.md` has passed.
Checked `decisions/`, `reviews/`, and this log for a recorded real beta
against a further emergency boundary action, or a second disinterested
countersign of that decision specifically; found neither. A 2026-09-24
external review
(`reviews/2026-09-24-hermes-gpt55-watchdog-deadline-review.md`) reached
the same reading and was watching for this run to act on it. Opened
[PR #83](https://github.com/anderskanten/countersign/pull/83),
`watchdog/revert-boundary-fast-track-limits`, proposing the revert of
the two `CHARTER.md` section 9 paragraphs that decision added, labeled
`custodian-required`, not merged. Added a dated note to the decision
file's "What happened" recording the same, without changing its
`status` field.

Check 2: same five decisions carry quoted charter text with a
non-empty countersign (a sixth new decision since the last run,
`countersign-section-required`, amends `skills/decide`, not
`CHARTER.md`, so it is not a check-2 candidate at all); in every case
the text is already present verbatim in the live `CHARTER.md`, so all
were skipped. None overdue.

Check 3: six provisional decisions. Five carry the explicit deadline
2026-11-22; `completion-deadline-for-charter-changes` computes to
about 2026-11-23. None overdue. No action.

## Upcoming

- **2026-11-22 / -23**: the six provisional decisions reach their
  90-day deadline.
- Whatever the custodian decides on PR #83 (merge or close) is the
  next thing to fold back into this log.
