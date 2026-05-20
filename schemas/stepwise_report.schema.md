# Stepwise Processing Report Schema

Stepwise reports describe each processing stage for manual, automatic, or
diagnostic branches.

Required fields per step:

| Field | Required | Description |
|---|---:|---|
| `branch` | yes | One of `manual`, `auto`, or `diagnostic`. |
| `step_index` | yes | Zero-based or one-based step index; the report must state which convention is used. |
| `method_key` | yes | MyGPR processing method key. |
| `input_shape` | yes | Input B-scan shape before this step. |
| `output_shape` | yes | Output B-scan shape after this step. |
| `params` | yes | Parameters actually used for this step. |
| `runtime_warnings` | yes | Runtime warnings returned by MyGPR. Use an empty list when none exist. |
| `qc_metrics` | yes | Step-level QC metrics. Label heuristic and ground-truth metrics separately. |
| `sanity_warnings` | yes | Baseline sanity warnings, invalid-branch warnings, or report-level caveats. |
| `branch_invalid_reason` | yes | Null/empty if branch is valid; otherwise explain why this branch should not be compared directly. |
| `preview_png` | yes | Relative path to the B-scan preview PNG for this step. |

AutoTune validation should preserve manual and auto stepwise B-scan preview PNGs
whenever possible. These previews are needed to explain not just the final score,
but where each branch improved, overprocessed, clipped, shifted, or failed.

