# FloorPlanning-using-Stockmeyer
Python implementation of VLSI floorplanning optimization using Stockmeyer Algorithm, HPWL, and Simulated Annealing.
# Area and Wirelength Optimization in VLSI Floorplanning

A Python implementation of VLSI floorplanning optimization using the Stockmeyer Algorithm, Half-Perimeter Wirelength (HPWL), Simulated Annealing (SA), and Constrained HPWL optimization.

---

## Overview

This project was developed as part of the **CAD for IC Design** course at **VIT Chennai**.

The objective is to optimize VLSI floorplans by reducing

- Silicon Area
- Wirelength
- Overall Cost

using classical Electronic Design Automation (EDA) algorithms.

---

## Features

✔ Stockmeyer Algorithm

✔ Polish Expression Evaluation

✔ Slicing Floorplan Generation

✔ HPWL Calculation

✔ Simulated Annealing Optimization

✔ Constrained HPWL Optimization

✔ Floorplan Visualization

✔ Performance Comparison

---

## Algorithms Used

### Stockmeyer Algorithm

Generates an optimal slicing floorplan by minimizing unused area using dynamic programming.

---

### HPWL

Computes Half-Perimeter Wirelength to estimate routing cost.

HPWL = (Xmax − Xmin) + (Ymax − Ymin)

---

### Simulated Annealing

Explores multiple floorplan configurations to avoid local minima and improve global optimization.

---

### Constrained HPWL

Optimizes routing while preserving the original floorplan dimensions.

---

## Results

| Metric | Before | After |
|---------|--------|-------|
| Area | 180 | 117 |
| Area Reduction | - | 35% |
| HPWL | 37 | 31 |

---

## Folder Structure

src/

Contains all optimization algorithms.

input/

Input block dimensions and netlists.

output/

Generated floorplans and comparison plots.

report/

IEEE paper.

images/

Screenshots used in README.

---

## Technologies

Python

NumPy

Matplotlib

Optimization Algorithms

Electronic Design Automation (EDA)

VLSI Physical Design

---

## Future Improvements

- Genetic Algorithm
- Particle Swarm Optimization
- Routing Congestion Estimation
- Timing-driven Floorplanning
- Power-aware Optimization

---

## Authors

- M. Ramya Sree
- Tejasvini R
- R. Sandhyaa
- Jagarakshitha V

Department of Electronics Engineering

VIT Chennai
