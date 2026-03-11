# Constant Extraction Spec (TP)

This file defines the theorem-constant extraction contract for this repository.

## Objective
Move constants from manual placeholder assignment to deterministic promotion:

1. extract raw constants from explicit component inputs and formulas,
2. normalize by declared references,
3. promote into `artifacts/constants_registry.json` and `artifacts/stitch_constants.json`.

## Inputs
- `artifacts/constants_extraction_inputs.json`

## Extracted Output
- `artifacts/constants_extracted.json`

## Promotion Output
- `artifacts/constants_registry.json`
- `artifacts/stitch_constants.json`
- `artifacts/promotion_report.json`

## Formula Set
- `kappa_sieve_raw = c_sieve_raw * level_density_raw - e_sieve_raw`
- `sigma_distribution_raw = distribution_floor_raw - bilinear_loss_raw - truncation_loss_raw`
- `kappa_compact_raw = 1.0 / (1.0 + delta_comp_sup_raw)`
- `rho_rigidity_raw = rho_rigidity_raw`
- `parity_transfer_raw = c_parity_raw * admissible_gain_raw - e_parity_raw`
- `eps_coh_raw = eps_coh_raw`
- `sigma_star_can_raw = sigma_star_can_raw`

## Validations
- positivity required for: `kappa_sieve`, `sigma_distribution`, `kappa_compact`, `rho_rigidity`, `parity_transfer`, `sigma_star_can`
- nonnegative required for: `eps_coh`
- strict-zero required for: `eps_coh` in strict mode

## Execution
`repro/run_repro.sh` runs:
1. `scripts/extract_constants.py`
2. `scripts/promote_constants.py`
3. `scripts/tp_closure_guard.py`
