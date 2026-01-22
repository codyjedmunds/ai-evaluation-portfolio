# Resolve vs Escalate: Decision Flow

This document defines a practical decision flow for determining whether an evaluation issue should be resolved locally or escalated for review or guideline clarification.

The goal is to preserve judgment quality while preventing unnecessary escalation, throughput disruption, and silent quality drift.

This flow is intended to support evaluator autonomy **without fragmenting standards**.

---

## Guiding Principle

Escalation is a tool for resolving **system-level ambiguity**, not a default response to individual uncertainty.

Local resolution is preferred when it can be performed consistently, defensibly, and without introducing downstream risk.

---

## Step 1: Identify the Issue Type

Before choosing a resolution path, classify the issue according to its primary cause.

Common issue types include:

- **Rubric ambiguity**  
  The rubric allows multiple plausible interpretations or produces conflicting outcomes.

- **Partial correctness**  
  The model output satisfies some but not all evaluation criteria.

- **Conflicting instructions**  
  Different sections of the rubric or task instructions cannot be jointly satisfied.

- **Model non-responsiveness or refusal**  
  The model avoids the task without a clear rubric-aligned reason.

- **Evaluator uncertainty without rubric conflict**  
  The evaluator is unsure, but the rubric itself is coherent.

Correct classification reduces inappropriate escalation.

---

## Step 2: Assess Local Resolvability

An issue is considered *locally resolvable* if **all** of the following conditions are met:

- The rubric provides a reasonable interpretation path
- Similar cases have been resolved consistently
- The evaluator can articulate a clear, defensible rationale
- The decision does not meaningfully affect downstream aggregation
- The outcome does not set new precedent

If these conditions are met, the evaluator should resolve locally and document the rationale.

---

## Step 3: Assess Escalation Criteria

Escalation is appropriate when **one or more** of the following conditions apply:

- The rubric produces contradictory outcomes
- Reasonable evaluators disagree materially
- The issue recurs across multiple samples
- Resolution would implicitly set precedent
- Incorrect handling risks systemic drift
- Confidence in any local resolution is low and persistent

Escalation should be proportional to impact, not driven by discomfort or risk aversion.

---

## Step 4: Choose the Resolution Path

Based on the assessment, select one of the following paths:

### Path A: Resolve Locally
Use when:
- The rubric is sufficient
- Impact is limited
- The rationale is defensible

Action:
- Apply the rubric
- Record a concise rationale
- Proceed with normal throughput

---

### Path B: Flag for QA Review
Use when:
- Confidence is moderate
- Consistency is uncertain
- Peer alignment would improve reliability

Action:
- Document the issue
- Flag for QA review
- Continue evaluation where possible

---

### Path C: Escalate for Guideline Clarification
Use when:
- The rubric fails systematically
- Disagreement persists among experienced evaluators
- The issue affects multiple samples or categories

Action:
- Escalate with clear documentation
- Avoid speculative resolution
- Resume once guidance is clarified

---

## Step 5: Document the Decision

All non-trivial decisions should include:

- Issue summary
- Resolution or escalation choice
- Justification
- Confidence level
- Notes on potential downstream impact

Documentation should support traceability without overburdening throughput.

---

## Anti-Patterns

Common failure modes include:

- **Escalating to avoid judgment**  
  Treating escalation as a safe default.

- **Resolving to avoid review**  
  Forcing local resolution when precedent risk exists.

- **Over-documenting trivial cases**  
  Creating noise that obscures meaningful signals.

- **Under-documenting precedent-setting decisions**  
  Allowing silent drift.

- **Flattening confidence**  
  Using identical rationale structure across heterogeneous difficulty.

---

## Notes

This flow is designed to:
- preserve evaluator discretion
- prevent silent standard divergence
- maintain audit-safe decision trails
- support continuous guideline improvement

It is a living document and should evolve as failure modes surface in production.
