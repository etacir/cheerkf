# H. Hazard scenarios

*Hazards thrust*

## H1. Simulate a large candidate set of hurricanes (H_coarse) on a coarse grid

Generate synthetic present-climate tracks and screen them cheaply for storms that affect the study region.

| | |
|---|---|
| **Inputs** | IBTrACS observed tracks (1980-2024); NOAA monthly SST; landfall decay setting; coarse ADCIRC grid |
| **Outputs** | 1,000-year synthetic track set (11,736 events in the run behind dataset v1.2); coarse-grid surge levels used to pick storms affecting NC and TX |
| **Point person (workflow slide)** | <span class="owner">Hazards thrust</span> |
| **Who did the work (records)** | Brian Blanton (tracks, ADCIRC); Jackson Parker (hazards workflow, per R. Davidson 24 Feb 2026) |
| **Code** | TCWiSE track generator (Nederhoff et al. 2021) and ADCIRC (github.com/adcirc/adcirc). CHEER run scripts and configurations are not in a CHEER repo. |
| **Data** | Final products land in DesignSafe PRJ-4392/Hazards/NC_Present_0_v1, _v2, _v3 (see H3) |
| **Documentation** | cheerkf > Hazards Thrust (v1.0 5 Jun 2024; v1.1; v1.2 9 Oct 2025); KO Inventory tabs 'Hzrds Models' and 'Hzrds Scen Data' |
| **Versions recorded** | Track sets: STORM (abandoned: did not match historical climatology); TCWiSE with default decay (abandoned: winds over land not physical); TCWiSE with faster decay (current). Naming differs between site and inventory; see 'Hazard versions' sheet. |
| **Status** | Current set final for Eastern NC. A new ~10,000-scenario set was awaited as of 10 Feb 2026 (kf* notes). Texas scenarios still needed for the TX loss dataset (Buildings task 9). |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Record scenario-generation settings (grid, retention cutoff), storage paths for model configurations (all 'TBD/Unknown'), and the new scenario set; reconcile version names. **Who:** Brian Blanton; Jackson Parker

*Sources: Davidson slide 2 Sep 2026; cheerkf hazardsthrust.md; KO Inventory (31 Jul 2026); kf* notes 10 Feb 2026; Davidson email 24 Feb 2026*

## H2. Select a small subset H << H_coarse and assign hazard-consistent annual occurrence probabilities P_h (OPS method)

Reduce the ensemble to a tractable set of scenarios whose weighted hazard reproduces the long-term 'true' hazard maps, so losses can be annualized.

| | |
|---|---|
| **Inputs** | Candidate scenarios with wind and flood fields; reference hazard maps (ASCE 7 wind; FEMA flood maps proved a poor match and the flood threshold was adjusted in Nov 2025); matching on wind and coastal flooding only |
| **Outputs** | Selected scenario IDs with P_h; calibration report |
| **Point person (workflow slide)** | <span class="owner">Jingya</span> |
| **Who did the work (records)** | Mohammad Askari (UCLA) wrote and runs the optimization code (weekly meetings with Rachel and Jingya from Oct 2025); method after Apivatanagul et al. 2011 |
| **Code** | github.com/CHEER-Hub/probabilistic-hazard-calibration (KO Inventory ID 'HP', status Development) |
| **Data** | Results circulated by email and Drive; no catalogued dataset |
| **Documentation** | Hurricane Hazard Optimization Report (Drive: Knowledge Framework/Connecting Pieces/Hurricane Probabilities, Jun 2025); Apivatanagul et al. 2011 for the method |
| **Versions recorded** | None named. Every CHEER regional loss row in the KO Inventory marks scenario probabilities '(to-do)'. |
| **Status** | In development; waiting on the new hazard scenario set (Feb 2026); flood-threshold fix Nov 2025 |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Name a version; log the reference maps and settings used; state which loss datasets used which P_h; confirm the point person (slide says Jingya, the code is Mohammad's). **Who:** Mohammad Askari (UCLA); Jingya Wang

*Sources: Davidson slide; KO Inventory 'Hzrds Prob Models' and 'Regional Loss Data' tabs; kf* notes 18 Nov 2025 and 10 Feb 2026; emails 'Hurricane Probabilities' Oct 2025*

## H3. Run the selected H scenarios through the high-resolution hazard models

Produce the wind, surge and inundation, inland flood and precipitation fields the damage model needs, on a common 250 m grid.

| | |
|---|---|
| **Inputs** | Selected tracks; ADCIRC (grid nc_inundation_9.99, GAHM wind, 1 s step, 15 min output); P-CLIPER v1b (precipitation); EF5/CREST with HAND v1b (inland hydrology and inundation) |
| **Outputs** | Per-event CSV on the 250 m CREST grid: longitude, latitude, max wind (open terrain and open water), max/min inundation, accumulated precipitation, max surge; zipped per dataset version |
| **Point person (workflow slide)** | <span class="owner">Hazards thrust</span> |
| **Who did the work (records)** | Brian Blanton (ADCIRC winds and coastal inundation); Chris Szpilka, OU (P-CLIPER, EF5) |
| **Code** | External models: ADCIRC; EF5 (Flamig et al. 2020); P-CLIPER (Geoghegan et al. 2018). CHEER configurations not in a CHEER repo. |
| **Data** | DesignSafe PRJ-4392/Hazards/NC_Present_0_v3/NC_Present_0_v3.zip (current); _v2/ (default-decay TCWiSE run); _v1/NC_Present_0_v1.zip (STORM) |
| **Documentation** | cheerkf hazardsthrust.md (file header, model configuration); KO Inventory 'Hzrds Models' (the most complete tab: version notes, validation, reasons versions were abandoned) |
| **Versions recorded** | P-CLIPER v1a (abandoned) > v1b (final); EF5 v1a (abandoned, DEM discontinuities) > v1b (final, 2025 HAND smoothing) > v2 (development); ADCIRC.v1 row has no details |
| **Status** | Final for Eastern NC present climate |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Fill storage paths for model configurations; complete the ADCIRC row; post the v1.2 dataset link on the site (currently blank); Texas runs. **Who:** Brian Blanton; Chris Szpilka

*Sources: cheerkf hazardsthrust.md; KO Inventory 'Hzrds Models' and 'Hzrds Scen Data'*
