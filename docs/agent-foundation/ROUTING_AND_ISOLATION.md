# Routing and Isolation

## Explicit isolation
For: real separation when it matters.
- channels, topics, labels and folders = organization and delivery
- sessions, subagents and explicit workflows = isolation of context, memory and tools
- pattern: the topic picks the initial policy → the coordinator decides complexity and role → if needed, delegates to a session/subagent → the result returns to the delivery place
- the routing policy lives in workspace files
Verify: the written routing states, per channel/topic, the default behavior, when to delegate and where alerts go.

## Lightweight per-topic/project continuity
For: not losing each project's decisions and open items without bloating global memory.
- one short file per topic/project: active decisions, real open items, local rules, last checkpoint
- update only on a decision, closure, blocker, durable rule or checkpoint
- no secrets and no LLM upkeep
Verify: each file fits in a quick read and contains no chat logs.
