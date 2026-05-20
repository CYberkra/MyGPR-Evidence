# AT-007 Post Zero-Time Policy Rerun

- Source commit: `b8cc89d3f026c858beab888cb3cbecd93192b723`
- Dataset: `pipe_demo_longline_v1`
- Ground truth available: `True`
- Zero-time policy: `explicit_only_fixed_zero`
- GX-003 ROI is used as-is.
- Historical AT-002/AT-003 are preserved as pre-fix baselines.

## Key Findings
- Implicit 423-sample shift eliminated: `True`
- Branch validity before -> after: `0` -> `0`
- First failing step before: `set_zero_time`
- First failing step after: `dewow`
- AutoTune status: `remains_inconclusive`
- Next bottleneck: `dewow parameter-domain refinement`

## Claim Boundary
- This rerun does not claim overall AutoTune superiority.
- Ground-truth metrics are used on GX-003; heuristic metrics remain diagnostic.

## Next Recommended Task
- `dewow_parameter_domain_refinement`

## Evidence
- `tables/before_after_validity_comparison.csv`
- `tables/before_after_metric_comparison.csv`
- `figures/before_after_zero_time_policy.png`
- `figures/before_after_branch_validity.png`
