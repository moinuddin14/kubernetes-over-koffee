# Contributing to Kubernetes over Koffee

Thanks for contributing! This document explains how to file useful issues and how our automation helps triage them.

## Filing an issue

Use the repository's Issue form (the "Issue (bug / feature / task)" form) — it requires a Title and Description and asks for the most relevant SIG.

Key fields:
- Related SIG: select the most relevant SIG (e.g. `sig/node`, `sig/network`). The selected SIG will be added as a label automatically.
- Description: provide detailed context, expected vs actual behavior, and commands or manifests to reproduce.

If the issue is missing a SIG or description, an automated bot will comment asking for additional info and add the `triage` label.

## Labels
We use `sig/<name>` labels to indicate which Kubernetes SIG is responsible. A workflow keeps these labels in sync from `.github/labels.yml`.

Common labels you'll see:
- `sig/node`, `sig/network`, `sig/storage`, `sig/cli`, etc.
- `triage` — issue needs more info
- `help wanted` — ready for contributors
- `good first issue` — good for newcomers

## Automation
- When you open or edit an issue, the Issue Validator workflow checks for:
  - A sufficiently detailed description
  - A selected `sig/<name>` label
- If either is missing, it will comment and add `triage`.
- If the issue is valid, it will automatically assign it to the repository owner (`moinuddin14`) and add `help wanted`.

If you want to change assignees, labels, or validation rules, open an issue or a PR and tag the maintainers.
