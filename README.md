# Laboratory-Midsommar
### Laboratory #2 (Experiment 9-14) :page_facing_up: 
### Introduction:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This series of experiments traces the evolution of communication technology from advanced analog modulation to modern digital transmission. The curriculum begins with Frequency Modulation (FM), demonstrating its superiority in noisy environments over amplitude-based systems. It then transitions into the digital domain, exploring the Sampling Theorem and Pulse Code Modulation (PCM). By building and testing encoders, decoders, and channel filters, these labs illustrate how physical limitations—such as bandwidth and synchronization—impact the ability to transmit and recover high-fidelity information in a digital world.
</p>

---

### Objectives:
* To practically investigate and demonstrate the principles of modern telecommunications through hands-on experimentation.
* To compare the noise resistance of frequency-modulated (FM) signals against amplitude-modulated (AM) systems.
* To analyze the end-to-end process of digitizing analog information through sampling, quantization, and Pulse Code Modulation (PCM).
* To examine the critical role of synchronization and bandwidth limitations in the successful transmission and recovery of digital data.

---

### Explanations of Experiments:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;In the analog phase (Exp 9-10), we see that information is best protected from noise by hiding it in the timing (frequency) of a wave rather than its strength (amplitude). However, for modern computing, signals must be converted into "bits." This requires Sampling (Exp 11), where we take "snapshots" of a wave. To turn these snapshots into data, we use PCM Encoding (Exp 12), which rounds the snapshots to the nearest number (quantization) and sends them as binary code.
</p>
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The most critical challenge revealed in this series is the Physical Reality of the Channel. No matter how perfect the digital code is, the wires and air it travels through (Exp 14) will always blur and distort the pulses. Therefore, communication is not just about sending data, but about managing Synchronization (Exp 13) and using hardware like filters and comparators to "clean up" the signal at the finish line.
</p>

---

**EXPERIMENT 9: Frequency Modulation** 

**INTRODUCTION**
<p align="justify">
* Explores FM as a robust alternative to amplitude modulation, demonstrating how varying a carrier’s frequency rather than its amplitude provides superior resistance to electrical noise.
</p>

**EXPLANATION**
<p align="justify">
* By using a Voltage Controlled Oscillator (VCO), an analog message is used to shift the carrier frequency. The amount of "swing" depends on the message's amplitude, while the speed of that swing depends on the message's frequency.
</p>

---

**EXPERIMENT 10: FM Demodulation** 

**INTRODUCTION**
<p align="justify">
* Focuses on the "Zero-Crossing Detector" method to recover original messages from FM signals by converting frequency variations into measurable voltage changes.
</p>

**EXPLANATION**
<p align="justify">
* The FM signal is "squared up" using a comparator to trigger a pulse generator. Because the pulses have a fixed width, changing the frequency changes the duty cycle. A low-pass filter then averages these pulses to reconstruct the original wave.
</p>

---

**EXPERIMENT 11: Sampling and Reconstruction**

**INTRODUCTION**
<p align="justify">
* Investigates the conversion of continuous analog signals into discrete digital formats through regular measurements of voltage.
</p>

**EXPLANATION**
<p align="justify">
* This lab proves the Nyquist Theorem: sampling a signal at least twice as fast as its highest frequency allows for perfect reconstruction. It demonstrates how "Sample and Hold" signals are smoothed back into analog form using filters.
</p>

---

**EXPERIMENT 12: PCM Encoding** 

**INTRODUCTION**
<p align="justify">
* Analyzes the fundamentals of digitizing analog voltages by sampling, quantizing, and converting them into an 8-bit serial binary stream.
</p>

**EXPLANATION**
<p align="justify">
* Each analog sample is compared to 256 quantization levels. The encoder assigns the closest binary number to that voltage. This lab highlights "quantization error"—the loss of detail that occurs when a signal is rounded to the nearest digital level.
</p>

---

**EXPERIMENT 13: PCM Decoding** 

**INTRODUCTION**
<p align="justify">
* Examines the recovery of analog messages from serial binary data, emphasizing the necessity of precise timing between the transmitter and receiver.
</p>

**EXPLANATION**
<p align="justify">
* The decoder reads the 8-bit strings and converts them back into proportional voltages. Without a shared "Clock" and "Frame Sync" signal, the decoder cannot identify where a binary number begins or ends, leading to total signal loss.
</p>

---

**EXPERIMENT 14: Bandwidth Limiting and Restoring Digital Signals** 

**INTRODUCTION**
<p align="justify">
* Demonstrates how transmission media (wires or fiber) act as filters that distort digital signals by removing their high-frequency harmonics.
</p>

**EXPLANATION**
<p align="justify">
* When bandwidth is restricted, sharp digital pulses become rounded, causing Inter-Symbol Interference. This experiment shows how a comparator can "square up" these distorted waves to restore clear logic levels for the receiver.
</p>

---

### Learnings: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The primary learning across these modules is the critical role of synchronization and physical constraints. Digital systems like PCM offer superior noise resistance but are entirely dependent on precise timing (Clock and Frame Sync). Furthermore, the fidelity of any communication system is bound by the Nyquist Rate (for sampling) and the Channel Bandwidth (for transmission), both of which dictate the maximum speed and quality of data transfer.
</p>

---

### Conclusions:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;It is concluded that while digital transmission systems are more complex than analog ones, they are far more reliable for modern communication because they can be "restored" and filtered more effectively. Success in telecommunications requires a balance between the bit-rate of the message and the bandwidth of the channel; if the channel is too narrow or the sampling is too slow, aliasing and distortion will occur. Ultimately, the use of low-pass filtering remains the universal "bridge" used to return modulated or sampled data back into a human-readable analog format.
</p>
