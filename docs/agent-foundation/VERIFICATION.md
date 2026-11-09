# Verification

Closing a piece of work = implemented + checked against real state + documented if it leaves a reusable lesson. "The command returned no error" is not evidence.

## Verification per change type
For: every change type has its concrete test.
- **config patch**: reread the real state after the restart (effective models, agents, fallbacks)
- **OpenClaw update**: release notes, `openclaw status`, affected config, workarounds still needed
- **reboot / system update**: active kernel and version, reboot pending or not, gateway and channel health after the post-boot window, logs if there was a restart loop even if health is green
- **watchdog / cron**: validate syntax (`bash -n`, `py_compile`), run once by hand, installed exactly once, local state/log, no duplicate alerts in steady state
- **environment variable as workaround**: file where it persists, real process receiving it (`/proc/<pid>/environ`), restart only the needed service, failure signature gone, impact and rollback documented
- **security / sandbox**: test a real flow on the host, not just the config
- **routing / models**: real availability and cost, a real task of the affected role
Verify: the closure of each change cites the evidence from its line.

## Gate before sending out
For: links, files and recipients go out correct.
- payload with links, files, attachments or structured fields → deterministic check before sending
- links reachable (or marked as unverified), files exist and are not empty, correct recipient/channel/thread, required fields complete, channel format, no secrets or private context
Verify: a send with a broken link or an empty file is blocked before it goes out.

## Review after degraded capacity
For: work done with less capacity does not become a durable decision without review.
- degraded = fallback or smaller model, partial context, critical tools missing, isolated session without the normal checks
- sensitive or durable work done this way → review with the right capacity: decisions, files/config touched, external actions, evidence used, what to accept or redo
Verify: no durable decision made on fallback goes without that review.

## Clear user-facing closure
For: substantial completed or blocked work. State the result, the concrete verification evidence, and any actual pending work or blocker. Mention material autonomous decisions. Omit empty fields and do not force a template onto trivial replies. Never equate prepared with sent, or a successful command with a verified outcome. The agent performs available checks rather than transferring them to the user.
Verify: the final reply agrees with observed state and distinguishes completion from pending work.

## Reproducible comparisons
For: evaluating models, prompts, or workflow changes on comparable evidence.
- Fix the inputs, pass criteria, and scoring method before running the comparison.
- Use the same task inputs and equivalent conditions; record versions, settings, tools, and any unavoidable differences.
- Preserve the outputs and evaluation evidence so another reviewer can check the conclusion. Protect private inputs and credentials.
- Score response quality and successful execution separately. A written answer does not prove that an action works.
- Report the scope and limitations; do not generalize beyond the tested tasks.
Verify: the comparison includes fixed criteria, recorded conditions, preserved outputs, and conclusions supported by the measured capability.

## Explicit verification limits
For: reporting incomplete or unavailable verification accurately.
- State exactly what was verified and what remains unverified, why, and the concrete evidence or access needed to finish checking.
- Perform available checks within the authorized scope before declaring a blocker.
- Keep partial checks distinct from end-to-end verification. Never present an attempted action, prepared artifact, or intermediate success as a verified final outcome.
Verify: every completion claim is supported by observed evidence; any remaining verification gap has an explicit reason and next check.
