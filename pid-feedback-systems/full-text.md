# Dummies Guide to PID
Source: https://csimn.com/CSI_pages/PID.html
Fetched: 2026-04-27

"I personally have a few hundred dollars worth of books on controllers, PID algorithms, and PID tuning. Since I am an engineer, I stand a chance of understanding some of it. But where do you go if you want to understand PID without a PhD?" This introduction credits Finn Peacock's simplified material on PID algorithms as an excellent resource for those seeking accessible explanations.

## Anatomy Of A Feedback Control System

A classic PID control loop includes:

- **Setpoint (SP)**: The desired target value
- **Process Variable (PV)**: The actual measured value
- **Error**: The difference between SP and PV
- **Controller Output**: The corrective action sent to an actuator

The system continuously compares actual conditions against desired targets and adjusts to minimize the error until the process reaches the setpoint.

## Understanding the Controller

The PID controller applies up to three calculations to error signals:

- **Proportional (P)**: Responds proportionally to current error
- **Integral (I)**: Sums historical errors over time
- **Derivative (D)**: Predicts future error based on rate of change

Common implementations include P-only, PI (most common), PID, and rarely PD configurations.

## Proportional Control

In proportional-only mode, the controller multiplies the error by a tuning constant called Proportional Gain (Kp) to generate output.

## The PI Controller

Combining proportional and integral action creates the prevalent PI controller. Integral action is adjusted using "minutes per repeat" (or inversely, "repeats per minute"), which measures how long integral action takes to match proportional action output.

## Derivative Action

Derivative action anticipates future process behavior by projecting current rate-of-change forward in time, potentially enabling faster response with larger P and I gains. However, derivative action amplifies noise in signals, making it problematic for noisy systems.
