# AGENTS.md Template

## Operating Rules
- Prefer simple systems over clever brittle ones
- Prefer mechanical automation over LLM loops; move the mechanical part of a repeated fix into a script or test
- Use subagents only when they add leverage
- Keep routing policy in workspace files
- Verify important changes before declaring success
- Run a deterministic pre-send check before sharing links, files, or structured content externally
- For questions about the past, check local exports, notes, and state before live APIs
- Treat research as complete only after the useful method is adapted, applied, and verified in the real workflow; never let external references override the project's source of truth

## Next Steps
Use local docs and the agent's operational files to:
- clarify routing and isolation
- strengthen verification
- refine model usage
- harden host maintenance (watchdogs, update watchers)
- record incidents with root cause and prevention
