# Dental Clinic Queuing System Simulation
[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org)
[![SimPy](https://img.shields.io/badge/SimPy-4.1-success)](https://simpy.readthedocs.io)
[![License](https://img.shields.io/badge/License-MIT-yellowgreen)](LICENSE)

--
**ASSIGNMENT 2 – FINAL PHASE | CO3007 – Performance Evaluation of Computer Systems**  
**Team: Shadow Gambit** | November 2025
--
## Project overview

This project implements a **discrete-event simulation** of a modern dental clinic using **SimPy**. The system consists of three sequential service stages with branching:

- **Reception** : M/M/2 (2 receptionists)
- **Examination** : M/M/3 (3 doctors)
- **Treatment** : M/M/2 (2 dental chairs) – only 30% of examined patients require treatment

**Objectives**

- Analyze system performance under various load conditions
- Identify bottlenecks during peak hours
- Compare simulation results with analytical M/M/c theory
- Recommend scaling strategies to maintain acceptable waiting times

## Simulated Scenarios

| Scenario               | Arrival Rate λ (patients/hour) | Key Observations                                | Conclusion                                    |
| ---------------------- | ------------------------------ | ----------------------------------------------- | --------------------------------------------- |
| Low Load               | 5                              | Almost no queue, server utilization < 30%       | Resources underutilized                       |
| Normal Load (Design)   | 10                             | Stable operation, avg. wait < 6 min             | Optimal operating condition                   |
| Peak Load              | 20                             | Severe congestion at Examination & Treatment    | Additional staff/chairs required              |
| Very High Load         | 30                             | Queue explosion, high rejection rate            | System collapses without expansion            |
| Capacity-Limited Queue | 15 + finite waiting room       | Rejection rate surges when queue is full        | Physical space limitation impacts performance |
| Scaling Solution       | 20 + extra resources           | Add 1 doctor & 1 chair → wait time drops 50–70% | Effective and practical solution              |

## Key Features

- Accurate **discrete-event simulation** using SimPy
- Real-time monitoring: queue length, server utilization, patient-level statistics
- Full comparison with M/M/c analytical formulas (error < 6%)
- Beautiful ANSI-colored console output ([SUCCESS], [INFO], [WARN])
- Rich visualizations: queue evolution over time, waiting time histograms
- Automated scenario reports with theoretical vs simulation comparison

## How to Run

```bash
# Clone the repository (if applicable)
git clone https://github.com/DgHnG36/System-Performance-Eval-ProjectHCMUT-251.git
cd System-Performance-Eval-ProjectHCMUT-251

# Install dependencies
pip install simpy numpy matplotlib pandas seaborn

# Launch the notebook
jupyter notebook "ASS2-FINAL-PHASE.ipynb"
```
