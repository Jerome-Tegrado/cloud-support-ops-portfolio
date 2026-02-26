# Runbook: <Incident Title>

## Purpose
<1–3 sentences: what this runbook helps diagnose/restore.>

## Scope / Assumptions
- Applies to: <what symptoms/incident types this covers>
- Test environment/vantage point: <where checks are run from; note results can differ by network/location>
- Primary signal(s): <what you treat as the main truth, e.g., HTTP/TLS response, service health>
- Supplemental signal(s): <ping/traceroute/logs, etc.>
- Approach: evidence-first, read-only checks before changes

## Inputs (what you need)
- Reported symptom:
- Affected service/URL/resource:
- Start time (with timezone):
- Impact scope (who/where/how many):
- Environment (prod/test/lab):

## L1 Safe Checks (Quick Triage)
1. Confirm the target (human error check)
   - <typo, wrong URL/path, wrong region, wrong account/tenant, wrong environment>

2. Reproduce the issue (basic confirmation)
   - <exact steps to reproduce>
   - Record timestamp + exact error

3. Primary availability/health checks
   - <primary check 1>
   - <primary check 2>

4. Basic dependency checks
   - <DNS/auth/network/storage/backend/etc. depending on incident>

5. Collect initial evidence
   - <commands/tools used + what outputs to capture>

## L1 Interpretation Guide
- If <condition> → likely <cause> → next step <action>
- If <condition> → likely <cause> → next step <action>
- Notes:
  - Treat supplemental signals as supportive only (may be blocked/filtered)
  - Do not conclude root cause without evidence

## L2 Deeper Checks (Isolation)
Use L2 when L1 is not enough to confirm the failing layer.

- Component isolation
  - Determine if failure is in: <client/auth/DNS/network/TLS/app/backend/platform>
  - Identify the first failing step (lookup → connect → handshake → response)

- Telemetry / logs (read-only)
  - <monitoring dashboards, log queries, metrics to check>
  - Capture timestamps + screenshots/snippets

- Configuration review (read-only)
  - <recent changes, access/RBAC, firewall/NSG, routing, cert bindings, app settings>

- Recent change correlation
  - What changed before incident start time?
  - Compare timestamps and note likely rollback candidates

## Decision Points
- If <X> fails → investigate <path A>
- If <Y> fails → investigate <path B>
- If evidence is insufficient or remediation is high-risk → escalate

## Safety Rule (before changes)
- Do read-only checks first
- Any change must include:
  - Reason (evidence-based)
  - Rollback plan
  - Verification steps
  - Owner/approval (if required)

## Escalation Triggers
Escalate when:
- Root cause not confirmed after L1/L2
- Next step requires high-risk/out-of-scope changes
- Platform/resource health indicates broader incident
- Impact/severity is high or widespread
- Access/logs required are unavailable

## Escalation Packet (Required)
Include:
- Incident summary + timestamps (with timezone)
- Impact / severity
- What you tested (L1/L2) and results (pass/fail)
- Evidence: command outputs, screenshots, logs, metrics
- Working theory (clearly label assumptions)
- Recent change correlation
- Specific ask/requested action
- References/links/attachments

## Rollback (if changes were made)
- Known-good baseline:
- Change made:
- Rollback method:
- Rollback triggers:
- Rollback evidence captured:

## Verification (after fix / after escalation)
- Re-test original symptom using the same steps
- Re-run primary checks and confirm expected results
- Repeat once (consistency check)
- Cross-vantage check (if available)
- Record final evidence + timestamps
- Final status: resolved / not reproduced / escalated / monitoring