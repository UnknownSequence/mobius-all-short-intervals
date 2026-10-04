# Möbius cancellation in all intervals of length x^0.5435

**Status: AI-generated research draft. No human has checked it; treat every claim as unverified.**

This repository holds a note produced by an automated multi-agent proof search run with Claude (Anthropic) on
3 October 2026. Siddharth Iyer selected the problem and co-designed the search strategy; the mathematics and
write-up were produced by the agents.

## Claim

Matomäki and Teräväinen ([On the Möbius function in all short intervals](https://doi.org/10.4171/JEMS/1205),
J. Eur. Math. Soc. 2023, Theorem 1.1) proved that for every θ > 0.55,

    Σ_{x<n≤x+H} μ(n) ≪ H / (log x)^{1/3−ε}   for all H ≥ x^θ.

The note (`paper/mobius_all_intervals_05435.pdf`) claims the same for every **θ > 0.5435**.

- **Method.** The Matomäki–Teräväinen reduction is kept unchanged. Their Lemma 4.4, a Heath-Brown–Iwaniec
  type lemma, is replaced by an argument using the large value estimates of Guth and Maynard
  ([Ann. of Math. 2026](https://doi.org/10.4007/annals.2026.203.2.6)) and the fourth moment of ζ. A
  computer certificate in exact rational arithmetic closes the exponent bookkeeping.
- **Limit of the method.** 69/127 ≈ 0.54331.

## How it was checked, and what is missing

- It was refereed only by independent AI agents.
- The agents read the text of Matomäki–Teräväinen only through a summarising web tool.
- `FINAL_REPORT.md`, section "Before sharing", lists the checks a person should do first.
- The certificate scripts and the full working record of the run (agent prompts, reports, lemma database) are
  not in this repository. `FINAL_REPORT.md` and `blueprint.md` refer to them by their original paths.

## Contents

| Path | What it is |
|---|---|
| `paper/` | the note, 15 pages (`.tex` and `.pdf`) |
| `FINAL_REPORT.md` | summary of the run |
| `blueprint.md` | the proof plan, updated after each round |

Related: [exact-semiprimes-lean](https://github.com/UnknownSequence/exact-semiprimes-lean), a companion project on
products of two primes in almost all short intervals, and
[squarefree-variance-short-intervals](https://github.com/UnknownSequence/squarefree-variance-short-intervals).
