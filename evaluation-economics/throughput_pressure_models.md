# Throughput Pressure Models

This document examines how **time and volume pressure reshape evaluator judgment**, not uniformly, but in patterned and predictable ways.

Rather than treating throughput as a simple speed–accuracy tradeoff, this analysis models how different **faculties of judgment fail at different thresholds**, producing phase-shifted degradation rather than gradual decline.

---

## Throughput Is Not a Scalar

In production environments, throughput pressure is often conceptualized as:
- more tasks per hour
- less time per item
- increased productivity expectations

However, judgment does not degrade evenly as time decreases.

Certain evaluative functions collapse early, while others remain intact far longer. This creates the illusion of stability even as critical signal quality erodes.

---

## What Breaks First

Under increasing throughput pressure, the following capacities tend to degrade in order:

### 1. Ambiguity Preservation
The ability to:
- hold multiple interpretations
- articulate uncertainty
- resist premature resolution

This faculty is cognitively expensive and offers little immediate reward under speed constraints. As pressure rises, ambiguity is resolved earlier and more aggressively.

---

### 2. Constraint Consistency
Maintaining nuanced constraints across multi-turn interactions requires memory, attention, and time.

Under load:
- constraints are simplified
- edge cases are normalized
- follow-up turns receive less scrutiny

Evaluators remain “accurate” on single-turn checks while losing cross-turn coherence.

---

### 3. Rationale Specificity
As time compresses, rationales drift toward:
- templated language
- generic justification
- surface references to guidelines

The evaluator’s decision may still be reasonable, but the **explanatory signal collapses**, making downstream review and calibration harder.

---

### 4. Escalation Sensitivity
Escalation decisions become biased toward:
- local resolution
- deferral rather than flagging
- avoidance of friction

This suppresses visibility into guideline gaps precisely when systems are under the most stress.

---

## What Persists Under Pressure

Not all faculties degrade quickly.

The following often remain stable even under high throughput:

- basic factual correctness checks
- obvious policy violations
- clearly disallowed content
- binary classification tasks

This persistence creates a false sense of robustness: metrics look acceptable while deeper judgment quality deteriorates.

---

## Phase Shifts, Not Slopes

Throughput pressure produces **phase shifts**, not smooth tradeoffs.

Quality may appear stable across a wide range of speeds, then suddenly collapse when a threshold is crossed. These thresholds vary by:
- task type
- evaluator experience
- rubric clarity
- review environment

Once crossed, recovery is slow and often requires explicit intervention.

---

## Compression Effects

When time per task shrinks, evaluators compress decision-making by:
- relying on first-pass impressions
- privileging confident outputs
- reducing internal debate
- favoring familiar patterns

Compression is efficient, but it systematically favors outputs that are:
- confident
- simple
- easily defensible

This interacts directly with false helpfulness incentives described elsewhere.

---

## Why Speed Targets Backfire

Hard speed targets encourage evaluators to:
- optimize for task completion rather than signal preservation
- treat uncertainty as noise
- minimize variance in decisions

Even when targets are met, the **distribution of errors changes**, skewing toward confident but shallow judgments.

This makes throughput-driven degradation difficult to detect using aggregate metrics.

---

## Implications

Understanding throughput pressure as phase-shifted degradation implies that:
- marginal speed increases may have non-marginal quality costs
- slowing down selectively can be more effective than global pacing changes
- different task classes require different throughput expectations

Treating throughput as a uniform constraint obscures where judgment is actually failing.

---

## Summary

Throughput pressure reshapes evaluator behavior by:
- collapsing ambiguity handling early
- preserving surface correctness
- compressing rationale quality
- suppressing escalation signals

These effects are predictable, repeatable, and structural.

Designing resilient evaluation systems requires recognizing **which forms of judgment are fragile under speed—and protecting them deliberately**, rather than assuming accuracy degrades evenly.
