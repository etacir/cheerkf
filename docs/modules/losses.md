# L. Losses for the inventory

*Buildings / Integration*

## L1. Compute loss for every building in the inventory for every scenario h

Overlay the inventory on the hazard fields, look up damage for each building and produce L_imch, loss by location, type, resistance and scenario, in the structure STARR reads.

| | |
|---|---|
| **Inputs** | Loss-model-ready inventory (I4, I5); hazard fields per scenario (H3); lookup tables (D1); scenario probabilities (H2) |
| **Outputs** | Regional loss datasets (zone x type x resistance x scenario; flood, wind and total loss ratios) |
| **Point person (workflow slide)** | <span class="owner">Jingya</span> |
| **Who did the work (records)** | Jingya Wang (since Jan 2026; previously Hesam Soleimani) |
| **Code** | github.com/CHEER-Hub/Inventory-Loss-link V1; STARR loss module |
| **Data** | CoPe Drive 'Loss Estimates' folders: New_Inventory_Old_scenarios (CHEER.v1, 22 Jul 2025); Old_Inventory_New_Hazard (v2, 22 Jul 2025); New_Inventory_TC_WiSE_V2 (v3, 6 Oct 2025); New_Inventory_TC_WiSE_V3 (v4, 23 Oct 2025); LOS0 preCHEER |
| **Documentation** | KO Inventory 'Regional Loss Data' tab; a readme for the Loss Estimates folder was requested on 6 Jan 2026 (status unknown); Inventory-Loss-link documentation |
| **Versions recorded** | LOS0; CHEER.v1 to v4 (all with scenario probabilities '(to-do)'). No version yet for losses on the NSI inventory decided on 17 Feb 2026. |
| **Status** | v1-v4 rest on inventories and hazard sets since replaced; a new set on NSI v1.1 with the current hazard dataset is needed |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Fill the empty 'Regional Loss Model' tab; log the NSI-based loss set; write the readme; align folder names with the hazard version names. **Who:** Jingya Wang

*Sources: KO Inventory 'Regional Loss Data'; kf* notes 6 Jan and 17 Feb 2026; Wang email 19 Jul 2025 (4-D loss format)*
