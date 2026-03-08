# EXPERIMENT 12 - PCM Encoding :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Digital transmission is rapidly replacing analog methods in modern commercial applications because of its superior ability to resist interference from electrical noise. While many different digital systems exist for various purposes they all require that analog information such as speech or music be converted into a digital format before transmission. This conversion process relies on sampling where the voltage of the analog signal is measured at specific regular intervals.

&nbsp;&nbsp;&nbsp;&nbsp;Figure 1a illustrates a message consisting of a pure sinewave alongside the digital sampling signal used to trigger measurements. The resulting waveform shows natural sampling where the sample follows any voltage changes occurring during the measurement period. Some digital systems cannot function with these changing samples so an alternative approach is used as seen in Figure 1b. This method is known as sample and hold or pulse amplitude modulation and it ensures the sample size remains fixed at the exact moment the signal is measured.
</p>

<img width="383" height="246" alt="image" src="https://github.com/user-attachments/assets/5fd5192f-98cd-4b30-8c13-e42ecc090eae" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Modern communication systems are increasingly shifting from analog to digital transmission because digital signals are far more effective at resisting interference from electrical noise. While information such as speech or music starts as an analog signal it must be converted to a digital format through a process called sampling. This involves measuring the analog signal's voltage at regular intervals to create a discrete representation. Techniques such as natural sampling and sample and hold schemes are used to capture these measurements with the latter being essential for systems where changing sample voltages are unacceptable.
</p>

---

### Objectives
* Investigate the operation of a Pulse Code Modulation (PCM) encoder using the Emona Telecoms-Trainer 101.
* Observe the conversion of analog message signals into a serial stream of binary digits through the encoding process.
* Evaluate the impact of quantization levels and the encoder's clock frequency on signal accuracy.
* Determine the specific voltage range of the 8-bit encoder by identifying the maximum and minimum binary codes.
* Identify the causes and effects of quantization error during the digitization of analog signals.

---

### Equipment
* Emana Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* two Emano Telecoms Trainer 101 oscilloscope leads
* assorted Emona Telecoms-Trainer 101 patch leads

---

**Procedure – Part A: Sampling a Sample Message**
1. Gather the required trainer components and ground the oscilloscope leads into a (GND) socket.
2. Connect the Master Signals 2kHz SINE output to the Dual Analog Switch input, using the 8kHz DIGITAL output as the control signal.
3. Set the Trigger Source to CH1 (or INT) and the Mode to CH1.
4. Adjust the Timebase to display two cycles of the 2kHz sine wave and set Vertical Attenuation to 1V/div.
5. Switch the scope Mode to DUAL to view both the original message and the sampled output simultaneously.
6. Draw the two resulting waveforms to scale, ensuring enough space remains for a third waveform later.
7. Modify the existing circuit by replacing the electronically controlled switch with a sample and hold module while keeping the 2kHz sine wave and 8kHz pulse train as the message and sampling signals.
8. Use the remaining space on the graph paper to draw the new sample and hold message to scale.

**Procedure – Part B: Sampling Speech**
1. Disconnect the 2kHz sine output and connect the speech module output to the circuit input.
2. Change the timebase to 2ms/div to accommodate the complexity of audio signals.
3. talk, sing, or hum into the microphone to observe how speech is converted into discrete samples.

**Procedure – Part C: Reconstructing a Sampled Message**
1. Set Timebase to $0.1\text{ ms/div}$
2. Set Gain to middle and Cut-off Frequency fully anti-clockwise.
3. Disconnect Speech module; connect S/H output to Filter input (per Figure 7).
4. Connect Ch. 1 to the original message and Ch. 2 to the Filter output.
5. Slowly turn the Cut-off control clockwise until the message signal reappears on the scope.

**Procedure – Part D: Aliasing**
1. Set the VCO module's Frequency Adjust control fully clockwise.
2. Set the Range control to the LO position.
3. Update the set-up as shown in Figure 9, using the VCO module to provide a variable sampling frequency to the S/H control input.

**Waveforms Results**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/a0145970-1771-4058-b04f-f42f1c7b8281" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/3b775d00-812f-4097-a013-8ae06cfabd6f" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/f7dfa261-ab91-4934-96f7-7f2408d5a89c" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/fe64918c-945e-4578-8a11-7a3176b5bcda" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/0edf1004-14b0-4050-ac04-628c51a6cef7" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/de441582-4521-4052-90d7-28f3854acb7d" />



https://github.com/user-attachments/assets/54ed6d04-ab21-4dd7-810b-869b987bcb91



**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This experiment demonstrates that digital communication depends on converting continuous analog signals into discrete samples and back again without loss of information. Through Parts A and B, it was observed that while natural sampling follows the message's voltage changes, the Sample and Hold (S/H) method is more effective for digital systems because it maintains a fixed voltage level for each interval.

&nbsp;&nbsp;&nbsp;&nbsp;The reconstruction process in Part C proved that these discrete samples still contain the original message's frequency; by using a Tuneable Low-pass Filter, the original sinewave can be isolated and recovered from the complex spectral components created during sampling. Finally, Part D highlighted the critical constraint of the Nyquist Criteria: if the sampling frequency (controlled via the VCO) drops below twice the message frequency, aliasing occurs. This creates irreversible distortion in the reconstructed signal, confirming that a sufficiently high sampling rate—exceeding the theoretical minimum to account for real-world filter limitations—is essential for accurate communication.
</p>

---

### Questions and Answers 
**Question 4 — What is the binary number that the PCM Encoder module is outputting?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;For a 0V DC input, the encoder typically outputs a code representing the mid-point of the range, often 10000000 or similar depending on the codec offset.
</p>

**Question 5 — Why does the code change even though the input voltage is steady?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Small noise fluctuations or clock instability can cause the sample to toggle between two adjacent quantization levels.
</p>

**Question 6 — Why does the PCM Encoder module output this code for 0V DC and not 00000000?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The system maps 00000000 to the most negative voltage (-2V) so 0V must be represented by a mid-range binary value.
</p>

**Question 7 — What happens to the Variable DC module's output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The DC voltage increases as the control is turned clockwise.
</p>

**Question 8 — In what way does the binary number change?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The binary value increases towards the maximum 8-bit value of 11111111.
</p>

**Question 9 — What happens to the Variable DC module's output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The DC voltage decreases as the control is turned anti-clockwise.
</p>

**Question 10 — What happens to the binary number that the PCM Encoder module is outputting?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The binary output decreases towards the minimum value of 00000000.
</p>

**Question 11 — Maximum allowable amplitude (peak-to-peak)?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The total range from -2V to +2V results in a 4V peak-to-peak capacity.
</p>

**Question 12 — Name for the difference between a sampled voltage and its closest level?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This is defined as quantisation error.
</p>

**Question 13 — Calculate the difference between levels.**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Dividing the 4V range by 256 codes gives roughly 15.6mV per level.
</p>

**Question 14 — To reduce quantization error it is better to have:**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;More quantisation levels between ±2V.
</p>

| PCM Encoder's output code | PCM Encoder's input voltage |
| --- | --- |
| 11111111 | +2.0V (APPROX) |
| 00000000 | -2.0V (APPROX) |

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment provided a clear look at how analog signals are turned into digital formats through sampling and then back again. It was observed that natural sampling captures the signal voltage as it changes while the sample and hold method keeps the voltage level steady for the duration of the sample. Using a low pass filter proved that an original message can be recovered from a sampled signal because the sampling process naturally preserves the original frequency component among many others. The most important part was seeing what happens when the sampling frequency is lowered too much. This led to aliasing where the reconstructed signal became distorted and did not look like the original message anymore. It was confirmed that the sampling rate must be at least twice the highest frequency of the message to avoid this issue.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This laboratory session demonstrated that digital transmission systems are superior to analog ones because they handle noise and interference much better. By testing both natural and pulse amplitude modulation it was shown that discrete samples contain all the necessary data to rebuild the original analog waveform. The use of a tuneable low pass filter successfully isolated the message frequency from the complex spectral components created during the sampling stage. However the results also proved that the sampling rate is a critical factor in communication. If the rate drops below the Nyquist minimum the signal cannot be reconstructed accurately due to aliasing distortion. Overall the experiment verified the theoretical foundations of digital sampling and reconstruction which are essential for modern telecommunications.
</p>

