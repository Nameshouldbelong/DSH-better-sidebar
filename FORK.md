# Fork: Nameshouldbelong/DSH-better-sidebar

Baseline: upstream **v0.22.1** — the last npm-published release on the DSH **0.1.7** support line (upstream main moved to a 0.2.0-rc.1 single-line with v0.24.0).

## Why this fork exists

dsh-better-sidebar **0.19.1** (the previous install) crashes on dsh **0.1.7-rc.2** with `Minified React error #130` whenever a file link is opened in the sidebar:

- 0.19.1's built client chunks reference **28 `Icon*` components** (e.g. `IconChevronDownOutline14`, `IconCloseOutline16`) that upstream **removed from `@deepseek-ai/dsh-client-ui-primitives`** in 0.1.7 — at render time they resolve to `undefined` → React #130.
- Verified on the 0.22.1 build: **all 52 primitives symbols** used across `lib/*.js` exist on host 0.1.7-rc.2 (0 missing).

## Versioning

`0.22.1-dsh17.1` — upstream v0.22.1 code, marked as the fork's 0.1.7-line release 1.
