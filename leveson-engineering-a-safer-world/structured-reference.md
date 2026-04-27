# Engineering a Safer World — Structured Reference
**Author:** Nancy G. Leveson
**Published:** 2011, MIT Press
**PDF:** library/reference/methodology/leveson-engineering-a-safer-world.pdf
**Extracted:** 2026-04-27 by Isotopy from Chapters 3, 4, and 8

---

## Core Thesis

Traditional safety engineering treats accidents as chains of failure events and focuses on component reliability. This fails for modern sociotechnical systems (software-intensive, organizationally complex). Safety is an **emergent property** of the whole system, not a component property. Reliability and safety are different: "The pilots may reliably execute the landing procedures on a plane or at an airport in which those procedures are unsafe."

**Old assumption:** Safety is increased by increasing the reliability of system components.
**New assumption:** Safety is an emergent property that arises from the interactions among components, not from individual component properties.

---

## Foundations: Systems Theory (Ch 3)

### Three Categories of Systems
1. **Organized simplicity** — few components, analytic reduction works (classical mechanics)
2. **Unorganized complexity** — many components, random interactions, statistics work (thermodynamics)
3. **Organized complexity** — many components with structured interdependencies; neither reduction nor statistics sufficient. Requires systems theory. Most modern engineered and social systems fall here.

### Two Pairs of Systems Theory Concepts
- **Emergence + Hierarchy**: Properties arise from interactions that don't exist in components alone. Systems organize hierarchically — each level has emergent properties not present in lower levels.
- **Communication + Control**: Systems maintain stability and adapt through information flow and feedback-based control.

### Four Conditions Required for Control
1. **Goal** — the controller must have a goal or set of goals
2. **Action** — the controller must be able to affect the system state (actuators, authority)
3. **Model** — the controller must have a model of the system being controlled
4. **Observability** — the controller must be able to ascertain the system state (sensors, feedback)

If any condition is missing or degraded, control is inadequate and safety constraints may be violated.

---

## STAMP: Systems-Theoretic Accident Model and Processes (Ch 4)

### Three Basic Constructs
1. **Safety constraints** — not events, but constraints on system behavior that must be enforced
2. **Hierarchical safety control structure** — layers of control from legislation down to physical process
3. **Process models** — every controller (human or automated) must maintain a model of what it controls

### Safety as a Control Problem
- Safety constraints must be identified and enforced at every level
- Accidents result from **inadequate control or enforcement** of safety constraints — not just component failures
- There is no "root cause." The accident cause is an **inadequate safety control structure** that, under certain circumstances, leads to violation of behavioral safety constraints

### Safety Constraints: Passive vs Active Controls
**Passive controls** maintain safety by their presence — barriers, interlocks, fail-safe designs. Fewer failure modes.

**Active controls** require action and have four stages:
1. **Detection** of a hazardous event or condition
2. **Measurement** of relevant variables
3. **Diagnosis** (interpretation of the measurement)
4. **Response** (recovery or fail-safe procedures)

Active controls have more failure modes but offer more flexibility.

### The Hierarchical Safety Control Structure
Two parallel hierarchies with interactions between them:
- **System Development** (left): Congress → Regulatory agencies → Company management → Project management → Design → Implementation → Manufacturing
- **System Operations** (right): Congress → Regulatory agencies → Company management → Operations management → Operating process (human controllers + automated controllers + physical process)

Between any two levels, two channels:
- **Reference channel** (downward): goals, policies, constraints, control commands
- **Measuring channel** (upward): feedback about how effectively constraints are being satisfied

**Asynchronous evolution**: Different parts of the system change at different rates. Technology changes faster than procedures; procedures faster than regulations. When one part evolves without corresponding updates to others, the control structure degrades. (Example: Black Hawk shootdown — F-15s had jam-resistant radios incompatible with Army helicopter radios.)

### Process Models
Every controller must contain a model of the process it controls (Figure 4.6). The model must contain:
- Required relationships among system variables (control laws)
- Current state of system variables
- Ways the process can change state

**Accidents occur when the process model diverges from reality.** The controller issues commands based on what it thinks is happening, not what is actually happening.

Examples: Mars Polar Lander software thought the spacecraft had landed (shut down engines too early). Herald of Free Enterprise captain thought ferry doors were closed. Cali Colombia B-757 pilots misidentified a navigation waypoint.

### Four Types of Inadequate Control Actions
1. A control action required for safety is **not provided**
2. An **unsafe control action** is provided
3. A potentially safe control action is provided at the **wrong time** (too early, too late, wrong sequence)
4. A control action is **stopped too soon** or **applied too long**

### Classification of Control Flaws (Figure 4.8)
Four numbered sources of inadequate control:

| # | Source | Failure modes |
|---|--------|---------------|
| 1 | **Unsafe inputs** | Control input or external information wrong or missing from higher-level controller |
| 2 | **Unsafe control algorithm** | Flaws in original design; process changes making algorithm unsafe; incorrect modification or adaptation |
| 3 | **Incorrect process model** | Inconsistent, incomplete, or incorrect model of the controlled process |
| 4 | **Inadequate actuator/sensor/process** | Actuator failure, sensor failure, component failure, process input missing, external disturbance |

Plus cross-cutting factors:
- Inadequate or missing feedback / feedback delays
- Conflicting control actions from multiple controllers
- Unidentified or out-of-range disturbances

### Coordination Failures: Overlap and Boundary Areas
- **Boundary areas**: separately controlled processes with shared boundaries — responsibility often poorly defined (blast furnace/transport department example)
- **Overlap areas**: two controllers influencing the same object — potential for conflicting actions (67% of steel industry incidents occurred in overlap areas)

### Operator Mental Models
- Designer's model is an idealization formed before the system exists
- Operator's model is based on training plus experience with the actual system
- Both may differ from the actual system — and from each other
- Operators must experiment to update mental models; errors are a necessary part of this feedback
- Taking operators "out of the loop" via automation degrades their models, making them more error-prone when automation fails

---

## STPA: System-Theoretic Process Analysis (Ch 8)

### What It Is
A hazard analysis technique based on STAMP. "Investigating an accident before it occurs." Identifies scenarios that can lead to losses so they can be eliminated or controlled in design or operations.

### Why Traditional Techniques Fail
- **Fault Tree Analysis / Event Tree Analysis**: Limited to failure events in electromechanical components. No guidance to analyst. Don't handle software, human decision-making, or organizational factors.
- **HAZOP**: Better guidance (uses guidewords on physical parameters), but based on physical component diagrams — doesn't cover control flaws.
- **FMEA**: Bottom-up reliability technique, very limited for safety analysis.

### Three Goals of STPA
1. Include causal factors beyond component failures: software flaws, component interaction accidents, human decision-making errors, organizational and management factors
2. Provide guidance for completeness (guidewords based on control flaws, not physical parameters)
3. Usable before a design exists — can guide design from earliest conceptual phases (safety-guided design)

### The STPA Process: Two Steps

**Step 1: Identify potentially hazardous control actions**

For each control action in the control structure, systematically check all four types:
- (a) Required control action is **not provided** or not followed
- (b) An **unsafe control action is provided**
- (c) A potentially safe control action is provided **too early, too late, or in wrong sequence**
- (d) A control action required for safety is **stopped too soon or applied too long**

**Step 2: Determine how each unsafe control action could occur**

For each unsafe control action identified in Step 1:
- (a) Examine each part of the control loop (inputs, algorithm, process model, actuators, sensors, feedback channels) to identify what could cause it. Design controls and mitigations. For multiple controllers of the same constraint, identify conflicts and coordination problems.
- (b) Consider how the designed controls could degrade over time:
  - i. Management of change procedures (planned changes)
  - ii. Performance audits (detecting unplanned changes that violate safety constraints)
  - iii. Accident and incident analysis (tracing anomalies to hazards and system design)

---

## Key Principles Summary

1. **Safety ≠ reliability.** A perfectly reliable component executing an unsafe design produces reliable unsafety.
2. **Accidents are control problems**, not failure-chain problems.
3. **Emergent properties** cannot be analyzed by decomposition — they arise from interactions.
4. **Every controller needs a model.** When the model diverges from reality, unsafe commands follow.
5. **No root cause.** Accidents result from an inadequate safety control structure, not a single point of failure.
6. **Asynchronous evolution degrades control.** Systems change at different rates; uncoordinated change creates gaps.
7. **Operators need feedback to maintain accurate mental models.** Removing them from the loop degrades their ability to intervene when automation fails.
8. **Safety-guided design** — integrate hazard analysis from the earliest conceptual phases, not after the design is complete.
9. **Behavior is a product of the environment** — to reduce operator error, change the environment, not the operator.
10. **Control structures must be maintained** — safety is not a one-time achievement but continuous enforcement of constraints as the system evolves.
