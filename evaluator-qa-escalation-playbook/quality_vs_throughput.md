# Quality vs Throughput

This document defines practical guidance for balancing evaluation quality and throughput in large-scale LLM annotation and evaluation workflows.

It treats efficiency as **elastic**, not constant, and recognizes that evaluation difficulty varies meaningfully across samples.

The goal is to maintain reliable signal without introducing silent drift, evaluator burnout, or artificial consistency.

---

## Core Principle

Throughput targets are constraints, not absolutes.

Quality degradation caused by uniform pacing across heterogeneous difficulty is a systemic failure, not an individual one.

---

## Why the Tradeoff Exists

In production environments:
- samples vary widely in ambiguity and complexity
- time expectations are often averaged
- evaluators are incentivized to normalize pace

This creates pressure to:
- rush difficult cases
- over-polish easy ones
- flatten confidence and rationale structure

Unchecked, these pressures reduce signal quality while preserving superficial consistency.

---

## Elastic Throughput Model

Evaluation speed should scale with **decision complexity**, not remain fixed.

### Appropriate Slowdown Indicators
Slower handling is justified when:
- rubric interpretation requires synthesis
- ambiguity cannot be resolved immediately
- competing reasonable outcomes exist
- precedent-setting implications are present
- escalation thresholds are being assessed

### Appropriate Acceleration Indicators
Faster handling is appropriate when:
- rubric application is direct
- ambiguity is minimal
- similar cases have been resolved consistently
- downstream impact is limited

Elastic pacing preserves signal integrity across the dataset.

---

## Evaluator Guidance

Evaluators should:
- allocate time proportional to difficulty
- vary rationale length with complexity
- explicitly note uncertainty when present
- avoid compensatory rushing after difficult cases

Evaluators should **not**:
- enforce identical time per sample
- standardize rationale structure across all cases
- suppress hesitation to maintain speed metrics

---

## QA and Reviewer Guidance

QA reviewers should:
- expect variance in handling time
- correlate rationale depth with sample difficulty
- flag patterns of systematic rushing or over-polishing
- assess consistency across similar cases, not all cases

QA reviewers should **not**:
- penalize justified slowdown
- reward superficial uniformity
- infer quality solely from throughput metrics

---

## Metrics Considerations

Useful signals include:
- variance-adjusted throughput
- rationale diversity aligned with difficulty
- escalation frequency by category
- confidence distribution across samples

Raw speed alone is insufficient to assess evaluation quality.

---

## Common Failure Modes

### Over-Normalization
Evaluators force uniform pace and structure to satisfy perceived expectations.

**Risk:** silent quality collapse masked by consistency.

---

### Compensatory Acceleration
Evaluators rush after difficult cases to “make up time.”

**Risk:** cascading errors and reduced attention.

---

### Performative Diligence
Evaluators over-document trivial cases to appear thorough.

**Risk:** noise inflation and reviewer fatigue.

---

## Operational Implications

Well-functioning pipelines:
- tolerate local variance
- monitor systemic patterns, not individual anomalies
- align incentives with signal preservation
- treat throughput as a tuning parameter, not a mandate

Quality and throughput are not opposites; they are coupled variables.

---

## Relationship to Other Documents

This guidance supports:
- `resolve_vs_escalate_flow.md`
- `failure_taxonomy.md`
- `reviewer_notes_template.md`

It informs when slowdown is appropriate and when escalation is justified.

---

## Scope & Limits

- This document does not set numeric targets.
- It does not replace project-level KPIs.
- It provides behavioral guidance, not enforcement rules.
