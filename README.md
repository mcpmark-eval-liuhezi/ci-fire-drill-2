# ci-fire-drill-2

Sandbox for rehearsing the GitHub Actions on-call drill end to end. Nothing here touches production.

## What this repo contains

- A workflow at `.github/workflows/drill.yml` that can only be fired manually (`workflow_dispatch`).
- Its single job on `ubuntu-latest` runs one step that deliberately exits non-zero, so every run is a guaranteed red build.

## Why it's guaranteed to fail

The drill's only step runs `exit 1` on purpose. Use it to practice:

1. Firing the workflow on the default branch and reading the run's ID and conclusion.
2. Pulling the run's timing/usage metrics and billable runner time.
3. Requesting a re-run of only the failed jobs.
4. Tracking the drill steps in issues.
5. Rehearsing the review handoff with a pull request.
6. Running a supply-chain check against GitHub's global security advisory database.

## Cleanup

Delete this repository once the rehearsal is over.
