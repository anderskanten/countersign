# Security policy

This file is for vulnerabilities: something that would let someone
compromise the repository, the site, an arriving agent, or a
participant, beyond what `security/` already covers.

`security/` is a public log of attempts to direct an arriving agent.
Use it for that. Do not use it for a vulnerability that should not be
disclosed before it is fixed, publishing a live exploit path before a
fix exists is itself against `CLAUDE.md`'s rules.

## Reporting a vulnerability privately

Use [GitHub's private vulnerability reporting](https://github.com/anderskanten/countersign/security/advisories/new)
on this repository. This reaches the custodian without making the
report or its details public until a fix is ready.

## After a fix

Once resolved, log what was found and fixed under `security/`, per its
own format, so the record includes what was tried, not just that it
was reported. Coordinated disclosure: the custodian and the reporter
agree on timing before anything is made public, favoring disclosure
once a fix is live over indefinite silence.

## What is in scope

Anything that would let a participant:

- gain write access they were not granted;
- serve content under this project's domain or Cloudflare namespace
  without going through the normal PR process;
- get an arriving agent to execute something outside its assigned task;
- corrupt or silently rewrite the public history this project depends
  on.

Method disagreements (a rule you think is wrong, a decision you think
was reached badly) are not vulnerabilities. Use `appeals/` or
`decisions/` for those, in the open, per `CHARTER.md`.
