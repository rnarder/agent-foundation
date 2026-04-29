# Skill Overlap Triage

Quick triage pass based on `skillify-doctor` overlap output.

## Purpose

Not every overlap is a problem.
Some are healthy adjacency between neighboring skills.
This note separates:
- healthy overlap
- watchlist overlap
- likely cleanup candidate

## Healthy overlap

These pairs look normal and probably do not need immediate action.

### brainstorming ↔ panorama-360
Reason: both live in pre-execution thinking space, but `panorama-360` is the deeper alignment mode.

### brainstorming ↔ writing-plans
Reason: brainstorming explores options; writing-plans converts chosen direction into executable steps.

### panorama-360 ↔ writing-plans
Reason: panorama clarifies; planning operationalizes.

### systematic-debugging ↔ verification-before-completion
Reason: debugging finds/fixes causes; verification confirms reality after a fix.

### requesting-code-review ↔ verification-before-completion
Reason: review is critique; verification is evidence.

## Watchlist overlap

These are not necessarily bad, but the boundaries should stay explicit.

### cost-zero-automation ↔ housekeeping-ops
Potential confusion:
- cost-zero-automation = design/build efficient automations
- housekeeping-ops = keep existing automations healthy over time

Suggested boundary:
- build/change path → `cost-zero-automation`
- monitor/maintain/audit path → `housekeeping-ops`

### cost-zero-automation ↔ writing-plans
Potential confusion:
- one is a domain-specific design lens
- the other is a general planning workflow

Suggested boundary:
- if low-cost automation tradeoffs are central, read `cost-zero-automation`
- if the main need is execution structure, read `writing-plans`

### requesting-code-review ↔ writing-plans
Potential confusion:
- both touch changes/refactors

Suggested boundary:
- before implementation or major change shape → `writing-plans`
- after implementation, before claiming done → `requesting-code-review`

### systematic-debugging ↔ writing-plans
Potential confusion:
- debugging follow-up work can need planning

Suggested boundary:
- root cause / evidence / hypothesis testing → `systematic-debugging`
- execution plan after diagnosis → `writing-plans`

### verification-before-completion ↔ writing-plans
Potential confusion:
- both mention verification and changes

Suggested boundary:
- planning says what to verify
- verification-before-completion performs the completion gate mindset

## Likely cleanup candidates

These seem worth tightening more actively.

### last30days ↔ x-search
Why it matters:
- both are about current discourse/search on the web/social/X
- easy to trigger the wrong one

Suggested split:
- `last30days` = broad recent research across Reddit + X + Web with synthesis
- `x-search` = X-specific retrieval/search path

Action:
- tighten descriptions so one is clearly panorama research and the other clearly X retrieval.

### openclaw-tavily-search ↔ x-search
Why it matters:
- both advertise generic search behavior

Suggested split:
- `openclaw-tavily-search` = generic web search fallback
- `x-search` = X/Twitter-specific search/retrieval

Action:
- make the provider/tool distinction explicit in descriptions and trigger language.

## Recommended next cleanup order

1. `last30days` ↔ `x-search`
2. `openclaw-tavily-search` ↔ `x-search`
3. `cost-zero-automation` ↔ `housekeeping-ops`
4. leave the planning/debugging/review cluster mostly as-is unless real confusion appears in use

## Principle

Do not remove overlap just because words are similar.
Clean up only when overlap causes bad routing, hesitation, or duplicated capability.
