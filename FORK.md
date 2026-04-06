# FORK

## Fork metadata

- **Parent repo:** [paperclipai/paperclip](https://github.com/paperclipai/paperclip)
- **Fork repo:** [benvdbergh/paperclip](https://github.com/benvdbergh/paperclip)
- **Upstream remote:** `upstream` → `https://github.com/paperclipai/paperclip.git`
- **Upstream default branch:** `master` (moves with parent; see baseline for what this fork pins to)
- **Fork default branch:** `master` (tracks `origin/master`)
- **Maintainers:** benvdbergh (update this list as ownership changes)

## Baseline (as of 2026-04-06)

- **Pinned parent release:** tag **`v2026.403.0`** @ `a07237779bd5391a4683a754ed95249d57a49b2c`
- **Fork `master` tip:** `a0723777` **+** one commit adding only `FORK.md` (ledger; no product code changes vs the tag).
- **Note:** After fetch, `upstream/master` may be **ahead** of this tag (parent continues on `master`). This fork intentionally tracks the **named release**, not necessarily `upstream/master` HEAD, until you choose a newer pin.

## Fork policy

- **Goal:** Stay aligned with [paperclipai/paperclip](https://github.com/paperclipai/paperclip), pinning to specific upstream **releases** when syncing, and recording decisions in this ledger.
- **Divergence policy:** **Strategic** — adopt parent releases by default; keep fork-only changes only when documented here.
- **Sync cadence:** **Event-driven** (e.g. after upstream releases you adopt).
- **Preferred sync mode:** **Merge** from `upstream/master` (or a release tag) into `master` when advancing; **reset --hard** to a release SHA only when discarding obsolete fork-only commits (as in the 2026-04-06 sync).

Narrative context (adapter plugins, Hermes externalization, UI QoL) is in root `AGENTS.md` § Fork-Specific where present.

## Divergence ledger

| Area | Type | Keep / Adopt / Hybrid | Reason | Last reviewed | Parent link |
|------|------|------------------------|--------|---------------|-------------|
| `FORK.md` | documentation | Keep | Fork governance ledger; only file differing from parent tag `v2026.403.0` @ `a0723777` | 2026-04-06 | — |

## Sync history

| Date | Upstream ref | Result | Notes |
|------|--------------|--------|-------|
| 2026-04-06 | `upstream/master` @ `eefe9f39` | baseline recorded | Initialized `FORK.md`; fork had been 4 commits ahead on older base |
| 2026-04-06 | **`v2026.403.0`** @ `a0723777` | **success** | `git reset --hard` to parent release; removed stale fork-only fixes; ledger refreshed |

## Upstream contribution log

| Date | Branch | PR URL | Status | Notes |
|------|--------|--------|--------|-------|
| — | — | — | — | No upstream PRs logged yet |
