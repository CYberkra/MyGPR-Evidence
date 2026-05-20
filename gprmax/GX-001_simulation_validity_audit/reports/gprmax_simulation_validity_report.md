# GX-001 gprMax Simulation Validity Audit

## Summary
- Package: `D:\CDUT-UavGPR-Controller\MyGPR\sample_data\gprmax_benchmarks\cylinder_single_v1`
- Source kind: `synthetic_reference`
- Native gprMax .out verified: `False`
- Paper usable as native gprMax evidence: `False`
- Recommendation: use for smoke/contract tests only; regenerate native gprMax package before paper claims

## Files
- model.in: `D:\CDUT-UavGPR-Controller\MyGPR\sample_data\gprmax_benchmarks\cylinder_single_v1\model.in`
- raw .out exists: `False`
- raw .out files: `[]`
- MyGPR CSV: `D:\CDUT-UavGPR-Controller\MyGPR\sample_data\gprmax_benchmarks\cylinder_single_v1\mygpr_bscan.csv`
- ground_truth.json: `D:\CDUT-UavGPR-Controller\MyGPR\sample_data\gprmax_benchmarks\cylinder_single_v1\ground_truth.json`

## Geometry And Timing
- domain_m: `[0.24, 0.21, 0.002]`
- dx_dy_dz_m: `[0.002, 0.002, 0.002]`
- time_window_ns: `18.0`
- time_step_s: `8.181818181818183e-11`
- dt source: `synthetic fallback/scenario metadata`
- dt consistency: `{'available': True, 'scenario_time_step_s': 8.181818181818183e-11, 'time_window_over_samples_s': 8.181818181818182e-11, 'absolute_mismatch_s': 1.2924697071141057e-26, 'relative_mismatch': 1.5796851975839072e-16}`
- source scan: `{'available': True, 'start_m': [0.04, 0.17, 0.0], 'end_m': [0.2, 0.17, 0.0], 'step_m': [0.002, 0.0, 0.0], 'trace_count': 81}`
- receiver scan: `{'available': True, 'start_m': [0.08, 0.17, 0.0], 'end_m': [0.24, 0.17, 0.0], 'step_m': [0.002, 0.0, 0.0], 'trace_count': 81}`

## PML / Boundary Risk
- default PML cells assumed: `10`
- margin_m: `[0.02, 0.02, 0.02]`
- risk flags: `['axis 2 domain 0.002 m is thinner than two default PML margins; treating it as a thin/2D dimension for margin screening', 'receiver end_m axis 0 at 0.24 m is inside/near upper PML margin 0.22 m']`

## Shape And Ground Truth ROI
- expected shape: `220 x 81`
- actual shape: `220 x 81`
- shape matches expected: `True`
- ROI exists: `True`
- ROI inside B-scan: `True`
- ROI warnings: `[]`

## Warnings
- source.kind is synthetic_reference; this package is suitable for smoke/contract tests only.
- No native gprMax .out file found in the package.
- axis 2 domain 0.002 m is thinner than two default PML margins; treating it as a thin/2D dimension for margin screening
- receiver end_m axis 0 at 0.24 m is inside/near upper PML margin 0.22 m

## Errors
- none

## Audit Conclusion
The current `cylinder_single_v1` fixture can be used for deterministic smoke,
contract, and stepwise-evidence plumbing tests. It must not be cited as a
native gprMax forward-model result until a raw `.out` package, verified
`dt`, domain/PML-safe scan geometry, and source-side `ground_truth.yaml` are
present and audited.
