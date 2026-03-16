# AM Radio Receiver: Analog & Digital Signal Processing
**LTI Systems | RF Demodulation | Active Filter Design | Software-Defined Radio**

## Project Overview
This project involved the end-to-end design, simulation, and hardware implementation of an AM radio receiver. The system was developed over five technical stages, transitioning from discrete analog component design (envelope detection and amplification) to a software-defined radio (SDR) implementation using digital signal processing.

---

## Technical Signal Chain

### 1. Envelope Detector (Non-Linear Demodulation)
* **Function:** Recovers the message-containing envelope from the high-frequency AM carrier.
* **Mechanism:** Utilized a half-wave rectifier (diode) and a shunt capacitor (0.1 uF) with a 2k ohm load resistor.
* **Engineering Challenge:** Characterized the non-linear behavior of the diode; when the AM voltage is positive, the capacitor stores charge to track the peak. When the AM voltage is negative, the diode acts as an open circuit and the capacitor discharges through the resistor.

### 2. IF Amplification & Signal Conditioning
* **Operation:** Integrated an Intermediate Frequency (IF) gain stage to boost signals captured by the antenna.
* **Implementation:** Designed an op-amp based amplifier stage with adjustable gain (typically 30x to 50x) to ensure the signal level exceeded the envelope detector's forward voltage threshold.
* **Validation:** Monitored Test Points via oscilloscope to verify the amplified time waveform and frequency spectrum.

### 3. Active Band-Pass Filtering (Selectivity)
* **Function:** Attenuates out-of-band noise and adjacent channel interference.
* **Design:** Built an active filter specifically tuned to isolate the 22.5 kHz to 25 kHz range.
* **Analysis:** Characterized the system’s frequency response H(w), ensuring that fundamental frequencies were preserved while high-frequency harmonics were minimized to prevent aliasing.

### 4. Audio Output Stage
* **Hardware:** Integrated an audio jack and power amplifier to drive loudspeakers.
* **Testing:** Conducted frequency sweeps from 100 Hz to 2000 Hz to validate the auditory response. Successfully tuned into local stations including **WILL 580 kHz** and **WDWS 1400 kHz**.

### 5. Digital Signal Processing (Software Radio)
* **Transition:** Replicated the analog receiver architecture in a digital environment (Software-Defined Radio).
* **Implementation:** Replaced physical inductors and capacitors with digital filters and discrete-time processing algorithms.
* **Comparison:** Analyzed the resemblance between continuous-time signals and their discrete-time counterparts, observing how digital filters approximate the behavior of physical analog components.

---

## Engineering Analysis & Tools
* **Theory:** Applied Fourier Transforms to analyze signals in the frequency domain, specifically identifying the 4 kHz bandwidth of the low-pass output signal.
* **Hardware:** Oscilloscopes (Time-domain and FFT modes), Function Generators, Protoboard circuit integration.
* **Analysis:** Calculated time constants (Delta T approx. 50us) and angular frequencies (approx. 125,700 rad/s) to ensure system stability and audio fidelity.

## Academic Context
This project was completed as part of the **ECE 210: Analog Signal Processing** curriculum at the **University of Illinois at Urbana-Champaign**.
