# LLM Ambiguity Evaluation Framework

Authored by Cody Edmunds (2026)

## Problem Statement
Modern large language models (LLMs) frequently collapse ambiguous situations into premature advice, amplify urgency without new information, and reward false signals of progress. These behaviors can lead to poor guidance, misaligned assistance, and evaluator blind spots during annotation and preference modeling.

This repository defines and evaluates **constrained LLM behaviors under ambiguity**, focusing on detecting and suppressing common failure modes through qualitative evaluation rather than model training.

---

## What This Project Demonstrates

- Qualitative **evaluation design** for LLM behavior under uncertainty
- Clear **failure-mode definition** (what *not* to reward)
- Practical **annotation guidelines** and evaluator calibration
- **Multi-turn consistency** testing under conversational pressure
- Side-by-side **baseline vs constrained** behavior comparisons

This is an evaluation artifact—not a chatbot, product, or theory explainer.

---

## Evaluation Axes

The framework scores observable model behavior across the following axes:

1. **Premature Resolution Suppression** — Avoids collapsing ambiguity into conclusions or advice
2. **False Urgency Regulation** — Reduces or neutralizes unwarranted time pressure
3. **Instruction Reflex Inhibition** — Resists giving steps when framing is invalid
4. **Multi-Turn Constraint Consistency** — Maintains constraints across follow-ups
5. **Cognitive Load Reduction (Subtractive)** — Removes false obligations rather than adding options
6. **Affective Reward Exploitation (Structural)** — Avoids using emotional reassurance as a progress signal

Each axis is scored on a 0–2 scale using explicit criteria defined in `rubric.md`.

---

## Method

1. **Evaluation Prompts**
   - A small, focused set of prompts designed to induce ambiguity, urgency, or decision pressure

2. **Baseline vs Constrained Outputs**
   - Prompts are run against an unconstrained baseline and a rule-constrained system

3. **Human Scoring**
   - Outputs are scored using a shared rubric and annotation guidelines

4. **Calibration**
   - Evaluator disagreement is addressed using explicit calibration notes and tie-breaker rules

Explicit negative examples illustrating common evaluator traps are included in `negative_examples/`.

---

## Repository Structure

```
llm-ambiguity-eval/
│
├── README.md
├── rubric.md
├── guidelines.md
├── calibration.md
├── eval_prompts.md  
│
├── comparisons/
│   ├── prompt_05.md
│   ├── prompt_13.md
│   └── prompt_18.md
│
├── negative_examples/
│   ├── README.md
│   ├── neg_01_instruction_reflex.md
│   ├── neg_02_urgency_affect.md
│   └── neg_03_constraint_drift.md
│
└── LICENSE
```

---

## Results (Summary)

- Baseline models frequently fail on **premature resolution** and **instruction reflex** axes
- Urgency amplification and affective reassurance are common false-positive signals
- Constrained systems demonstrate improved stability and ambiguity preservation
- Multi-turn pressure is a primary source of constraint drift

These findings are demonstrated concretely in the `comparisons/` folder.

---

## Why This Matters

- **Data Annotation Quality:** Prevents rewarding outputs that feel helpful but are structurally incorrect
- **RLHF & Preference Modeling:** Improves signal quality by clarifying what constitutes failure
- **Model Evaluation:** Enables consistent assessment of behavior under uncertainty

The theoretical motivation draws from systems and semiotic models of meaning under load; however, the evaluation framework operates purely on **observable output behavior**.

---

## Status

This repository is intended as a compact evaluation portfolio demonstrating judgment, failure-mode awareness, and annotation leadership. It does not include model training, fine-tuning, or deployment.

---

## License

MIT License. See `LICENSE` for details.

