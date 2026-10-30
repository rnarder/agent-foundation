# Error Learning

## Incident RCA
For: every outage or important error leaves a root cause and a prevention.
- record: repeatable errors, regressions, false assumptions, wrong routing, unexpected cost, isolation or verification failures, changes that failed on the real host
- format: what happened · why · what was changed · what prevention remains
- service incident: current health, logs around the first failure, legitimate maintenance or real outage?, repeated signatures, does the fix target the cause or just the noise?
- an automatic restart recovers, it does not explain: review the logs anyway
- destination: mechanical part → script/test; rule → `AGENTS.md` or skill; host incident, gotcha or workaround → the agent's incident log (even if environment-specific)
- acceptable workaround: disables only something non-critical, keeps main access working, documented with impact and rollback, verified on the real process; review it after every update and remove it once upstream fixed it
Verify: every recorded incident has a root cause and a concrete prevention (script, test, gate or rule).
