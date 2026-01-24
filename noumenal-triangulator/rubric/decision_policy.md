# Decision Policy

This policy translates Auditor outputs (detected failure modes and assigned severities)
into a containment decision for the Noumenal Triangulator pipeline.

This policy defines how detected failure modes and assigned severities are
translated into a containment decision.

The goal of this policy is not to maximize intervention, but to ensure that
outputs proceed only when risk is appropriately bounded.

Decisions are policy-driven, reviewable, and context-sensitive.

---

## Decision inputs

The Escalation Controller considers:

- Maximum severity observed across all failure modes
- Number of detected failure modes
- Presence of specific high-risk patterns (e.g., role collapse, missing key variables)
- Intended downstream use (when specified)

No single signal is sufficient on its own; decisions are made by thresholding
combinations of signals.

---

## Primary decision table

| Max Severity | Failure Count | Recommended Action |
|--------------|---------------|--------------------|
| 0            | Any           | ALLOW              |
| 1            | 1–2           | ALLOW              |
| 1            | 3+            | ANNOTATE           |
| 2            | 1             | ANNOTATE           |
| 2            | 2+            | CLARIFY            |
| 3            | Any           | CLARIFY or HALT    |

This table defines default behavior. Contextual overrides may apply.

---

## Action definitions

- **ALLOW**  
  Output may proceed without modification.

- **ANNOTATE**  
  Output may proceed with warnings, caveats, or scope limitations attached.

- **CLARIFY**  
  Output must not proceed until missing variables or ambiguities are resolved.

- **HALT**  
  Output should not be used and must be escalated to a human reviewer.

---

## Override rules

The following conditions may override the default table:

### Automatic CLARIFY

- Missing Key Variable (F1) at Severity 2 or higher
- Ambiguity Masking (F6) in decision-support contexts

### Automatic HALT

- Role Collapse (F7) at Severity 3
- Incentive Distortion (F4) producing false urgency or moral pressure
- Any Severity 3 failure in high-stakes or irreversible contexts

Overrides must be explicitly documented in the decision rationale.

---

## Decision rationale requirements

Every containment decision must include:

- Referenced failure modes (by code)
- Assigned severities
- Evidence quotes from the output
- Threshold or override rule invoked

Decisions without explicit rationale are invalid.

---

## Notes on application

- Multiple low-severity failures may outweigh a single moderate failure.
- High severity does not automatically imply HALT unless override conditions
  are met.
- When in doubt between ANNOTATE and CLARIFY, prefer CLARIFY.
- Human judgment remains authoritative; this policy formalizes when it is required.
