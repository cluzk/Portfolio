# Clap-Activated Driving Car
**Analog Circuit Design | Signal Conditioning | Power Electronics**

## Project Overview
This project involved the design and implementation of an autonomous robotic car that defaults to forward motion and reverses for a precise duration of 5–10 seconds upon detecting a loud acoustic trigger. The system is built entirely from analog subcircuits, integrating sound sensing, signal amplification, timing logic, and motor control without the use of a microcontroller.


---

## System Architecture & Subcircuits

### 1. Microphone & Op-Amp (Signal Capture)
* **Transduction:** Uses an electret microphone with an internal JFET to capture acoustic vibrations.
* **Amplification:** Raw microphone output (~200–400mV) is processed through an **LM358 inverting operational amplifier** with a gain of **-30x**.
* **Outcome:** Converts a small acoustic spike into a ~7V signal capable of triggering subsequent MOSFET logic.

### 2. Peak Detector (Signal Conditioning)
* **Function:** Processes the brief amplifier spike into a momentary voltage pulse compatible with the timing circuit.
* **Mechanism:** Utilizes a diode and capacitor to "capture" the voltage peak. A parallel resistor is tuned to control the discharge rate, ensuring the pulse stays above the MOSFET threshold long enough to trigger the timer.

### 3. Timed Reactor (Timing Logic)
* **Core Logic:** Uses the charging/discharging characteristics of an **RC circuit** paired with a **CD40106B Schmitt-Trigger Inverter**.
* **Implementation:** Using a **100µF capacitor** and **100kΩ resistor**, a time constant of ~10s was achieved, resulting in a measured reverse duration of **8.9 seconds**.

### 4. H-Bridge (Directional Control)
* **Configuration:** A bridge of four MOSFETs acts as switches to alternate current paths through the DC motors.
* **Logic:** When the timed reactor signal is "High," one diagonal pair of MOSFETs activates to reverse the motor; when "Low," the other pair moves the car forward.

### 5. Speed Control (PWM)
* **Modulation:** Implements **Pulse-Width Modulation (PWM)** via a Schmitt-trigger oscillator connected to the H-bridge enable (EN) pin.
* **Adjustability:** A **100kΩ potentiometer** allows for manual adjustment of the duty cycle, providing variable speed control and velocity tuning.

---

## Testing & Validation
* **Oscilloscope Analysis:** Verified signal integrity across all stages, specifically the 7V amplified clap spike and the 8.9s timing window.
* **Troubleshooting:** Resolved integration issues such as common-grounding errors between the amplifier and peak detector stages.
* **Success:** The final build successfully meets all design requirements, automatically reverting to forward motion after the timed interval.

## Academic Context
This project was completed as part of the **ECE 110** curriculum at the **University of Illinois at Urbana-Champaign**. Final performance was validated through transient response analysis and physical demonstration.

