# V21.4 AXIS OPTIONS — REFERENCE FOR STAGE 2 POINT-VALUE DESIGN

Every possible closed-vocabulary option for all 13 Stage 1 axes, pulled directly from `VAE_v21_4_engine.md`. This is reference material for *you* to design Stage 2's scoring against — the model itself never sees or computes a number (that separation is a settled foundation of this project, not open for revision here).

Three structural facts matter before assigning points, so they're stated once here rather than repeated 13 times below:

1. **Floor-veto axes vs. plain ladders.** On Axes 1, 2, 3, 4, 8 and 10, the *first listed row* is a genuine failure/negative condition, distinct from the **bolded** row that follows it (the "ordinary" starting position, per Rule R2). The model checks the floor first and only climbs the ladder once the floor doesn't hold. This suggests the point-gap from floor to ordinary may reasonably be larger, or categorically different, from the gaps between higher rungs — that's your call, but treat the floor as qualitatively distinct from "the next rung down," not just the next integer.
2. **Gate values are not low scores.** `NOT_ESTABLISHED` (evidence didn't resolve) and `NOT_PRESENT` (the feature genuinely doesn't apply — e.g. no repeated unit, no chance event) are not the same thing as a poor result, and they are not each other. A sheet with no residue at all is not weaker than one with residue that failed to integrate; a sheet where evidence was genuinely ambiguous is not the same as one that was examined and found wanting. Recommend excluding both from whatever aggregate you build, or handling them as an explicit "not scored on this axis" state — not folding either into the numeric scale, and not defaulting either to the floor or the ordinary value.
3. **Not every axis produces one value per painting.** Axis 11 produces one verdict *per tested element* (an array) — you'll need your own rule for turning that into a single per-painting contribution (worst element governs? average? something else?). Axis 12 is already reduced to one value per painting at the Stage 1 level (the most extensive/bounded tested event governs, per Block 5.2); the others tested are noted at 7.3 for your reference but don't feed Axis 12 itself.
4. **v21.3 adds R11:** no axis may record its highest listed value at `LOW` confidence — if the evidence is that uncertain, the record settles one rung down. This doesn't replace axis-specific tightening (see the calibration notes below on Axes 1, 2, 8, 11) but it closes off ceiling claims that were only ever weakly grounded to begin with.
5. **Your calibration anchor, for when you design the actual point values (not encoded anywhere the model sees):** competent, error-free execution — the *ordinary* (bolded, second) rung on a ladder axis — should land around the middle of whatever scale you use, not near the bottom. The top rung of each ladder is meant to be rare enough that most of your current body of work shouldn't reach it at all. That's a Stage 2 design decision, not a Stage 1 one — nothing about it belongs in the engine or schema.

---

## AXIS 1 — SUBSTRATE INTEGRITY
Single value. Evidence: 4.2, 4.3, `analysis`/`crop`.

| Value | Condition |
|---|---|
| `BREACHED` *(floor)* | Deposit lost its shape entirely, or migration ran past any boundary the mark could have had |
| `SOUND` *(ordinary)* | No breach; demand LIGHT |
| `SOUND_UNDER_DEMAND` | No breach; demand MODERATE |
| `SOUND_UNDER_HEAVY_DEMAND` | No breach; demand HEAVY |
| `HELD_AT_CHARACTERISTIC_FAILURE` *(tightened v21.3)* | `SOUND_UNDER_HEAVY_DEMAND` + a named cell shows the failure mechanism actively underway and stopping short |

**Calibration note:** hit ceiling in 3/3 test runs under the v21.2 wording ("heavy demand, nothing broke"). Tightened to require a specific, locatable near-miss rather than generic unincident heavy work.

## AXIS 2 — BOUNDARY MORPHOLOGY
Single value. Evidence: 2.1, 4.4. `NOT_ESTABLISHED` if fewer than 3 segments locatable.

| Value | Condition |
|---|---|
| `CONTROL_LOST` *(floor)* | A below-family segment that fails the junction test |
| `AT_SUBSTRATE` *(ordinary)* | Every segment at family position |
| `ABOVE_SUBSTRATE` | ≥1 departure, not all at a junction |
| `PLACED` | ≥1 departure, all at a junction |
| `SUSTAINED` *(tightened v21.3)* | `PLACED`, held across a run reaching both the first and last third of the long axis (was: any 2+ cell run) |
| *(gate)* `NOT_ESTABLISHED` | — |

**Calibration note:** hit ceiling in 2/3 test runs under the old 2-cell bar. Now aligned to the same long-axis-span standard Axes 3/4 already use, which correctly held as a hard ceiling in those tests.

## AXIS 3 — MARK INTEGRITY
Single value. Evidence: 2.2 only. `NOT_ESTABLISHED` if fewer than 3 elements have locatable limits.

| Value | Condition |
|---|---|
| `BREAKS_DOWN` *(floor)* | >1 element shows limit NO / interior CLOSED_TO_UNIFORM or HOLLOW / retracing PRESENT / bloom ASYMMETRIC_TRACKING |
| `HOLDS` *(ordinary)* | At most one element shows any of those |
| `HOLDS_AGAINST_SPREAD` | `HOLDS`, plus a limit held against the family's migration |
| `HOLDS_ACROSS_SCALE` | `HOLDS_AGAINST_SPREAD`, smallest and largest elements both hold |
| `HOLDS_AT_EXTENT` | `HOLDS_ACROSS_SCALE`, density+limit held across a run spanning both outer thirds |
| *(gate)* `NOT_ESTABLISHED` | — |

## AXIS 4 — KINEMATIC INDEX
Single value. Evidence: 2.3, 2.4. `NOT_ESTABLISHED` if no element has a traceable path.

| Value | Condition |
|---|---|
| `PHASE_FAILURE` *(floor)* | Any element shows a named failure in an observable phase |
| `PHASES_SOUND` *(ordinary)* | Every observable phase sound |
| `MODULATED` | `PHASES_SOUND` + continuous width/density variation with pressure or direction change |
| `MODULATED_THROUGH_DEPLETION` | `MODULATED` + modulation carried through a dry passage, depletion RESOLVED |
| `RESOLVED_AT_SCALE` | `MODULATED_THROUGH_DEPLETION` + one element resolves entry-through-terminal across both outer thirds |
| *(gate)* `NOT_ESTABLISHED` | — |

## AXIS 5 — VISUAL CADENCE
Single value. Evidence: 2.5. No floor — `NOT_PRESENT` is a neutral absence, not a failure.

| Value | Condition |
|---|---|
| *(gate)* `NOT_PRESENT` | No repeated unit |
| `UNIFORM` *(ordinary)* | Interval, tone, width constant |
| `VARIED` | One of those changes describably |
| `GOVERNED` | `VARIED` + the change tracks a change elsewhere on the sheet |

## AXIS 6 — TONAL ARCHITECTURE
Single value. Evidence: 3.1, 3.2. No gate value defined.

| Value | Condition |
|---|---|
| `SINGLE_BAND` | No cell mixes ink bands internally (see engine note: doesn't by itself mean the sheet is tonally flat) |
| `SEPARATED` *(ordinary)* | ≥1 cell holds 2+ bands |
| `DISTRIBUTED` | `SEPARATED` + the bands sit in non-adjacent cells |
| `STRUCTURED` | `DISTRIBUTED` + forward/back reading follows the bands |
| `TONE_CARRIES` | `STRUCTURED` + a spatial relationship rests on tone alone |

**Flag for the next axis-rebuild pass, not fixed here:** this ladder has a known gap — two single-banded cells in different bands still register as `SINGLE_BAND`, even though tone clearly varies across the sheet. A genuine cross-cell tonal-range dimension is missing and should be checked against the axis-research documents before being added, not patched ad hoc.

## AXIS 7 — FIGURE-GROUND TENSION
Single value. Evidence: 3.3. `NOT_PRESENT` if no unpainted area is locatable (neutral, not a failure).

| Value | Condition |
|---|---|
| *(gate)* `NOT_PRESENT` | No locatable unpainted shape |
| `GROUND_SHAPED` *(ordinary)* | Findable-limit unpainted shape exists |
| `GROUND_HELD` | Bounded by ink on >1 side |
| `GROUND_STRUCTURAL` | Shares limits with an element, neither reading as leftover |
| `GROUND_INTERLOCKS` | `GROUND_STRUCTURAL` at ≥2 named junctions **that aren't one boundary sampled twice** *(tightened v21.4)* |

**Calibration note:** hit in 2/4 runs, one at LOW confidence (now blocked by R11 regardless), one where the model's own decision note admitted the two "junctions" were points along a single continuous shared boundary. Now requires a named cell, between the junctions, where the sharing actually breaks.

## AXIS 8 — EQUILIBRIUM
Single value. Evidence: 3.6 + `mass_displacement`. No gate value defined.

| Value | Condition |
|---|---|
| `UNACCOUNTED` *(floor)* | Nothing answers the mass |
| `ACCOUNTED` *(ordinary)* | ≥1 thing answers it |
| `ACCOUNTED_ASYMMETRICALLY` | What answers differs in extent, band or kind from the mass |
| `ACCOUNTED_ACROSS_FIELD` | Every declared cell stands in a locatable relation to the mass |
| `WEIGHT_ORGANISES` | `ACCOUNTED_ACROSS_FIELD` + every element's position is accountable to it |

**Calibration note:** `ACCOUNTED_ACROSS_FIELD` hit in 3/3 test runs — the "answering" definition (added last release) let any cell that was merely a different *kind* of thing (ground vs. ink) count, which is true of almost every non-mass cell. v21.3 requires a stated positional role (opposite, flanking, bridging) in addition to the categorical difference, not instead of it.

## AXIS 9 — FIELD EXTENT
Single value. Evidence: 5.1, 3.5, 1.2. `NOT_ESTABLISHED` if the sheet has no element (residue only).

| Value | Condition |
|---|---|
| `LOCAL` *(ordinary — this axis has no floor rung, LOCAL is the base state)* | Primary's influence reaches only itself + adjacent cells |
| `BANDED` | Spans a contiguous run, leaves a row/column unaccounted |
| `FIELD` | Reaches elements separated by ≥1 intervening cell |
| `WHOLE` | No declared cell is unaccounted for |
| *(gate)* `NOT_ESTABLISHED` | No primary exists |

## AXIS 10 — GLOBAL COHERENCE
Single value. Evidence: 3.4, 3.5.

| Value | Condition |
|---|---|
| `DISPERSED` *(floor)* | ≥2 masses, no locatable relation between them at all |
| `COHERENT` *(ordinary)* | Masses read as one field |
| `COHERENT_WITH_COUNTER` | `COHERENT` + a counter-running element still relates to it |
| `COHERENT_ACROSS_REGISTERS` | `COHERENT_WITH_COUNTER` in mass, direction *and* band |
| `COHERENT_UNDER_CONFLICT` | `COHERENT_ACROSS_REGISTERS` + two comparable organisations both stay legible |

## AXIS 11 — STRUCTURAL DEPENDENCY
**Per tested element (array), not one value per painting.** Evidence: 5.1. Empty when the sheet has no element. *You need a reduction rule for Stage 2 — see note above.*

| Value | Condition |
|---|---|
| `REDUNDANT` | Removing it costs nothing locatable |
| `REPLACEABLE` | Costs something; a named, C1–C3-tested substitute could carry it |
| `NECESSARY` | Costs something; nothing present could carry it |
| `IRREPLACEABLE` *(restored v21.4)* | `NECESSARY` + costs two or more independently-locatable organisational properties, each on separate evidence |

**Calibration note:** `IRREPLACEABLE` was dropped somewhere before this rebuild started, despite being (per Pete) the one axis design that had actually validated well in V20. Without it, `NECESSARY` was absorbing both "very good" and "the absolute ceiling" — and across all four test runs so far, every single tested element (8 for 8) came back `NECESSARY`, because there was nowhere higher to distinguish a merely-necessary element from one doing two structural jobs at once. Restored as the genuine top rung; `NECESSARY` now means "very good," not "perfect."

## AXIS 12 — STOCHASTIC INTEGRATION
Single value per painting (already reduced from multiple tested events at Stage 1 — see 5.2's aggregation rule). Evidence: 5.2.

| Value | Condition |
|---|---|
| *(gate)* `NOT_PRESENT` | No chance-driven event locatable |
| `UNCONTROLLED` *(floor, once an event exists)* | Isolated / disruptive / unrelated to structure |
| `ACCEPTED` *(ordinary)* | Neither corrected nor developed |
| `INCORPORATED` | A later mark or the primary's continuation relates to it |
| `GENERATED` | Placement/extent/bounding relation consistent with intentional creation |
| `EXPLOITED` | The passage's logic *depends on* the material's behaviour |

## AXIS 13 — COMPOSITIONAL CLOSURE
Single value. Evidence: 3.2, 3.3, 2.2, 5.3.

| Value | Condition |
|---|---|
| `RESOLVED` *(ordinary — the good outcome is the floor here, not an escalation)* | No marker anywhere surveyed |
| `WORKED_PAST` | A marker in one cell, or markers confined to mutually adjacent cells |
| `WORKED_PAST_REPEATEDLY` | Markers in ≥2 cells, at least two non-adjacent |

---

*Generated from VAE_v21_4_engine.md. If the engine changes, regenerate this table from it rather than editing both independently — this file has no authority of its own.*
