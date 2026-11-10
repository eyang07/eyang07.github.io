---
layout: page
title: Learning Modular Multiplication with Neural Networks
importance: 4
description: Neural modular multiplication for the SAIR challenge, with submission results and an evaluation audit.
permalink: /research/neural-modular-multiplication/
---

The SAIR Modular Arithmetic Challenge asks neural networks to learn modular multiplication. I explored supervised arithmetic scratchpads that make intermediate computations explicit, helping limit errors across long calculations. The evaluated submission uses a learned recurrence for each tier.

## Competition results

Submission **MAC01-T00044** (`cire77/modmul`, revision `6e7450f098f84bca6b0037b994060d3ad45b4f38`) received a reported score of **69.4%**, with **76.4 seconds** of inference time and an audit status of **Warning**. Observed accuracy was at least 90% on tiers T1–T7, including 100% on T5–T7, before falling to 2% on T8–T10.

| Tier | Observed accuracy |
| --- | ---: |
| T0 | 45% |
| T1 | 100% |
| T2 | 100% |
| T3 | 98% |
| T4 | 90% |
| T5 | 100% |
| T6 | 100% |
| T7 | 100% |
| T8 | 2% |
| T9 | 2% |
| T10 | 2% |

**Audit warning — operand pre-reduction.** The submitted implementation reduces both operands modulo the input modulus in Python before selecting the tier-specific recurrence. The evaluation rules require a preprocessing hook to use only its own argument; using the modulus to pre-reduce an operand outside the model removes part of the calculation the model must learn. These figures therefore describe the observed submitted implementation, not a confirmed rules-compliant result. The audit also notes that the learned recurrence itself does not use multi-phase host composition.
