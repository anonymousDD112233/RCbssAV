# Balancing Robustness and Efficiency in Multi-Agent Combinatorial Path Finding with Sum of Service Time

This repository contains the official code accompanying the AAMAS-2026 submission:  
> **Balancing Robustness and Efficiency in Multi-Agent Combinatorial Path Finding with Sum of Service Time**

It implements the **Robust CBSS framework under the Sum of Service Time (SST) objective**, including both algorithms presented in the paper:
- **$RCbss_{T}Strict$** – Strict Verification variant that guarantees the desired robustness  
- **$RCbss_{T}Anytime$** – Anytime Verification variant that balances robustness and planning efficiency  

The framework extends the **Conflict-Based Steiner Search (CBSS)** to support:
- **Optimization under the SST objective ($CBSS_{SST}$)** (instead of SOC) via a MILP-based allocation  
- **Elimination of fixed goal destination requirements** for agents  
- **Robust planning** against stochastic execution delays (Strict & Anytime)

This repository includes full source code, benchmark data and an experiment scripts to enable **full reproducibility** of the results presented in the paper.

---

## Repository Structure

- **Agent_Goal_locations_files/** – Agent and goal locations files for experiments.  
- **ExperimentalResults/** – Processed experimental results from all experiments.  
- **Maps/** – Benchmark maps used in experiments.
- **FindConflict.py** – Detects conflicts between agents’ paths.  
- **LowLevelPlan.py** – Computes individual agent paths under constraints.
- **NodeStateConstClasses.py** – Defines data structures for nodes, states, and constraints.
- **Planner_Configuration.py** - Executes the desired planner configuration, handling the setup logic to launch a complete planning run.
- **RunTest.py** - Framework for running the experiments reported in the paper
- **Run_Simulation.py** - Runs the online execution
- **Verify.py** – Verifies solution robustness using simulations.
- **createMap.py** – Generates agent and goal location for maps.
- **kBestSequencingByService.py** - Finds the $K$-best service-time allocations using MILP.

---

## Requirements & Installation

### Python
- **Python** ≥ 3.10  
- Recommended: **Ubuntu 20.04+** (tested on Ubuntu 24.04, AMD EPYC 7702P, 16 cores)  

---

### External Solvers

This project relies on the **Gurobi Optimizer** for solving the MILP formulations used in allocation and sequencing.  
We employ the official Python interface: `import gurobipy`

#### Installation  
- Download and install Gurobi from the official website: https://www.gurobi.com/  
- Install the Python bindings (usually included with the installer) or via pip install gurobipy once Gurobi is installed.  
- Ensure that the Gurobi license is activated. Academic users can obtain a free academic license directly from Gurobi.  

#### Notes  
- The experiments in the paper were run with Gurobi v11.0.3.  
- Gurobi must be accessible in your PYTHONPATH and properly licensed for the solver to function.  


## Randomization & Seeds
All randomized components are initialized with fixed seeds for reproducibility:
- **Verify.py**: `seed = 47`
- **FindConflict.py**: `seed = 42`
- **Run_Simulation.py**: `seed = 44`

Other components are fully deterministic given identical inputs.
