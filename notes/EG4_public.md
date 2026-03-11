# EG4 Public Note

Gates: `TP_G4`, `TP_G5`
Constants: `rho_rigidity`, `parity_transfer`

This note packages rigidity and transfer. Rigidity excludes the bad-limit class by contradiction with the admissible identities, while the transfer inequality carries the rigid endpoint into the intended target class. The extracted theorem-level constants are `rho_rigidity > 0` and `parity_transfer > 0`, obtained from

- `rho_rigidity_raw`
- `c_parity_raw * admissible_gain_raw - e_parity_raw`

Together these gates block spurious endpoint models and preserve the intended target structure.
