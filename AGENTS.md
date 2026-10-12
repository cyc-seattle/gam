# AGENTS.md

Break-glass [GAM](https://github.com/GAM-team/GAM) scripts and Google Group settings templates for CYC's Google
Workspace. `gsuite-sync` in `cyc-seattle/isthmia` does this work day to day; use this repo only when it's broken.
See `README.md` for setup and each script.

## Tasks

Run them with `mise run <task>`:

- `install`: install the pinned tools (`gam`, `shellcheck`).
- `check`: `shellcheck` the scripts.
- `ci`: everything CI runs. It depends on `check`.
- `use-project`, `check-service-account`, `auth`: set up GAM's credentials.
- `export`: write group state to the spreadsheet.

There is no Node and there are no tests.

## Credentials

GAM keeps its credentials in `~/.config/gam/`, never in git. The `GAM_*` settings in `mise.toml` name the org, not
a secret, so they stay committed.

## Workspace access

GAM runs as the Workspace super-admin, for break-glass use only. Don't use it for routine work that `gsuite-sync`
can do.

## Comments

Comments explain **why**, not what. Keep them to a line or two. Write one where a reader would otherwise get it
wrong: a non-obvious constraint, a surprising API behavior, or a decision that looks arbitrary but isn't.

- Don't narrate the code, restate the diff, or argue for the approach you chose.
- Cite an issue (`#107`) instead of recounting its discussion.
- Don't cite a local plan file.
- Test each comment: if you deleted it, would a competent reader still make the same change correctly? If yes,
  delete it.

The same applies to docs:

- **Record the outcome, not the path to it.** Say what to do today, not what failed on the way.
- **No personal identifiers.** Use a role name or `<placeholder>` instead of an email address or a numeric account
  ID. Where a command needs a literal, use it once.
