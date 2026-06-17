---
layout: page
title: Deductive Verification vs. Model Checking for Physical Safety of a Feedback-Controlled Drone
importance: 1
# --- review these fields ---
status: ongoing          # e.g. ongoing / submitted / published
role:                    # e.g. Research Assistant
year: 2026
# ---------------------------
links:
  - label: code
    url: https://github.com/eyang07/droneV
  - label: talk
    url: /presentations/deductive-proof-vs-model-checking/
permalink: /research/deductive-verification-drone/
---

A comparative study of three formal verification paradigms applied to a shared CPS model: the physical safety of a feedback-controlled drone. 

The drone is modeled as a point mass in ℝ³ under gravity, governed by a deterministic guard-band controller that applies inward corrective thrust near the edges of a safe region and a hover thrust otherwise. We use an exact discrete update map obtained by sampling the continuous Lagrangian dynamics under a zero-order-hold assumption.

We specify the safety and liveness properties:
— staying inside the geofence (P1)
- bounding speed (P2)
- recovering from the guard band (P3)

Then we verify the system in three ways: explicit-state model checking in TLA+/TLC, symbolic (BDD-based) model checking in nuSMV, and deductive theorem proving in Lean 4. We then increase the tier of complexity by introducing new physical dynamics such as wind, and more involved controller logic to see how each verification paradigm scales.
