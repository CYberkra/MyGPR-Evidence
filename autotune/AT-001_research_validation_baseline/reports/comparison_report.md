# AT-001 AutoTune Research Validation Baseline

## Impact Scan
- Dataset: `cylinder_single_v1`
- Shape: `[220, 81]`
- Ground truth available: `True`
- Metric type: `ground_truth`
- Evidence mode: `smoke`
- Source commit: `70407ae3b6b112be05444a77fb4a7943033a1407`
- Output path: `D:\CDUT-UavGPR-Controller\MyGPR-Evidence\autotune\AT-001_research_validation_baseline`

## Scope Boundary
- This run compares a reasonable manual expert baseline against per-step AutoTune parameters.
- It does not claim AutoTune selects the global best workflow.
- It does not use intentionally bad manual parameters.
- Ground truth is used only for validation/reporting, not for AutoTune search.

## Manual Baseline Parameters
```json
{
  "set_zero_time": {
    "new_zero_time": 0.0
  },
  "dewow": {
    "window": 23
  },
  "frequency_filter_1d": {
    "filter_type": "bandpass",
    "low_freq_mhz": 300.0,
    "high_freq_mhz": 2500.0,
    "taper_ratio": 0.08
  },
  "subtracting_average_2D": {
    "ntraces": 41
  },
  "energy_decay_gain": {
    "strength": 0.8,
    "smoothing_samples": 31,
    "min_gain": 0.6,
    "max_gain": 5.0,
    "floor_ratio": 0.05
  }
}
```

## Auto-Tuned Parameters
```json
{
  "set_zero_time": {
    "new_zero_time": 0.24545454545454545
  },
  "dewow": {
    "window": 25,
    "_low_energy_guard": true
  },
  "frequency_filter_1d": {
    "filter_type": "bandpass",
    "low_freq_mhz": 300.0,
    "high_freq_mhz": 5805.555555555555,
    "taper_ratio": 0.04
  },
  "subtracting_average_2D": {
    "ntraces": 4
  },
  "energy_decay_gain": {
    "strength": 1.2,
    "smoothing_samples": 61,
    "min_gain": 0.6,
    "max_gain": 4.0,
    "floor_ratio": 0.05
  }
}
```

## Final Metrics
| Branch | Branch valid | Heuristic comparison_score proxy | truth_score | Branch invalid reason |
|---|---:|---:|---:|---|
| manual | yes | 1.1953 | 3.2802 | - |
| auto | yes | 0.9782 | 2.0584 | - |

## Stepwise Sanity Table
| Branch | Step | Method | Output shape | Runtime warnings | Sanity warnings | Invalid reason | Preview |
|---|---:|---|---|---|---|---|---|
| manual | 1 | `set_zero_time` | `[220, 81]` | - | - | - | `figures/step_01_manual_set_zero_time.png` |
| manual | 2 | `dewow` | `[220, 81]` | - | - | - | `figures/step_02_manual_dewow.png` |
| manual | 3 | `frequency_filter_1d` | `[220, 81]` | - | - | - | `figures/step_03_manual_frequency_filter_1d.png` |
| manual | 4 | `subtracting_average_2D` | `[220, 81]` | - | - | - | `figures/step_04_manual_subtracting_average_2D.png` |
| manual | 5 | `energy_decay_gain` | `[220, 81]` | - | - | - | `figures/step_05_manual_energy_decay_gain.png` |
| auto | 1 | `set_zero_time` | `[220, 81]` | - | - | - | `figures/step_01_auto_set_zero_time.png` |
| auto | 2 | `dewow` | `[220, 81]` | - | - | - | `figures/step_02_auto_dewow.png` |
| auto | 3 | `frequency_filter_1d` | `[220, 81]` | - | - | - | `figures/step_03_auto_frequency_filter_1d.png` |
| auto | 4 | `subtracting_average_2D` | `[220, 81]` | - | - | - | `figures/step_04_auto_subtracting_average_2D.png` |
| auto | 5 | `energy_decay_gain` | `[220, 81]` | - | - | - | `figures/step_05_auto_energy_decay_gain.png` |

## Branch Validity
- Manual branch invalid reason: `none`
- Auto branch invalid reason: `none`

If a branch has an invalid reason, this evidence must not be used as a fair manual-vs-auto conclusion.

## Ground Truth And Metric Boundary
- Ground truth available: `True`
- Heuristic QC only: `False`
- Heuristic QC metrics and ground-truth metrics are stored separately in `comparison_summary.json` and `stepwise_report.json`.
- If ground truth is unavailable, reports must not claim the result is closer to the real subsurface structure.

## Current Paper Claim Boundary
- Can claim: the AT-001 runner creates reproducible stepwise evidence for manual-vs-auto validation and exposes early baseline failures.
- Cannot claim: AutoTune is globally optimal, field-general, or truth-guided.

## Limitations
- This baseline validates one small deterministic fixture first; it is not a global workflow optimum claim.
- AutoTune uses heuristic search during selection; ground truth is used only for validation/reporting.
- Manual baseline is an experience-based baseline, not a visual expert session with interactive retuning.

## Known Risks
- Single-scene evidence may not generalize to field UAV-GPR data.
- Heuristic QC can prefer visually cleaner images that are not geologically better.
- Zero-time choices can invalidate later branch comparisons if early signal is removed.
