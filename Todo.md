# Project TODOs — next improvements for issue triage & automation

This file lists useful next steps you can take to improve issue triage, automation, and contributor experience. Each item includes a short description, estimated effort, files to change, and suggested owner.

1) Map priority -> label
   - Description: Auto-add a `priority/*` label based on the Issue form `Priority` field (Low/Medium/High/Critical).
   - Effort: Low (1-2 hours)
   - Files: `.github/labels.yml` (add `priority/*` labels), `.github/ISSUE_TEMPLATE/issue_form.yml` (ensure priority values map), `.github/workflows/issue-validator.yml` (add logic to apply label)
   - Suggested owner: Repo maintainer

2) Strict per-type validation
   - Description: Make the validator require different fields depending on `Type` (e.g., require `Steps to reproduce` for `bug`).
   - Effort: Medium (2-4 hours)
   - Files: `.github/ISSUE_TEMPLATE/issue_form.yml`, `.github/workflows/issue-validator.yml`, `CONTRIBUTING.md` (update guidance)
   - Suggested owner: Repo maintainer

3) Auto-map Type -> label improvements
   - Description: Extend mapping to add secondary labels (e.g., `impact/high` or `area/ui`) and optionally remove conflicting labels.
   - Effort: Medium (2-3 hours)
   - Files: `.github/labels.yml`, `.github/workflows/issue-validator.yml`

4) Improve label-sync reliability
   - Description: Switch to a maintained label-sync action or add a scheduled sync job to ensure labels stay consistent.
   - Effort: Low (1-2 hours)
   - Files: `.github/workflows/labels-sync.yml`

5) Add bots / integrations
   - Description: Integrate a GitHub App or bot (like probot) for richer interactions, e.g., quick-replies, Slack notifications, or per-SIG routing.
   - Effort: Medium to High (4-8+ hours + infra)
   - Files: `.github/workflows/*`, server or app repo, documentation

6) Add tests for workflows
   - Description: Use `act`, `nektos/act`, or a workflow testing framework to validate behavior locally or in CI; add a workflow that runs synthetic test issues.
   - Effort: Medium (3-6 hours)
   - Files: `.github/workflows/test-*.yml`, test scripts, README

7) Add CONTRIBUTING examples and templates
   - Description: Expand `CONTRIBUTING.md` with explicit examples for filing bugs, feature requests, and a code of conduct. Add separate Markdown issue templates if desired.
   - Effort: Low (1-2 hours)
   - Files: `CONTRIBUTING.md`, `.github/ISSUE_TEMPLATE/*.md`

8) Add per-SIG owners and routing
   - Description: Maintain a `SIG-owners.md` mapping (sig -> GitHub teams/users) and update the workflow to assign or ping the SIG owners automatically.
   - Effort: Medium (3-5 hours)
   - Files: `.github/workflows/issue-validator.yml`, `SIG-owners.md`

9) Add label lifecycle rules
   - Description: Decide when to remove `triage`/`help wanted`, add auto-close rules for stale triage issues, or add `needs-reproduction`.
   - Effort: Low to Medium (2-4 hours)
   - Files: `.github/workflows/*`, `.github/labels.yml`

10) Add analytics and dashboards
   - Description: Collect issue metrics (time-to-triage, open issues per SIG) using GitHub API + a simple dashboard or GitHub Project automation.
   - Effort: Medium to High (4-12 hours)
   - Files: new analytics scripts, optional infra

----

How to proceed: pick one item, open an issue for it (use the new issue form), and assign it to a maintainer. If you'd like, I can implement any of these — tell me which one to start with.
