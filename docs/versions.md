# Versions and compatibility

## Versioning policy (proposed)

- Every code object and dataset carries a version. Code uses semantic versions (`v1.2.0`) with a changelog and a
  Git tag; datasets carry a version in their name and, where published, a DOI.
- A version is frozen once an analysis or paper uses it. Errors are fixed in a new version, never in place, and the
  Hub is notified through the announcements channel.
- Superseded versions remain available and are marked with the reason.
- Every STARR run writes a **run manifest** listing the version of each input, so any result can be traced.
- Maturity labels from the 2024 kf* scheme: **Level 0** internal, **Level 1** shareable within CHEER,
  **Level 2** published.

## Hazard datasets: one dataset, several names  <span class="todo">to be confirmed</span>

The same hazard dataset is named differently on the earlier site, in the Knowledge Object Inventory and in
DesignSafe and Drive folders. This table matches them as far as the records allow; the last column needs
confirmation from Brian Blanton and Jingya Wang.

| Site name | Inventory, scenario tab | Inventory, models tab | Storage | Landfall decay rate | Loss datasets built on it |
|---|---|---|---|---|---|
| preCHEER (97 hurricanes) | HS0 preCHEER (Final, 9/1/2022) | - | CHEER G-Drive folder 1o0UIyhxd6lrb8UaLEdzZ4brN34pXiwv- | - | LOS0; CHEER.v1 (Individual.v1 inventory) |
| v1.0 (posted 5 Jun 2024) | HS1 STORM.v1 (Final) | TK1 STORM (Abandoned: did not match historical climatology) | PRJ-4392/Hazards/NC_Present_0_v1/NC_Present_0_v1.zip | - | Possibly CHEER.v2 ('TCWISE.v1' label, folder Old_Inventory_New_Hazard, 22 Jul 2025) |
| v1.1 (no posting date) | HS2 TCWISE.v1 (Abandoned; no storage) and HS3 TCWiSE.v2 (Abandoned; NC_Present_0_v2) | TK2 TCWiSE.v1 (Abandoned: decay produced unphysical overland winds); TK3 TCWiSE.v2 (Final) | PRJ-4392/Hazards/NC_Present_0_v2/ | Site: default 0.0155 /hr; Inventory: 'default (0.15)' | Possibly CHEER.v3 ('TCWISE.v1' label, folder New_Inventory_TC_WiSE_V2, 6 Oct 2025) |
| v1.2 (posted 9 Oct 2025) | HS4 TCWiSE.v3 (Final) | (no row) | PRJ-4392/Hazards/NC_Present_0_v3/NC_Present_0_v3.zip (site link is blank) | Site: 0.044 /hr ('faster decay'); Inventory: 'reduced ... to 0.44' | Possibly CHEER.v4 ('TCWISE.v2' label, folder New_Inventory_TC_WiSE_V3, 23 Oct 2025) |

## Compatibility matrix  <span class="todo">to be confirmed</span>

Which versions have actually been run together. Rows are the regional loss datasets; add a row for every new run.

| Loss dataset | Hazard set | Inventory | Damage model | Scenario probabilities | Date | Location |
|---|---|---|---|---|---|---|
| LOS0 (preCHEER) | preCHEER 97 storms | preCHEER zone inventory | LM0 (Matlab) | preCHEER | 2022 | Drive |
| CHEER.v1 | preCHEER 97 storms | Individual.v1 | CHEERsafe.v1 | to do | 22 Jul 2025 | Drive: New_Inventory_Old_scenarios |
| CHEER.v2 | TCWiSE (labelled v1) | preCHEER | CHEERsafe.v1 | to do | 22 Jul 2025 | Drive: Old_Inventory_New_Hazard |
| CHEER.v3 | TCWiSE (labelled v1) | Individual.v1 | CHEERsafe.v1 | to do | 6 Oct 2025 | Drive: New_Inventory_TC_WiSE_V2 |
| CHEER.v4 | TCWiSE (labelled v2) | Individual.v1 | CHEERsafe.v1 | to do | 23 Oct 2025 | Drive: New_Inventory_TC_WiSE_V3 |
| next | v1.2 (TCWiSE.v3) | NSI joint inventory v1.1 | CHEERsafe.v1 + fixes | pending | - | - |

## Known discrepancies to resolve

1. Hazard datasets carry three naming schemes: the site (v1.0, v1.1, v1.2), the KO Inventory (STORM.v1, TCWiSE.v1, v2, v3 as HS1-HS4) and DesignSafe folders (NC_Present_0_v1, v2, v3). The Regional Loss Data rows use a fourth ('TCWISE.v1', 'TCWISE.v2') that appears to be numbered one behind the scenario tab, and the loss folders (TC_WiSE_V2, V3) a fifth.
2. TCWiSE decay rates disagree by a factor of ten between the site (default 0.0155, chosen 0.044 per hour) and the inventory (0.15 and 0.44), and the inventory describes the change as 'reduced' where the site says 'faster'.
3. TCWiSE.v2 is 'Final' on the Hazards Models tab (TK3) and 'Abandoned' on the Hazard Scenario Data tab (HS3).
4. Storage location is 'TBD/Unknown' for every hazard model configuration, and the site's v1.2 dataset link is empty.
5. The ID 'LM1' is used for both CHEERsafe.v1 and MMH.v1.
6. Rachel's slide assigns H2 (scenario probabilities) to Jingya; the code (probabilistic-hazard-calibration) and the 2025-26 optimization work are Mohammad's.
7. The site still names Hesam Soleimani (emeritus) as contact for FORTUNA, Inventory Data, the deep models and the Inventory-Loss Link; Jingya took over the link in January 2026 and the classifiers have no owner.
8. Scenario probabilities are marked '(to-do)' on every CHEER regional loss dataset (v1-v4), so none is annualizable as recorded.
9. Rachel's slide writes the damage lookup as P(D=d|mcwfp); CHEERsafe.v1 is wind and flood only. Precipitation-based damage is a Year 5 plan.
10. Bug fixes to CHEERsafe (Mar 2026: indexing; hip-roof case) and UF's Sep 2026 modifications have no version entries, contrary to the 25 Mar 2026 instruction.
11. Four inventory tabs are empty: Individual Loss Data, Regional Loss Model, Gov't Thrust Data, Econ Thrust Data. Inventory Model and Inventory Data have three sparse rows each and none of the 2026 inventories (Christoph's NC/TX, Shangjia's joint inventory, Jingya's NSI v1.1).
12. The 'Meetings' tab records inventory-review requests to the Hazards and Buildings thrusts dated 4 May 2026, both still 'Pending'.
