# AT-009 Background Suppression Domain Convergence and Gain Policy Refinement

- Source commit: `ffb86822ccf273e5f38c26dd6a37d547b59ee4b8`
- Dataset: `pipe_demo_longline_v1` shape `[2037, 90]`
- Ground truth: `available`
- Zero-time policy: `excluded`
- Dewow policy: `excluded_primary`
- GX-003 ROI is used as-is.

## Main result
- Recommended ntraces range: `73-73`
- Best conservative/interpretable gain variant: `energy_decay_gain`
- Constrained AutoTune status: `inconclusive_near_tie`
- No overall AutoTune superiority claim is made.

## Constrained AutoTune comparison
| Branch | ntraces | gain | ROI contrast | clipping | risk_flags |
|---|---:|---|---:|---:|---|
| `manual_recommended` | 73 | `energy_decay_gain` | 49.09 | 0.001004 | `` |
| `safe_conservative` | 41 | `energy_decay_gain` | 20.28 | 0.001004 | `` |
| `auto_tuned_constrained_simulated` | 73 | `energy_decay_gain` | 49.09 | 0.001004 | `best_params_at_edge` |

## Claim boundary
- Ground-truth metrics and heuristic QC are separated.
- AGC remains display-oriented and non-amplitude-preserving.
- Dewow stays optional/diagnostic and is excluded from this primary lane.

## Next recommended task
- constrained AutoTune preset finalization + multi-scene native gprMax expansion.

## Known risks
- Single native gprMax scene is still insufficient for broad generalization.
- Constrained AutoTune result is domain-bounded and may shift on other scenes.
- Dewow is excluded in this primary lane; this is not global dewow invalidation.
