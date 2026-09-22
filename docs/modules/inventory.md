# I. Household-housing inventory

*Buildings thrust*

## I0. Earlier inventory versions (reference)

Record the inventories that earlier loss datasets were built on, so results remain traceable.

| | |
|---|---|
| **Inputs** | preCHEER: zone-based inventory (census tracts). Individual.v1: NSI + FEMA + Microsoft footprints fused by FORTUNA, attributes from roof and building-type classifiers. Dynamic.v1: Caroline Williams projection. |
| **Outputs** | IDAT0 preCHEER (GitHub CHEER-Hub/LossModel/Inputs); Individual.v1 building-level inventory (Drive 'Data Fusion' and 'CHEER-Inventory' folders); Dynamic.v1 (location TBD) |
| **Point person (workflow slide)** | <span class="owner">n/a</span> |
| **Who did the work (records)** | Hesam Soleimani (emeritus) for FORTUNA and Individual.v1; Caroline Williams (departed) for Dynamic.v1 |
| **Code** | github.com/CHEER-Hub/Fortuna (V0, data fusion); classifiers as Colab notebooks (see I3) |
| **Data** | Drive: Data Fusion directory (by FIPS) and CHEER-Inventory directory (links on cheerkf inventory_data.md) |
| **Documentation** | cheerkf > Building Inventory Generator (FORTUNA), > Inventory_Data (both Oct 2025); Inventory Data Dictionary (Google Sheet) |
| **Versions recorded** | FORTUNA V0; Inventory Data V0; KO Inventory rows IDAT0, Dynamic.v1, Individual.v1 (sparse) |
| **Status** | Superseded for new losses: on 17 Feb 2026 the team chose Shangjia's NSI-based inventory because parts of the Individual.v1 workflow (image acquisition, imputation code) could not be reproduced |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Mark these rows as superseded with the reason; keep them for provenance of CHEER.v1, v3, v4 loss datasets. **Who:** KF team

*Sources: cheerkf fortuna.md, inventory_data.md, deep_m.md; KO Inventory 'Inventory Data' tab; Zoom summary of kf* meeting 17 Feb 2026*

## I1. Create a basemap of building footprints with basic variables

Establish the canonical list of buildings for the study region, with occupancy, stories, year built, value and location, and provenance for each attribute.

| | |
|---|---|
| **Inputs** | Building footprints (Microsoft/Overture), NSI, county assessor parcels, permit data, CHEER summer-scholar labels, UCLA CHEER Inventory v0 for roof shape and foundation |
| **Outputs** | Pre-imputation footprint inventory for Eastern NC (18 Aug 2026) and Texas (26 Aug 2026): canonical table plus _point, _geo and _evidence sidecars |
| **Point person (workflow slide)** | <span class="owner">Christoph</span> |
| **Who did the work (records)** | Christoph Nolte (BU) |
| **Code** | openplaces pipeline (public repo; stages ingest > harmonize > enrich > curate) |
| **Data** | CoPe Drive folder 1x7Ns775WM7C5Gu7zqF-xggPqYEAXnmqu (NC and TX pre-imputation) |
| **Documentation** | docs.openplaces.io > 'U.S. footprint inventory (CHEER)' 2026: data description, pipeline, output columns, provenance, validation |
| **Versions recorded** | Not yet named in the KO Inventory. R. Davidson asked on 24 Aug 2026 that it be logged as a distinct version (no reply on the thread). |
| **Status** | Delivered pre-imputation; imputation handed to Mohammad |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Add rows to 'Inventory Model' and 'Inventory Data' tabs: version name, date, what it does and does not include, difference from earlier inventories, storage path, documentation link. **Who:** Christoph Nolte (with the KF team)

*Sources: Emails 'Footprint inventory delivered' 18-26 Aug 2026; docs.openplaces.io page; Davidson slide*

## I2. Impute missing values for the basic variables

Fill gaps in the footprint inventory (stories, year built, roof shape and similar) so every building carries the attributes the damage model needs.

| | |
|---|---|
| **Inputs** | Pre-imputation inventory (I1) and its evidence sidecars |
| **Outputs** | Imputed inventory (not yet delivered in the material read) |
| **Point person (workflow slide)** | <span class="owner">Mohammad</span> |
| **Who did the work (records)** | Mohammad Askari |
| **Code** | 'mice' imputation workflow being set up (Aug 2026); no repo recorded |
| **Data** | None yet |
| **Documentation** | None yet |
| **Versions recorded** | None |
| **Status** | In progress since Aug 2026 |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Repo, documentation and version name; record the imputation model and the variables imputed. **Who:** Mohammad Askari

*Sources: Nolte email 18 Aug 2026; Davidson slide*

## I3. Add variables derived from image processing (roof shape, building type)

Derive attributes that records do not provide: roof shape from satellite imagery and building type from street view, because the damage lookup is keyed on them.

| | |
|---|---|
| **Inputs** | Satellite tiles; street-view images (the free Microsoft imagery plan ended Sep 2025; replacement source unresolved) |
| **Outputs** | Roof shape (9 classes) and building-type labels per building |
| **Point person (workflow slide)** | <span class="owner">? (unassigned on the slide)</span> |
| **Who did the work (records)** | Hesam Soleimani built the classifiers (emeritus); Mohammad holds the training data and model weights; BRAILS++ integration is the Year 5 plan |
| **Code** | Roof Classifier V0 and Building Type Classifier V0: Colab notebooks and Drive weights, not in a repo; BRAILS++ (NHERI SimCenter) external |
| **Data** | Training data on Drive (links on cheerkf deep_m.md) |
| **Documentation** | cheerkf > Developed Deep Models (Oct 2025) |
| **Versions recorded** | V0 for each classifier |
| **Status** | Not integrated into any pipeline; no owner |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Assign an owner; decide between re-running the classifiers and BRAILS++; move notebooks and weights into a CHEER-Hub repo and DesignSafe. **Who:** ET to assign (Mohammad is the natural candidate)

*Sources: cheerkf deep_m.md; Zoom summary 17 Feb 2026; Year 4 annual report plans; emails 'CHEER's next source of satellite imagery' Sep 2025*

## I4. Assign building type m and resistance level c to each building

Map each building to the CHEERsafe archetypes (m) and resistance combinations (c) that the lookup tables use; sample c where it is uncertain.

| | |
|---|---|
| **Inputs** | Imputed inventory with roof shape, stories, garage, year built, value, distance to coast; NSI joint inventory |
| **Outputs** | Loss-model-ready inventory, e.g. nsi_joint_inventory_v1p1.parquet (single-family, wood frame, five roof shapes; EPSG:4326) |
| **Point person (workflow slide)** | <span class="owner">Jingya?</span> |
| **Who did the work (records)** | Jingya Wang (took over the Inventory-Loss Link from Hesam in Jan 2026) |
| **Code** | github.com/CHEER-Hub/Inventory-Loss-link (V0 archived; V1 live: random sampling of uncertain attributes, STARR-aligned output); Jingya's NSI processing script (location not recorded) |
| **Data** | Joint_HH_Inventory_NSI_East_NC_V1.parquet > inventory_for_loss_model.parquet > nsi_joint_inventory_v1p1.parquet (paths not recorded) |
| **Documentation** | cheerkf > Inventory_Loss Link (Oct 2025); > NSI Joint Inventory v1.1 Processing (2026); Inventory Data Dictionary |
| **Versions recorded** | Inventory-Loss Link V0, V1; NSI Joint Inventory v1.1 |
| **Status** | Functioning. NSI v1.1 covers single-family homes only; manufactured and multi-family units are excluded. |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Record storage paths; archetype assignment for MMH and low-rise multifamily (Christopher); Texas resistance levels (UF); update the site contact (still lists Hesam). **Who:** Jingya Wang; Christopher Alegbeleye; Duzgun Agdas and David Prevatt

*Sources: cheerkf inventory_loss_link.md and nsi_inventory_processing.md; Buildings task list (R. Davidson, 25 Nov 2025) in the KO Inventory*

## I5. Attach households to each building

Create the joint household-housing inventory so that losses can be disaggregated by household type, including renters.

| | |
|---|---|
| **Inputs** | NSI-based building inventory; synthetic population (ACS 2018-2022) |
| **Outputs** | East NC joint household-housing inventory (NSI-based), shared 19 May 2026 for CHEER internal use |
| **Point person (workflow slide)** | <span class="owner">Shangjia</span> |
| **Who did the work (records)** | Shangjia Dong (UD) with Qiuyuan Xiao and Rachel Davidson |
| **Code** | Not catalogued (methods are described in two papers listed as written on the Buildings task list) |
| **Data** | Drive file 15fzxN-... linked in S. Dong's 19 May 2026 email |
| **Documentation** | Two papers in preparation (synthetic population; joint inventory method). Shangjia agreed on 20 May 2026 to link the inventory in the KF. |
| **Versions recorded** | NSI-based v1 (East NC). Planned: a version built on the footprint inventory (Christoph), a more efficient method, and Texas. |
| **Status** | Delivered internally; not in the KO Inventory |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Add to the 'Inventory Data' tab with code location and a version definition. **Who:** Shangjia Dong

*Sources: Emails 'Joint Housing-household inventory - East NC' 19-20 May 2026; Buildings task list items 10-11*
