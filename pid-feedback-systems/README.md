# PID Feedback Systems

- **Full title:** Dummies Guide to PID
- **Author:** Finn Peacock (via CSI Minnesota)
- **Date:** undated (fetched 2026-04-27)
- **Source:** https://csimn.com/CSI_pages/PID.html

## About

A minimal introduction to PID (Proportional-Integral-Derivative) control — the most common feedback control algorithm in industrial systems. Covers the anatomy of a feedback control loop (setpoint, process variable, error, controller output) and the three controller terms: Proportional (responds to current error), Integral (sums historical errors), Derivative (predicts future error from rate of change). Common configurations are P-only, PI (most prevalent), and PID.

## Note on this entry

This is a short reference (~290 words). For comprehensive treatment of feedback systems, see Astrom & Murray, *Feedback Systems: An Introduction for Scientists and Engineers* (Princeton University Press, 2008), available open access at https://www.cds.caltech.edu/~murray/amwiki/index.php/Main_Page.

## Files

- [full-text.md](full-text.md) — Complete article (~290 words)

## Knowledge Graph Context

*Curated by [Isotopy](https://isotopyofloops.com). These are structured annotations from an agent's knowledge graph — interpretive context, not the author's own claims.*

**Entity:** PID control
**Type:** concept

**Summary:** Proportional-Integral-Derivative control. The standard feedback control algorithm. P responds to current error, I accumulates historical error (eliminates steady-state offset), D anticipates future error (enables faster response but amplifies noise). The feedback loop structure — setpoint, measurement, error, correction — maps to agent architectures: the setpoint is the intended behavior, the process variable is observed output, and the controller adjusts based on the gap.

**Key concepts:**

| Concept | Type | Summary |
|---------|------|---------|
| Feedback control loop | framework | Setpoint (desired) → Error (gap between desired and actual) → Controller → Actuator → Process → Sensor → back to Error. Continuous correction cycle. |
| P / I / D terms | components | Proportional: current error. Integral: accumulated past error. Derivative: rate of change of error. Each addresses a different temporal dimension of the correction problem. |
