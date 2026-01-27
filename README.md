# AI Evaluation Portfolio

A collection of documentation artifacts demonstrating **evaluation design, judgment under ambiguity, and escalation control** in complex review and decision-making systems.

This work focuses on a problem that increasingly defines modern AI systems:

> **Failures now arise less from incorrect answers than from answers being allowed to matter when they shouldn’t.**

Rather than optimizing outputs, the materials here examine how ambiguity is collapsed, authority is assumed, escalation becomes decoupled, and confidence substitutes for structure — and how evaluators decide when to allow, pause, reroute, or escalate responses.

While this repository is grounded in AI evaluation contexts, the failure modes and control patterns documented here apply broadly to complex review, escalation, and decision-making systems.

---

## Overview

This repository contains a focused set of documentation artifacts demonstrating **human judgment, quality control, and decision-making under constraint** in production-scale LLM evaluation and QA workflows.

The emphasis is not on model training, prompt engineering, or automation, but on:

- evaluating outputs under ambiguity  
- preserving uncertainty rather than prematurely resolving it  
- maintaining evaluator consistency under pressure  
- handling reviewer disagreement and escalation fatigue  
- distinguishing productive escalation from procedural escalation  
- understanding why quality degradation is often a rational system outcome  

All examples are synthetic and contain no client or proprietary data.

---

## Architectural Overview

This repository is not a collection of independent documents.

It reflects a single evaluation architecture expressed across multiple resolution layers:

- **Axioms and framing**  
- **Economic and incentive pressures**  
- **Operational workflows**  
- **Enforcement and decision artifacts**

The canonical system-level specification is maintained in a companion repository:

**AI Eval Lab — Architecture**  
https://github.com/codyjedmunds/ai-evaluation-lab/blob/main/ARCHITECTURE.md

---

## Key Concepts Introduced

- **Escalation Decoupling** — when escalation continues procedurally after it stops restoring meaning  
- **Rational Quality Drift** — why degradation emerges as a stable equilibrium under incentives, not evaluator failure  
- **Observable System Signals (Non-Punitive)** — aggregate indicators of incentive stress that do not rely on individual monitoring  
- **Evaluator-Side Failure Taxonomy** — structural judgment failures that emerge under scale, ambiguity, and pressure  

---

## Contents

### 1. `llm-ambiguity-eval/`

A qualitative evaluation framework for identifying and scoring failure modes when instructions are incomplete, conflicting, shifting, or time-pressured.

Includes:

- a structured evaluation rubric  
- calibration guidance  
- negative examples illustrating common evaluator errors  
- side-by-side comparisons showing subtle judgment differences  

This section demonstrates how ambiguity can be surfaced, preserved, and scored rather than collapsed into narrative clarity.

**Primary focus:** epistemic judgment and evaluator calibration.

---

### 2. `noumenal-triangulator/`

A documentation-first, post-hoc evaluation pipeline demonstrating how fluent but quietly misleading outputs can be audited after generation, without rewriting, correcting, or debating the content.

The **Noumenal Triangulator** separates evaluation into three roles:

- **Registrar** — neutral extraction of claims, assumptions, constraints, and unresolved ambiguity  
- **Auditor** — detection of structural failure modes and assignment of severity  
- **Escalation Controller** — policy-driven containment and routing decisions  

Rather than asking *“Is this answer correct?”*, the system asks:

> **Is this output allowed to matter yet?**

The included worked example demonstrates a common *quiet wrongness* pattern — a fluent response that prematurely resolves ambiguity by assuming a benign regime (low stakes, reversible error).

The system converts this into a traceable **CLARIFY** decision, pausing downstream use until missing variables or assumptions are explicitly resolved.

**Primary focus:** post-hoc evaluation, containment logic, and judgment under ambiguity.

---

### 3. `evaluator-qa-escalation-playbook/`

A practical playbook for operating evaluation workflows in production environments.

Includes:

- an evaluator-side failure taxonomy  
- decision flows for resolving vs. escalating edge cases  
- explicit checks for escalation decoupling  
- guidance on quality vs. throughput trade-offs  
- example escalation scenarios  
- reviewer note templates  
- governance and audit-safety considerations  

This section focuses on what happens *after* evaluative rules exist — guideline gaps, reviewer disagreement, escalation fatigue, and the risk of escalation continuing to execute correctly after it stops restoring clarity.

**Primary focus:** QA operations, escalation control, and production reliability.

---

### 4. `evaluation-economics/`

An analysis of why quality degradation, false helpfulness, and evaluator disagreement persist even when evaluators are competent and acting in good faith.

Rather than treating failures as individual mistakes, this section examines evaluation pipelines as **incentive-constrained systems**.

Covers:

- incentive misalignment in annotation and evaluation environments  
- the asymmetric cost of false helpfulness  
- throughput pressure and its effects on judgment quality  
- why quality drift is often a stable equilibrium  
- how escalation decoupling becomes an economic deadweight loss  
- practical leverage points for improving signal without moralizing or surveillance  

**Primary focus:** incentives, costs, and systemic behavior.

---

## How the Pieces Fit Together

The components form a closed loop:

- `llm-ambiguity-eval` defines what evaluators should notice  
- `noumenal-triangulator` defines when outputs may proceed, pause, reroute, or escalate  
- `evaluator-qa-escalation-playbook` defines how judgment is maintained under pressure  
- `evaluation-economics` explains why these systems drift without structural support  

**Judgment → containment → operation → incentives**

This repository does not argue for better answers.  
It argues for better decisions about **when answers are allowed to act on the world**.

---

## Background & Intent

This work is informed by:

- 8+ years in end-user and production support roles  
- sustained exposure to ambiguous, high-context issues under time pressure  
- graduate-level training in applied AI/ML business applications  
- independent research on LLM evaluation and failure-mode analysis  

The intent is to demonstrate readiness for roles involving:

- LLM evaluation and annotation  
- reviewer or QA support  
- escalation handling and governance  
- guideline refinement  
- evaluation operations and delivery analytics  
- trust & safety or policy-adjacent evaluation  

---

## Scope & Limits

- This repository is documentation-first by design  
- No scripts, automation, or live tooling are included  
- The emphasis is on human judgment, not system optimization  
- Governance discussions are procedural, not legal advice  

---

## Feedback

Feedback from practitioners working in review, governance, reliability, or trust & safety roles, as well as LLM evaluation, QA, or annotation operations, is welcome.
