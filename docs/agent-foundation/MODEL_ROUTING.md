# Model Routing

## Model per task according to the real plan
For: each task with the right model, without excess cost or risk.
- order: is an LLM needed? → what level? → which models does the real plan cover? → which fallback keeps continuity?
- no LLM: mechanical tasks
- small/fast: triage, classification, structured extraction, normalization
- main: conversation, synthesis, normal operational decisions
- strong: complex debugging, architecture, delicate decisions
- by role: `triage` cheap, `main` main model, `ops` strong and reliable, `review` stable, `research` good enough at controlled cost
- premium models never on automatic
- the policy lives in workspace files
Verify: the routing is written down and every model in the normal flow passed the checklist below.

## Promoting a model to the normal flow
- available on this host/provider
- covered by the real plan/cost
- tested on a real task of the role
- measurement isolated from concurrent activity on the same account
- the fallback after it still makes sense

## Fallback
For: continuity without surprises.
- chosen for quality and cost, not just availability
- notify if the fallback changes quality, latency or cost significantly
- work done on fallback goes through the review in `VERIFICATION.md`
