# Inventory–Loss Link

*Prepared by Hesam Soleimani ); updated by Hesam Soleimani; last updated October 12, 2025. Maintained by the kf\* manager; see [Governance](../governance.md).*

!!! info "Reference page"
    Carried over from the 2024-26 Knowledge Framework site. The module pages under **Workflow** summarize this material; this page keeps the full original for reference.


**Status:** *Functioning*, with ongoing updates planned  

---

# Overview

This document summarizes the **Inventory–Loss Link** module, which executes the **CHEER-Safe** loss model using a **building-by-building** schema derived from the developed inventory system.  

---

## Version Control

The following table tracks the version history of this module, outlines its functionality and objectives, and provides references to detailed documentation and related CHEER resources.

| Version | Main Feature(s) | Key Purpose | Upgrades | Resources |
|----------|-----------------|--------------|-----------|------------|
| **Inventory–Loss Link (V0)** | Region-wide, building-level hurricane damage assessment (including both flood and wind impacts). | The key purposes are:<br>1. Transform the input building inventory into **CHEER-Safe** native archetypes.<br>2. Extract flood depth and wind ratio for each entity.<br>3. Calculate flood, wind, and total losses (in %).<br>4. Transform the loss data structure into a structured object. | – | [GitHub Page (archived as V0, with documentation included)](https://github.com/CHEER-Hub/Inventory-Loss-link/tree/main) *(members only)* |
| **Inventory–Loss Link (V1)** | Region-wide, building-level hurricane damage assessment (including both flood and wind impacts). | Same as V0, with the following changes/improvements:<br>1. In cases of stochastic behavior in the inventory or assigned configuration, perform **random sampling**.<br>2. Transform the loss data structure to align with the [**STARR**](https://github.com/CHEER-Hub/STARR_DBI) *(members only)* framework . | – | [GitHub Page (live and archived as V1)](https://github.com/CHEER-Hub/Inventory-Loss-link/tree/main) *(members only)*<br><br>[Documentation](https://cheer-hub.github.io/Inventory-Loss-link/Data_Fusion.html) *(link no longer works)* |

---
