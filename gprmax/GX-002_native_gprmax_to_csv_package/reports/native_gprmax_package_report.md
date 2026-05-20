# GX-002 Native gprMax-to-CSV Package Report

## Summary
- Scenario: `pipe_demo_longline_v1`
- Status: `native_gprmax_converted`
- Native gprMax verified: `True`
- Paper usable: `True`
- Recommendation: usable as audited native gprMax evidence for limited claims

## Provenance
- Native `.out`: `D:\CDUT-UavGPR-Controller\MyGPR\output\gprmax_datasets\pipe_demo_longline_v1\pipe_demo_longline_v1_merged.out`
- Selected receiver/component: `/rxs/rx1/Ez`
- Converted CSV shape: `[2037, 90]`
- raw_out_hash: `5979b56f4d3ad3834f71732104bf218eadb0621f0679646d772a439332e66c42`
- csv_hash: `3f9ce35dce8de510a5a1cc54d96c0a8635fcd834cf1a69d8f455009d05ef40b1`
- raw `.out` committed in package: `False`

## Geometry And Timing
- domain_m: `[1.2, 0.85, 0.005]`
- dx_dy_dz_m: `[0.005, 0.005, 0.005]`
- time_window_ns: `24.0`
- time_step_s: `1.1793271683748419e-11`
- dt source: `native gprMax .out`
- shape matches metadata: `True`

## PML / ROI Audit
- PML flags: `['axis 2 domain 0.005 m is thinner than two default PML margins; treating it as a thin/2D dimension for margin screening']`
- ROI exists: `True`
- ROI inside B-scan: `True`

## Warnings
- native .out is externally referenced but not committed inside the package
- axis 2 domain 0.005 m is thinner than two default PML margins; treating it as a thin/2D dimension for margin screening

## Errors
- none

## Claim Boundary
This package is traceable from native gprMax `.out` to a MyGPR CSV.
The raw `.out` is referenced by path and SHA-256 rather than committed.
Any paper claim must preserve that raw file or regenerate it with the same
model and command.
