---
skill: claim-check
skill_version: bac900759a832c6d692e778844ce565b75831fb5
agent: jenny-hermes-gpt55
vendor: OpenAI GPT-5.5, self-declared
harness: Hermes Agent
date: 2026-09-24
outcome: partial
---

## Task

Use `skills/claim-check` on factual repository claims in the public entry files, after Terje asked me to participate more actively and build a broader basis before reporting back.

Target commit: `bac900759a832c6d692e778844ce565b75831fb5`.

Target files:

- `README.md`
- `llms.txt`
- `CLAUDE.md`
- repository tree at the target commit

## Run log

1. Read `skills/claim-check/SKILL.md` and applied its claim extraction procedure.
2. Read `README.md`, `llms.txt`, and `CLAUDE.md`.
3. Listed tracked files with `git ls-files`.
4. Enumerated skill directories containing `SKILL.md` with Python.
5. Compared those skill names to the skill list in `llms.txt`.
6. Listed `.github` and found only `.github/CODEOWNERS`, no `.github/workflows` directory or workflow files.
7. Searched repository text for `<script`, `javascript:`, `analytics`, and `cookie`.

Command evidence collected:

- `skills_with_SKILL ['ab-run', 'blind-first-pass', 'claim-check', 'decide']`
- `llms_skill_names ['ab-run', 'blind-first-pass', 'claim-check', 'decide']`
- `workflow_files []`
- `<script [] count 0`
- `javascript: [] count 0`
- `analytics ['CLAUDE.md'] count 1`
- `cookie ['CLAUDE.md', reports...] count 6`

The `analytics` and `cookie` hits are prose references to the no-analytics/no-cookies rule and past claim-check topics, not implementation code.

## Claims and verdicts

### Claim 1

`llms.txt` says there are four skills: `blind-first-pass`, `claim-check`, `decide`, and `ab-run`.

Verdict: `supported`.

Source: repository tree at target commit. `skills/*/SKILL.md` contains exactly these four directories:

- `skills/ab-run/SKILL.md`
- `skills/blind-first-pass/SKILL.md`
- `skills/claim-check/SKILL.md`
- `skills/decide/SKILL.md`

### Claim 2

`llms.txt` says the site is static markdown and no JavaScript is required.

Verdict: `not contradicted within searched corpus`.

Searched corpus: all tracked repository files at target commit using text search for `<script` and `javascript:`. Both returned zero hits. This supports the repository-level implementation claim for the checked corpus, but it does not prove the deployed site has no injected platform scripts outside the repository.

### Claim 3

`CLAUDE.md` says no build step, no JavaScript, no analytics, no cookies.

Verdict: `not contradicted within searched corpus`.

Evidence: no workflow files under `.github`, no `<script`, no `javascript:`. The only `analytics` hit is the rule text in `CLAUDE.md`; the `cookie` hits are prose references in `CLAUDE.md` and older reports, not cookie-setting code.

Limit: I checked repository contents, not Cloudflare deployment settings or live HTTP response headers.

### Claim 4

`CLAUDE.md` says trust-anchor files have no independent review requirement yet, naming `CHARTER.md`, `AGENTS.md`, `CLAUDE.md`, `llms.txt`, and `.github/`.

Verdict: `supported for repository configuration, not for GitHub server settings`.

Source: `.github/CODEOWNERS` exists and names `/CHARTER.md @anderskanten`, but there are no workflow or branch-protection files in the repository. That supports the claim that the repository itself does not encode an independent review requirement. It does not prove GitHub branch protection settings, because those are outside the git tree and I did not have authenticated GitHub API access.

### Claim 5

`README.md` says the project has no queue system enforcing reciprocity.

Verdict: `not contradicted within searched corpus`.

Evidence: no workflow files, no queue implementation files, and no queue-specific configuration in the tracked tree. This is an absence claim, so the verdict is intentionally weaker than `supported`.

## Where the instruction did not match reality

`skills/claim-check` asks for exact sources. That works well for repository-internal claims because the source is the target tree itself. It is weaker for claims about GitHub branch protection or deployment configuration, because those facts can live outside the repository. I marked those as limited rather than pretending the tree proves more than it does.

## Proposed change

No change to `skills/claim-check`. The skill already forces the right distinction between supported claims and absence claims.

## Self-check

I initially wanted to mark the static-site and no-review claims as fully supported. That would overstate the evidence. The repository tree supports them only inside the checked corpus. Live deployment settings and GitHub branch protection remain external state.