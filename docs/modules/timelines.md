# T. Time series of losses

*Integration thrust*

## T1. Simulate N_large multi-year hurricane time series (20 periods per year)

Turn per-event losses into long-term (30-year) event-loss timelines for STARR's annual time step.

| | |
|---|---|
| **Inputs** | Scenario set with P_h (H2); per-scenario losses (L1) |
| **Outputs** | Large ensemble of 30-year event-loss timelines |
| **Point person (workflow slide)** | <span class="owner">Jingya</span> |
| **Who did the work (records)** | Jingya Wang |
| **Code** | github.com/CHEER-Hub/Timeline-Scenario-Reduction (public; one Jupyter notebook) |
| **Data** | Notebook outputs; not catalogued |
| **Documentation** | Repo README and notebook; KO Inventory 'Hzrds Prob Models' (ID 'SR') |
| **Versions recorded** | SR final (1 Feb 2026), implemented on preCHEER inputs, compatible with any version |
| **Status** | Final |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Record which scenario set, P_h and loss set each timeline release used. **Who:** Jingya Wang

*Sources: KO Inventory; KF Content Catalog; STARR flowchart 2024 (2,000 30-year scenarios)*

## T2. Select a subset N << N_large of timelines with the OPS-based method and assign P_s

Reduce the timeline ensemble to a set STARR can run while preserving the loss distribution.

| | |
|---|---|
| **Inputs** | Timeline ensemble (T1) |
| **Outputs** | Reduced set (e.g. 2,000 30-year scenarios) with occurrence probabilities P_s |
| **Point person (workflow slide)** | <span class="owner">Jingya</span> |
| **Who did the work (records)** | Jingya Wang |
| **Code** | Same repo as T1 |
| **Data** | Not catalogued |
| **Documentation** | Same as T1 |
| **Versions recorded** | Same as T1 |
| **Status** | Final |

!!! warning "Open item <span class="todo">to be confirmed</span>"
    Same as T1. **Who:** Jingya Wang

*Sources: As T1*
