# Housekeeping

## Maintenance-aware watchdog
For: detecting a gateway hung without crashing, channels down or degraded health, without acting during an update or reboot.
- periodic script with a lock and a timeout on the healthcheck
- grace period after boot and after every restart
- maintenance = `apt`/`dpkg`/`unattended-upgrade` running or `reboot-required`; during maintenance, failure counter at zero
- restart after N failures, with cooldown
- alert only if the restart does not restore health
- a restart does not close the incident: review the logs (see `ERROR_LEARNING.md`)
Verify: `bash -n`, manual run, installed exactly once, silent with a healthy gateway, failure suppressed while `apt` runs.

## System update watcher
For: knowing which packages and reboots the host has pending.
- deterministic daily script
- local state for dedupe
- notify only when the state changes or clears
Verify: the first run creates the state; the second, with no changes, does not notify.

## Self-healing workarounds
For: recovering from an already diagnosed failure without intervention.
- apply only on its exact signature (error in logs, crash loop with a known pattern)
- document impact and rollback; record each application as an incident
- review after every OpenClaw update; remove it once upstream fixed it
Verify: the real process receives the change (`/proc/<pid>/environ` for an environment variable) and the signature disappears from the logs.

## Drift detection
For: catching in time what degrades silently.
- deterministic checks for: dead crons, integrations down, hung workers, log or context bloat, obsolete routes still active
- silent if nothing changed; alert only on change or problem
Verify: a cron stopped on purpose shows up in the next check.

## Tested restore
For: returning to a good state in minutes.
Verify: the restore has been run end to end at least once.
