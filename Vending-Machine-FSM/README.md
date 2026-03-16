# Vending Machine Controller: Finite State Machine
**Digital Logic Design | Sequential Circuit Implementation | FPGA & TTL Hardware**

## Project Overview
This project involved the design and hardware implementation of a Finite State Machine (FSM) that controls a vending machine. The system manages coin inputs (Nickels, Dimes, Quarters), tracks the current balance through state transitions, and determines whether to **Accept (A)** a coin or **Dispense (P)** a product based on a specific pricing logic.

The project spanned two phases: a software-based verification in **Xilinx Vivado** and a physical hardware build using **TTL logic chips** and **D-Flip-Flops**.

---

## Technical Specifications

### 1. FSM Design & State Logic
The controller was designed as a 3-bit state machine (S2, S1, S0) to track various amounts of currency previously and currently inserted.
* **Inputs:** N (Nickel), D (Dime), Q (Quarter).
* **Outputs:** * **A (Accept):** Logic high if the inserted coin is valid for the current state.
    * **P (Product):** Logic high when the total balance reaches or exceeds the product price.
* **Logic Optimization:** Transition and output logic were optimized using **Karnaugh Maps (K-Maps)** and implemented exclusively using NAND, NOR, and NOT gates to minimize chip count.

### 2. Physical Hardware Implementation (Protoboard)
* **Storage Elements:** Utilized **7474 (Dual D-Flip-Flops)** or **74175 (Quad D-Flip-Flops)** to store the 3-bit state, synchronized by a common clock signal.
* **Combinational Logic:** Integrated various TTL DIP chips (7400, 7402, 7404) to calculate the "Next State" logic and output signals.
* **Debugging & UI:** * **LEDs:** Used to visualize state bits (S2S1S0) and system outputs (A, P) in real-time.
    * **Debounced Inputs:** Managed coin triggers via tactile switches.

### 3. Digital Verification (SDR & Vivado)
* **Platform:** Xilinx Vivado.
* **Simulation:** Verified the FSM transitions through a custom testbench, ensuring that sequential logic handled edge cases (such as rejecting coins once the dispense state is reached).
* **Waveform Analysis:** Validated timing constraints, ensuring the state updated correctly on the positive edge of the clock (rising edge).

---

## Engineering Skills Demonstrated
* **Sequential Logic:** Experience with synchronous state transitions and timing requirements (setup/hold times).
* **Schematic Mastery:** Translated complex boolean expressions into physical wiring diagrams with pin-to-chip assignments.
* **Hardware Troubleshooting:** Isolated issues in combinational logic paths and resolved signal integrity problems on a physical breadboard.
* **HDL Simulation:** Functional verification of digital hardware using industry-standard tools.

## Tools & Components
* **Hardware:** 74-series TTL ICs (NAND, NOR, NOT, D-FF), LEDs, Potentiometers, Breadboard.
* **Software:** Xilinx Vivado (Logic Simulation), GitHub (Version Control).

## Academic Context
This project was a core component of the digital systems curriculum at the **University of Illinois at Urbana-Champaign**, focusing on the transition from boolean theory to physical hardware realization.
