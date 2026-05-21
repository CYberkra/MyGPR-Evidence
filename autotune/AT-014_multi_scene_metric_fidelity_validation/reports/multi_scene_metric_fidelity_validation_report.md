# AT-014 Multi-scene Metric Fidelity Validation

- Source commit: `7efd03ef02c91579a7990a7e48002355467ca65e`
- Included scenes: `['GX-003', 'GX-004', 'GX-005', 'GX-006']`
- AT-011 policy unchanged: `True`
- Gate reassessment: `blocked`

## Strict findings
- GX-004: `{'status': 'evaluated', 'best_candidate_label': 'local', 'best_generated_ntraces': 9, 'min_false_positive_proxy': 0.00927039667309975, 'artifact_risk_present': False}`
- GX-005: `{'status': 'evaluated', 'max_target_preservation_gap': 0.28198196186790736, 'target_imbalance_risk_present': True, 'note': 'Strict per-target processed ROI metrics reported in gx005_per_target_processed_metrics.csv'}`
- GX-006: `{'status': 'evaluated', 'interface_suppression_risk_present': True, 'clutter_false_positive_risk_present': False, 'note': 'Layer/interface metrics are reported separately from clutter false-positive metrics.'}`
- GX-004 only uses no-target/negative-control fidelity metrics; no target-preservation metric is used.
- GX-005 reports strict processed per-target metrics for target_A and target_B.
- GX-006 reports layer/interface-aware metrics separately from clutter false-positive metrics.

## Scene best candidates
- GX-003: `local` ntraces=`9`
- GX-004: `local` ntraces=`9`
- GX-005: `local` ntraces=`9`
- GX-006: `local` ntraces=`9`

## Gate status
- status: `blocked`
- risk_flags: `['gx005_target_imbalance', 'gx006_interface_suppression', 'synthetic_thin2d_scene_limit']`
- AT-013 proxy limitation addressed: `True`
- AT-011 ratio family is replayed unchanged: 0.05, 0.10, 0.20, 0.40, 0.70, 1.00.
- Thin-2D synthetic limitation remains active for all scenes.
- No preset promotion. No overall AutoTune superiority claim. No field-performance claim.
