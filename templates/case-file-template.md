# <Week/Pack> — <Incident Type> (Lab)

# Ticket Case File

## Customer symptom
<What the user/customer reported. Keep it 1–3 sentences.>

## Impact / Severity
<What is impacted, how many users, urgency, and your initial severity assumption.>
<If unsure, state: "Unverified outage until evidence confirms." >

## Hypothesis tree (initial)
- <Possible cause 1: DNS / auth / service down / config / permissions / etc.>
- <Possible cause 2>
- <Possible cause 3>
- <Possible cause 4>

## Evidence Table
| Check | Command / Tool | Result | What it means | Proof file |
|---|---|---|---|---|
| <check name> | `<command>` | <pass/fail + key output> | <short meaning> | `evidence/raw/<file>.txt` |
| <check name> | `<command>` | <pass/fail + key output> | <short meaning> | `evidence/raw/<file>.txt` |

## Diagnosis (evidence-based)
<Write 3–6 sentences based on what your evidence proves.>
- Confirmed:
- Not confirmed yet:
- Notes / constraints:

## Fix / Mitigation
<What you changed or did NOT change.>
- If no changes: "No remediation changes applied. Read-only verification only."
- If changes: list what changed and why.

## Verification Notes
- Primary proof: `<key line/result>`
- Secondary proof: `<key line/result>`
- Notes: <important limitations, blocked tools, environment constraints>

## Decision Notes
<Explain your reasoning: what you prioritized and why. Example: "DNS -> HTTPS -> optional tools".>
<Include: why you did/didn’t escalate.>

## Communication Updates

### First Update
<Short customer-friendly update: what you’re checking and when you’ll update next.>

### Next Update
<Progress update: what was ruled out, what’s next.>

### Resolution Update
<Final summary: what evidence showed, whether you reproduced, what outcome was, what changes were made (or not).>

## Proof Artifact
- Diagram / screenshot: `evidence/<artifact>.png`
- Source (editable): `evidence/<artifact-source>`

## Cleanup Proof (end of week)
<What resources you will delete/stop and where proof will be stored.>
Example: "Delete `rg-<name>` and save proof in `cleanup-proof/`."