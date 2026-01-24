# Evaluation Economics

This folder examines **why quality degradation, false helpfulness, and evaluator disagreement persist in large-scale LLM evaluation systems—even when everyone is acting competently and in good faith**.

Rather than treating these failures as individual mistakes or moral lapses, this work analyzes evaluation pipelines as **incentive-constrained systems**. It shows how rational behavior under throughput pressure, vague objectives, and proxy metrics produces predictable forms of drift.

The goal is not critique for its own sake, but **diagnosis**: understanding the economic forces that shape evaluator behavior so that interventions can be designed where they actually matter.

---

## Core Premise

Most evaluation failures are not caused by:
- careless annotators
- bad faith reviewers
- lack of training
- insufficient guidelines

They are caused by **misaligned incentives interacting with ambiguity**.

When speed, agreement, and surface-level helpfulness are rewarded—explicitly or implicitly—evaluators adapt. Over time, systems converge toward outputs that are:
- fast to justify
- easy to agree on
- superficially coherent
- structurally incorrect under ambiguity

This convergence is **rational**, stable, and hard to reverse without changing the incentive landscape.

---

## What This Folder Covers

### Incentive Misalignment
How common evaluation metrics (agreement rates, throughput targets, escalation volume) unintentionally reward premature resolution, template conformity, and false confidence.

This includes:
- Goodhart-style pressure in annotation environments
- Proxy collapse (helpfulness ≠ correctness under ambiguity)
- Why “follow the rubric” is not a sufficient safeguard

---

### The Cost of False Helpfulness
Why false positives in evaluation (rewarding outputs that feel helpful but are wrong) are often more damaging than false negatives—especially in preference modeling and RLHF contexts.

Explores:
- Asymmetric downstream costs
- How reassurance and urgency mimic quality signals
- Why evaluators systematically under-penalize confident errors

---

### Throughput Pressure Models
How time pressure reshapes judgment.

Rather than treating speed as a simple scalar, this work examines:
- Which kinds of judgments degrade first under load
- Why ambiguity resolution is disproportionately sacrificed
- How evaluators learn to optimize for “passable” over “defensible”

---

### Why Quality Drift Is Rational
A central claim of this folder:

> Under most production constraints, quality drift is not a bug—it is an equilibrium.

This section explains how evaluator behavior settles into stable patterns that minimize friction and maximize apparent performance, even as true signal quality erodes.

No villain required. No incompetence assumed.

---

### Evaluator Labor Signals
Identifying observable signals *CMs and QA leads can observe **without surveillance** to diagnose incentive stress, including:
- sudden drops in escalation
- compressed rationale variance
- anomalously fast resolution of ambiguous cases
- reviewer overconfidence clustering

These are treated as **system signals**, not individual faults.

---

### Intervention Leverage Points
Practical, non-moralizing interventions that can shift outcomes, such as:
- uncertainty-aware scoring
- escalation cost rebalancing
- selective slowdown incentives
- negative-example calibration as counter-pressure
- decoupling agreement from correctness in specific regimes

The emphasis is on *small structural changes* with outsized effects.

---

## Relationship to the Rest of the Portfolio

This folder complements—but does not duplicate—the other components:

- **`llm-ambiguity-eval/`** documents *what* evaluators should notice and how ambiguity should be scored.
- **`evaluator-qa-escalation-playbook/`** documents *how* judgment is maintained operationally under pressure.
- **`evaluation-economics/`** explains *why* those systems tend to fail without structural support.

Together, they form a closed loop:
judgment → operation → incentives.

---

## Scope & Limits

- This is a qualitative, documentation-first analysis.
- No formal economic modeling or quantitative optimization is attempted.
- No ideological or policy claims are made.
- All examples are synthetic and generalized.

The focus is explanatory power and operational usefulness, not theory completeness.

---

## Intent

This work is intended for:
- Evaluation and Quality Analysts
- QA and escalation leads
- Evaluation Ops and Delivery teams
- Early-stage AI teams diagnosing signal degradation
- Anyone responsible for maintaining judgment quality at scale

It assumes familiarity with evaluation workflows but does not require economics or modeling backgrounds.

---

## Closing Note

Complex systems do not fail loudly.  
They fail *smoothly*, by rewarding the behaviors that make them feel like they are working.

This folder exists to make those dynamics legible—so that judgment can remain sharp without asking humans to be heroes.

