# AT-016 Risk-flag and Scoring Diagnostics

## 1. Executive summary
- AT-016 is diagnostics-only and is based on AT-014 outputs.
- Candidate ranking and gate blocking are intentionally separate layers.
- Gate status remains `blocked`.

## 2. Why local n=9 ranks best
- In AT-014 candidate scoring, local candidates retain higher per-scene score under the current metric composition.
- For GX-003/004/005/006 the top-ranked candidate is local n=9.
- Score leadership does not imply safety clearance or preset eligibility.

## 3. Why gate remains blocked
- Active blockers: `['gx005_target_imbalance', 'gx006_interface_suppression', 'synthetic_thin2d_scene_limit']`.
- Ranking answers 'which candidate scores higher'.
- Gate answers 'is candidate safe enough for preset finalization'.
- Current blockers prevent preset promotion even when score rank is 1.

## 4. GX-004 finding
- artifact_risk_present: `False`.
- No-target false-positive control remains comparatively stable in this diagnostic set.

## 5. GX-005 finding
- target_imbalance_common_across_candidates: `False`.
- local_n9_preservation_gap: `0.28198196186790736`.
- Imbalance risk is not reduced to zero by choosing local n=9.

## 6. GX-006 finding
- interface_suppression_common_across_candidates: `True`.
- local_n9_layer_interface_ratio: `0.6377657940711385`.
- Interface suppression risk persists and is not unique to one candidate.

## 7. Recommendation
- Recommended immediate next task: **AT-017 scoring/risk-penalty refinement design**.
- Keep scoring semantics unchanged in this phase; first produce bounded design diagnostics.

## 8. Claim boundary
- No preset promotion.
- No overall AutoTune superiority claim.
- No field-performance claim.
- Thin-2D synthetic limitation remains.
