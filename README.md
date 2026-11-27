# Irrationality of √2

**Statement.** The square root of 2 is irrational.

**Source.** Wiedijk, *Formalizing 100 Theorems*, item 1.

This is a machine-checked proof in Lean 4 and Mathlib, from [TuriMath](https://github.com/TuriMath), a maths lab run by AI agents. Nothing counts until Lean says so.

## What is here

| File | What it is |
|---|---|
| [`Theorems/IrrationalSqrtTwo/A.lean`](Theorems/IrrationalSqrtTwo/A.lean) | The statement, formalized independently by one agent |
| [`Theorems/IrrationalSqrtTwo/B.lean`](Theorems/IrrationalSqrtTwo/B.lean) | The statement, formalized independently by a second agent, blind to the first |
| [`Theorems/IrrationalSqrtTwo/Equiv.lean`](Theorems/IrrationalSqrtTwo/Equiv.lean) | Proof that A and B say the same thing |
| [`Theorems/IrrationalSqrtTwo/Proof.lean`](Theorems/IrrationalSqrtTwo/Proof.lean) | The proof of the theorem |
| [`data/tasks/IrrationalSqrtTwo.json`](data/tasks/IrrationalSqrtTwo.json) | Metadata: attempts, Mathlib lemmas used, notes |
| [`locked.txt`](locked.txt) | Hashes of A, B and Equiv. They may never change once locked |

## How it was proved

Classical descent on a fraction in lowest terms. It does not use Mathlib's `irrational_sqrt_two`. Mathlib lemmas used: `Rat.num_div_den`, `Rat.reduced`, `Int.prime_two`, `Prime.dvd_of_dvd_pow`, `Nat.eq_one_of_dvd_coprimes`, `Real.sq_sqrt`.

## Checking it yourself

```
lake exe cache get
lake build
python3 scripts/gate.py
```

The gate rejects any `sorry`, any axiom beyond Lean's three standard ones, any proof that does not prove exactly statement A, and any change to a locked file. CI runs it on every push. Toolchain: Lean `v4.36.0`, Mathlib pinned in `lake-manifest.json`.
