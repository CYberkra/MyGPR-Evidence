# GX-002 Native gprMax-to-CSV Package Preparation Record

## Summary
- Status: `pending_native_out`
- Source repo: `https://github.com/CYberkra/MyGPR`
- Source branch: `codex/research-gprmax-autotune`
- Source commit: `b1fb5ce540ac00a6ac880ddf78c1feeffbb80a6f`
- Evidence purpose: record that MyGPR now has tooling to prepare a native gprMax-to-CSV benchmark package.

## What GX-002 Added In MyGPR
GX-002 added package-preparation tooling in MyGPR for the future native data chain:

```text
model.in / native .out or _merged.out
-> selected /rxs/<receiver>/<component>
-> MyGPR-compatible CSV
-> scenario + manifest + ground truth
-> audit
-> Evidence repository
```

The intended runner is:

```bash
python scripts/gprmax_benchmark/prepare_native_gprmax_package.py \
  --model-in <path/to/model.in> \
  --out <path/to/native_or_merged.out> \
  --output-dir <path/to/package_dir> \
  --receiver rx1 \
  --component Ez \
  --scenario-id <scenario_id> \
  --ground-truth <path/to/ground_truth.yaml-or-json>
```

## Current Evidence Status
No paper-usable native gprMax package is recorded in this Evidence item yet.
This GX-002 Evidence record is intentionally pending. It must not be cited as a
native gprMax benchmark result.

## Required Missing Input
To complete GX-002 as native evidence, provide:

- native gprMax `.out` or `_merged.out`;
- exact `model.in` used to generate the output;
- `ground_truth.yaml` or `ground_truth.json`;
- selected receiver/component, normally `/rxs/rx1/Ez`;
- generated CSV, preview, manifest, and audit produced by the MyGPR tool.

## Claim Boundary
- Paper usability: `no`
- Native gprMax provenance verified: `no`
- Converted CSV available in this Evidence record: `no`
- Raw `.out` committed: `no`

Do not claim AutoTune or processing performance from this GX-002 record. The
next step is to run `prepare_native_gprmax_package.py` locally with real gprMax
output and then replace this pending record with a completed package audit.
