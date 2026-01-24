# Failure Taxonomy

This document enumerates recurring failure modes observed in large-scale AI evaluation, annotation, and escalation systems. These failures are not individual mistakes, but structural pathologies that emerge under scale, time pressure, ambiguity, and incentive misalignment.

The taxonomy is intended to be diagnostic, not punitive.

---

## Rubric Literalism

**Description:**  
Evaluators adhere rigidly to rubric wording even when contextual signals clearly indicate misclassification.

**Diagnostic Signs:**
- High inter-annotator agreement with low downstream usefulness
- Annotator justifications mirror rubric language verbatim
- Edge cases repeatedly “resolved” without escalation yet reappear later

**Root Cause:**  
Rubrics are treated as ground truth rather than measurement instruments designed to be revised.

---

## Premature Ambiguity Collapse

**Description:**  
Ambiguous cases are forced into discrete labels too early, eliminating uncertainty before it can be examined or resolved.

**Diagnostic Signs:**
- Overconfident labels on underspecified inputs
- Reduced use of “uncertain” or “needs clarification” pathways
- Downstream disagreement framed as “model failure” rather than evaluation failure

**Root Cause:**  
Operational pressure to close tickets overrides epistemic caution.

---

## Escalation Avoidance

**Description:**  
Evaluators avoid escalation due to perceived cost, friction, or fear of negative performance signals.

**Diagnostic Signs:**
- Unusually low escalation rates in high-ambiguity domains
- Repeated borderline calls by the same evaluators
- “I handled it locally” rationales without documented reasoning

**Root Cause:**  
Escalation is socially or economically penalized.

---

## Escalation Overuse

**Description:**  
Escalation is used as a substitute for judgment, pushing routine or well-understood cases upward.

**Diagnostic Signs:**
- High escalation volume with low variance in outcomes
- Seniors acting as rubber stamps
- Little learning or rubric refinement despite frequent escalation

**Root Cause:**  
Incentives reward deferral of responsibility over accurate resolution.

---

## Template Drift

**Description:**  
Evaluation templates and checklists accumulate legacy assumptions that no longer reflect the system being evaluated.

**Diagnostic Signs:**
- Questions that no longer map cleanly to model behavior
- Evaluators expressing “this doesn’t quite fit, but…”
- Growing reliance on comments to override template outputs

**Root Cause:**  
Templates outlive the conditions under which they were designed.

---

## Escalation Decoupling

**Description:**  
Procedural escalation continues (tickets advance, seniors review, approvals are issued) after the semantic frame that escalation presupposes has already decayed.

The system appears to function correctly — metrics pass, workflows execute — but escalation no longer restores meaning or resolves uncertainty. It performs governance theater on stale premises.

**Diagnostic Signs:**
- Stable or increasing escalation volume alongside declining semantic coherence
- Compressed variance in escalation rationales (“approved as expected”)
- Persistent senior approval despite acknowledged downstream incoherence
- Issues recur at higher abstraction levels without reframing

**Root Cause:**  
Escalation is hierarchically coupled but semantically uncoupled. Authority advances faster than understanding.

**Why It Matters:**  
Once escalation decoupling occurs, further escalation increases cost without increasing truth. The system expends resources while drifting further from the conditions it was built to govern.

**Primary Risk:**  
False confidence at scale — the appearance of diligence masking the loss of epistemic control.

---

## Notes

Many failures co-occur. Escalation Decoupling is often downstream of Template Drift or Premature Ambiguity Collapse, but once present it becomes self-sustaining unless explicitly detected and interrupted.

Detecting and correcting these failures typically requires changes to feedback loops, incentive structures, or escalation semantics — not additional training alone.
