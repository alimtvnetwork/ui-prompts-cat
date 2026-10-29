# Recent session — 2026-10-29

This note records what was created and shipped on 2026-10-29. Paths below are relative git paths.

## go-email-reader

- Specifications for warm-up sequences 08 through 13 are in `02-spec/21-app/08-ui-and-warm-up-algorithm-improvements/` through `02-spec/21-app/13-ui-and-warm-up-algorithm-improvements/`.
- Plans are in `.ai-memory/plans/pending/08-ui-and-warm-up-algorithm-improvements.md` through `.ai-memory/plans/pending/13-ui-and-warm-up-algorithm-improvements.md`.
- Sequence 08 is the connector and gate map. Sequence 09 is brakes. Sequence 10 is the send lease and cool-down. Sequence 11 is the shadow compare. Sequence 12 is the pace envelope. Sequence 13 is the shared quiet window.
- The live tick now consults `internal/warmup/gatefeed.go`. A peer can tighten the remaining-send cap and cannot raise it. An absent or stale peer does not stop local warm-up. Local quiet hours hold. A quiet skip does not send. A dry run does not spend the cap. The gate order is health, cadence, connector, theme.
- The reader UI gate map reads `GET /api/warmup/gates`.
- Commit `f3864ee` is on `main` and is pushed. The remote uses SSH.
- Sequences 08 through 13 stay pending as catalogs. Only the gate engine is implemented.
- `user.email` is `local@gitmap`. The name is `gitmap automation`.

## gitmap-v28

- Cursor-like IDE setup landed in `cli/cmdide/ide_setup.go`, `cli/cmdide/setup/`, and `cli/cmdui/ui_server_ide_setup.go`.
- The spec is `02-spec/21-app/352-cursor-like-ide-setup-from-gitmap/`.
- Pushed commits include `3229df9b4`, `864012968`, and `04690b952`.
- `cli/cov` is a coverage profile and was not committed.

## repo-cache

- Commit `f474298` stores heatmap databases, including `.heatmap/06-cursor/go-email-reader/heatmap.db`.
- SQLite `-shm` and `-wal` sidecars were not committed.

## Push denied

These local commits are still unpushed because GitHub denied `alimtvnetwork`:

- `alim.karim.profile` (19 commits)
- `kubernetes-training-v1` (19 commits)
- `common-linux-installer` (1 commit)

## Rules learned

- Do not put a personal access token in a git remote URL. Use SSH.
- Do not commit coverage profiles or SQLite sidecar files.

## Last 30 commits in this repo

```text
0659c95 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts (29-Oct-26 06:33 pm)
0d8f8ef feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts (29-Oct-26 04:24 pm)
ab99f86 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts (29-Oct-26 03:18 pm)
9f26c49 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts (29-Oct-26 02:55 pm)
84af1d1 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts (28-Oct-26 10:19 am)
1cfff71 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
4b772ad feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
5c40a61 feat(sync): sync canonical prompts, skills, gitmap agent standards, and purge deprecated 46 task manager
fe2ed1c feat(sync): sync canonical prompts, skills, gitmap agent standards, and purge deprecated 46 task manager
5853cd0 feat(sync): sync canonical prompts, skills, gitmap agent standards, and purge deprecated 46 task manager
9dfa3dd feat(sync): sync canonical prompts, skills, gitmap agent standards, and purge deprecated 46 task manager
c04b915 feat(sync): sync canonical prompts, skills, gitmap agent standards, and purge deprecated 46 task manager
392dd37 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
36d9578 feat(sync): sync canonical prompts, skills, gitmap agent standards, and purge deprecated 46 task manager
898f6b9 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
f830d18 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
3cdd425 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
caaebbc feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
a8d07d2 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
eda7020 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
c957285 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
02cd86b feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
32796f1 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
6a26dd6 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
76d2648 Chore: chore - purge deprecated v4 prompts
8f2849e feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
67d73e6 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
274efe0 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
14b33bf feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
bd67d31 feat(sync) - sync canonical v6 execute suite, gitmap heatmap telemetry, skills, and prompts
```
