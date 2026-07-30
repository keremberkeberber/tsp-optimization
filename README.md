# Traveling Salesman Problem (TSP) Optimization: 2.5-Opt vs. Ant Colony Optimization

This repository contains Python implementations of heuristic algorithms developed to solve Traveling Salesman Problem (TSP), including a test case with 10 instances each with 20 cities.

The project compares a **Two-Phase Heuristic (Farthest Insertion + 2.5-Opt)** against an **Ant Colony Optimization (ACO)** metaheuristic using Euclidean distance metrics.

## Implemented Algorithms

### 1. Two-Phase Heuristic (`2.5_opt_heuristic.py`)
* **Phase 1 (Farthest Insertion):** Constructs an initial closed tour starting from the origin depot (0, 0) by selecting cities with the largest minimum-distance to the current path.
* **Phase 2 (2.5-Opt Local Search):** Performs steepest-descent local search combining 2-opt (edge reversals) and Or-opt (reinserting 1, 2, or 3 consecutive nodes) to remove edge crossings.
* **Tie-Breaking & Verification:** Fully deterministic execution with zero variation across runs. Features an optional internal `--verify` check that asserts delta-gain bookkeeping against full tour recalculations.
* **Pure Python:** Implemented strictly using the Python standard library (`math`, `csv`, `time`) without external solvers.

### 2. Ant Colony Optimization (`ant_colony_optimization_heuristic.py`)
* **Swarm Intelligence:** Probabilistic metaheuristic utilizing artificial ants, pheromone updates, and evaporation ($\alpha=1$, $\beta=5$, $\rho=0.5$).
* **Vectorized Computations:** Utilizes `numpy` and `pandas` for efficient matrix calculations and runtime tracking.

## Requirements
* **Python 3.x**
* **Standard Libraries:** `math`, `csv`, `time`, `collections`
* **Data Science Libraries:** `numpy`, `pandas`
