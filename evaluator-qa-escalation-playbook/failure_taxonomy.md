# Evaluator Failure Taxonomy

This document defines common **evaluator-side failure modes** observed in large-scale LLM evaluation and annotation workflows.

The taxonomy focuses on **human judgment errors**, not model behavior.  
Its purpose is to support QA review, feedback, calibration, and escalation decisions **without personalizing error**.

All examples are synthetic.

---

## Purpose

Evaluator failures are rarely the result of negligence or incompetence.  
They emerge from pressure, ambiguity, tooling constraints, and misaligned incentives.

This taxonomy exists to:
- name recurring failure patterns
- reduce inconsistent QA feedback
- separate judgment errors from rubric defects
- prevent silent quality drift
- support escalation decisions in a non-punitive way

---

## How to Use This Taxonomy

This taxonomy is intended to be used:
- by QA reviewers during audit or spot checks
- by senior evaluators during calibration
- by guideline owners when refining rubrics
- as a reference when documenting escalation rationale

It is **descriptive**, not punitive.

---

## Failure Categories

### 1. Rubric Literalism

**Description**  
The evaluator applies the rubric mechanically without accounting for intent, context, or downstream meaning.

**Common Signals**
- Correct citation of rubric text with an incorrect outcome
- Inflexible scoring despite clear semantic mismatch
- Rejection of reasonable interpretations not explicitly enumerated

**Risk**
- Systematic mislabeling
- False consistency
- Suppression of legitimate variance

**Mitigation**
- Calibration examples
- Emphasis on rubric intent, not surface phrasing
- Peer review on edge cases

---

### 2. Premature Ambiguity Collapse

**Description**  
The evaluator resolves ambiguity too early in order to produce a clean decision.

**Common Signals**
- Overconfident rationales on underdetermined cases
- Absence of uncertainty language where ambiguity is evident
- Forced binary outcomes

**Risk**
- Loss of signal
- Downstream training distortion
- Overstated model competence or failure

**Mitigation**
- Encourage explicit acknowledgment of ambiguity
- Allow partial or qualified rationales
- Reinforce ambiguity as a valid state

---

### 3. Escalation Avoidance

**Description**  
The evaluator resolves locally despite indicators that escalation is appropriate.

**Common Signals**
- Repeated local resolutions on precedent-setting issues
- Minimal documentation on high-impact cases
- Rationale optimized for speed over defensibility

**Risk**
- Silent guideline drift
- Inconsistent standards across evaluators
- Accumulation of unreviewed precedent

**Mitigation**
- Normalize escalation as system maintenance
- Clarify escalation thresholds
- Provide low-friction escalation pathways

---

### 4. Escalation Overuse

**Description**  
The evaluator escalates issues that could be resolved locally with reasonable confidence.

**Common Signals**
- Escalation driven by discomfort rather than rubric conflict
- High escalation volume on low-impact cases
- Minimal attempt at local interpretation

**Risk**
- Throughput degradation
- Reviewer overload
- Delayed feedback cycles

**Mitigation**
- Reinforce evaluator autonomy
- Provide examples of appropriate local resolution
- Calibrate escalation proportionality

---

### 5. Template Drift

**Description**  
Evaluator rationales converge into a uniform structure regardless of task difficulty or ambiguity.

**Common Signals**
- Identical phrasing across heterogeneous cases
- Flattened confidence language
- Reduced specificity over time

**Risk**
- Loss of evaluative signal
- Artificial appearance of certainty
- Reduced audit credibility

**Mitigation**
- Periodic rationale audits
- Encourage variance aligned with difficulty
- Rotate exemplar rationales

---

### 6. Confidence Flattening

**Description**  
The evaluator presents all judgments with the same apparent confidence level.

**Common Signals**
- Uniform tone across trivial and complex cases
- Absence of confidence markers
- Over-polished rationales

**Risk**
- Misleading downstream interpretation
- Masked uncertainty
- Reduced calibration effectiveness

**Mitigation**
- Allow graded confidence expression
- Normalize uncertainty markers
- Reinforce confidence as informational, not performative

---

### 7. Instruction Shadowing

**Description**  
The evaluator defers excessively to instruction phrasing, even when conflicting or outdated.

**Common Signals**
- Citing superseded guidance
- Ignoring contextual updates
- Over-prioritizing static instructions over live clarification

**Risk**
- Lagging alignment
- Fragmented standards
- Reviewer frustration

**Mitigation**
- Clear versioning of guidelines
- Explicit update signaling
- QA clarification loops

---

### 8. Outcome Anchoring

**Description**  
The evaluator’s judgment is influenced by perceived model quality rather than rubric criteria.

**Common Signals**
- Leniency toward “good-looking” outputs
- Harsher scoring of awkward but correct responses
- Rationales referencing perceived intent rather than criteria

**Risk**
- Bias introduction
- Inconsistent scoring
- Training signal contamination

**Mitigation**
- Blind evaluation where feasible
- Re-emphasis on criteria-first judgment
- Calibration against counterintuitive examples

---

## Relationship to Escalation Flow

This taxonomy supports the `resolve_vs_escalate_flow.md` by:
- providing shared language for QA feedback
- clarifying when evaluator behavior, not the rubric, is at fault
- distinguishing resolvable uncertainty from systemic ambiguity

Failure classification should inform, not replace, escalation decisions.

---

## Scope & Limits

- This taxonomy does not enumerate all possible errors.
- It is not a performance evaluation rubric.
- It does not prescribe disciplinary action.
- It is intended to evolve as new failure modes surface.

## Feedback

Suggestions for additional failure modes or refinements are welcome from practitioners working in LLM evaluation, QA, or annotation operations.

