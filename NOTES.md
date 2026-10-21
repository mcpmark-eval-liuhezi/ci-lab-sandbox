# Instructor prep notes — CI debugging exercise

## Session context
- Sandbox repo: `ci-lab-sandbox` (safe to break, disposable)
- The `verify` job in `.github/workflows/lab-ci.yml` fails on purpose (`exit 1`)
- Trainees: new hires, Friday workshop

## Instructor run order
1. Open the pull request "Lab exercise: flaky verification job" and show the failing check on the PR page.
2. Have trainees open the failed run and read the log for the `verify` job.
3. Demonstrate "Re-run failed jobs" and discuss what the PR status shows after the retry.
4. Use the issue tree (`Workshop follow-up tracker`) to demo sub-issues; note that "Write instructor notes" was detached as out of scope.

## Talking points
- A failing check blocks nothing here (no branch protection yet) — good place to mention required checks.
- The retry will fail again: the job is deterministic, not actually flaky. Emphasize reading logs before re-running.

## Cleanup reminder
Delete this repo after the workshop.
