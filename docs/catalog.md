# Catalog of code and data

Every code object and dataset the framework uses, with where it lives and whom to ask. Status follows the
Knowledge Object Inventory. Repositories marked *private* are visible only to CHEER-Hub members
<span class="todo">to be confirmed: the Feb 2026 catalog listed the STARR repositories and FORTUNA as public; on
21 Sep 2026 they were not visible to outside visitors</span>.

## Code

| Object | Module | Location | Visibility | Lead | Status |
|---|---|---|---|---|---|
| STARR-V0 (baseline framework, Python; Matlab original in `STEER`) | STARR | github.com/CHEER-Hub/STARR-V0 | private | Jingya Wang | Final (Sep 2024) |
| STARR_DBI (dynamic building inventory) | STARR | github.com/CHEER-Hub/STARR_DBI | private | Jingya Wang | Development |
| STARR_gov_model_V1 (five funding designs) | STARR | github.com/CHEER-Hub/STARR_gov_model_V1 | private | Jingya Wang | Development |
| LossModel (CHEERsafe damage model) | D | github.com/CHEER-Hub/LossModel | private | Mohammad Askari (UCLA) | CHEERsafe.v1 final; release awaits licensing |
| Manufactured-home damage model (MMH) | D | in progress on GitHub | private | Christopher Alegbeleye | MMH.v1 final (Oct 2025) |
| CHEERSafe-Vis (hazard visualization app) | D | cheersafe-vis.streamlit.app | public | Mohammad Askari (UCLA) | Live |
| Inventory-Loss-link (V0 archived, V1 live) | I, L | github.com/CHEER-Hub/Inventory-Loss-link | private | Jingya Wang (formerly Hesam Soleimani) | V1 |
| Timeline-Scenario-Reduction | T | [github.com/CHEER-Hub/Timeline-Scenario-Reduction](https://github.com/CHEER-Hub/Timeline-Scenario-Reduction) | public | Jingya Wang | Final (Feb 2026) |
| probabilistic-hazard-calibration (scenario probabilities) | H | github.com/CHEER-Hub/probabilistic-hazard-calibration | private | Mohammad Askari (UCLA) | Development |
| openplaces (footprint inventory pipeline) | I | [docs.openplaces.io](https://docs.openplaces.io/en/latest/3_examples/curate/US_footprint-cheer-2026.html) | public | Christoph Nolte | Delivered NC and TX, Aug 2026 |
| FORTUNA (data fusion, V0) | I | github.com/CHEER-Hub/Fortuna; docs on hesam-92-19.github.io | private | Hesam Soleimani (emeritus) | Superseded |
| Roof-shape and building-type classifiers (V0) | I | Colab notebooks and Drive weights | internal | unassigned | Not integrated |
| Python project templates (bronze, silver, gold) | all | github.com/CHEER-Hub | private | Mohammad Askari (UCLA) | Available |
| MD-Git-Essentials (Markdown and Git tutorial) | all | [cheer-hub.github.io/MD-Git-Essentials](https://cheer-hub.github.io/MD-Git-Essentials/) | public | Mohammad Askari (UCLA) | Available |

## Data

| Dataset | Module | Location | DOI / identifier | Lead | Status |
|---|---|---|---|---|---|
| Hazard scenarios, Eastern NC, present climate, v1.2 (TCWiSE.v3) | H | DesignSafe PRJ-4392/Hazards/NC_Present_0_v3 | PRJ-4392 | Brian Blanton | Final (Oct 2025) |
| Hazard scenarios v1.1 (TCWiSE, default decay) | H | DesignSafe PRJ-4392/Hazards/NC_Present_0_v2 | PRJ-4392 | Brian Blanton | Superseded |
| Hazard scenarios v1.0 (STORM) | H | DesignSafe PRJ-4392/Hazards/NC_Present_0_v1 | PRJ-4392 | Brian Blanton | Superseded |
| preCHEER 97-hurricane set | H | CHEER Google Drive | - | Rachel Davidson | Final (2022) |
| Footprint inventories, NC and TX, pre-imputation | I | CoPe Drive (Buildings) | none yet | Christoph Nolte | Delivered Aug 2026 |
| NSI joint inventory v1.1 (single-family, loss-model ready) | I | path to be recorded | none yet | Jingya Wang | 2026 |
| Joint household-housing inventory, East NC (NSI-based) | I | CoPe Drive (Buildings) | none yet | Shangjia Dong | May 2026, internal |
| Individual.v1 inventory (FORTUNA) | I | Drive: Data Fusion, CHEER-Inventory | - | Hesam Soleimani (emeritus) | Superseded |
| CHEERsafe lookup tables | D | circulated by email; Drive v2 folder | none yet | Mohammad Askari (UCLA) | v1 |
| Regional loss datasets CHEER.v1 to v4 | L | CoPe Drive, Loss Estimates | - | Jingya Wang | Superseded inputs |
| STARR housing projection dataset | STARR | DesignSafe PRJ-4651 | [10.17603/ds2-tnqp-ag38](https://doi.org/10.17603/ds2-tnqp-ag38) | Jingya Wang | Published |
| STARR full-framework dataset | STARR | DesignSafe PRJ-5985 | [10.17603/ds2-n11h-fr68](https://doi.org/10.17603/ds2-n11h-fr68) | Jingya Wang | Published |
| STARR government-model dataset | STARR | DesignSafe PRJ-6106 | [10.17603/ds2-vxbh-cm52](https://doi.org/10.17603/ds2-vxbh-cm52) | Jingya Wang | Published |

The working copy of this catalog is the *CHEER Knowledge Object Inventory* spreadsheet in the CoPe Drive
(Knowledge Framework / STARR to KF). This page should be regenerated from it, not edited by hand, once the
inventory is complete.
