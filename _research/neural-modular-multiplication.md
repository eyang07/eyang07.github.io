---
layout: page
title: Learning Modular Multiplication with Neural Networks
importance: 4
description: Learning modular multiplication through supervised transformer scratchpads for the SAIR challenge.
permalink: /research/neural-modular-multiplication/
---

The SAIR Modular Arithmetic Challenge asks neural networks to learn modular multiplication from their parameters. My approach uses a decoder-only transformer with abacus-style positional embeddings to generate a supervised arithmetic scratchpad, multiplying and reducing after each digit to keep intermediate values small. At inference, the model emits digit tokens without directly performing division or modular arithmetic.

Progress came from making intermediate computations explicit: partial sums unlocked tier 3, quotient-times-modulus products unlocked tier 4, and a higher numeric base shortened the execution chain for tier 5. These representational changes helped limit the accumulation of errors across long computations.

The submitted models reached **htop90 = 5** in runs through the organizers' evaluation pipeline, compared with the public baseline of **1**. Tier 5 covers 33–64-bit primes and remained close to the 90% accuracy threshold, so its held-out pass was not certain. Work toward tier 6 focused on faster decoding with a key-value cache, a denser numeric base, and a self-checking borrow field to reduce off-by-one errors.

