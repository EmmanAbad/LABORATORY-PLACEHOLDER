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
* **Weight Optimization**: Ensure the total mass of the robot does not exceed the **1kg** maximum weight requirement
* **Wireless Control**: Implement a stable Bluetooth communication link using the **Dabble** library and an **ESP32** board
* **Dual-Function Performance**: Balance motor torque and speed to excel in both high-speed agility trials and high-strength soccer tasks

---

### Explanations of Project:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The project is an integrated hardware-software system designed for competitive robotics. The hardware consists of a lightweight acrylic base that houses the electronic brain and power system. Four N20 Micro Metal Gear Motors provide the mechanical drive, while the L298N Motor Driver acts as the interface between the low-power ESP32 signals and the high-power requirements of the motors.

&nbsp;&nbsp;&nbsp;&nbsp;  On the software side, the robot is programmed using **C++ (Arduino IDE)**. The code utilizes Pulse Width Modulation (PWM) at a frequency of 1000Hz to control the speed of the motors through the `ledcWrite` function. The **Dabble app** on a smartphone acts as the remote controller, sending directional commands that the ESP32 interprets to set motor speeds at a defined maximum of 255.
</p>

---

### How Componenets is used:
| Component | Function / Usage |
| :--- | :--- |
| **Acrylic Base** | Provides the structural frame for mounting motors and electronics. |
| **ESP32 Dev Board** | The central controller that processes Bluetooth signals and manages motor logic. |
| **L298N Motor Driver** | Receives PWM signals from the ESP32 to drive the four DC motors in forward or reverse. |
| **Micro Metal Gear Motors** | Converts electrical energy into mechanical rotation to drive the wheels. |
| **N20 MiniQ Wheels** | Provides the necessary grip and traction for movement on the competition floor. |
| **LiPo/Power Bank** | Supplies the necessary voltage and current to both the ESP32 and the motor driver. |

---

<details>
<summary>FINAL PROJECT - RC Car</summary> 

**INTRODUCTION**
* This project involves the development of a compact, four-wheel-drive RC robot designed for the RC Cup (Agility) and RC Soccer (Strength) competitions. Built on a Type C ESP32 platform, the robot utilizes high-torque N20 micro gear motors and an L298N driver to meet strict size ($10 \times 15 \times 12$ cm) and weight ($1$ kg) requirements.

<details><summary><b>[View FINAL PROJECT - RC Car Details]</b></summary><br>https://github.com/EmmanAbad/Project-Quicksilver/blob/main/FINAL%20PROJECT%20-%20RC%20Car.md<br></details>

</details>

---

### Learnings: 
* **Wireless Protocols**: Gained experience in configuring ESP32 Bluetooth modules and integrating them with mobile gamepad applications.
* **PWM Control**: Learned how to implement 1000 Hz frequency PWM signals with 8-bit resolution to vary motor speed and direction.
* **Motor Logic**: Understood the logic required to rotate motors by toggling specific pins (16-19) between HIGH and LOW states for directional control.
* **Hardware Efficiency**: Discovered the importance of secure wiring using zipties and electrical tape to prevent signal loss during high-impact collisions.

---

### Conclusions:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The RC Robot successfully meets all competition requirements regarding size, weight, and component selection. Through the integration of the ESP32 and the L298N driver, the robot demonstrates reliable wireless control and sufficient maneuverability for both the RC Cup and RC Soccer events. This project reinforces the importance of modular design and efficient power management in creating small-scale competitive robotics.
</p>



