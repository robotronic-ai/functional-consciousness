# Functional-consciousness project — clean campaign archive

This is a reviewer-facing, English-only repackaging of the project's research campaigns. It
supersedes the six-folder layout previously on the public repository (folders 01–06 below are
carried over unchanged in substance, only re-audited for this edition) and adds seven campaigns
completed or drafted since: the Λ addressing-sufficiency theory and its empirical test (08–09), a
scaling/certification line for Γ (07), three independently-authored protocol extensions (10–12),
and the strictly-behavioral access-capability specification A†-SPEC (13).

**Update note (differential).** This revision adds two folders: `14-four-family-closure-and-compression-limit/`
and `15-causal-construct-validity-protocol/`, plus their README entries below. Folders 01–13 are
unchanged from the previous edition of this archive and are not re-described below beyond their
existing index rows.

Each numbered folder is a **clean edition**, not a literal translation of the frozen internal
record. Frozen, hashed protocol files are never retyped — translating a hashed document would
change its hash and break the project's own pre-registration story. Instead, every `README.md`
and every file under `docs/` is freshly written in English to describe, accurately, what a
protocol did and what it found. Scripts under `scripts/` are the final canonical harnesses only,
carried over with comments translated where needed and logic untouched. Data under `results/`
(or `data/`) is copied as-is. Superseded drafts, abandoned diagnostics, and other trial-and-error
residue are left out — but a genuinely found-and-fixed defect is never hidden: where a campaign
hit a real bug or had to correct a definition, that history is kept and narrated (see e.g.
`06-transformer-measurement/results/STATUS.json`'s `archived_defects`, or `08`'s and `04`'s
adjudication notes).

No `*_PRIVATE.json` file (a private scoring oracle) appears anywhere in this archive. Their
absence is what makes candidate-fixed holdout verification meaningful to a reader re-running a
campaign's generator: the private oracle stays private, the generator and harness are public.

## Reproduction discipline

Every campaign in this archive follows the same discipline. A protocol is written and hashed
before any candidate is coded against it. A generator produces fixtures from the frozen protocol.
A private oracle (never published) records the expected verdict for each fixture. A candidate is
written and its hash is recorded before it is scored. Where a result claims a **candidate-fixed
holdout**, a second, independent fixture set is generated *after* the candidate's hash is frozen,
and the same unmodified candidate is re-run against it — the strong form of reproducibility used
here, since nothing about the candidate can adapt to the second set.

Verdicts use a fixed vocabulary and are never silently strengthened:

| Verdict | Meaning |
|---|---|
| **V1 / POINT** | A unique value is identified. |
| **V3 / PARTIAL** | Several values remain compatible with the observations; reported as a set, not collapsed to one. |
| **V4 / NA** | The available intervention algebra is insufficient to certify either way. |

A `V3` or `V4` verdict is never silently turned into a `V1` number in any document in this
archive.

## Campaign index

| # | Folder | Manuscript link | Status |
|---|---|---|---|
| 01 | `01-persistent-active-factorization` | §8.2–§8.3 | Closed: exact preregistered collision witness, not a working general extractor — the campaign's own conclusion. |
| 02 | `02-gauge-transport-identification` | §8.4 area (gauge/fiber transport) | Closed: exact gauge-ambiguity and transport-closure characterization. |
| 03 | `03-canonical-boundary-closure` | Boundary/ρ-certification | Closed: theorem + certification + composition results. |
| 04 | `04-gamma-delta-characterization` | §7.1–§7.2, §16.6, §18 | Γ conditionally axiom-characterized (needs one additional explicit axiom); Δ exactly decomposed; Γ/Δ independence witnessed; prospective + candidate-fixed-holdout validation both 32/32. |
| 05 | `05-keff-r-normalization` | K_eff / R | Closed: definition, invariance and normalization theorem, finite audit. Analytic only, no scripts needed. |
| 06 | `06-transformer-measurement` | Transformer re-entry measurement | Closed, with two archived-and-fixed defects documented rather than hidden. |
| 07 | `07-gamma-scaling-and-certification` | §7.1 scaling / certification | Mixed — see below. |
| 08 | `08-lambda-addressing-theory` | §17.5 "Pont d'adressage", §7.3 | Closed constructive theory: 7 theorems, 4 exact finite witness domains, all PASS. Status `STABILIZED-CONSTRUCTIVE-THEORY`. |
| 09 | `09-lambda-addressing-empirical` | §17.5, §7.3 | Screening protocol executed on a real model across 3 stages (up to ~1.26M state pairs); **zero candidate fibers found**, so Λ itself was never opened for scoring. Universal Λ-necessity remains **OPEN**, not settled either way. |
| 10 | `10-continuous-predictive-geometry` | Predictive-state theory, continuous extension | Pure math + exact finite/closed-form verification only. **Not yet applied to any trained model.** |
| 11 | `11-rmt-prospective-physical-cut` | §17.6-adjacent prospective validation | Protocol and analysis engine complete and self-tested; **`NOT_EXECUTED_REAL_MODEL`** — no result yet from the manuscript's actual target model. |
| 12 | `12-readout-relative-minimal-predictive` | Predictive realization theory | Theoretical derivation + exhaustive finite verification (13,538 cases, 0 failures). Stochastic/continuous extensions explicitly `OPEN`. No trained model involved. |
| 13 | `13-a-dagger-spec-behavioral-protocol` | Independent instrument for a future H_org bridge test | Frozen, hashed, **`NOT SEALED`** spec (v0.24, 11 behavioral clauses). By design never references Γ/Δ/R/Λ/B/T/U/Addr, so it can eventually decircularize the organizational-necessity bridge test. **Never run against any system.** Its only adjudication instrument (the W1–W6 grid) is stale — built for an older 5-clause v0.11 draft, itself never adjudicated, and covers none of the 6 clauses added since. |
| 14 | `14-four-family-closure-and-compression-limit` | H_CO⁺ localization argument; §18/Annexe A caution on c_O | Compression Limit Theorem: **proved**, self-contained. Four-family axis-completeness (Ψ=(𝒮,𝒢,𝒞,𝒪), no 5th/6th family): **reported from a separate conversational record, not independently re-verified with frozen artifacts in this edition**. Claim Ladder L0–L6: notation adapted from folder 15's executed witnesses; L3/L4 currently **not established / refuted** for the compact profile. |
| 15 | `15-causal-construct-validity-protocol` | H_CO⁺, §17.6/17.7 (H_C†,I, PCI_T) | Organizational-closure repair chain (typed-binding → joint-synergy → static sufficiency): **executed**, exact witnesses and an exact conditional sufficiency theorem for static access consequences; temporal consequences explicitly open. Functional-access necessity bridge (Breadth/Temporal/Unity ⟹ Δ,R,Γ>0): **executed** on frozen fixtures, necessity only, not sufficiency. FCI-3 causal construct validity protocol: **frozen design, never executed against real architecture pairs.** Intervention-identification safeguards: adjudicator logic validated on synthetic cases only. |

## Reading this archive honestly

Three campaigns in this edition (10, 11, and the target-transformer sub-bundle of 07) are
**designs and tooling that have not yet been run against a real trained model**, one empirical
campaign (09) ran fully but returned a **negative screening result**, not a confirmation, and
one specification (13) is frozen text with **no adjudication and no executed instance at all**.
Folder 14 mixes one fully proved, self-contained theorem (the Compression Limit Theorem) with one
narrative campaign summary explicitly flagged as **unverified in this archive edition** (the
four-family axis-completeness argument) — readers should not treat the two as having the same
evidentiary status. Folder 15 is the most execution-heavy of the new folders — its repair chain,
necessity bridge, and identification-adjudicator validation are all run on frozen fixtures with
real result files — but its centerpiece forward-looking protocol (FCI-3) is, like folders 10, 11,
and 13, a frozen design that has **never been run against a real architecture pair**.
This is stated plainly inside each folder and repeated here because it matters for how the whole
archive should be read by a skeptical reviewer: this is not a claim that every listed campaign is
a finished, executed result. Folders 01–06, 08, and most of 07 and 12 are closed, executed, and
verified (several via candidate-fixed holdout). Folders 10 and 11, and the target-transformer half
of 07, are validated instruments and preregistered protocols waiting on a real-model run. Folder
13 is one level earlier still: a well-formedness self-check (W1–W6) has been designed but never
completed even once, against any version of the spec. Folder 14's axis-completeness document and
folder 15's FCI-3 protocol sit in that same "not yet independently executed in this archive"
category, each explicitly labeled as such. None of this is a gap being concealed — it is the
honest, current state of each work stream.

## Suggested reading order

1. `04-gamma-delta-characterization` and `05-keff-r-normalization` — the core Γ/Δ/R axis results.
2. `07-gamma-scaling-and-certification` — what changes, and what doesn't yet, at larger scale.
3. `08-lambda-addressing-theory` then `09-lambda-addressing-empirical` — the Λ addressing-sufficiency theory and its (negative) empirical screen.
4. `01`–`03` and `06` — the supporting factorization, gauge-transport, boundary-closure and transformer-measurement results.
5. `10`–`12` — the three protocol extensions, all instrument-complete, not yet run on a real model.
6. `13-a-dagger-spec-behavioral-protocol` — the future non-circular access instrument: frozen text only, not yet adjudicated or run.
7. `14-four-family-closure-and-compression-limit` — why axis-completeness alone does not certify the compact profile: read the Compression Limit Theorem first, the axis-completeness narrative and Claim Ladder second.
8. `15-causal-construct-validity-protocol` — the executed adversarial repair chain and necessity bridge behind folder 14's L3/L4 verdicts, followed by the identification safeguards and the not-yet-executed FCI-3 protocol that would advance L5.
