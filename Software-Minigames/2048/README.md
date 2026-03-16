# 2048
**C | Dynamic Memory Allocation | Game Logic | UIUC ECE 220**

## Project Overview
This project is a C implementation of the puzzle game 2048, developed for variable-sized grids. It focuses on implementing complex state-update algorithms, handling directional input, and managing dynamic memory for game structures.

## Technical Highlights
* **Dynamic Grid Management:** Designed a `game` data structure that supports variable dimensions (rows x columns). Managed memory allocation and deallocation for the game board to ensure no memory leaks during resets or re-initializations.
* **Tile-Sliding & Merging Algorithm:** Engineered a deterministic movement engine for all four directions (Up, Down, Left, Right). The algorithm handles two primary phases per move:
    * **Sliding:** Shifting all non-empty tiles as far as possible in the target direction.
    * **Merging:** Combining adjacent tiles of equal value into a single tile of their sum.
* **Collision Constraint Logic:** Implemented a "single-merge" rule per turn, ensuring that a newly merged tile cannot combine with another tile in the same move, mirroring the original game’s mechanics.
* **State Validation:** Developed a `legal_move_check` function to determine if the game has reached a "Game Over" state by verifying if any empty cells remain or if any adjacent tiles can still be merged.
* **Pointer-Based Access:** Utilized a `get_cell` helper function to safely access 1D array elements as 2D coordinates, including boundary checking to prevent segmentation faults.

## Game Rules Implemented
1. **Movement:** Tiles slide in the chosen direction until they hit the edge or another tile.
2. **Merging:** If two tiles of the same number collide, they merge into one (e.g., 2 + 2 = 4).
3. **Score Tracking:** The score is updated in real-time based on the sum of merged tiles.
4. **Termination:** The game ends when no legal moves (slides or merges) are possible.
