# Project-Quicksilver

### Final Project (RC Car) :car: 

### Introduction:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This project details the design and construction of a compact RC Robot engineered for high-performance competition in both agility (RC Cup) and strength (RC Soccer) categories. Adhering to strict dimensional constraints—10 cm width, 15 cm length, and 12 cm height—and a weight limit of 1kg, the robot leverages a four-wheel-drive configuration to maximize traction and maneuverability.

&nbsp;&nbsp;&nbsp;&nbsp;At its core, the system utilizes a Type C ESP32 Development Board for wireless communication, programmed via the Arduino environment. This allows for real-time control through a smartphone interface. To translate these signals into movement, an L298N Dual H-Bridge motor driver manages the power distribution to four Micro Metal DC Gear Motors (N20). These motors were selected for their high torque-to-size ratio, which is essential for the "Strength" requirements of the competition.

&nbsp;&nbsp;&nbsp;&nbsp;The chassis is built on a custom acrylic base, providing a rigid yet lightweight frame to house the battery pack and delicate wiring. Assembly involved precise soldering and modular wire management using zip ties and electrical tape to ensure electrical reliability during high-impact maneuvers. By integrating hardware efficiency with responsive software control, this RC robot serves as a robust platform for competitive robotics.
</p>

---

### Objectives:
* **Dimensional Compliance**: Design and assemble a chassis that remains under the $10 \text{ cm} \times 15 \text{ cm} \times 12 \text{ cm}$ size limit
* Observe and analyze the functional relationship between binary input data and the resulting modulated waveforms.
* Execute signal demodulation using techniques such as envelope detection, filtering, and product detection.
* Restore distorted analog signals back into clean digital square waves using comparator circuits.
* Evaluate system performance against interference, synchronization requirements, and spectral efficiency.

---

### Explanations of Project:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The robot's "brain" is an ESP32 Development Board, which receives directional commands via Bluetooth. These signals are processed in the loop() function to determine motor polarity and speed. Since the ESP32 pins cannot provide enough current to drive motors directly, an L298N Dual H-Bridge module acts as the power intermediary, drawing energy from the battery pack to drive the four N20 motors. The code uses PWM (Pulse Width Modulation) via the ledcWrite function to control the speed of the motors, allowing for smooth acceleration and precise turning.
</p>

---

<details>
<summary>FINAL PROJECT - RC Car</summary> 

**INTRODUCTION**
* This project involves the development of a compact, four-wheel-drive RC robot designed for the RC Cup (Agility) and RC Soccer (Strength) competitions. Built on a Type C ESP32 platform, the robot utilizes high-torque N20 micro gear motors and an L298N driver to meet strict size ($10 \times 15 \times 12$ cm) and weight ($1$ kg) requirements.

**EXPLANATION**
* The experiment highlights how digital information can be mapped onto an analog carrier for transmission. It provides a practical look at how hardware components like rectifiers and filters act as an envelope detector to recover the message. A key lesson is the necessity of using a comparator to fix signal degradation, as filtering inherently rounds the edges of the digital pulses.

<details><summary><b>[View EXPERIMENT 15 - Amplitude Shift Keying Details]</b></summary><br>https://github.com/EmmanAbad/Laboratory-Heretic/blob/main/EXPERIMENT%2015%20-%20Amplitude%20Shift%20Keying.md<br></details>

</details>

---

<details>
<summary>EXPERIMENT 16 - Frequency Key Shifting</summary> 

**INTRODUCTION**
* Frequency Shift Keying is a modulation method where the frequency of a carrier wave is varied in accordance with digital binary signals. The system toggles between a "Mark" frequency for logic 1 and a "Space" frequency for logic 0. This experiment explores the FM-based nature of FSK, which provides better noise immunity than amplitude-based methods because the receiver can ignore amplitude fluctuations.
  
**EXPLANATION**
* This laboratory session demonstrated the role of frequency variation in carrying digital information. It successfully showed that complex digital signals can be recovered using relatively simple components like filters and threshold detectors. A major takeaway was the importance of signal conditioning to ensure data integrity, especially in identifying the distinct frequency shifts at the receiver.

<details><summary><b>[View EXPERIMENT 16 - Frequency Key Shifting Details]</b></summary><br>https://github.com/EmmanAbad/Laboratory-Heretic/blob/main/EXPERIMENT%2016%20-%20Frequency%20Shift%20Keying.md<br></details>

</details>

---

<details>
<summary>EXPERIMENT 17 - Binary Phase Shift Keying</summary> 

**INTRODUCTION**
* Binary Phase Shift Keying is a sophisticated modulation scheme where the phase of a constant-amplitude carrier is shifted by 180 degrees to represent binary data. Unlike ASK or FSK, BPSK maintains a constant frequency and amplitude, making it highly robust against noise. The experiment examines the circuitry required to modulate and then demodulate these signals using product detection.

**EXPLANATION**
* The experiment highlights the efficiency of phase-based communication. It shows that while the carrier frequency and amplitude remain static, the information encoded in the phase shifts provides a resilient way to transmit data. Seeing the rounded output of the low-pass filter taught a practical lesson on how bandwidth limitations affect signal integrity and how a comparator can restore that accuracy.

<details><summary><b>[View EXPERIMENT 17 - Binary Phase Shift Keying Details]</b></summary><br>https://github.com/EmmanAbad/Laboratory-Heretic/blob/main/EXPERIMENT%2017%20-%20Binary%20Phase%20Shift%20Keying.md<br></details>

</details>

---

<details>
<summary>EXPERIMENT 18 - Quadrature Phase Shift Keying</summary> 

**INTRODUCTION**
* Quadrature Phase Shift Keying is an advanced variation of BPSK that transmits two bits per symbol by utilizing four distinct phase states. By employing orthogonal carriers (90 degrees apart), QPSK can transmit at twice the rate of BPSK within the same radio-frequency bandwidth. This experiment explores serial-to-parallel conversion and the summation of orthogonal carriers.

**EXPLANATION**
* This session illustrated the transition from serial data to a multi-phase modulated signal. The primary takeaway is that QPSK achieves higher data density through orthogonality, allowing two independent signals to occupy the same frequency space. It also highlighted that precise phase synchronization at the receiver is the most critical factor for successfully separating overlapping signals.

<details><summary><b>[View EXPERIMENT 18 - Quadrature Phase Shift Keying Details]</b></summary><br>https://github.com/EmmanAbad/Laboratory-Heretic/blob/main/EXPERIMENT%2018%20-%20Quadrature%20Phase%20Shift%20Keying.md<br></details>

</details>

---

<details>
<summary>EXPERIMENT 19 - DSSS Modulation and Demodulation</summary> 

**INTRODUCTION**
* Direct Sequence Spread Spectrum is a secure modulation technique that replaces a standard carrier with a high-speed pseudo-noise (PN) sequence. This spreads the message energy across a wide frequency spectrum, making the signal look like low-level noise to unauthorized users and providing resistance to jamming. The experiment focuses on the correlation between identical PN codes for data recovery.

**EXPLANATION**
* The most critical takeaway was the absolute necessity of perfect synchronization. Without an exact matching PN sequence at the receiver, the data remains indistinguishable from background noise. The experiment also provided a practical understanding of how spreading the signal energy makes it resilient against interference, as the despreading process collapses the message while further spreading any jamming signals.

<details><summary><b>[View EXPERIMENT 19 - DSSS Modulation and Demodulation Details]</b></summary><br>https://github.com/EmmanAbad/Laboratory-Heretic/blob/main/EXPERIMENT%2019%20-%20DSSS%20Modulation%20and%20Demodulation.md<br></details>

</details>

---

<details>
<summary>EXPERIMENT 20 - Undersampling in SDR</summary> 

**INTRODUCTION**
* Software Defined Radio (SDR) shifts the decoding process from rigid hardware to flexible software. To handle high-frequency signals without requiring extreme sampling rates, SDR uses "undersampling" or bandpass sampling. This experiment investigates how intentionally causing aliasing can shift a high-frequency carrier down to baseband, allowing for efficient digital processing.

**EXPLANATION**
* The experiment highlights a shift in traditional sampling perspectives. While standard sampling requires rates exceeding twice the highest frequency, SDR leverages the fact that radio signals are bandwidth-limited. Seeing a 2 kHz signal emerge from a 100 kHz carrier using a lower sampling rate clarified how aliasing can be used as a productive tool rather than just a source of distortion.

<details><summary><b>[View EXPERIMENT 20 - Undersampling in SDR Details]</b></summary><br>https://github.com/EmmanAbad/Laboratory-Heretic/blob/main/EXPERIMENT%2020%20-%20Undersampling%20in%20SDR.md<br></details>

</details>

---

### Presentations:







---

### Learnings: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The laboratory sessions provided a practical understanding of how hardware constraints affect digital integrity. A key takeaway is that while modulation and filtering often cause signal rounding and distortion, specialized components like comparators are essential for restoring the sharp transitions required for accurate data reception. Furthermore, the experiments emphasized the critical role of synchronization, especially in DSSS and QPSK, where precise timing and phase alignment are necessary to successfully recover the original message from noise or multiplexed streams.
</p>

---

### Conclusions:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The successful execution of these experiments validates the theoretical advantages of modern digital modulation. From the simplicity of ASK to the robustness of DSSS and the efficiency of QPSK, the study confirms that digital communication is a balance of managing electromagnetic geometric relationships and hardware limitations. These methodologies remain foundational to the design of resilient wireless networks and secure telecommunication links.
</p>



