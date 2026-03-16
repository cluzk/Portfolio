# Game of Life (Cellular Automata)
**C | 2D-to-1D Array Mapping | State Machines | UIUC ECE 220**

## Project Overview
This project is a C implementation of John Conway’s "Game of Life," a cellular automaton where complex patterns emerge from simple binary rules. The simulation runs in the terminal, processing generations of "cells" based on their local neighbors.

## Technical Highlights
* **1D Array Mapping:** Optimized memory access by representing a 2D game board using a single-dimensional array. Implemented the mapping logic: Index = (Row * Width) + Column.
* **Neighbor Detection Logic:** Developed an efficient `countLiveNeighbor` function using nested loops and boundary-check logic to scan the 8-cell Moore neighborhood (horizontal, vertical, and diagonal).
* **Pure Function Generation:** Ensured each generation is a pure function of the preceding one by calculating state transitions simultaneously across the entire board, preventing updated cells from influencing neighbors within the same "tick."
* **Stability Detection:** Built a predictive `aliveStable` function that compares the current board to the calculated next state to determine if the system has reached a "steady state," allowing the simulation to terminate automatically.

## Rules of Simulation
1. **Under-population:** Any live cell with < 2 live neighbors dies.
2. **Survival:** Any live cell with 2 or 3 live neighbors lives on.
3. **Over-population:** Any live cell with > 3 live neighbors dies.
4. **Reproduction:** Any dead cell with exactly 3 live neighbors becomes a live cell.
