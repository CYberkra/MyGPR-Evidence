# AT-006 Zero-Time Policy Fix

- Source commit: `61ad8a3ac55d9e604f802b9c8ca8ddb3474b65ad`
- Dataset: `pipe_demo_longline_v1` (`native_gprmax_converted`)
- Dataset shape: `[2037, 90]`
- Time step: `0.011793 ns`
- Zero-time policy: `explicit_only_fixed_zero`

## Root Cause
Validation branches that call set_zero_time with empty params fall back to method default new_zero_time=5.0 ns. On GX-003 dt this maps to ~423 samples and can collapse global energy.

## Fix Implemented
Validation runners now infer native_gprmax_converted context and apply zero_time_policy=explicit_only_fixed_zero, forcing missing zero-time params to 0.0 ns and disabling implicit tuning.

## Policy Checks

| Check | Status | Notes |
| --- | --- | --- |
| `legacy_default_shift` | `warn` | Legacy empty params path relies on method default (5.0 ns). |
| `guarded_policy_shift` | `ok` | Validation guard enforces fixed-zero when zero-time is implicit. |
| `no_zerotime_preset_reusable` | `ok` | AT-005A lane reused as formal no-zero-time validation preset. |

## Before / After
- Legacy shift samples: `423`
- Legacy shift ns: `4.988554`
- Legacy global energy ratio: `0.002239`
- Guarded shift samples: `0`
- Guarded shift ns: `0.000000`
- Guarded global energy ratio: `1.000000`

## No-Zero-Time Preset
- Reused lane policy: `excluded`
- Report (md): `..\MyGPR-Evidence\autotune\AT-006_zero_time_policy_fix\_no_zerotime_lane\reports\no_zerotime_gain_validation_report.md`
- Report (html): `..\MyGPR-Evidence\autotune\AT-006_zero_time_policy_fix\_no_zerotime_lane\reports\no_zerotime_gain_validation_report.html`

## Claim Boundary
- This task does not prove overall AutoTune superiority.
- This task does not replace GX-003 ROI.
- This task only hardens validation-time zero-time policy.

## Next Step
Rerun AT-002 and AT-003 under the guarded policy, preserving prior conclusions as historical evidence.
