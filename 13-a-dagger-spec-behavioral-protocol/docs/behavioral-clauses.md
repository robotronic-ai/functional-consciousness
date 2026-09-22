# The eleven behavioral clauses

Source: `A_DAGGER_SPEC_v0.24_DRAFT.md`, §3–§4. Each clause below is restated at the level a
reviewer needs to follow what is tested and why; the full mathematics (target/null
statistics, admissibility conditions, calibration) lives in the frozen source document, not
here.

Every clause states, by construction, what it does **not** claim about internal mechanism —
this is a structural requirement of the SPEC (§1), not a stylistic habit: identifiers that
sound like they name an internal operation (CONTROL, HARD-ERASURE, SELECTIVE-ERASURE,
TEMPORAL-AUTONOMY, ELAPSED-TIME-CONTROL, SOURCE-BINDING, CAUSAL-OWNERSHIP) are only permitted
to keep their name if they carry an explicit non-claim line, checked mechanically as part of
the X2 cross-cutting rule (see `w1-w6-verification-grid.md`).

## How the eleven clauses compose

**Core ladder** — cumulative, three rungs, each a superset of the one below:

```
A†_0 = { DELAYED-USE, SUBST }
A†_1 = A†_0 + { INTERFERENCE }
A†_2 = A†_1 + { POSTCUE-MULTI-USE, CONTROL }
```

A system's core rung `j*_core` is the highest rung it clears; if it does not even clear
`A†_0` the result is not silently reported as "0" but as a distinct symbol `⊥` ("did not
clear the detection floor"), kept apart from BLOCKED (undetermined) and INVALID (protocol
defect).

**Four independent capability certificates** — not additional rungs, not ordered relative to
each other or to the core ladder, and not compressible into any single scalar:

```
Cert_T = { TEMPORAL-AUTONOMY, ELAPSED-TIME-CONTROL }
Cert_E = { HARD-ERASURE, SELECTIVE-ERASURE }
Cert_B = { SOURCE-BINDING }
Cert_A = { CAUSAL-OWNERSHIP }
```

The SPEC is explicit that a system can pass `Cert_E` and fail `Cert_T`, or vice versa, and
that this is a valid, uninteresting-to-flag capability profile rather than an anomaly
requiring explanation — the whole reason for reporting four separate certificates instead of
a cumulative ladder above `A†_2` is that nothing justifies conditioning one capability's
result on another's.

## The five core-ladder clauses

**DELAYED-USE.** After content `z_e` is presented and withdrawn, does a demand issued later
(`t+k`) get a response that actually depends on `z_e`, with nothing about `z_e` re-entering
the system from outside after withdrawal? This is the floor test: does the episode have any
later behavioral effect at all. Its null is simply the same demand with no presentation of
`z_e` in the first place.

**SUBST.** Two matched trial arms are set up in advance, one presenting content `z_e`, the
other a different content `z'_e`, both freshly drawn under the same procedure. After the same
withdrawal and delay, does the later response track *which* content was actually presented?
Where DELAYED-USE asks "did presentation matter at all," SUBST asks the sharper question:
"does the *identity* of what was presented determine the identity of the response." Nothing
is swapped mid-trial — the two arms are assigned once, at the start, so a system cannot pass
by any mechanism that merely detects a later within-trial substitution.

**INTERFERENCE.** Does DELAYED-USE still hold when the delay interval is filled with a
distractor — content unrelated to `z_e`, generated blind to it? Critically, the clause
requires the instance to first *demonstrate*, on an independent measure, that the tested
system actually processed the distractor before crediting a pass; otherwise a system that
never engaged with the distractor at all would trivially pass a clause meant to test
retention *under* interference.

**POSTCUE-MULTI-USE.** Content is presented and withdrawn; only afterwards is the system told
which of several possible demands (`L₁ … Lₙ`) it must answer, drawn blind to the content
itself. This tests whether a system can hold content usably enough that it can still be
asked one of several unforeseen-at-encoding questions about it — though the SPEC is explicit
that a system which simply pre-computes all `n` answers at presentation time and discards
everything else legitimately passes; the clause demonstrates prepared multi-use, not
open-ended flexible recall, and must not be described as the latter.

**CONTROL.** An INHIBIT instruction suppresses the content-dependent response at a given
moment; a later QUERY on the *same* episode recovers a correct response anyway. This is a
composite of two required halves — suppression and recovery — scored on the same episodes, so
that a system must demonstrate both controlled non-expression and later usability, not either
one alone. Its null is deliberately not "no demand at all" (which a competent system could
fail for reasons unrelated to control) but the same demand, at the same occasion, with the
INHIBIT signal simply absent.

## The six higher-capability clauses (the four certificates)

**TEMPORAL-AUTONOMY** (`Cert_T`). Two silent intervals of randomized, distinguishable
duration are marked only by boundary events — no timestamp, heartbeat, or other
time-correlated signal crosses the system boundary during them. Afterwards, the system must
say which interval was longer. This tests behavioral sensitivity to elapsed real time with no
exogenous temporal information supplied — explicitly not a claim that the system contains a
clock or oscillator, only that its behavior tracks elapsed duration. The SPEC is candid that
a loop holding a wall-clock reading in the deployment envelope can pass this clause without
the underlying model contributing anything — which is exactly the wrapper-test situation
(`docs/spec-structure-and-layers.md`), and why deployment-envelope disclosure is mandatory
for this clause specifically.

**ELAPSED-TIME-CONTROL** (`Cert_T`). The system is given a binding (an action and a deadline)
at trial entry; after a randomized silent interval, a QUERY *restates that same binding* and
asks the system to emit the action if the deadline has passed, or withhold it if not. Because
the binding is handed back at query time, this clause isolates timing specifically from
retention — a system that merely forgot the binding is not the failure mode being probed
here, DELAYED-USE and SUBST already cover that. It is deliberately runnable on a plain
stateless request/response endpoint with no persistent session required.

**HARD-ERASURE** (`Cert_E`). A four-arm design (CLEAN / PLACEBO / POISON / ERASE) tests
whether a REVOKE instruction genuinely removes a freshly-bound content's later influence,
rather than merely producing a system that *says* it has forgotten while remaining
behaviorally influenced. The clause combines two independently-calibrated sub-tests: a
marginal-distribution similarity test (does the erased arm's overall response distribution
resemble the no-content-ever-presented reference arm?) and a held-out predictive test (can a
classifier still recover the erased content from the response, beyond what an uninformed
baseline could?). Both are required, because the marginal test alone can be fooled by a
system whose *per-episode* behavior remains fully determined by the erased content even while
its *aggregate* response distribution looks unchanged — a documented, worked counter-example
in the source SPEC.

**SELECTIVE-ERASURE** (`Cert_E`). An episode carries three or more independent fresh
bindings; a pre-registered subset is revoked after encoding. The clause requires *both* that
the revoked bindings lose causal influence *and* that the non-revoked bindings retain it — a
system that simply forgets everything on any REVOKE signal must not pass, since that would
trivially "solve" erasure by erasing indiscriminately.

**SOURCE-BINDING** (`Cert_B`). Content is presented through one of (by default) two
distinguishable channels, and the system must later answer correctly in both directions —
given the content, which source did it come from, and given the source, what content did it
carry. Both directions are required because either alone is separately gameable (a tag riding
with the content passes the first; recency or position passes the second); requiring both is
what makes the clause a genuine test of the *binding* between source and content rather than
of either fact in isolation. This is explicitly not a test of self/other distinction — that
is CAUSAL-OWNERSHIP.

**CAUSAL-OWNERSHIP** (`Cert_A`). The system acts inside an environment whose outcomes are
generated by a pre-registered structural causal model in which exogenous events can imitate
the observable consequences of the system's own actions. Across randomized interventions, the
system must learn which transitions it actually controls and then apply that knowledge on
held-out transfer trials. The null condition is not a simple outcome-matched control but a
full replay of the system's own previously-observed interaction stream, made causally
independent of its current actions — this closes the gap left by a weaker null, under which a
system could score above chance merely by detecting non-causal statistical patterns rather
than by actually distinguishing "I observed this" from "my action controls this."
