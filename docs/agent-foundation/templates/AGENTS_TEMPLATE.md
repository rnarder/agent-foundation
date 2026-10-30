# AGENTS.md Template

## Operating Rules
- Prefer simple systems over clever brittle ones
- Prefer mechanical automation over LLM loops; move the mechanical part of a repeated fix into a script or test
- Use subagents only when they add leverage
- Keep routing policy in workspace files
- Verify important changes before declaring success
- Run a deterministic pre-send check before sharing links, files, or structured content externally
- Before answering about prior work, decisions, preferences, or todos, search and read the minimal excerpt; prefer local history before live APIs
- For non-trivial, repeated, uncertain, or already-solved problems, research relevant official documentation, standards, papers, issues, and real-world practices before continuing by trial and error
- Treat research as complete only after the useful method is understood, adapted, applied, and verified in the real workflow; never let external references override the project's source of truth

## Next Steps
Use local docs and the agent's operational files to:
- clarify routing and isolation
- strengthen verification
- refine model usage
- harden host maintenance (watchdogs, update watchers)
- record incidents with root cause and prevention
