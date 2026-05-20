# MyGPR Evidence Repository

This repository stores research evidence for MyGPR experiments. It is not the
source repository for the MyGPR application, algorithms, tests, or durable
project rules.

## Source Of Truth

- Main code repository: https://github.com/CYberkra/MyGPR
- MyGPR source branch and commit must be recorded for every evidence artifact.
- MyGPR remains the only source of truth for application code, processing
  algorithms, tests, long-term rules, and implementation decisions.
- This repository stores experiment outputs, B-scan figures, reports, metrics,
  manifests, and audit notes.

## Evidence Requirements

Every evidence package must record:

- Source repo.
- Source branch.
- Source commit.
- Dataset name, shape, hash, and generation command.
- Whether ground truth is available.
- Whether metrics are heuristic QC metrics or ground-truth metrics.
- Known limitations and risks.

Large raw data must not be committed. For large or private datasets, record only
the dataset hash, shape, local/external path, and exact command used to generate
or process it.

## Evidence Types

Evidence type must be explicit:

- `smoke`: minimal run proving a route executes.
- `normal`: ordinary validation run with realistic parameters.
- `stress`: exaggerated or adversarial run used to expose behavior clearly.
- `paper-candidate`: curated result intended for paper or group-meeting figures.

Stress evidence must not be described as a field-flight baseline.

## Metric Boundary

Heuristic QC metrics and ground-truth metrics must not be mixed without labels.

- Heuristic QC metrics evaluate image quality or sanity without true target
  knowledge.
- Ground-truth metrics use known target/background regions from a validated
  manifest or sidecar.

Reports must label which metric family is used and whether ground truth is
available.

