---
layout: page
title: Learning Modular Multiplication with Neural Networks
importance: 4
status: ongoing
year: 2026
description: Training transformer scratchpads to learn modular multiplication for the SAIR Modular Arithmetic Challenge.
permalink: /research/neural-modular-multiplication/
---

I am participating in the SAIR Modular Arithmetic Challenge, which asks models to compute modular multiplication from learned parameters rather than hand-coded reduction routines. The difficulty is exact long-chain execution: small per-step errors compound rapidly as the prime range grows.

My approach represents the computation as an autoregressive scratchpad. A decoder-only transformer with abacus-style positional embeddings emits supervised intermediate arithmetic instead of predicting the final residue in one step. For tier 3, I use an interleaved Horner-style multiply-reduce pass over one operand, reducing after each digit so that all intermediate values remain within a short, reliable digit range.

Current results: tier 2 is solved and submitted with `htop90 = 2`, exceeding the public baseline of `htop90 = 1`. For tier 3, long-division reduction over the full prime range reaches about 96% exact match; diagnostics found exact single-digit multiplication and localized the remaining error to an omitted intermediate sum, which has since been added to the scratchpad. The composed tier-3 model is currently training.

Training labels use ordinary integer arithmetic to generate supervision targets. At inference, the deployed model emits digit tokens only and performs no division or modular operation directly.
