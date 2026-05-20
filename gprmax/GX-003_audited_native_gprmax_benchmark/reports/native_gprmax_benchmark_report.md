# GX-003 Audited Native gprMax Benchmark

## Summary
- Source MyGPR commit: `6507e2535815020d4b79d273db5de471e0045277`
- Scenario id: `pipe_demo_longline_v1`
- Benchmark type: `normal native_gprmax_converted`
- Stress profile: `no`
- Paper-candidate status: `limited paper-usable provenance evidence; not an AutoTune performance result`
- Native gprMax verified: `true`
- Paper usable by audit: `true`

## Provenance Chain
```text
model.in + native _merged.out + ground_truth.yaml
-> prepare_native_gprmax_package.py
-> /rxs/rx1/Ez
-> MyGPR-compatible CSV
-> audit_gprmax_package.py
-> GX-003 Evidence
```

## Source Files
- model.in path: `D:\CDUT-UavGPR-Controller\MyGPR\output\gprmax_datasets\pipe_demo_longline_v1\pipe_demo_longline_v1.in`
- model.in SHA-256: `c71ab607892d1b8192a1f82177b65e389312cd93467e8a757be04df43d6d6bea`
- native _merged.out path: `D:\CDUT-UavGPR-Controller\MyGPR\output\gprmax_datasets\pipe_demo_longline_v1\pipe_demo_longline_v1_merged.out`
- native _merged.out SHA-256: `5979b56f4d3ad3834f71732104bf218eadb0621f0679646d772a439332e66c42`
- ground_truth.yaml path: `D:\CDUT-UavGPR-Controller\MyGPR\output\gprmax_datasets\pipe_demo_longline_v1\ground_truth.yaml`

## Conversion
- Command: `python scripts\gprmax_benchmark\prepare_native_gprmax_package.py --model-in output\gprmax_datasets\pipe_demo_longline_v1\pipe_demo_longline_v1.in --out output\gprmax_datasets\pipe_demo_longline_v1\pipe_demo_longline_v1_merged.out --output-dir output\gprmax_native_csv_packages\GX-003_pipe_demo_longline_v1 --receiver rx1 --component Ez --scenario-id pipe_demo_longline_v1 --ground-truth output\gprmax_datasets\pipe_demo_longline_v1\ground_truth.yaml`
- Receiver/component: `/rxs/rx1/Ez`
- Converted CSV local path: `D:\CDUT-UavGPR-Controller\MyGPR\output\gprmax_native_csv_packages\GX-003_pipe_demo_longline_v1\mygpr_bscan.csv`
- Converted CSV Evidence path: `gprmax/GX-003_audited_native_gprmax_benchmark/tables/mygpr_bscan.csv`
- Converted CSV SHA-256: `3f9ce35dce8de510a5a1cc54d96c0a8635fcd834cf1a69d8f455009d05ef40b1`
- Shape: `2037 samples x 90 traces`

## Audit Result
- dt source: `native gprMax .out`
- time_step_s: `1.1793271683748419e-11`
- time_window_ns: `24.0`
- domain_m: `[1.2, 0.85, 0.005]`
- dx_dy_dz_m: `[0.005, 0.005, 0.005]`
- shape matches metadata: `true`
- ROI exists: `true`
- ROI inside B-scan: `true`
- native_gprmax_verified: `true`
- audit paper_usable: `true`

## PML / Domain Notes
- PML/domain audit warnings: `axis 2 domain 0.005 m is thinner than two default PML margins; treating it as a thin/2D dimension for margin screening`
- Interpretation: the model is a thin 2D-style gprMax geometry. This is acceptable for limited native benchmark evidence when explicitly documented, but it is not a full 3D field-scale UAV-GPR model.

## Limitations
- Raw `_merged.out` is not committed to Evidence; it is recorded by absolute path and SHA-256.
- This is a normal native conversion benchmark, not a stress profile and not an AutoTune redesign result.
- Paper use must preserve or regenerate the exact raw `_merged.out` and `model.in`.
- This evidence supports the native gprMax-to-CSV provenance chain, not a claim that AutoTune is better than manual processing.
