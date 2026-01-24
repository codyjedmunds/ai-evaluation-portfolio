# Noumenal Triangulator

A three-stage evaluation pipeline for auditing LLM outputs under ambiguity,
failure risk, and coordination pressure.

Given a prompt and a model response, the system produces a structured audit
and a containment decision indicating whether the output can be used as-is,
requires annotation, needs clarification, or should be halted and escalated.

---

## What problem this solves

Large language models often produce fluent responses that appear complete while
quietly resolving the wrong question, omitting key variables, or compressing
uncertainty into narrative confidence.

These failures are difficult to detect because they do not present as factual
errors. They present as clarity.

In production evaluation, annotation, and RLHF workflows, such failures can
silently degrade data quality and downstream decision-making.

The Noumenal Triangulator is designed to evaluate model outputs after generation.
It does not attempt to fix or rewrite responses. Instead, it determines whether
an output is fit to proceed, and under what conditions.

---

## How it works (high level)

Evaluation is separated into three distinct stages to prevent premature
resolution and role collapse:

1. **Registrar**  
   Records claims, assumptions, constraints, and unresolved ambiguities without
   interpretation or correction.

2. **Auditor**  
   Identifies failure modes, incentive distortions, and narrative compression,
   assigning severity and citing evidence from the output.

3. **Escalation Controller**  
   Applies explicit decision thresholds to determine the appropriate containment
   action based on Registrar and Auditor findings.

Each stage produces a written artifact. The final decision is traceable to
specific evidence rather than model confidence.

## Worked example

The repository includes a complete worked example in
`examples/01_quiet_wrongness/` demonstrating a common failure pattern:

A fluent model response that prematurely resolves ambiguity by assuming a
benign regime (low stakes, reversible error) without surfacing or bounding
those assumptions.

The example shows how the Registrar, Auditor, and Escalation Controller
together convert this “quiet wrongness” into an explicit containment decision
(CLARIFY), without rewriting or correcting the model output.


---

## Containment decisions

The system produces one of four actions:

- **ALLOW**  
  The output is internally consistent and sufficiently bounded to proceed.

- **ANNOTATE**  
  The output is usable but requires warnings, caveats, or scope limitations.

- **CLARIFY**  
  Key variables or ambiguities must be resolved before proceeding.

- **HALT**  
  The output should not be used and must be escalated to a human reviewer.

These actions are policy-driven, reviewable, and reproducible.

---

## Interface

This is not an autonomous agent or a live chat system.

The primary interface is a local case file generator.

Each evaluation produces structured, machine-readable artifacts
(e.g., JSON, YAML, and Markdown) alongside a human-readable HTML report.
This design allows results to be inspected directly by reviewers or
ingested by downstream systems such as dashboards, KPIs, or evaluation
pipelines without modifying the core logic.

The system itself does not take action. It emits decisions and evidence
that can be consumed by other tooling.

---

## Example usage

```bash
pip install -e .
python -m nt run \
  --input examples/01_quiet_wrongness/input.md \
  --output examples/01_quiet_wrongness/model_output.txt \
  --save runs/
