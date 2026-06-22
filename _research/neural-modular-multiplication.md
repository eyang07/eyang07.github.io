---
layout: page
title: Learning Modular Multiplication with Neural Networks
importance: 4
status: ongoing
year: 2026
description: Training transformer scratchpads to learn modular multiplication for the SAIR Modular Arithmetic Challenge.
permalink: /research/neural-modular-multiplication/
---

I am participating in the SAIR Modular Arithmetic Challenge, which asks models to compute modular multiplication from learned parameters rather than hand-coded reduction
  routines. The difficulty is exact long-chain execution: small per-step errors compound rapidly as the prime range grows, since end-to-end accuracy is approximately the
  per-token accuracy raised to the chain length, and the chain length doubles with each tier.

  My approach represents the computation as an autoregressive scratchpad. A decoder-only transformer with abacus-style positional embeddings emits supervised intermediate
  arithmetic instead of predicting the final residue in one step, using an interleaved Horner-style multiply-reduce pass that reduces after each digit so all intermediate
  values stay within a short, reliable range. The central methodological finding is that successive tiers were unlocked by representational changes rather than added scale:
  each wall fell when a previously implicit intermediate was made explicit and supervised — the partial-sum at tier 3, the explicit quotient-times-modulus products at tier
  4 — and the numeric base was raised at tier 5 to keep the chain short enough for reliable execution.

  Current results: tiers 1 through 5 are solved and submitted, reaching htop90 = 5 and reproduced through the organizers' evaluation pipeline, well above the public
  baseline of htop90 = 1. Tier 5, which spans 33-to-64-bit primes, sits near the 90% threshold and is best characterized as a high-probability but not certain pass on the
  held-out seed, with tier 4 as a guaranteed floor.

  Current work targets tier 6 (64-to-128-bit primes), where the binding constraint shifts from accuracy to the fixed inference-time decode budget. I address this on two
  fronts: a key-value cache that reduces autoregressive decoding from cubic to quadratic cost in sequence length, and a denser numeric base that holds the tier-6 chain
  length equal to tier 5's, so the harder regime is reached without a longer execution chain. I additionally introduce a self-checking "borrow" field that re-expresses each
  remainder against the modulus bound, forcing the model to locally verify each reduction step and hardening it against the dominant off-by-one error.

  Training labels use ordinary integer arithmetic to generate supervision targets. At inference, the deployed model emits digit tokens only and performs no division or
  modular operation directly.

