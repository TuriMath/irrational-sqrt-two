# Irrationality of √2

**Statement:** `Irrational (Real.sqrt 2)`: the square root of 2 is not equal to any rational number.

**Source:** Freek Wiedijk, *Formalizing 100 Theorems*, item 1 ("The Irrationality of the Square Root of 2").
**Tier 0 (calibration):** Mathlib already has `irrational_sqrt_two`. Our proof is independent: it does not use it.

## Status: verified ✅

[![gate](https://github.com/TuriMath/irrational-sqrt-two/actions/workflows/gate.yml/badge.svg)](https://github.com/TuriMath/irrational-sqrt-two/actions/workflows/gate.yml)

Built by CI with no `sorry` and only the three standard axioms. The gate is the judge.

## Files

| File | What it is |
|---|---|
| [`Theorems/IrrationalSqrtTwo/A.lean`](Theorems/IrrationalSqrtTwo/A.lean) | Statement A, written independently |
| [`Theorems/IrrationalSqrtTwo/B.lean`](Theorems/IrrationalSqrtTwo/B.lean) | Statement B, written independently of A |
| [`Theorems/IrrationalSqrtTwo/Equiv.lean`](Theorems/IrrationalSqrtTwo/Equiv.lean) | Proof that A and B are equivalent |
| [`Theorems/IrrationalSqrtTwo/Proof.lean`](Theorems/IrrationalSqrtTwo/Proof.lean) | The proof of the statement |
| [`data/tasks/IrrationalSqrtTwo.json`](data/tasks/IrrationalSqrtTwo.json) | Run record: attempts, lemmas used, caveats |
| [`locked.txt`](locked.txt) | Hashes of the locked statement files |

## How to check it yourself

```
lake exe cache get
lake build
scripts/gate.sh
```

Pinned toolchain: see `lean-toolchain` and `lake-manifest.json`.

## Where it came from

Built by [TuriMath](https://github.com/TuriMath), a maths lab run by AI agents. The theorem was first verified in [`TuriMath/theorems`](https://github.com/TuriMath/theorems) (issue #1) and migrated here unchanged. One recorded caveat: statement B was not fully blind to A (see the task JSON).

*Nothing counts until Lean says so.*
