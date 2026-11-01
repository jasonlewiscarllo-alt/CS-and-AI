# CONTENT OUTLINE: HARDWARE, NETWORKS AND BEHAVIOURIST AI

## PART 1: HARDWARE

## 1.1 Physical Parts of a Computer
 - ### 1.1.1 The CPU
 -  * The "brain," containing CU, ALU, registers, and cache.
 - ### 1.1.2 RAM
 -  - * Short-term, volatile workspace.
 - ### 1.1.3 Motherboard
 -  - * Main circuit board holding components and traces.
 - ### 1.1.4 Wi-Fi Card
 -  - * Converts digital data to radio waves and vice versa.
 - ### 1.1.5 ROM
 -  - * Non-volatile memory for firmware (BIOS/UEFI).
 - ### 1.1.6 GPU and TPU
 -  - * Specialised processors for parallel workloads (GPU) and machine learning matrix operations (TPU).
 - ### 1.1.7 The System Clock
 -  - * *(Note: Section heading is present on page 4, but text for this subsection is missing/blank in the PDF).*

## 1.2 Number Systems + Units
 - ### 1.2.1 What Is a Bit?
 -  - * Abstraction of high/low voltage levels.
 - ### 1.2.2 Units of Data
 -  - * Bit, nibble, byte, KB, MB, GB, TB (using the 1024 convention).
 - ### 1.2.3 Denary (Decimal)
 -  - * Base 10.
 - ### 1.2.4 Binary
 -  - * Base 2, place-value chart, and binary-to-denary worked examples.
 - ### 1.2.5 Hexadecimal
 -  - * Base 16 (0–9, A–F).
 - ### 1.2.6 Why Hexadecimal Matters
 -  - * Compact shorthand for binary (nibbles), used for memory addresses and colour codes.
 - ### 1.2.7 Conversion Examples
 -  - * Checked binary-to-denary worked examples.
 - ### 1.2.8 Activity: Conversion Practice
 -  - * 6 questions with checked answers.
 - ### 1.2.9 Exam-Style Practice
 -  - * 2-mark question on why hex is used for memory addresses.

## 1.3 Binary Logic
 - ### 1.3.1 From Transistors to Logic Gates
 -  - * Symbols and truth tables for AND, OR, XOR, NAND, NOR, XNOR.
 - ### 1.3.2 Combinational Circuits
 -  - * Half-adders (sum and carry), full adders, and multiplexers.
 - ### 1.3.3 Sequential Circuits
 -  - * Flip-flops and latches (storing a single bit).
 - ### 1.3.4 Activity: Build a Half-adder
 -  - * Drawing circuits and completing truth tables. Addresses the misconception that a bit is a physical object.

## 1.4 System Architecture & the Von Neumann Engine
 - ### 1.4.1 Core Subcomponents
 -  - * Control Unit (CU), Arithmetic Logic Unit (ALU), Immediate Access Store (IAS), and System Clock.
 - ### 1.4.2 Registers
 -  - * PC, MAR, MDR, CIR, ACC, SR. Includes a table of their functions in the FDE cycle.
 - ### 1.4.3 System Bus Architecture
 -  - * Table breaking down the Data Bus (bi-directional), Address Bus (uni-directional), and Control Bus (READ/WRITE/CLOCK).
 -  - * **Status Flag Meanings:** Explicit AS/A Level definitions for Carry, Overflow, Zero, and Negative flags.

## 1.5 The Fetch-Decode-Execute (FDE) Machine Cycle
 - ### 1.5.1 The Cycle Step by Step
 -  - * Fetch, Decode, Execute, Writeback. Includes a 7-step breakdown of bus activity for exam answers.
 - ### 1.5.2 Interrupts and the Interrupt Service Routine (ISR)
 -  - * Causes of interrupts, saving state, priority, and restoring state. Addresses the misconception that interrupts "restart" the computer.
 - ### 1.5.3 Worked Activity: Complete the FDE Diagram
 -  - * Scrambled stages to place in order with the associated registers/buses.
 - ### 1.5.4 Exam-Style Practice
 -  - * 3 questions (PC role, Fetch stage, Interrupts) with marking points.

## 1.6 Memory Hierarchy
 -  - * **Memory Hierarchy Pyramid:** Diagram and table comparing Registers, L1/L2/L3 Cache, System RAM, and Secondary Storage (SSD).
 - ### 1.6.1 Activity: Rank the Access
 -  - * Ranking register, L1 cache, RAM, and SSD by speed.
 - ### 1.6.2 Exam-Style Practice
 - * 2-mark question on why cache sits between CPU and main memory.

## 1.7 Processor Specialisation: CPU vs GPU vs TPU
 - ### 1.7.1 Architecture Comparison
 -  - * CPU (low latency, branch prediction), GPU (high throughput, SIMT), and TPU (systolic array, ASIC for matrix multiplication).
 - ### 1.7.2 Activity: Choose the Right Processor
 -  - * 4 scenarios to match with CPU, GPU, or TPU.

## 1.8 Input / Output (I/O) Systems
 - ### 1.8.1 Main Components
 -  - * Input devices, processing unit, memory, output devices, and I/O controllers.
 - ### 1.8.2 Worked Example: Mouse Click
 -  - * A 4-step trace from input signal to monitor update.
 - ### 1.8.3 Activity: Trace an I/O Path
 -  - * Tracing a smart speaker voice command.

## 1.9 Embedded Systems
 - ### 1.9.1 Main Components
 -  - * Microcontroller, memory, sensors, actuators, I/O interfaces.
 - ### 1.9.2 Examples
 -  - * Washing machine, automotive control system.
 - ### 1.9.3 Real-Time Constraints
 -  - * Hard real-time deadlines (e.g., anti-lock braking system).
 - ### 1.9.4 Exam-Style Practice
 -  - * 3-mark question on washing machine components.

## 1.10 CPU Core Types and Performance
 - ### 1.10.1 Classification by Performance Design
 -  - * P-cores vs. E-cores.
 - ### 1.10.2 Classification by Instruction Execution
 -  - * Single-core vs. multi-core.
 - ### 1.10.3 Worked Scenario
 -  - * OS scheduling a game and background music across P-cores and E-cores.
 - ### 1.10.4 Activity: Match the Core
 -  - * 4 tasks to match to P-cores or E-cores.

## 1.11 RAM: DRAM vs SRAM
 - ### 1.11.1 DRAM
 -  - * Transistor + capacitor, needs refresh.
 - ### 1.11.2 SRAM
 -  - * Multi-transistor latch, no refresh needed.
 - ### 1.11.3 DRAM vs SRAM Comparison
 -  - * Table comparing mechanism, refresh, speed, cost, and use.
 - ### 1.11.4 Activity: Justify the Choice
 -  - * Choosing DRAM for main memory and SRAM for L3 cache.

## 1.12 ROM Types: PROM, EPROM and EEPROM
 - ### 1.12.1 PROM
 -  - * Programmable once.
 - ### 1.12.2 EPROM
 -  - * Erased with UV light.
 - ### 1.12.3 EEPROM
 -  - * Erased/reprogrammed electrically.
 - ### 1.12.4 Comparison
 -  - * Table comparing the three types.
 - ### 1.12.5 Flash Memory
 -  - * Erases in blocks, used in SSDs and USB drives.
 - ### 1.12.6 Exam-Style Practice
 -  - * 2-mark question on choosing ROM for in-circuit firmware updates.

## 1.13 Display Connections: HDMI vs VGA
 - ### 1.13.1 HDMI
 -  - * Digital video and audio.
 - ### 1.13.2 VGA
 -  - * Analogue video only.
 - ### 1.13.3 Comparison
 -  - * Table comparing signal type, audio, connectors, and use.
 - ### 1.13.4 Worked Example
 -  - * Connecting to a modern vs. older projector.
 - ### 1.13.5 Activity: Diagnose the Connection
 -  - * Explaining why a VGA connection has no sound and a blurry image.

---

## PART 2: NETWORKS

### 2.1 FOUNDATIONS
#### 2.1.1 Network Fundamentals
* Network: Two or more devices connected to share data and resources.
* **Nodes:** Devices connected to the network.
* **Links:** Wired/wireless pathways.
* **Routers:** Connect different networks and forward packets by IP address.
* **Switches:** Direct data within a LAN using MAC addresses.

#### 2.1.2 Packets and Packet Switching
* **Packet:** A small chunk of data with a header (source/destination/sequence number), payload (actual data), and trailer (end marker + error-check bits).
* **Packet Switching:** Breaks data into packets that travel independently and are reassembled at the destination.

### 2.2 PROTOCOLS AND ADDRESSING
#### 2.2.1 Protocols and Addressing
* **TCP:** Connection-oriented, reliable.
* **IP:** Connectionless addressing/routing.
* **MAC Address:** 48-bit physical identifier.
* **IP Address:** Logical address (IPv4 32-bit, IPv6 128-bit).

#### 2.2.2 URL Anatomy and DNS
* **URL:** Protocol + subdomain + domain + top-level domain + path.
* **DNS:** Translates domain names into IP addresses.

### 2.3 TOPOLOGIES AND TRANSMISSION
#### 2.3.1 Network Topologies
* Each topology has different trade-offs in cost, reliability, and scalability.
* Star isolates failures; bus is cheap but has a single point of failure; mesh is fault-tolerant but expensive; tree is hierarchical; hybrid combines strengths.

#### 2.3.2 Data Flow and Transmission
* **Simplex:** One direction.
* **Half-duplex:** Both directions, but not simultaneously.
* **Full-duplex:** Both directions simultaneously.
* **Serial:** One bit at a time (longer distances).
* **Parallel:** Multiple bits simultaneously (short distances, skew/crosstalk issues).
* **Synchronous:** Timed/blocking.
* **Asynchronous:** Not timed/non-blocking.

### 2.4 ARCHITECTURE, THREATS, AND SECURITY
#### 2.4.1 Network Architecture
* **LAN:** Limited area, star topology.
* **WAN:** Large geographical area, mesh/hybrid.
* **MAN:** City/campus, tree.
* **Client-Server:** Centralised, fixed roles.
* **P2P:** Decentralised, each node acts as client and server.

#### 2.4.2 Network Threats and Security
* **Malware:** Virus, worm, Trojan, spyware, adware, ransomware.
* **Cyberattacks:** Brute-force, packet sniffing, DoS/DDoS, hacking, phishing, spam, social engineering.
* **Vulnerabilities:** Weak passwords, unpatched software, misconfigured access, removable media.
* **Countermeasures:** Firewall, encryption, antivirus, authentication, VPN, IDS/IPS. Symmetric vs asymmetric encryption; HTTPS uses both.


---

## PART 3: BEHAVIOURIST AI

### 3.1 FOUNDATIONS
#### 3.1.1 Introduction to Behaviourist AI
* Behaviourist AI (also called behaviour-based AI or reactive AI) builds intelligent autonomous systems by coupling sensory inputs directly to motor actions.
* It does not rely on complex internal world models or formal logical deliberation.
* Pioneered by Rodney Brooks in the late 1980s.

#### 3.1.2 The Symbolic Crisis
* Classical symbolic AI relied on manipulating abstract symbols and failed in real physical environments due to:
* **Frame Problem:** Impossibility of efficiently updating a central world model with every non-change.
* **Symbol Grounding Problem:** Abstract symbols have no natural link to real sensor signals.
* **SMPA Latency Bottleneck:** Deliberative loops spend too long updating maps and calculating routes, causing physical robots to freeze or crash when environments change mid-calculation.

#### 3.1.3 Core Axioms of Behaviourist AI
* Four principles (Brooks, "Intelligence Without Representation"):
* **The World is Its Own Best Model:** Query the real environment with sensors instead of maintaining an inaccurate internal map.
* **Embodied and Situated Cognition:** Intelligence must be in a physical body interacting with a physical environment.
* **Tight Sensorimotor Coupling:** Connect sensors directly to actuators via fast parallel channels (Sense → Act).
* **Emergent Behaviour:** Complex smart-looking behaviour emerges from simple reactive rules interacting with an unpredictable environment.

### 3.2 SUBSYMPTION ARCHITECTURE
#### 3.2.1 Layered Behaviours
* Subsumption organises control into parallel task-achieving layers built from Augmented Finite State Machines (AFSMs).
* Higher layers run concurrently above lower survival behaviours.
* **Layers:** Layer 0 basic survival (collision avoidance), Layer 1 wandering and exploration, Layer 2 goal seeking.

#### 3.2.2 Suppression and Inhibition
* **Suppression:** A higher layer intercepts and replaces the input signal flowing into a lower layer.
* **Inhibition:** A higher layer blocks or silences the output command emitted by a lower layer.
* **Robotic Vacuum Example:** Layer 0 bumper → stop/reverse/rotate 45°; Layer 1 drive forward; Layer 2 dirt sensor → outward spiral.

### 3.3 NAVIGATION AND DECISION MECHANICS
#### 3.3.1 Motor Schema and Artificial Potential Fields (APF)
* Motor Schema Architecture (Arkin) models control as continuous vector fields.
* **Net velocity:** Sum of attractive force (pull toward goal) and repulsive forces (push from obstacles).
* Repulsion activates only within obstacle influence distance Q*.
* **Local Minima Trap:** When attractive and repulsive vectors cancel (F_total = 0) before the goal, the robot gets stuck.
* **Solutions:** Inject random noise vectors (random walks) or switch to wall-following until the gradient clears.

#### 3.3.2 Finite State Machines (FSM) and Q-Learning
* **FSM:** Restricts the agent to one active state at a time and switches on environmental triggers (e.g., PATROL → CHASE → FLEE based on player spotted / health under 20%).
* **Model-Free Q-Learning (Operant Conditioning):** Learns an optimal policy matrix Q(s,a) directly from environmental rewards using a learning rate α and discount factor γ.

### 3.4 LIMITATIONS, ETHICS, AND INTEGRATION
#### 3.4.1 Limitations and Ethics
* Reactive systems lack internal state representation; struggle with generalisation and dynamic/partially observable environments.
* Raise ethical issues around privacy, consent, and unintended consequences in modern applications (camera-equipped robots, telemetry from delivery bots).

#### 3.4.2 Integration: Autonomous Edge Robotics Pod
* **Hardware:** SoC with CPU + GPU + TPU/NPU systolic array, SRAM and NVMe storage, LiDAR, ultrasonic proximity sensors, drive motors, connected via system buses.
* **Networking:** 5G NR transceiver / UDP socket stack; sends telemetry via UDP, receives high-level target coordinates from the Fleet Central Server via reliable TCP.
* **Behaviourist AI:** Onboard Subsumption / APF navigation inside GPU/NPU memory arrays; Layer 0 collision avoidance overrides all remote commands; APF calculates motion vectors toward the target while repelling obstacles; Layer 0 Subsumption instantly halts motors if a pedestrian steps in front, regardless of network delay.

#### 3.4.3 Future Trends (Brief Enrichment)
* Advanced RL, neuromorphic computing, quantum computing, 5G, federated learning, distributed AI, AI hardware.
* AI hardware (CPU vs GPU vs TPU; ASIC, FPGA); distributed and federated learning; 5G and edge AI.

---

## REFERENCES

1. Watson, D., & Williams, H. (2016a). *AI and Computer Science Textbook, IGCSE & O Level* (2nd ed.). [Publisher details to be confirmed].
2. Watson, D., & Williams, H. (2016b). *Computer Science Textbook, AS & A Level*. [Publisher details to be confirmed].
3. IEEE Technology Navigator. (n.d.). Computer Networks. https://technav.ieee.org/area/computer-networks/
4. Splunk. (2024, April 10). Network Topology: The Complete Guide. https://www.splunk.com/en_us/blog/learn/network-topology.html
5. CERT UCC. (2024, August 19). Malware: Insights and Protection. https://ug-cert.ug/malware-insights-and-protection/
6. Cisco Learning Network. (2015, June 10). TCP connection oriented and IP connections.
7. MIT CSAIL. (2014). SSL/TLS and HTTPS.
8. auDA. (2022, September 13). Key terms explained: website URLs. https://www.auda.org.au/
9. Microsoft Learn. (2009, October 8). How DNS query works. https://learn.microsoft.com/
10. Max Medium. (2026). *Module PDF: Hardware, Networks and Behaviourist AI*. Team source document.
11. Max Medium. (2026). *Networks.md*. Team draft.
