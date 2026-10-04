# Möbius 11/20 improvement, phase II: final report

**Run:** 3 Oct 2026, 12:55–14:20 AEST (about 1 h 25 min). It stopped once both goals had been settled as far as the current tools allow.

**Strategy:** overseer, provers, drunkard (v2), set-creator, falsifier, scout, referees, bridge-builder and focus mode. New in this phase: provers got the goofy agents' output, a stuck prover had to restate its obstacle in terms of a set, and a control prover in every round worked without any goofy input.

## Outcome

### Goal A (consolidation): reached and refereed

Matomäki–Teräväinen's Theorem 1.1 holds for every **θ > 0.5435**:

Σ_{x<n≤x+H} μ(n) ≪ H/(log x)^{1/3−ε} for H ≥ x^θ.

That is δ = 0.0065 below 11/20 (phase I gave 0.548).

- **Proof change:** the exact certificate now uses the inf_k form of Guth–Maynard's Proposition 12.1 (k = 1..12).
  - GA found and fixed a gap in the earlier box-edge argument: the inf_k bound is now used only where σ > 7/10 strictly.
  - The corner lemma (Lemma Q) holds for τ < 0.472, and Lemma Z does not depend on τ.
- **Referee:** R4 accepted. Its independent re-verifier checked 331,054 boxes at τ = 913/2000 and 586,580 at τ = 0.456692, with 0 failures.
- **Remark:** the certificate also passes at θ ≥ 69/127 + 9.1·10⁻⁷ (with ε ≤ 10⁻⁷). A control run at 0.5433 fails. 69/127 = 0.543307 is the limit of this method.
- **Write-up:** `paper/mobius_all_intervals_05435.tex` and `.pdf` (15 pages).

### Goal B (below 69/127): not reached

**Refereed partial result (SUB542; referee R5 accepted with corrections).** At θ = 0.542, Lemma 4.4′ holds for every admissible triple outside the near-equal box max(|a−0.4|, |b−0.4|) ≤ 0.0075. The certificate has 425,506 leaves.

So the theorem for θ > 0.542 reduces to a single residual family NE[0.0075]: a smooth factor of length about 0.2 and two groups each of total length about 0.4. For five smooth factors of lengths 0.2+δ_i, a configuration stays open if and only if |δ_i+δ_j| ≤ 0.0075 for all i ≠ j. GA2 also certified r = 0.0125 at θ = 0.541 and r = 0.02 at θ = 0.540; the referee did not re-run these.

**The exact obstacle.** When all segments are equal, the residual case is exactly the fifth moment of one short ζ-segment (PB1, and independently the control PC1).
- At 69/127 there is an exact triple point σ = 91/127, τ = 290/127. There the mean value theorem on s², the k = 5 term of Guth–Maynard Prop 12.1, and the requirement all equal 180/127.
- Classical tools cannot beat the fourth-moment count for σ < 3/4 (control PC2).
- PC3 (control) found a slice equivalence. Beating the fourth-moment count uniformly in τ is equivalent, up to T^ε, to improving Ingham's large-value bound for ζ itself at heights T^{0.09}–T^{0.095}. This is below T^{1/8}, where no improvement is known (PC3's memory; not checked against the literature).

**Most promising lead.** PB3's multi-scale "Euler-product coherence" (PB3-ITE): a large value of a long segment forces a much shorter segment to be nearly as large nearby.
- It is strongly supported numerically (defect δ ≈ 0.05).
- Its exact price (PB4): k = 4 with δ_I ≤ 0.496 would give θ* ≈ 0.540.
- It follows from Lindelöf. No unconditional proof is known; the bridge between scales is circular through the approximate functional equation.

## Did the goofy agents help this time?

**Yes, more than in phase I, though mostly by steering rather than by supplying a lemma that went into a proof.**

- **"Wait a minute" moments with sets.**
  - **E9 (joint A–C set) → PB1 refuted the joint route O2b.** On equal segments A = C², so the route can never work. This was last run's top-ranked goofy lead.
  - **X7 (difference pairs) → PB2.** GM's binding S2 term is exactly X7's difference sum over W−W.
  - **E12, E13 and S4's zero-neighbourhood set → PB3's coherence lead (ITE),** the most promising positive idea of the run. On the way, PB3 refuted E12's own explanation: the coherence comes from the Euler product, not from shared dual terms.
- **Drunkard.**
  - DR4's pricing pinned where any gain must occur: σ ≈ 0.716 and below 0.7.
  - DR5's spread-or-closed dichotomy (P1) was refuted by PB4 (the Halász–Montgomery 3/4 barrier). That refutation produced the exact identity d_c = 2 − 4/κ and the exact price of ITE.
  - DR6 flagged the same flaw independently, and found a bug in the drunkard code, now fixed.
- **Bridge-builder.** BB's obstacle map proposed ATT-1, which became the refereed reduction SUB542 below 69/127.
- **Controls.** PC1, PC2 and PC3 independently reproduced the frontier and the obstacle, and PC3 found the strongest "why it is hard" statement (the Ingham-bound equivalence). So the control line was as good as the goofy line at diagnosis. The goofy line was better at producing new directions (ITE, the S2/X7 identification) and at killing wrong ones early (O2b, DR5-P1).

## Database at close (`db/lemmas.json`, 46 entries)

| Status | Entries |
|---|---|
| Refereed | THM5435 (R4); SUB542 (R5); DR2-L1 (energy dichotomy, PB2) |
| Imported from phase I (refereed there) | L5F, L4P, THM548 |
| Refuted | O2b (joint route); DR5-P1 (spread branch); E12's original explanation (in sets.md) |
| Open | O4sym (fifth moment of one segment); PB3-ITE (coherence conjecture); W(δ) (BB's live target) |
| Analyses | BB-MAP, PC2-OBS, PC3-EQ, PB4-F, N7 (model prices) |

`db/sets.md` now has E1–E17 (including E15 SET-MS and E16 NE(θ, r)) and the exploratory sets X2, X9 and X12.

## Rounds

| Time | Phase | Agents and results |
|---|---|---|
| 12:55–12:58 | Phase 0 | Imported the database; literature probes (ANTEDB: α₅ ≤ 11/20; mixed moments Cor 9.14); drunkard v2 |
| 12:58–13:22 | Round 1 | GA (Goal A certificate), PB1, PB2, PC1 (control), SC5, DR4, S4 |
| 13:23–13:38 | Round 2 | R4 (accepts Goal A), BB (obstacle map), PB3 (ITE), PC2 (control), DR5, W2 (paper) |
| 13:38 | Checkpoint | Saved to the Mac |
| 13:39–14:05 | Round 3 | GA2 (SUB542), PB4, PC3 (control), SC6, DR6, W2 (R4 fixes) |
| 14:02–14:20 | Round 4 | R5 (accepts SUB542 with corrections), W2 (adds §6.1), final report |

## Before sharing

1. **Human checks** inherited from phase I: the MT text (Lemmas 3.1, 4.2, 4.3, 4.5) in the original, the classical citations, and reruns of the certificates (`numerics/certify_exact_k.py`, `rounds/round2/R4_scripts/r4_verify.py`).
2. **Literature:** check PC3's claim that no improvement of Ingham's large-value bound for ζ below T^{1/8} is known. If one exists, Goal B may follow directly.

## Files

- `paper/`: the note for θ > 0.5435, with the refereed reduction below 69/127 (15 pages).
- `db/`:
  - `lemmas.json`: the lemma database;
  - `sets.md`: the set-creator's sets;
  - mutants (rounds 1–3), obstacles and operator weights.
- `rounds/round1` to `rounds/round4`: every agent's report, checkpoint and scripts.
- `numerics/`: certificates (`certify_exact_k.py` and others) and the exponent models.
- `drunkard.py`: v2.1, seeded mutation code with the range bug fixed.
- `agents/`: the prompts given to each agent.
- `prior/`: phase-I material.
- `blueprint.md`: the proof plan, updated after each round.
