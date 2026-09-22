# 13 — A†-SPEC behavioral-access protocol (specification only, not yet run)

Clean English edition of `A†-SPEC`, a strictly behavioral specification of functional
access capability, together with its adjudication instrument, the W1–W6 verification grid.
Unlike every other numbered folder in this archive, this one is not the record of an
executed campaign. It is the record of a **frozen, hashed, not-yet-sealed measurement
specification** and of a **not-yet-run adjudication grid** for it. Both facts are stated
here as plainly as the source documents themselves state them.

## Status — read this first

- **A†-SPEC is at version v0.24, DRAFT, and its own header states `Status: NOT SEALED.`**
  It has been frozen and hashed as a text (§0, provenance note), but it has not cleared its
  own §12 sealing procedure, and it has **never been run as a campaign against any system**
  — human, animal, or artificial. No `A†` measurement exists anywhere in this archive.
- **The only adjudication instrument available, the W1–W6 verification grid, is at v0.4 and
  targets an older draft, `A_DAGGER_SPEC_v0.11_DRAFT.md`**, not the current v0.24 text. Its
  own status line reads `TO BE ADJUDICATED. Not yet run.` Every cell in its grid — five
  clauses × six criteria, plus seven cross-cutting checks — is blank. No one has adjudicated
  it, against v0.11 or against anything else.
- Consequently: **the version the grid was built against (v0.11, 5 clauses) is not the
  version now frozen (v0.24, 11 clauses)**, and even a full re-run of the existing grid
  against v0.11 would not constitute adjudication of v0.24. Before A†-SPEC can be considered
  sealed under its own §12, the grid must be rebuilt against v0.24's actual clause text — six
  clauses were added since v0.11 (TEMPORAL-AUTONOMY, ELAPSED-TIME-CONTROL, HARD-ERASURE,
  SELECTIVE-ERASURE, SOURCE-BINDING, CAUSAL-OWNERSHIP) — and then adjudicated by someone
  other than the drafter, which is a rule the SPEC states about itself (§1): "the check is
  entrusted to no author's judgement." See `docs/w1-w6-verification-grid.md`.

Nothing in this folder should be read as reporting a sealed instrument, an executed
measurement, or an adjudicated verification. It documents a specification's current,
honest, in-progress state.

## What A†-SPEC is

`A†` measures **functional access capability** — a family of episodic-use capabilities
demonstrated under controlled external intervention — and explicitly nothing else. It is
built around three separately-sealed layers (§0.3):

```
Functional layer   A†        knows nothing about internal organisation
Bridge layer        H_{N,I}   relates the external A* protocol to A†, per instance
Physical layer       P[C]     knows nothing about consciousness
```

and a strict split between the **SPEC** (frozen once, this document: clauses, scoring
typing, thresholds rule, verdict vocabulary, normative estimators) and an **INSTANCE**
(frozen before each campaign: delay, battery, cue families, concrete score functions,
datasets — everything a laboratory must decide to actually run the SPEC). See
`docs/spec-structure-and-layers.md` for the full architecture, including why the SPEC
treats its own thresholds as "metrological, not ontological," why results cannot be
compared across instances without a declared linking procedure, and what A† is built to be
unable to separate (the "wrapper test" of §0.7).

The measured object is a cumulative three-rung **core ladder** (`A†_0`, `A†_1`, `A†_2`) plus
four independent **capability certificates** (`Cert_T`, `Cert_E`, `Cert_B`, `Cert_A`), built
from eleven named behavioral clauses. See `docs/behavioral-clauses.md`.

## Why this matters for the manuscript

The manuscript's organizational-necessity bridge test (`H_org` / `H_CO^+`, §9 of the SPEC)
needs an independent way to establish that a system exhibits access-type behavior, so that
"does this system behave as though it has access" and "is this system organizationally the
kind of thing the manuscript's Γ/Δ/R/Λ framework says can have access" are not the same
question asked twice. A†-SPEC is designed from the ground up to be that independent
instrument: **its clause text never references Γ, Δ, R, Λ, nor B, T, U, Addr, nor
integration, irreducibility, recurrence, or multi-role propagation** (§0.2). This is not an
incidental stylistic choice — it is mechanically checked. §1's cross-cutting rules X1/X2
require a whole-token scan of the clause text for exactly these symbols (a mechanical
sub-check, X1a/X2a, anyone including the drafter may run) followed by an adjudicated check
of whether any surviving occurrence is used in the forbidden sense (X1b/X2b, which the
drafter may not run). §15 records the mechanical scan's own result on the current text: zero
occurrences of every forbidden symbol.

That non-circularity is the entire point of building A†-SPEC as a separate document rather
than as a clause inside the main framework: only an instrument that could never have
smuggled in a reference to Γ/Δ/R/Λ can later be used, without begging the question, to test
whether organizational necessity (as the manuscript's axes define it) predicts behavioral
access (as A†-SPEC measures it). See `docs/spec-structure-and-layers.md` and §9 of the SPEC
itself (`H_{N,I}`, the bridge hypothesis family this specification exists to eventually
feed).

## Main content

1. **Three-layer architecture, SPEC/INSTANCE split, and what A† cannot separate.**
   `docs/spec-structure-and-layers.md`.
2. **The eleven behavioral clauses**, what each tests and why, summarized at reviewer
   level. `docs/behavioral-clauses.md`.
3. **The W1–W6 verification grid**: the six well-formedness criteria, the seven
   cross-cutting checks, and the version-mismatch problem stated in full.
   `docs/w1-w6-verification-grid.md`.
4. **Issue history**: three ambiguities found and resolved during earlier grid/SPEC
   co-development (I-1, I-2, I-3), kept and narrated rather than dropped, per this
   archive's "never hide a found defect" discipline. `docs/issue-history.md`.
5. **Machine-readable status summary.** `results/STATUS.json`.

## Reproduction discipline

This campaign follows the same discipline as every other campaign in this repository (see
the root `README.md` for the full statement): a protocol is frozen and hashed before any
candidate is coded; a generator produces fixtures and a private oracle records the expected
verdict for each one; a candidate is written against the frozen fixtures; and where the
result claims a **candidate-fixed holdout**, a second, independent fixture set is generated
*after* the candidate's hash is frozen and the same unmodified candidate is re-run against
it. Verdicts are reported as `V1/POINT` (a unique value), `V3/PARTIAL` (several values remain
compatible, reported as a set) or `V4/NA` (the intervention algebra abstains) — no result here
silently turns a partial finding into a single number.

**How that discipline applies here.** There is no candidate and no private oracle in this
folder, because A†-SPEC has not yet been run as a campaign: it is the *protocol* half of the
discipline above, not yet followed by a generator, a candidate, or any fixtures. The SPEC's
own §12 sealing procedure is its analogue of this repository's "freeze and hash before any
candidate" step, and its own §7.0 ("no instance parameter is set from the campaign's target
systems") is its analogue of keeping the oracle private. Both are stated, in the SPEC's own
vocabulary, as requirements the eventual campaign must meet — neither has been exercised
yet. The W1–W6 grid is the SPEC's own pre-registered adjudication instrument, playing the
role a private oracle's verdict vocabulary plays elsewhere in this archive: `PASS` / `FAIL`
/ `AMBIGUOUS` per cell, `AMBIGUOUS` blocking, exactly as `V3/PARTIAL` and `V4/NA` are never
silently collapsed to a bare number in the rest of this archive. Its cells are, as of this
edition, entirely unfilled.

## No private files

No `*_PRIVATE.json` scoring oracle, no fixture set, and no candidate exist for A†-SPEC,
because no campaign under it has been run. There is nothing private to withhold in this
folder: it contains the frozen specification text's structure and the frozen (but not yet
executed) adjudication grid, both restated in clean English, and nothing else.

## Contents

```
README.md
docs/
  spec-structure-and-layers.md   — the three layers, SPEC vs INSTANCE, §0.5 metrological-
                                    not-ontological clause, §0.6 instance-relativity and the
                                    cross-instance-comparison ban, §0.2 what A† is not, and
                                    the §0.7 wrapper test (what A† cannot separate)
  behavioral-clauses.md          — the eleven clauses, the core ladder and the four
                                    certificates they compose into, summarized for a reviewer
  w1-w6-verification-grid.md     — the six well-formedness criteria, the seven cross-cutting
                                    checks (X1's Γ/Δ/R/Λ/B/T/U/Addr ban among them), and the
                                    v0.11-vs-v0.24 version-mismatch caveat in full
  issue-history.md               — I-1/I-2/I-3: three ambiguities found and resolved during
                                    earlier SPEC/grid co-development
results/
  STATUS.json                    — machine-readable status: spec version and NOT_SEALED
                                    state, grid version/target mismatch, grid NOT_RUN state,
                                    what this specification is meant to eventually
                                    decircularize, and the next steps before sealing
```
