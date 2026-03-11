# Reviewer Map

## Claim Scope

- Canonical-lane claim: inside the `manifold_constrained` lane, if the theorem chain in this repository holds and the guard certificate passes, the repository-level closure claim is satisfied.
- Standard target claim: carried by the in-repo bridge theorems tying the lane to the target statement.

## Theorem Dependency Chain

1. `EG1`: coercive response and active control floor.
2. `EG2`: capture and admissible continuation.
3. `EG3`: compactness and no-collapse spacing.
4. `EG4`: rigidity and transfer.
5. Identification bridge: strict coherence on the determining class.
6. Scalar closure: `TP_G1, TP_G2, TP_G3, TP_G4, TP_G5, TP_G6, TP_GM` all `PASS`.

Primary files:

- `paper/TWIN_PRIME_CONJECTURE_PREPRINT.md`
- `notes/EG1_public.md`
- `notes/EG2_public.md`
- `notes/EG3_public.md`
- `notes/EG4_public.md`
- `notes/IDENTIFICATION_BRIDGE.md`

## Closure Gates

| Gate | Constant | Description |
|------|----------|-------------|
| `TP_G1` | `kappa_sieve` | projected sieve response has a strict positive floor |
| `TP_G2` | `sigma_distribution` | distribution defect stays above capture floor across truncation and bilinear losses |
| `TP_G3` | `kappa_compact` | normalized near-failure families are precompact and truncation windows do not collapse |
| `TP_G4` | `rho_rigidity` | bad near-parity obstruction models are excluded |
| `TP_G5` | `parity_transfer` | rigid limit transfers to the twin-prime endpoint class |
| `TP_G6` | `eps_coh` | strict coherence / identification closure |
| `TP_GM` | derived | final strict margin |

## Falsification Conditions

- `repro/certificate_runtime.json` has any non-`PASS` gate.
- `lane.active_lane != "manifold_constrained"`.
- `all_pass != true`.
- Any manifest hash mismatch under `repro/repro_manifest.json`.
- A verified counterexample to any EG theorem statement used in the paper.

## Reproducibility Check

Run:

```bash
bash repro/run_repro.sh
```

Then verify:

```bash
python3 - <<'PY'
import json
from pathlib import Path
d=json.loads(Path('repro/certificate_runtime.json').read_text())
assert d.get('all_pass') is True
assert d.get('lane',{}).get('active_lane') == 'manifold_constrained'
for g in ['TP_G1','TP_G2','TP_G3','TP_G4','TP_G5','TP_G6','TP_GM']:
assert d['gates'].get(g) == 'PASS', g
print('OK')
PY
```
