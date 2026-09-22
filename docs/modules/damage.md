# D. Damage model (CHEERsafe)

*Buildings thrust*

## D1. Develop damage-probability lookup tables P(D = d | m, c, w, f) for site-built single-family, manufactured and low-rise multifamily homes

Component-based damage model that converts wind speed and flood depth into damage-state probabilities and loss ratios for each archetype and resistance level.

| | |
|---|---|
| **Inputs** | Archetype definitions (site-built: 8 m x 192 c; MMH: 8 m x 40 c, 168 combinations); wind and flood hazard levels; NCIUA claims (about 800,000) for validation; HUD standards and literature for MMH |
| **Outputs** | Damage-state and loss-ratio lookup tables; component-level damage ratios (feature added Dec 2025) |
| **Point person (workflow slide)** | <span class="owner">Mohammad, Christopher</span> |
| **Who did the work (records)** | Mohammad Askari (CHEERsafe); Christopher Alegbeleye (MMH); Daniel (low-rise multifamily concept); UF (Prevatt, Agdas) testing and sensitivity analysis |
| **Code** | github.com/CHEER-Hub/LossModel (private): CHEERsafe Python package; MMH code 'in progress' on GitHub; CHEERSafe-Vis hazard visualization app (cheersafe-vis.streamlit.app) |
| **Data** | Lookup tables circulated by email (Oct 2025) and a Drive 'v2' loss-ratio folder (Aug 2025). KO Inventory 'Individual Loss Data' tab is empty. |
| **Documentation** | LossModel/docs; CHEERSafe paper (in revision, Sep 2026); MMH paper in preparation; UF 'less-technical manual' (R. Davidson has not seen it) |
| **Versions recorded** | LM0 preCHEER (Matlab; Peng and Legg dissertations); CHEERsafe.v1 (final); MMH.v1 (final 2 Oct 2025). Bug fixes of Mar 2026 (indices; hip-roof case) and UF modifications of Sep 2026 have no version entries. |
| **Status** | v1 in use by several groups; public release waiting on licensing (annual report comment, Jun 2026) |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Version log covering the fixes and UF changes; fill the lookup-table tab; fix the duplicate ID 'LM1'; settle licensing; note that the precipitation term p in the slide's notation is not yet in the model. **Who:** Mohammad Askari; Christopher Alegbeleye; Duzgun Agdas

*Sources: KO Inventory 'Individual Loss Model'; emails 'Version updating' 25-26 Mar 2026 and 'CHEER-UF check in' 18 Sep 2026; KF Content Catalog; Year 4 annual report comments*
