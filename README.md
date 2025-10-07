# Balancing Robustness and Efficiency in Multi-Agent Combinatorial Path Finding with Sum of Service Time

This repository contains the official code accompanying the AAMAS-2026 submission:  
> **Balancing Robustness and Efficiency in Multi-Agent Combinatorial Path Finding with Sum of Service Time**

It implements the **Robust CBSS framework under the Sum of Service Time (SST) objective**, including both algorithms presented in the paper:
- **$RCbss_{T}SV$** – Strict Verification variant that guarantees the desired robustness  
- **$RCbss_{T}AV$** – Anytime Verification variant that balances robustness and planning efficiency  

The framework extends the **Conflict-Based Steiner Search (CBSS)** to support:
- **Optimization under the SST objective ($CBSS_{SST}$)** (instead of SOC) via a MILP-based allocation  
- **Elimination of fixed goal destination requirements** for agents  
- **Robust planning** against stochastic execution delays

This repository includes full source code, benchmark data and an experiment scripts to enable **full reproducibility** of the results presented in the paper.

---

## Repository Structure

- **Agent_Goal_locations_files/** – Agent and goal locations files for experiments.  
- **ExperimentalResults/** – Processed experimental results from all experiments.  
- **Maps/** – Benchmark maps used in experiments.
- **FindConflict.py** – Detects conflicts between agents’ paths.  
- **LowLevelPlan.py** – Computes individual agent paths under constraints.
- **NodeStateConstClasses.py** – Defines data structures for nodes, states, and constraints.
- Robust_Planner.py
- RunTest.py
- Run_Simulation.py
- **Verify.py** – Verifies solution robustness using simulations.
- **createMap.py** – Generates agent and goal location for maps.
- kBestSequencingByService.py

---

## Requirements & Installation

### Python
- **Python** ≥ 3.10  
- Recommended: **Ubuntu 20.04+** (tested on Ubuntu 24.04, AMD EPYC 7702P, 16 cores)  

### External Solvers


## Randomization & Seeds
All randomized components are initialized with fixed seeds for reproducibility:
- **Verify.py**: `seed = 47`
- **FindConflict.py**: `seed = 42`
- **Run_Simulation.py**: `seed = 44`

Other components are fully deterministic given identical inputs.
