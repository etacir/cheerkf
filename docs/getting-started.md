# Getting started  <span class="todo">to be confirmed</span>

This page will walk a new user through running the framework end to end on the Eastern North Carolina test case.
The steps below are the intended structure; each needs to be written by the module lead named.

1. **Get access.** Request membership of the CHEER-Hub GitHub organization and the DesignSafe project PRJ-4392
   (cheer-hub@udel.edu). Outside users: see [Governance](governance.md) for the release status.
2. **Set up an environment.** Python 3.11 or later; each repository lists its own requirements. *(Mohammad Askari (UCLA))*
3. **Download a hazard dataset.** DesignSafe PRJ-4392/Hazards/NC_Present_0_v3. *(Brian Blanton)*
4. **Download or build an inventory.** NSI joint inventory v1.1 for a quick start; openplaces plus imputation for a
   new region. *(Jingya Wang, Christoph Nolte)*
5. **Run CHEERsafe** on the inventory for one scenario. *(Mohammad Askari (UCLA))*
6. **Compute losses** for all scenarios with the Inventory-Loss Link. *(Jingya Wang)*
7. **Build timelines** with Timeline-Scenario-Reduction. *(Jingya Wang)*
8. **Run STARR-V0** and read the outputs. *(Jingya Wang)*

Until the write-ups exist, the best entry points are the STARR-V0 repository README and the
[Markdown and Git tutorial](https://cheer-hub.github.io/MD-Git-Essentials/).
