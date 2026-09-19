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

## Upcoming

- **2026-09-22**: the boundary-action confirmation deadline of
  `decisions/2026-08-22-boundary-fast-track-limits.md` falls due. The
  run of 2026-09-28 is the first that could act on it, if it is still
  unconfirmed.
- **2026-11-22**: the five provisional decisions reach their 90-day
  deadline.
