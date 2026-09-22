# The W1–W6 verification grid — and why it does not (yet) adjudicate v0.24

Source: `A_DAGGER_SPEC_v0.11_DRAFT.md`'s six well-formedness criteria as restated by the
grid document `A_DAGGER_W1_W6_VERIFICATION_GRID_v0.4.md`, and §1 of
`A_DAGGER_SPEC_v0.24_DRAFT.md`. This file restates what the grid is and does, in clean
English; it does not fill in any cell, because none has been filled in by anyone.

## Version mismatch, stated up front

**The grid is built against `A_DAGGER_SPEC_v0.11_DRAFT.md`.** Its own header names that
exact file and a hash (`e92a1005…`) as its target document. The SPEC in this archive is
`v0.24`. Between v0.11 and v0.24 the clause set grew from five clauses to eleven — v0.11
apparently covered only DELAYED-USE, SUBST, INTERFERENCE, POSTCUE-MULTI-USE and CONTROL,
which is exactly the set the grid's clause-by-clause table covers today. The six clauses
added since (TEMPORAL-AUTONOMY, ELAPSED-TIME-CONTROL, HARD-ERASURE, SELECTIVE-ERASURE,
SOURCE-BINDING, CAUSAL-OWNERSHIP) have no rows in this grid at all.

**Separately, and just as importantly: the grid has never been run, against v0.11 or against
anything else.** Its own status line reads `TO BE ADJUDICATED. Not yet run.` Every verdict
cell in its five-clause table, every cross-cutting check, and the adjudication-record table
at the end are blank. No adjudicator, drafter or otherwise, has recorded a single PASS, FAIL
or AMBIGUOUS anywhere in this document.

So there are two separate gaps, not one: (a) the grid's coverage is stale — it does not even
attempt to cover six of the eleven current clauses — and (b) even the coverage it does have
has never been exercised. Before A†-SPEC can be considered sealed under its own §12
procedure, both gaps have to close: the grid needs to be rebuilt against v0.24's actual
clause text (eleven clauses, not five, plus whatever cross-cutting checks the newer clauses'
non-claim-line exemptions require), and then it needs to actually be run by an adjudicator
who did not draft the clauses — a rule the SPEC states about itself (§1): the check "is
entrusted to no author's judgement." Nothing in this archive should be read as implying that
adjudication has happened, or that the existing grid, run as-is, would be sufficient even for
v0.11.

## What the grid checks: six criteria as questions

For each clause, the grid asks one question per criterion, with a required answer:

| Criterion | Question | Required answer |
|---|---|---|
| **W1 — TABULATION-INVARIANCE** | Could two systems with identical external interventional behavior under this clause receive different verdicts? | **No** |
| **W2 — NO-LINGUISTIC-REQUIREMENT** | Can the clause be instantiated on a non-verbal organism, with no step requiring language? | **Yes** |
| **W3 — EPISODIC-NOVELTY** | Could a parameter-stored disposition, with no episodically fresh binding, pass the clause? | **No** |
| **W4 — EXOGENOUS-NO-REPLAY** | Does the clause's procedure re-inject the target content, or an informationally equivalent code, back into the system after initial presentation? | **No** |
| **W5 — BOUNDARY-RULE-SEALING** | Does the clause name a resource type, or otherwise depend on anything beyond the frozen boundary rule applied uniformly? | **No** |
| **W6 — NA-IS-NOT-FAIL** | Does the clause have a well-defined "not applicable to this interface" condition, distinct from failure and statable on the interface? | **Yes** |

Each clause × criterion pair is one cell (five clauses × six criteria = thirty cells in the
current grid), recorded as `PASS`, `FAIL`, or `AMBIGUOUS`. `AMBIGUOUS` is explicitly a
blocking verdict, not a soft one: per the SPEC's own §13 reopening rule, "an ambiguity
yielding two different verdicts for the same observations" is one of the few things that can
reopen an already-sealed SPEC, so an ambiguous cell must be corrected in the text before
sealing — never adjudicated away by preference.

The v0.24 SPEC text itself (§1) restates and sharpens W1–W6 for the full eleven-clause set —
this is the version whose text the *next* grid must be checked against, once rebuilt.

## Cross-cutting checks (X1–X7)

Beyond the per-clause grid, seven checks apply to the document as a whole:

- **X1 — the non-circularity ban.** No clause text may contain: Γ, Δ, R, Λ, B, T, U, Addr,
  integration, irreducibility, recurrence, multi-role propagation. This is the mechanical
  half of the check described in the root README of this folder — the property that lets
  A†-SPEC eventually serve as a non-circular instrument for the manuscript's organizational
  bridge test. The v0.24 SPEC text sharpens this into a two-phase X1a/X1b split (a mechanical
  whole-token scan anyone can run, followed by an adjudicated judgment of whether any
  surviving occurrence is used in the forbidden sense, which the drafter may not perform) —
  itself evidence that the SPEC has moved substantially since v0.11, in ways this grid does
  not yet reflect.
- **X2 — no architecture or resource naming.** No clause text may name an architecture or a
  resource type (cache, memory, register, and similarly concrete terms).
- **X3 — null conditions exist and differ from target conditions**, for every clause.
- **X4 — the verbatim-buffer control.** Every clause must admit a large verbatim buffer as a
  possible pass (this is the concrete instantiation of the W1 "no architectural preference"
  principle).
- **X5 — the disposition-only control.** Every clause must reject a system holding only a
  pre-existing, non-episodic disposition (the concrete instantiation of W3).
- **X6 — conformance-case consistency.** The conformance cases in SPEC §8 must be consistent
  with whatever verdicts the grid records.
- **X7 — the null insensitivity criterion.** For every clause, a system genuinely insensitive
  to the effect the clause is built to detect must score at its null, not merely at a fixed
  low value — the grid is explicit that this is *not* the same as requiring the null to sit
  at zero (SUBST's null sits at chance for a content-insensitive system, not at zero; see
  `issue-history.md` for how this check itself was corrected mid-development).

## Adjudication record — entirely blank

The grid's closing table asks for an adjudicator's name, a date, the SPEC version and hash it
was run against, cell counts by verdict, any blocking items, and a final `SEALABLE /
NOT SEALABLE` call. Every field is empty in the source document. No date, no name, no cell
counts, and no verdict of any kind has been recorded. This folder reproduces that fact rather
than filling in any placeholder value.
