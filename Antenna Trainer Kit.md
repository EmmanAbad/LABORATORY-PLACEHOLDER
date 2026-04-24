# FINAL PROJECT - RC Car :car: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The RC Car is a low-profile, four-wheeled vehicular robot built on a transparent acrylic chassis that emphasizes a modular and visible internal layout. It features a 4WD (Four-Wheel Drive) powertrain using high-torque N20 micro motors, which are mounted securely to the underside of the base using specialized white brackets. The top of the chassis houses the central control hub, consisting of the ESP32 microcontroller and the L298N motor driver, with a multi-colored wiring harness connecting the digital pins to the driver inputs.

&nbsp;&nbsp;&nbsp;&nbsp;Visually, the robot is characterized by its high-traction, treaded MiniQ wheels designed for surface grip during rapid accelerations and sharp turns. The power system is underslung or integrated into the base to maintain a low center of gravity, which is essential for preventing rollovers during the "Agility" phase of the competition. The wiring is managed with zipties and electrical tape, ensuring that no loose leads interfere with the mechanical rotation of the axles or wheels during high-speed operation.
</p>

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/60771358-e37c-479a-9417-f8bdb5cee367" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The field of competitive robotics requires a precise balance between mechanical durability and software responsiveness. This project details the engineering and assembly of a custom-built RC Robot specifically designed to meet the rigorous demands of the RC Cup and RC Soccer competitions. The primary challenge of this build was to integrate high-torque drive systems and wireless control within a compact frame that does not exceed 10 cm in width, 15 cm in length, and 12 cm in height. Furthermore, the entire assembly was required to maintain a total weight of less than 1kg to remain eligible for the competition.

&nbsp;&nbsp;&nbsp;&nbsp;At the heart of the robot is a Type C ESP32 Development Board, which provides the necessary Bluetooth connectivity for remote operation. The robot utilizes a four-wheel-drive (4WD) configuration, employing four JGA12-N20 Micro Metal DC Gear Motors capable of 500RPM at 6V. These motors are controlled via an L298N Dual H-Bridge module, allowing for independent control of the left and right drive sides. By mounting these components on a rigid acrylic base and optimizing the power delivery system, the robot achieves the high power-to-weight ratio needed for the agility trials of the RC Cup and the physical strength required for the RC Soccer matches.
</p>

---

### Objectives
* **Standardized Footprint**: Construct a robot that strictly adheres to the maximum dimensions of 10 cm x 15 cm x 12 cm.
* **Weight Management**: Implement a design that optimizes structural integrity while staying below the 1kg weight limit.
* **Wireless Interconnectivity**: Establish a reliable Bluetooth communication protocol between the ESP32 and a mobile gamepad interface.
* **Drive System Synchronization**: Configure the L298N motor driver to provide synchronous 4WD control for consistent movement.
* **Competitive Versatility**: Ensure the robot possesses sufficient speed for agility tasks and enough torque for strength-based soccer interactions.

---

### How the RC Car Works (System Operation)
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The robot operates as an integrated wireless system. The user provides inputs via a smartphone application (Dabble), which are transmitted over Bluetooth to the ESP32. The ESP32 processes these inputs using a C++ program that maps gamepad buttons to specific motor states. 

&nbsp;&nbsp;&nbsp;&nbsp;To achieve movement, the ESP32 sends Pulse Width Modulation (PWM) signals and digital logic signals to the L298N motor driver. The driver then amplifies these signals to provide enough current to the four N20 motors. For example, when the "Forward" command is received, the ESP32 sets the pins to drive both the right and left motor sets in the same direction at maximum PWM speed (255). Turning is achieved through differential steering, where the left and right motor sets rotate in opposite directions, allowing the robot to spin in place.

<img width="961" height="765" alt="image" src="https://github.com/user-attachments/assets/85239c69-cc23-4e06-a123-3850918d47eb" />

###### RC Car Program
<details><summary><b>[View RC CAR PROGRAM Details]</b></summary><br>https://github.com/EmmanAbad/Project-Quicksilver/blob/main/RCProgram.ino<br></details>

</p>

---

**Antenna Elements**

| Category | Item | Function / Usage |
| --- | --- | --- |
| **Component** | <details><summary><b>ESP32 (Type C)</b></summary><br><img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/f326f3bf-e3ea-41b3-8360-2117eb49d182" />
<br></details> | Processes Bluetooth signals and generates PWM signals for motor speed control. |
| **Component** | <details><summary><b>L298N Motor Driver</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/1b615904-031c-4246-a02a-377dc458d0ab" />
<br></details> | Acts as a high-current bridge to drive motors based on low-power ESP32 signals. |
| **Component** | <details><summary><b>N20 Micro Motors</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/33dc3b7d-57a1-4026-b1f7-137cbdda73de" />
<br></details> | Four 6V 500RPM gear motors providing the mechanical drive force. |
| **Component** | <details><summary><b>Acrylic Base</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/f2ca54fd-ee1e-4ecf-a74d-de2fbaec0f6f" />
<br></details> | The main structural frame of the robot, providing a mounting surface for all parts. |
| **Component** | <details><summary><b>LiPo / Power Bank</b></summary><br><img width="200" height="200"" alt="image" alt="image" src="https://github.com/user-attachments/assets/1c576bc8-7042-415f-9185-45b75f49790f" />
<br></details> | Supplies the necessary voltage and current for both the logic and the actuators. |
| **Tool** | <details><summary><b>Soldering Iron & Lead</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/f77e9e59-55ba-4aea-86a5-b9de0565f861" />
<br></details> | Used for making permanent, secure electrical connections on motor terminals. |
| **Tool** | <details><summary><b>Precision Screwdrivers</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/6830c17b-8609-46bf-b5f0-9e1de2c8932b" />
<br></details> | Used for fastening the N20 motor brackets and the acrylic chassis assembly. |
| **Tool** | <details><summary><b>Zipties & Electric Tape</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/ba5a8db4-be3b-4241-b402-fa7aea224bff" />
<br></details> | Essential for wire management and insulating exposed connections. |
| **Tool** | <details><summary><b>Soldering Paste</b></summary><br><img width="200" height="200" alt="image" alt="image" src="https://github.com/user-attachments/assets/36ee7ecd-eb5d-4cc5-aae3-783c17cf1e7d" />
<br></details> | Facilitates cleaner and more reliable solder joints on mechanical parts. |

---

**Components and Technical Tools Learning**
###### Technical Tool Learnings
* **Precision Soldering**: Mastered the technique of applying soldering paste to N20 motor terminals to ensure high-conductivity joints that can withstand the vibrations of a soccer match.
* **Effective Wire Management**: Discovered that using zipties not only improves the aesthetic of the build but is a mechanical necessity to prevent wires from snagging on moving axles.
* **Torque vs. Speed Calibration**: Learned to use precision tools to adjust motor bracket tension, ensuring that all four wheels maintain equal contact with the ground for maximum torque delivery.

###### Component-Level Learnings
* **ESP32 GPIO Management**: Gained expertise in mapping digital pins (16-19) and utilizing PWM channels to vary speed, rather than just simple ON/OFF control.
* **H-Bridge Logic**: Understood the internal logic of the L298N, specifically how it uses dual-input signals per channel to determine clockwise or counter-clockwise rotation.
* **Power Distribution**: Learned how to effectively split power between a logic board (ESP32) and high-draw actuators (motors) to prevent system brownouts during peak acceleration.
* **Firmware Customization**: Developed the ability to configure the Dabble library to create a low-latency Bluetooth link, ensuring the robot responds instantly to user commands.

---

### Procedural Stesp (Assembly and Configuration)

###### Step 1: Chassis Preparation and Motor Mounting
Begin by preparing the acrylic base. Mark the positions for the four N20 micro motors. Using the MiniQ brackets and precision screwdrivers, secure each motor to the corners of the chassis. Ensure the axles are perfectly parallel to maintain straight-line tracking.

###### Step 2: Electronic Component Placement
Position the L298N Motor Driver and the ESP32 Development Board on the top surface of the acrylic base. Use adhesive spacers or mounting screws to fix them in place, ensuring there is enough clearance to prevent electrical shorts against the chassis.

###### Step 3: Soldering and Wiring
Apply soldering paste to the motor terminals. Solder solid wires to each of the four motors. Route these wires toward the center of the robot. Connect the motors in pairs (left side and right side) to the output terminals of the L298N driver. Use male-to-female and female-to-female wires to connect the ESP32 GPIO pins (16, 17, 18, and 19) to the logic inputs of the L298N.

###### Step 4: Firmware Upload
Connect the ESP32 to a computer via a Type-C cable. Using the Arduino IDE, upload the control firmware. Ensure the Dabble library is included and the Bluetooth device name is correctly set. Verify that the PWM frequency is set to 1000Hz for smooth motor operation.

###### Step 5: Power Integration and Wire Management
Connect the power source (LiPo or Power Bank) to the L298N power terminals and the ESP32. Use zipties to bundle the loose wires and electrical tape to insulate all exposed solder joints. This prevents mechanical interference with the wheels.

###### Step 6: Testing and Calibration
Pair the smartphone with the ESP32 via Bluetooth. Open the Dabble app and test the directional controls. If the robot moves in the wrong direction, reverse the polarity of the motor wires at the L298N terminal blocks.

---

### Pictures

<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/0b7a7085-601c-4024-afd4-210c8965ea8d" />

<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/c2550788-3e7f-4c7f-aaae-0ed991d6efb6" />

<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/b934e6c5-5008-45b5-8a67-91d165230034" />

---

### Learnings
* **PWM Implementation**: Gained proficiency in using `ledcSetup` and `ledcAttachPin` to control DC motor speed with an 8-bit resolution.
* **Differential Steering Logic**: Developed the logic required to translate simple gamepad inputs into complex motor states for turning and reversing.
* **Hardware Integration**: Learned the practicalities of mounting N20 motors using MiniQ brackets to ensure a stable wheel alignment.
* **Firmware Debugging**: Experienced the process of establishing a Bluetooth handshake and naming the device for clear identification.
* **Circuit Efficiency**: Understood the necessity of using direct motor driver connections to handle the current demands of four separate gear motors.

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The construction of this RC Robot successfully demonstrates the application of embedded systems in a competitive robotics environment. By strictly following the dimensional and weight constraints, a highly mobile and powerful platform was achieved. The use of the ESP32 and L298N combination proved to be an efficient choice for wireless 4WD control, providing the necessary responsiveness for the RC Cup and the durability for RC Soccer. This project reinforces key engineering principles, including efficient space utilization, secure electrical assembly, and the effective mapping of software logic to mechanical action.
</p>
