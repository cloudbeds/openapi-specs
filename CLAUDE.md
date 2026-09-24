# CLAUDE.md

Guidance for coding agents and engineers working in this repository. Read it before making changes.

## What this repository is

Public, read-only mirror of the Cloudbeds OpenAPI specifications (`src/*.yaml`, `src/*.json`): PMS v1.2/v1.3/v2.0,
Guest Profiles, Group Profile, Fiscal Document, Accounting, Insights, Payments Vault, Pay by Link, Payment Element,
Attribute Tagging, OTA Build-to-Us. The same specs power <https://developers.cloudbeds.com> and the generated
Python SDK (<https://github.com/cloudbeds/cloudbeds-api-python>). MIT licensed.

There is no build, test, lint or CI here. The repository settings are managed by Terraform.

## 🔴 `src/` is generated — do not edit it here

Every file under `src/` is written by the sync workflow in `cloudbeds/developer-docs` (commits titled
`Sync OpenAPI specs from developer-docs`, author `github-actions[bot]`). Any manual change to `src/` in this
repository is overwritten on the next sync and never reaches the published documentation.

- To change a spec, change it in `cloudbeds/developer-docs` (private) and let the sync land it here.
- Do not open PRs against `src/` in this repository; close and redirect any that appear.
- `README.md`, `LICENSE` and this file are the only hand-maintained content.

## Public repository rules

- 🔴 This repository is public. Never add anything internal: hostnames, tenant or property identifiers, credentials,
  example tokens, internal links (Jira, Slack, Confluence, ArgoCD), squad or people names.
- 🔴 Never commit a spec that documents an unreleased or internal-only endpoint; that decision is made upstream in
  `developer-docs`.
- Do not create or move tags or releases; consumers pin to commits or fetch `main`.

## Git conventions

- Default branch `main`. Human changes (README, licence) go through a PR on a `<type>/<slug>` branch with a
  conventional commit subject (`docs: ...`, `chore: ...`), lowercase, imperative, under 100 characters.
- 🔴 Never rewrite history on `main`; fix forward.
- Never bypass the sync by force-pushing spec files, even to fix a typo — fix it upstream.

## If something is wrong in a spec

Report it to the API documentation owners via the upstream `developer-docs` repository rather than patching here.
