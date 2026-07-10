# FloorPlanning-using-Stockmeyer
Python implementation of VLSI floorplanning optimization using Stockmeyer Algorithm, HPWL, and Simulated Annealing.
# Area and Wirelength Optimization in VLSI Floorplanning using Stockmeyer, HPWL and Simulated Annealing

![Python](https://img.shields.io/badge/Python-3.x-blue)
![VLSI](https://img.shields.io/badge/Domain-VLSI-green)
![EDA](https://img.shields.io/badge/EDA-Floorplanning-orange)

## Project Overview

Modern VLSI chips contain millions to billions of transistors, making efficient physical design one of the most important stages of IC implementation. During physical design, **floorplanning** determines the placement of functional blocks on a chip. Poor floorplanning leads to larger chip area, longer routing paths, increased power consumption, and degraded performance.

This project presents a **Python-based implementation** of classical VLSI floorplanning optimization techniques that minimize both **chip area** and **interconnect wirelength**. The work combines deterministic and stochastic optimization methods to generate compact and efficient chip layouts.

This project was developed as part of the **CAD for IC Design** course at **Vellore Institute of Technology (VIT), Chennai**.

---

# Problem Statement

Given:

- A set of rectangular circuit blocks
- Block dimensions
- Netlist connecting different blocks
- Polish Expression describing slicing structure

Develop an optimization framework that

- Minimizes silicon area
- Minimizes interconnect wirelength
- Preserves non-overlapping placement
- Produces optimized VLSI floorplans

---

# Objectives

- Generate slicing floorplans from Polish Expressions
- Implement the Stockmeyer Algorithm
- Compute Half-Perimeter Wirelength (HPWL)
- Optimize wirelength using HPWL
- Apply Simulated Annealing to avoid local minima
- Compare different optimization strategies
- Visualize floorplans before and after optimization

---

# Algorithms Used

## 1. Polish Expression

The floorplan is represented using a postfix expression containing

- Block identifiers
- Horizontal cut (H)
- Vertical cut (V)

Example:

```
B3 B7 H B5 B1 V B8 B2 H V B4 V B6 V H
```

The expression is evaluated using a stack to generate the slicing tree.

---

## 2. Stockmeyer Algorithm

The Stockmeyer algorithm computes the optimal slicing floorplan using dynamic programming.

### Purpose

- Minimize total chip area
- Remove dead space
- Generate compact layouts

Area is calculated as

```
Area = Width × Height
```

The algorithm prunes dominated solutions and retains only Pareto-optimal width-height combinations.

---

## 3. Half-Perimeter Wirelength (HPWL)

After obtaining an optimized floorplan, the routing cost is estimated using HPWL.

Formula

```
HPWL = (Xmax − Xmin) + (Ymax − Ymin)
```

HPWL is widely used because it provides a fast approximation of routing length.

---

## 4. Simulated Annealing

Simulated Annealing is a stochastic optimization algorithm inspired by the annealing process in metallurgy.

Instead of accepting only better solutions, SA occasionally accepts worse solutions with a probability

```
P = exp(-ΔCost / Temperature)
```

This helps escape local minima and move toward globally optimized floorplans.

---

## 5. Constrained HPWL Optimization

Unlike unconstrained optimization, constrained HPWL preserves the dimensions obtained from the Stockmeyer floorplan while reducing routing cost.

Advantages

- Fixed chip outline
- Better manufacturability
- Practical floorplanning

---

# Project Workflow

```
Input Blocks
      │
      ▼
Read Polish Expression
      │
      ▼
Generate Initial Floorplan
      │
      ▼
Stockmeyer Optimization
      │
      ▼
HPWL Calculation
      │
      ▼
HPWL Optimization
      │
      ▼
Simulated Annealing
      │
      ▼
Constrained HPWL
      │
      ▼
Performance Comparison
```

---


# Results

## Area Optimization

| Stage | Width | Height | Area |
|--------|-------|--------|------|
| Initial Floorplan | 15 | 12 | 180 |
| Stockmeyer Optimized | 13 | 9 | 117 |

Area Reduction

```
35%
```

---

## Wirelength Optimization

| Method | HPWL |
|----------|------|
| Stockmeyer | 37.0 |
| HPWL Optimization | 31.0 |
| Simulated Annealing | 33.5 |
| Constrained HPWL | 32.5 |

---

# Performance Comparison

| Optimization | Area | HPWL | Total Cost |
|--------------|------|------|------------|
| Stockmeyer | 117 | 37 | 154 |
| HPWL | 117 | 31 | 148 |
| Simulated Annealing | 117 | 33.5 | 150.5 |
| Constrained HPWL | 117 | 32.5 | 149.5 |

---

# Technologies Used

- Python
- NumPy
- Matplotlib
- Object-Oriented Programming
- VLSI Physical Design
- Electronic Design Automation (EDA)

---

# Applications

- ASIC Physical Design
- VLSI CAD Research
- Academic Projects
- Floorplanning
- Physical Design Automation
- Chip Area Optimization
- Routing Optimization

---

# Future Improvements

- Genetic Algorithm based floorplanning
- Particle Swarm Optimization
- Machine Learning assisted floorplanning
- Timing-aware optimization
- Thermal-aware floorplanning
- Routing congestion estimation
- 3D IC floorplanning

---

# References

1. Stockmeyer, P.C. "Optimal Orientations of Cells in Slicing Floorplan Designs."
2. Kirkpatrick et al. "Optimization by Simulated Annealing."
3. Wong and Liu. "A New Algorithm for Floorplan Design."
4. Baker, R.J. *CMOS Circuit Design, Layout and Simulation.*

---

# Authors

**Team Project**

Developed as part of the **CAD for IC Design** course at **Vellore Institute of Technology, Chennai**.

**Team Members**

- M. Ramya Sree
- Tejasvini R.
- R. Sandhyaa
- Jagarakshitha V



This project is released under the MIT License.
