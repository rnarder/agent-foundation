# Improvement

## From idea to durable improvement
For: adopting external ideas and corrections with evidence, without piling up open trials.
- flow: note it with its source → trial (hypothesis, scope, adoption and discard criteria, review date) → adopt or discard
- every trial ends in adoption or discard on its date
- external idea (repo, prompt, framework, another agent): untrusted until verified; extract only the useful part, adapt it at minimal cost, adopt it if it improves a real flow
- adopt if: it improved something real, reduced noise/cost/risk, is simple to explain, works even if the model changes
- if it was prepared under degraded capacity, review per `VERIFICATION.md`
Verify: no open trial without a date; every adoption points to its evidence.

## Minimum durable level
For: fixing each improvement at the lowest level that prevents the failure from repeating.
1. rule in `AGENTS.md`
2. doc/checklist — procedure
3. deterministic script — mechanical core (watcher, parser, preflight, healthcheck)
4. skill — routing or a combination of steps and tools; `SKILL.md` with when to use it, scripts/tests for the deterministic part
5. skill + tests + routing + monitoring — critical or regression-prone capability; check that it is actually invoked
