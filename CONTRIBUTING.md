# Contributing to Stitch

Thanks for taking the time to contribute. This file routes your change to the
right repository — every piece of Stitch has exactly one source of truth, and
commits anywhere else get overwritten by the next sync.

## Where does my change go?

| Change | Repository | Flow |
|---|---|---|
| Client UI / engine (`src/`, `extension/`, autoreg core) | [Stitch-Manager](https://github.com/StitchWB/Stitch-Manager) | PR to `main` |
| A service plugin (mail, totp, sheets, radar, …) | that plugin's own repo | PR to `main`; see its README |
| A new service plugin | fork [stitch-plugin-template](https://github.com/StitchWB/stitch-plugin-template) | own repo + optional catalog listing |
| Community data-only plugin | [stitch-plugin-catalog](https://github.com/StitchWB/stitch-plugin-catalog) | PR with a catalog entry |
| Distribution server, signing, autoreg methods | private hub | core team only (report needs as issues in Stitch-Manager) |

Do not open hub-mirror PRs: `plugins-src/` and the Zone-1 client tree inside
the private hub are mirrors/submodules and are refreshed automatically.

## Plugin authoring

Service plugins are out-of-process subprocesses speaking JSON-RPC 2.0 with a
declarative UI schema. The contract lives in
[docs/service-plugins.md](https://github.com/StitchWB/Stitch-Manager/blob/main/docs/service-plugins.md)
(public mirror) and the scaffold in stitch-plugin-template.

## Pull requests

- One concern per PR; describe the *why*, not the diff.
- Conventional commit titles (`feat:`, `fix:`, `docs:`, …) — release notes and
  changelogs are generated from them.
- Label the PR (`feat`, `fix`, `plugin`, `docs`): GitHub release notes in
  Stitch-Manager are categorized by these labels.
- Keep CI green: lint + compile + manifest checks run on every PR.
- No new dependencies without a reason stated in the PR.

## Issues

Use the issue templates in the repository you found the problem in. For
security reports see [SECURITY.md](SECURITY.md) — never as public issues.
