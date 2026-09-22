# A†-SPEC structure: three layers, SPEC vs INSTANCE, and what it refuses to claim

Source: `A_DAGGER_SPEC_v0.24_DRAFT.md`, §0. This is a restatement of the architecture for a
reviewer, not a copy of the source text.

## 1. Three layers, sealed separately

A†-SPEC is deliberately built as one of three layers that never merge:

| Layer | Symbol | What it knows about |
|---|---|---|
| Functional | `A†` | Only externally observed behavior under a declared protocol. Nothing about internal organisation. |
| Bridge | `H_{N,I}` | The relationship between `A†` and an external, pre-existing consciousness-science protocol `A*`, relative to one functional instance `I`. |
| Physical | `P[C]` | Physical/implementational constraints (locality, capacity, closure). Nothing about consciousness. |

Each layer is sealed on its own schedule (§12), and revising one never automatically reopens
another — in particular, revising the physical layer never reopens `A†`. This document
(folder 13) is entirely about the functional layer; the bridge layer (§9) and physical layer
(§10) are described only insofar as they explain why the functional layer is shaped the way
it is.

## 2. SPEC versus INSTANCE

A†-SPEC insists on a hard split between two kinds of object, and is explicit that the SPEC
alone is not a runnable instrument (§0.4, §11.3):

- **SPEC** — frozen once, by this document: the eleven clause definitions, the six
  well-formedness criteria (W1–W6), how scores are typed, the PASS/FAIL/UNQUALIFIED/
  NA_interface/INVALID verdict vocabulary, the calibration formula, the sizing rule, the
  core ladder and the four certificates, the interpretation prohibitions, the conformance
  suite, two fixed constants (`ε_null = 0.10`, `σ_max = 0.20`), and — critically — the
  **normative estimators and inferential procedures** (the unbiased divergence estimator
  `D̂_2`, the still-unfixed predictive-advantage estimator `Ĵ`, the intersection-union
  verdict rule, and which interval-construction method applies to which primitive). All of
  this must be published and hashed together, once, as a single reference implementation.
- **INSTANCE** `I` — frozen separately before *each* campaign: the concrete delay `k`, the
  battery `q`, the cue families, distractors, interval parameters, probe families, handles,
  which family of score function is used (forced-choice, symbolic, graded, distributional),
  the concrete datasets that calibrate, qualify and score each component, and the execution
  parameters (resampling unit, repetition counts, seeds).

The SPEC is freezable with no instance yet decided — that is exactly the state A†-SPEC is
in now: frozen (pending §12 sealing) with zero instances ever declared. A†-SPEC further
distinguishes a canonical reference instance, `A†-REF1` (§11.3), from ordinary
"A†-compatible experimental instances": only two laboratories both running REF1 are
guaranteed to be running the same instrument without a separate linking procedure. REF1 does
not yet exist either.

## 3. "Thresholds are metrological, not ontological" (§0.5)

This is stated as the rule governing the reading of every future result under this
specification. A rung or a certificate is a **detectability boundary of this particular
battery**, not a boundary between "has access" and "has no access":

    A†_j = 0   does NOT mean   A* = 0

A system can fall below the instrument's floor while still possessing access under any
underlying theory, including a continuous one — the SPEC takes no position on that theory
and explicitly refuses to let its own instrumental floor be read as an ontological claim.
Conclusions from `A†` are comparative (a system placed relative to declared reference
systems on a common battery), never absolute. Ontological hypotheses such as `H_CO^+` (§9.6)
live in the bridge layer and are not themselves measurements.

## 4. Instance-relativity and the cross-instance-comparison ban (§0.6)

There is no single, unique `A†_0`. Sensitivity depends on everything an instance decides —
delay, battery, score functions, cue family, distractor, interval parameters, controls,
sizing, bootstrap parameters — so every reported value carries its instance identifier `I`
explicitly: `A†_{j,I}(S)`, `Cert_X,I(S)`.

The consequence the SPEC draws from this is strict: **comparing two rungs or two
certificates obtained under two different, unlinked instances is not licensed.** Statements
like "system X reaches rung 2, system Y only rung 1" are not permitted across instances
unless a pre-registered linking procedure — itself an instance-level object, minimally a set
of systems measured under both instances with their profiles reported — has established that
the two instances are equivalent. The "common battery" of §0.5 means within one instance, or
across instances that have actually been linked; it is never assumed by default.

## 5. What A† explicitly is not (§0.2)

The SPEC lists, by name, five things a result under it may never be read as:

- **Not a measure of consciousness.** The phrase "level of consciousness" is banned from
  every derived document; `j*_core,I` is only a rung of functional capability under a
  declared protocol.
- **Not a measure of organisation.** No clause may mention Γ, Δ, R, Λ, B, T, U, Addr,
  integration, irreducibility, recurrence, or multi-role propagation — this is the property
  that makes A† usable as a non-circular instrument for the bridge test (see the root
  README of this folder).
- **Not a measure of memory quality or architecture type.**
- **Not a measure of acquired knowledge** — W3 (episodic novelty) explicitly excludes
  parameter-stored dispositions from counting as a pass.
- **Not a discriminator of architecture classes** — this is the specific claim §0.7's
  wrapper test exists to police, described next.

## 6. What A† cannot separate: the wrapper test (§0.7)

The SPEC states its own limit rather than leaving it to be discovered: **if a purely
external loop wrapped around an unchanged model — adding no parameter and no internal
pathway — can pass a clause, then that clause is scoring the loop, not the model.** Several
natural candidate discriminators are checked against this test and fail it: a memory or
budget constraint fails it (and additionally measures the physical layer, not the functional
one); timed emission fails it (a scheduler can produce it); maintaining a commitment fails it
(a loop can resolve it once internally, hold the result, and re-supply it).

The observational statement the SPEC does assert, and only this one: if two realisations
produce the same observable interventional kernel under the declared boundary, `A†` cannot
distinguish them — and where an external loop placed inside the system's boundary reproduces
that kernel, whatever clause it passes attributes nothing to the model underneath. A stronger
claim — that *any* function realised by internal recurrence can always be realised by an
external loop — is deliberately not asserted; latency, bandwidth, observability and compute
constraints might block that in practice, and the weaker observational statement is all W1
requires.

What follows from this, stated as the SPEC's own licensed/not-licensed pair:

```
A† discriminates SYSTEMS AS DEPLOYED.      licensed
A† discriminates ARCHITECTURE CLASSES.     not licensed
```

Separating architectures is left to the bridge layer or the physical layer, by controlled
intervention — never to this battery. Practically, this is why every A†-SPEC result must
carry its full deployment envelope `E_S` (§2.3) alongside the model identifier: a result is
about the pair `(model, E_S)`, and two envelopes wrapped around the same model are, by
design, two different measured systems that may receive different verdicts — this is treated
as correct, not as a defect to be engineered away.
