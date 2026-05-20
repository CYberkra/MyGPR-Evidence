# Evidence Manifest Schema

Each evidence package must include a manifest that records provenance, dataset
identity, metric family, generated artifacts, and limitations.

Recommended file name:

```text
evidence_manifest.json
```

Required fields:

| Field | Required | Description |
|---|---:|---|
| `artifact_id` | yes | Stable artifact identifier, for example `AT-001` or `MC-001`. |
| `task_id` | yes | Task or experiment identifier that produced the evidence. |
| `source_repo` | yes | MyGPR source repository URL. |
| `source_branch` | yes | MyGPR source branch used to generate the evidence. |
| `source_commit` | yes | Exact MyGPR commit hash used to generate the evidence. |
| `evidence_repo` | yes | Evidence repository URL. |
| `evidence_commit` | yes | Evidence repository commit containing this manifest. Use `pending` before commit. |
| `generated_at` | yes | ISO-like timestamp with timezone where possible. |
| `command` | yes | Exact command or GUI workflow used to generate the evidence. |
| `dataset_name` | yes | Human-readable dataset or scenario name. |
| `dataset_shape` | yes | B-scan shape, usually `[samples, traces]`. |
| `dataset_hash` | yes | Hash of the source dataset or generated data package. Do not store private raw data. |
| `ground_truth_available` | yes | Boolean indicating whether validated ground truth is available. |
| `metric_type` | yes | One of `heuristic_qc`, `ground_truth`, or `mixed_labeled`. |
| `artifacts` | yes | Relative paths to figures, tables, reports, manifests, or summaries. |
| `limitations` | yes | List of known limitations. |
| `known_risks` | yes | List of known risks or unresolved caveats. |

Notes:

- `source_commit` is mandatory. Evidence without a source commit is not
  reproducible.
- `metric_type` must not hide whether a score is heuristic or ground-truth
  based.
- Large raw data must be referenced by hash/path/command, not committed.

