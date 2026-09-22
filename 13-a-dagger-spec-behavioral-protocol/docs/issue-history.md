# Issue history: three resolved ambiguities from grid/SPEC co-development

Source: §4 ("Issue history") of `A_DAGGER_W1_W6_VERIFICATION_GRID_v0.4.md`. The grid
document states its own reason for keeping this history rather than deleting it once the
issues were fixed: "Withholding a known defect in order to preserve the adjudicator's
independence would be perverse. Independence means the adjudicator must redo the reasoning,
not that the history is hidden." This archive keeps the same discipline (see the root
README's "never hide a found defect" statement) and restates the three recorded issues here,
in its own words, as a demonstration of that rigor — not because they still affect the
current v0.24 text (they were fixed several SPEC versions ago), but because the process that
found and fixed them is itself evidence worth preserving.

All three issues were found while building or reviewing the grid against early SPEC drafts
(v0.8–v0.10), and all three were resolved in the SPEC text itself, one version at a time.

## I-1 — SUBST admitted two incompatible readings (resolved in SPEC v0.9)

While building grid v0.1 against SPEC v0.8, the reviewers found that SUBST's clause text
supported two genuinely different experimental designs at once. One reading described a
purely behavioral, presentation-level intervention — present a different piece of content
than would otherwise have been shown, and see whether the later response tracks it. This
reading is runnable on a non-verbal organism and satisfies the tabulation-invariance
criterion (W1). The other reading, which the clause text itself cited as its "reference
design," described an internal-state intervention — reaching inside the system's memory
representation and swapping one stored component for another. This second reading fails W1
outright (two systems with identical external behavior need not have any internal component
to swap) and fails W2 as well (it presupposes an addressable internal state, which nothing
guarantees a non-verbal organism has).

Two readings of the same clause text meant the same observed system could receive two
different, individually defensible verdicts — precisely the kind of defect the SPEC's own
§13 reopening rule treats as blocking. A third reading surfaced during the first attempt at a
fix and was caught in review: a within-trial version in which content is presented and then
*replaced* mid-trial, which violates W4 by re-injecting information about the content after
initial presentation.

**The fix.** SPEC v0.9 settled SUBST as a purely between-arm design: two matched trial arms,
assigned at random before the trial begins, differing only in which content is initially
presented; nothing is swapped or replaced once a trial is underway; both contents must
independently satisfy the episodic-freshness requirement (W3). The internal-state reading was
demoted to an architecture-specific enrichment that may be reported alongside the main result
but never enters the clause's score or any rung verdict.

## I-2 — SUBST's null statistic had the wrong polarity (resolved in SPEC v0.10)

Found on review of SPEC v0.9 — and notably, this particular defect was *not* caught by the
grid itself, which the grid document records candidly as a finding in its own right about the
grid's limits.

The general normalization formula used throughout the SPEC (`a_i = (T_i − T_i^null)/(1 −
T_i^null)`, clipped to `[0,1]`) requires the null statistic to behave like a *floor*: a value
a fully incompetent or insensitive system would score near. But v0.9's SUBST used "sham"
control arms — trials differing from their matched arm only in some deliberately
task-irrelevant feature — as that null. A competent system is *expected* to score well on a
sham arm precisely because the sham manipulation shouldn't matter to it, so a well-performing
system would drive both its target score and its "null" score toward the same high value,
producing an uninterpretable division (effectively 0/0) or spuriously tripping the
SPEC's separate invalid-instance safeguard. Every other clause in the SPEC used a genuine
floor null (manipulation absent, or chance-level performance); SUBST, using a ceiling-like
sham instead, was the mismatched case.

**The fix.** SPEC v0.10 replaced the sham-based null with a cross-target scoring null: the
same collected responses, rescored against the *other* arm's target content rather than
their own. This produces the correct floor behavior — a content-insensitive or chance-level
system scores equally against either target, giving `a_subst ≈ 0`, while a genuinely
content-tracking system scores near its own arm's target and near zero against the other's.
The sham arms were kept, but demoted to an auxiliary specificity control that is reported
separately and never enters the clause's actual score. This fix also motivated a new
cross-cutting check, X7 (the null insensitivity criterion), added to the grid specifically to
test null validity across every clause going forward.

## I-3 — the null's meaning was being described in clause-specific-incompatible terms (resolved in SPEC v0.11)

Found on review of SPEC v0.10, and in the course of finding it, the reviewers discovered that
this same imprecision had been silently baked into the grid document as well — so fixing it
corrected both documents together.

Two related problems survived the I-2 fix. First, the SPEC's general definition of the null
statistic still described it as measured "under the clause's null condition" and its
invalid-instance safeguard still described the failure mode as a task being "solvable without
presentation" — language that fits DELAYED-USE-style clauses but does not fit SUBST at all,
whose null is a counterfactual rescoring of the same responses rather than a distinct
experimental condition; for SUBST, a null statistic approaching its ceiling means something
different (insufficient separation between the two targets), not "solvable without
presentation." Second, the SPEC had claimed that its `ε_null` ceiling constant "enforces" a
separate SUBST-specific admissibility condition (that the two arms' targets be distinguishable
under the scoring function). On inspection this claim was simply false: the admissibility
condition is a property of the experimental design, checkable before any system is ever run,
while the ceiling is a statistic computed from a system's actual responses — a system that
responds far from both targets could produce a passing (low) null statistic even under a
badly under-separated design, so the ceiling does not actually catch that design defect in
general.

**The fix.** SPEC v0.11 redefined the null statistic by its functional role (the value an
insensitive system is expected to produce) rather than by its experimental form, restated the
invalid-instance ceiling with clause-specific readings of what a ceiling violation actually
means kept separate from each other, and withdrew the incorrect "enforces" claim entirely.
Because the grid's own X7 check (added after I-2) had been written assuming the null must
behave strictly as a floor — which is wrong specifically for SUBST, whose insensitive-system
value sits at chance, not at zero — the grid itself needed a corresponding correction, and X7
was restated in terms of the insensitivity criterion that actually unifies all five clauses'
nulls, rather than in terms of a floor value that only fits most of them.

## What this history demonstrates

All three issues were caught by adversarial re-reading rather than by any automated check,
and all three were disclosed, dated, and tied to the exact SPEC version that fixed them,
rather than silently smoothed over in later drafts. That is the standard this archive expects
of every campaign: a defect, once found, is recorded with its resolution, not deleted from
the record. It is also, however, a limited kind of evidence: it demonstrates textual and
logical rigor during drafting, not empirical validation of the instrument. None of the three
issues concerned an executed measurement, because none has ever been executed — see the root
README and `w1-w6-verification-grid.md` for the current, still-unadjudicated state of the
grid this history is drawn from.
