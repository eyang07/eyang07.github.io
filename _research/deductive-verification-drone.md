---
layout: page
title: Deductive Verification vs. Model Checking for Physical Safety of a Feedback-Controlled Drone
importance: 1
# --- review these fields ---
status: ongoing          # e.g. ongoing / submitted / published
role:                    # e.g. Research Assistant
year: 2026
# ---------------------------
description: Comparing deductive verification and model checking for guaranteeing the physical safety of a feedback-controlled drone.
links:
  - label: code
    url: https://github.com/eyang07/droneV
  - label: talk
    url: /presentations/deductive-proof-vs-model-checking/
permalink: /research/deductive-verification-drone/
---

This project is a comparative study of three formal-verification paradigms applied to one shared model: the physical safety of a feedback-controlled drone. The drone is modeled as a point mass in ℝ³ under gravity, governed by a deterministic guard-band controller that applies inward corrective thrust near the edges of a safe region and a hover thrust otherwise. Sampling the continuous Lagrangian dynamics under a zero-order-hold assumption gives an exact discrete update map, and so a closed-loop system whose safety and liveness properties — staying inside the geofence (P1), bounding speed (P2), recovering from the guard band (P3), and, in later tiers, avoiding an obstacle (P4) — are specified in linear temporal logic. The same system is then verified three ways: explicit-state model checking in TLA+/TLC, symbolic (BDD-based) model checking in nuSMV, and deductive theorem proving in Lean 4. A tiered design — a baseline box, then obstacles, then adversarial wind — lets me watch how each method scales as the model grows more complex.

The contribution is the side-by-side comparison itself, which exposes a genuine tradeoff between automation and strength of guarantee. The two model checkers operate on a finite fixed-point abstraction (a scaled-integer lattice with Δt = 1/4) and agree exactly on the reachable-state count (3,709,475 states at Tier 1; 2,949,788 at Tier 2), a cross-check that both encode the same discrete system; they verify every property automatically, but only over that finite instance. Lean, by contrast, proves safety and the velocity bound over the real-valued, parametric model for every valid parameter set — a stronger, universal guarantee — at the cost of greater manual effort, and it does not establish the liveness/recovery property P3 unconditionally (Tier 1 requires an explicit drift hypothesis; Tier 2 recovery is left to future work). The study is careful not to overclaim: it notes a minor tie-break discrepancy between the model-checking and Lean encodings, and frames the model-checking results explicitly as claims about the finite abstraction rather than the continuous system.
