# Blueprint — Möbius 11/20 improvement, phase II (started 12:55 AEST, budget ~2 h)

Prior run ('Mobius attempt'): MT Theorem 1.1 holds for θ > 0.548 (internally refereed). Method limit with the same
inputs: 69/127 ≈ 0.54331 (inf_k form of Guth–Maynard Prop 12.1; refereed symmetric five-factor case L5F) or 0.54376
(closed form). Binding: five smooth factors x^{1/5}, all at σ ≈ 0.7185 ("triple point": mean value theorem, GM Prop 12.1
third term, ζ fourth moment).

## Goal A (consolidation): θ > 69/127 + ε (target statement: θ > 0.5435)
- A1 certificate with the inf_k form of Prop 12.1, exact arithmetic (base: prior numerics/p4_check.py, certify_exact.py)
- A2 Lemma Q (corners) and Lemma Z (ζ-moment transfer) for τ up to 0.4566
- A3 assembly + referee

## Goal B (new ideas): below 69/127
Critical object: I(θ) = ∫_{T0}^{x^{1-θ}} |N1···N5(1/2+it)| dt, N_i smooth segments of length x^{1/5}; need ≪ x^{1/2}(log x)^B
(log-loss suffices: MT's prime polynomial P gives (log x)^{-A}); plus nearby configurations with tiny extra pieces.
Candidate routes:
- R1 full smoothness: treat as a 5-fold divisor (d5-box) counting problem; exponent pairs / B-process on segments; ζ mixed
  moments (ANTEDB Cor. 9.14: sixth moment restricted to |ζ| ≥ T^{11/72} is ≪ T^{1+o(1)}); note α5 ≤ 11/20 (Heath-Brown).
- R2 joint large values: ζ (or a segment) is not large on most of the large-value set of A (prior O2b; small-x numerics
  lean against).
- R3 energy dichotomy (prior DR2-L1, unrefereed): high-energy binding sets are harmless via GM Lemma 1.7; reduce to
  low-energy sets, then use Heath-Brown's difference-set theorem / GM's method on low-energy sets?
- R4 better large values for products of two ζ-segments (length T^{0.88}) at σ ≈ 0.72.
- R5 anything the goofy agents propose.
Pipeline changes vs prior run: provers get db/sets.md and top mutants; a stuck prover must restate its obstacle via a set;
bridge-builder matches failures to sets; control prover PC has no goofy input.

## After round 1 (13:22)
- Goal A: THM5435 proved informally (GA): exact certificate with inf_k Prop 12.1 at theta >= 0.5435 (and down to 69/127 + 1e-6); gap in box-edge argument found and fixed. Referee pending (R4).
- Goal B: no improvement below 69/127. Joint route O2b REFUTED (A = C^2 on equal segments; found via set E9). Energy route capped at 19/35 inside GM's method (PB2). Control PC1 and PB1 independently: obstacle = large values / fifth moment of a single zeta segment at sigma ~ 0.7165 (O4sym). Priced targets in N7.
- Goofy leads for round 2: E12 DualCore + E13 level profile + S4's zeta-zero neighbourhoods -> an inverse theorem for large values of zeta segments ('dual-core' structure); X7 = GM's binding S2 difference sum (PB2).

## After round 2 (~13:40)
- Goal A REFEREED (R4 ACCEPT): theta > 0.5435 (remark: > 69/127 + 9.1e-7). Paper draft 13 pp (W2).
- Goal B: single live target W(delta) (BB); classical tools provably insufficient (PC2, control); goofy leads: PB3-ITE
  (multi-scale/Euler-product coherence, numerically supported, would give ~0.535), DR5-P1 (spread-or-closed dichotomy,
  gap 0.06 in the energy exponent). Round 3: ATT-1 rigorous sub-family below 69/127 (GA2); PB4 on DR5-P1 + ITE; control PC3.
