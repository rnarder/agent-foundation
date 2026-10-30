# Core Principles

## Mechanical work leaves the model
For: lower cost and repeatable results.
- mechanical task (lookup, parsing, dates, filters, dedupe, validations, health checks, polling) → script, cron or deterministic check
- when fixing a repeatable failure, extract its mechanical part into a script or test; the model keeps only judgment: synthesis, prioritization, ambiguity, tradeoffs
Verify: no cron, heartbeat or periodic loop calls a model for deterministic work.

## 360 overview before important changes
For: not breaking what already works when touching architecture, config, routing or automations.
- before changing: current state, constraints, options and tradeoffs
Verify: the change records what was there before and why the option was chosen.

## Research until applied
For: research that ends in a verified change.
- for a repeated or uncertain problem, primary sources before trial and error
- cycle: research → understand → adapt → apply → verify
- it counts only if it changes a decision, workflow, artifact or gate and proves its value on the real path
- the project's sources of truth prevail over external references
Verify: every closed research item points to the change it produced.

## Local history before live APIs
For: answering about the past at lower cost, with fewer credentials in play and with the reasons behind decisions.
- exports, notes and local state first; live API only if information is missing or current state is needed
Verify: a question about a past event is answered without calling the live API when a local source exists.

## Catalog ≠ real plan
For: not designing on models, providers or features the plan does not include.
- available in the catalog, valid route and acceptable cost are three separate checks
- a theoretical improvement is worth nothing on the host until tested there
