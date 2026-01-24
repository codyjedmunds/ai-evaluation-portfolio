# Why Quality Drift Is Rational

This document explains why **quality degradation in LLM evaluation systems is not a failure of discipline, training, or oversight**, but a predictable and stable outcome of rational behavior under production constraints.

Quality drift does not occur because evaluators stop caring.  
It occurs because evaluators adapt correctly to the incentives and signals the system provides.

---

## Drift as an Equilibrium, Not a Breakdown

In many evaluation environments, quality decline is framed as:
- fatigue
- complacency
- lack of rigor
- insufficient training
- poor hiring

These explanations assume that evaluators are deviating from expected behavior.

In practice, drift emerges when evaluators **successfully optimize** for:
- throughput
- agreement
- low friction
- minimal escalation
- defensible justifications

When these pressures remain stable, the system settles into a **local equilibrium** where further quality degradation slows or plateaus—but quality recovery is also unlikely without intervention.

This equilibrium can be internally coherent while being externally misaligned.

---

## The Rational Evaluator’s Optimization Problem

Evaluators are typically constrained by:
- limited time per task
- incomplete or conflicting rubrics
- downstream review uncertainty
- implicit performance comparisons
- escalation costs (time, social, or reputational)

Given these constraints, the rational strategy is to:
- resolve cases locally when possible
- select interpretations that are easy to justify
- avoid signaling uncertainty unless explicitly required
- converge toward patterns that reviewers accept quickly

None of these behaviors violate guidelines.  
They are *adaptive responses* to the environment.

---

## Why Ambiguity Handling Degrades First

Ambiguity is expensive.

Handling ambiguity well requires:
- slowing down
- holding multiple interpretations
- articulating uncertainty
- risking disagreement
- potentially triggering escalation

When time or agreement pressure increases, evaluators rationally conserve effort by:
- collapsing ambiguity early
- choosing the most “reasonable” interpretation
- treating uncertainty as noise rather than signal

As a result, ambiguity preservation is often the **first casualty** of throughput pressure—even when evaluators remain accurate on simpler cases.

---

## Confidence as a Survival Strategy

In many systems, confidence functions as a protective signal.

Confident rationales:
- appear decisive
- reduce reviewer scrutiny
- minimize follow-up questions
- increase agreement likelihood

Hesitant or nuanced rationales:
- invite reinterpretation
- increase review time
- raise escalation probability

Over time, evaluators learn—implicitly—that confidence is safer than precision under review, even when the underlying case is uncertain.

This produces a gradual shift from defensible judgment to **defensible performance**.

---

## Why Drift Persists After Calibration

Calibration sessions often identify drift after it has already stabilized.

At that point:
- evaluator habits are entrenched
- reviewers have adapted to new baselines
- throughput expectations have adjusted

Correcting drift now requires evaluators to:
- slow down
- surface uncertainty
- accept increased friction

Unless incentives change, this correction is *locally irrational* for individuals—even if it benefits the system globally.

Thus, drift persists.

---

## Escalation Decoupling: When Oversight Stops Working

At a certain point, quality drift survives not because escalation fails to exist—but because **escalation no longer tracks meaning**.

Escalation Decoupling occurs when:
- escalation procedures continue to execute
- review volume remains normal or increases
- approvals are still granted
- but the semantic frame those procedures rely on has already decayed

The system appears healthy:
- metrics pass
- tickets move
- senior reviewers sign off

Yet escalation now operates on **stale premises**.  
It enforces consistency within an outdated frame rather than restoring alignment.

At this stage:
- additional escalation does not recover quality
- disagreement is resolved procedurally rather than semantically
- oversight becomes performative rather than corrective

The system is no longer drifting quietly — it has stabilized *after* drift.

---

## The Economic Cost of Decoupled Escalation

Once escalation decoupling occurs, the economics change sharply.

- Marginal escalation cost increases (time, staffing, coordination)
- Marginal semantic benefit approaches zero
- Resources are consumed without restoring evaluative signal

From an economic perspective, continued escalation under frame decay becomes a **deadweight loss**:
- expensive
- stabilizing
- and misleadingly reassuring

This is why simply “adding more reviewers” or “tightening escalation” often worsens throughput without improving quality.

---

## Drift Without Bad Actors

Crucially, quality drift and escalation decoupling do not require:
- negligence
- dishonesty
- laziness
- adversarial intent

They emerge from:
- reasonable people
- making reasonable choices
- under reasonable constraints

This is why punitive or moral responses to drift rarely succeed.

---

## Implications

If quality drift and escalation decoupling are rational, then:
- exhortation is ineffective
- training alone is insufficient
- surveillance creates new distortions
- blaming evaluators misses the point
- escalation volume is not a proxy for alignment

Stability requires changing the **structure of the optimization problem**, not the character of the people solving it.

---

## Summary

Quality drift in LLM evaluation systems is:

- predictable
- incentive-driven
- behaviorally rational
- resistant to surface-level fixes

When drift progresses far enough, escalation itself can decouple from meaning—producing oversight without correction.

Understanding drift as an equilibrium—not a failure—creates the possibility of designing systems where *good judgment is once again the easiest option*.

The next sections examine which failure modes are most damaging, and where small structural changes can still produce outsized improvements.
