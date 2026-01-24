# Evaluator QA & Escalation Playbook

This playbook provides practical, production-ready guidance for maintaining evaluation quality and operational safety in large-scale LLM annotation and evaluation workflows.

It applies in environments where:
- evaluation rubrics exist but encounter edge cases
- reviewers disagree in good faith
- throughput pressure competes with judgment quality
- escalation decisions affect downstream trust and consistency

The focus is on **human evaluator behavior and process integrity**, not model performance, tooling, or automation.

All examples are synthetic and contain no client or proprietary data.

---

## Purpose

This playbook addresses a common gap that appears after an evaluation framework is defined:

> *How should evaluators, reviewers, and QA handle ambiguity, disagreement, and precedent risk once the rubric is stressed in production?*

Its goals are to:
- prevent silent quality drift
- ensure escalation is proportional and meaningful
- preserve evaluator autonomy without fragmenting standards
- support audit-safe, defensible decision-making at scale

---

## Intended Audience

This playbook is intended for:
- evaluators and annotators working with written rationales
- QA reviewers and senior evaluators
- operations or delivery leads supporting evaluation pipelines
- guideline owners responsible for rubric refinement

It assumes familiarity with rubric-based evaluation but does not require technical or modeling expertise.

---

## Contents

### `resolve_vs_escalate_flow.md`
Defines the core decision flow for determining whether an issue should be:
- resolved locally
- flagged for QA review
- escalated for guideline clarification

This document anchors the playbook and governs routing behavior under ambiguity.

---

### `failure_taxonomy.md`
Defines common **evaluator-side failure modes**, including:
- rubric literalism
- premature ambiguity collapse
- escalation avoidance or overuse
- template drift
- escalation decoupling

The taxonomy supports QA feedback and calibration without personalizing error.

---

### `reviewer_notes_template.md`
Provides a lightweight, standardized template for documenting non-trivial decisions, including:
- issue classification
- resolution or escalation rationale
- confidence level
- downstream impact

Designed to support traceability without over-documentation.

---

### `quality_vs_throughput.md`
Guidance on managing the tradeoff between speed and accuracy, including:
- when slowdown is appropriate
- how to avoid artificial consistency
- how to interpret throughput metrics without collapsing signal

Treats efficiency as elastic rather than constant.

---

### `governance_and_audit_safety.md`
Outlines procedural practices that support:
- auditability through traceable decisions
- escalation logging without surveillance
- certifiability of human judgment
- guideline improvement through feedback loops

This section is procedural rather than legal and is tool-agnostic.

---

### `case_studies.md`
A small set of synthetic scenarios demonstrating:
- partial correctness
- preserved ambiguity
- precedent-setting escalation
- peer alignment avoiding unnecessary escalation

Each case illustrates correct application of the playbook under real constraints.

---

## Relationship to `llm-ambiguity-eval`

This playbook complements the evaluation framework in `llm-ambiguity-eval/`.

- **`llm-ambiguity-eval`** defines how ambiguous outputs are judged.
- **This playbook** defines how that judgment is maintained, routed, and audited in production environments.

The two are designed to work together without duplication.

---

## Scope & Limits

- This playbook is documentation-only.
- It does not prescribe automation, tooling, or enforcement mechanisms.
- It does not define legal, contractual, or compliance policy.
- It focuses on evaluator judgment, QA practice, and operational process.

## Feedback

Feedback from practitioners working in LLM evaluation, QA, escalation, or annotation operations is welcome.


