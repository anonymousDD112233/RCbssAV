# Balancing Robustness and Efficiency in Multi-Agent Combinatorial Path Finding with Sum of Service Time

This repository contains the official code accompanying the AAMAS-2026 submission:  
> **Balancing Robustness and Efficiency in Multi-Agent Combinatorial Path Finding with Sum of Service Time**

It implements the **Robust CBSS framework under the Sum of Service Time (SST) objective**, including both algorithms presented in the paper:
- **$RCbss_{T}SV$** – Strict Verification variant that guarantees the desired robustness  
- **$RCbss_{T}AV$** – Anytime Verification variant that balances robustness and planning efficiency  

The framework extends the **Conflict-Based Steiner Search (CBSS)** to support:
- **SST-based allocation** via a MILP formulation ($CBSS_{SST}$)  
- **K-best allocations** to replace the sequencing step in CBSS  
- **Robust planning** against stochastic execution delays

This repository includes full source code, benchmark data and an experiment scripts to enable **full reproducibility** of the results presented in the paper.


