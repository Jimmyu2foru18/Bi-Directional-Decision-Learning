# Neutral Centered Bidirectional Decision Learning (NCBDL)

> A machine learning framework where every decision begins from a neutral state (`0`) and evolves through 
the accumulation of positive and negative evidence.

---

## Overview

- Neutral Centered Bidirectional Decision Learning (NCBDL) is a research project looking at an alternative way of design for machine learning decision making.
- Instead of forcing probabilities or using binary classifications, the idea is that the system starts from **true neutrality** and accumulates evidence in both directions until enough confidence exists to make a decision.

```
Negative <──────────── 0 ────────────> Positive
```

The **magnitude** of the value represents confidence, while the **sign** represents direction.

---

# The Idea

**Traditional Machine Learning:**

> "Which class is most likely?"

**NCBDL Idea:**

> "How much evidence supports and opposes this?"

This creates a more interpretable decision process where every response/decision has a stronger sense of reasoning for it being measurable.

- Every decision begins at **0**
- Evidence is additive
- Positive evidence increases confidence
- Negative evidence decreases confidence
- A confidence interval and a margin of error is accounted for and compaired
- Possible CoT
- Confidence is proportional to distance from zero
- Decisions occur only after thresholds are crossed

---

# Math Side

Initial state
```
S₀ = 0
```
Equation = Least Squares Method + Calc. Summations + Dot Product 
```
Sₜ₊₁ = Sₜ + Σ(wᵢ · eᵢ)
```

Where

| Symbol | Meaning |
|---------|---------|
| S | Current decision score |
| w | Weight of evidence |
| e | Evidence value |
| t | Time or iteration |

Decision

```
- S > + T  → Positive

- S < -T  → Negative

- -T ≤ S ≤ T → Neutral
```

---

# Architecture

```
             Input
               │
               ▼
      Feature Extraction
               │
               ▼
      Evidence Generation
               │
               ▼
      Evidence Weighting
               │
               ▼
      Score Accumulator
               │
               ▼
        Threshold Engine
               │
        ┌──────┴──────┐
        ▼             ▼
    Decision      Stay Neutral
               │
               ▼
        Learning Feedback
               │
               ▼
        Weight Adjustment
```


# Project Ideas to build on 

- LLM reasoning
- Medical diagnosis
- Autonomous vehicles
- Fraud detection
- Robotics
- Recommendation systems
- Cybersecurity
- Risk analysis

---

# Process of Decision 

01. Receive input
02. Extract features
03. Evaluate evidence
04. Assign evidence weights
05. Update score
06. Compare with thresholds
07. Produce decision
08. Receive feedback
09. Update weights
10. Repeat

---
