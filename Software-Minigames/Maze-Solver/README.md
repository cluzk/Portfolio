# Recursive Maze Solver
**C | Depth-First Search (DFS) | Backtracking | Memory Management**

## Project Overview
This project is a high-performance maze solver implemented in C. It utilizes a recursive Depth-First Search (DFS) algorithm to find a valid path through a 2D grid, emphasizing efficient stack management and robust memory handling.

## Technical Highlights
* **Recursive DFS Algorithm:** Engineered a recursive solver that explores the maze by systematically attempting moves in four directions (Up, Down, Left, Right). 
* **Backtracking Implementation:** Developed a state-reversal mechanism to handle dead ends. If a path fails to reach the exit, the algorithm "backtracks" by popping the current call from the stack and exploring alternative branches. This ensures an exhaustive search of all possible paths.
* **Path Differentiation:** Implemented logic to distinguish between the final solution path and explored cells that were eventually discarded:
    * **Solution Path:** Marked as the successful route from start to exit.
    * **Visited Cells:** Tracked and marked to prevent redundant processing and infinite loops, proving the algorithm's coverage.
* **Dynamic Memory & File I/O:** * **Resource Allocation:** Parses external maze files to dynamically allocate a custom `maze_t` structure and a 2D character array for the grid.
    * **Memory Integrity:** Implemented a manual teardown function to free all nested memory, ensuring zero memory leaks as verified via **Valgrind**.
* **Base Case Logic:** Optimized the recursion with multiple base cases to handle boundary conditions (grid edges), wall collisions, and state-checking to ensure efficient termination.
