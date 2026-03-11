# Canonical Routing Index (TP)

This file is the single routing map for where each proof package lives in:

- main preprint sections/appendices,
- mirror note files,
- certificate/artifact keys.

## Gate Routing

| Gate | Main preprint location | Mirror note | Registry/artifact key(s) |
|---|---|---|---|
| `TP_G1` (coercivity) | `Section 4`, `Appendix A` | `notes/EG1_public.md` | `kappa_sieve` |
| `TP_G2` (capture) | `Section 5`, `Appendix B` | `notes/EG2_public.md` | `sigma_distribution` |
| `TP_G3` (compactness/no-collapse) | `Section 5`, `Appendix C` | `notes/EG3_public.md` | `kappa_compact` |
| `TP_G4` (rigidity) | `Section 6.1`, `Appendix D` | `notes/EG4_public.md` | `rho_rigidity` |
| `TP_G5` (transfer) | `Section 6.2`, `Appendix E.4` | `notes/EG4_public.md` | `parity_transfer` |
| `TP_G6` (strict coherence) | `Section 6.3`, `Appendix E.6` | `notes/IDENTIFICATION_BRIDGE.md` | `eps_coh` |
| `TP_GM` (final strict margin) | `Section 8`, `Appendix E.5` | derived | all above keys |

## Repro Routing

| Artifact | Path |
|---|---|
| Runner | `repro/run_repro.sh` |
| Guard | `scripts/tp_closure_guard.py` |
| Runtime certificate | `repro/certificate_runtime.json` |
| Baseline certificate | `repro/certificate_baseline.json` |
| Registry | `artifacts/constants_registry.json` |
| Stitch constants | `artifacts/stitch_constants.json` |
| Third-party rerun protocol | `repro/THIRD_PARTY_RERUN_PROTOCOL.md` |
