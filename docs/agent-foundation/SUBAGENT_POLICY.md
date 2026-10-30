# Subagent Policy

## When to delegate
For: delegating only when focus, isolation or parallelism pay for the coordination.
- yes: long tasks, separable research, complex debugging, isolated implementation, independent review, parallel branches that save time, work that benefits from fresh context, explicit request for a harness (Codex/Claude/Cursor/Gemini)
- no: short answers, a single command, tightly coupled reasoning, mechanical plumbing, when summarizing costs more than doing, when the subagent would need constant micro-decisions
- for medium tasks: 1 coordinator + 1 implementer or researcher + optional reviewer

## Runtime
For: not paying for continuity that is not used.
- isolated subagent: bounded run that only returns a result
- persistent ACP: continuity, its own thread or a coding session lasting more than one turn
- close persistent sessions that no longer add continuity

## Capabilities and cost
For: limiting risk and spend per role.
- each role with the minimum tools; `research` and `review` without `exec`, browser or messaging unless needed
- a separate agent only if it brings different tools, context or permissions; mechanical triage belongs to the deterministic router/main
- the cheapest model that works for the role; strong ones only where there is leverage
Verify: after changing sandbox or capabilities, a real task of the role works on the host.
