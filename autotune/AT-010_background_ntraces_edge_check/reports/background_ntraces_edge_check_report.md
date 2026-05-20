# AT-010 Background ntraces Edge Check and Preset Candidate

- Source commit: `2ed606e7f4ec26bff24cfb2980479f6dc96573dc`
- Dataset: `pipe_demo_longline_v1` shape `[2037, 90]`
- Ground truth: `available`
- Zero-time policy: `excluded`
- Dewow policy: `excluded_primary`
- GX-003 ROI is used as-is.

## Decision
- Preset candidacy classification: `not_ready_edge_limited`
- Best ntraces: `97`
- Recommended ntraces range: `89-121`
- ntraces=73 remains supported: `False`
- Edge-risk flags: `false_positive_increase,monotonic_rightward_trend,multiple_near_optima`

## Claim boundary
- This is an edge-check following AT-009; no overall AutoTune superiority claim is made.
- AGC is not used for physical correctness claims here.
- Dewow remains optional/diagnostic and excluded in this primary lane.

## Next recommended task
- more native gprMax model generation + constrained preset cross-scene validation.

## Known risks
- Single native gprMax scene cannot establish broad preset generalization.
- Edge-check may still be domain-limited without wider scenario coverage.
- Dewow remains excluded only for this primary lane policy.
