# CONTENT OUTLINE: HARDWARE, NETWORKS AND BEHAVIOURIST AI

## PART 1: HARDWARE

### 1.1 FOUNDATIONS
#### 1.1.1 What Is Computer Hardware?
* Computer hardware is the physical parts of a computer that can be seen and touched.
* These parts work together to process data at high speed, store information, and allow user interaction.
* Hardware is distinct from software, which consists of the instructions and programs.

#### 1.1.2 Main Hardware Components
* **CPU:** The "main brain" that processes instructions.
* **RAM:** Short-term, volatile workspace.
* **Motherboard:** Connects parts using traces.
* **Wi-Fi card:** Sends and receives radio signals.
* **ROM:** Non-volatile memory for firmware and persistent instructions (Note: PDF correction needed, ROM is not high-speed working memory).
* **GPU:** Handles many parallel tasks for graphics.
* **TPU:** A specialized AI chip.

#### 1.1.3 Binary Logic and Circuits
* **Bits and Voltage:** 1 represents high voltage, 0 represents low voltage.
* **Logic Gates:** AND, OR, XOR, NAND, NOR, and XNOR.
* **Combinational Circuits:** Adders and multiplexers.
* **Sequential Circuits:** Flip-flops and latches that lock voltage on clock ticks.

### 1.2 ARCHITECTURE AND EXECUTION
#### 1.2.1 Von Neumann Architecture
* Instructions and data share memory connected by system buses.
* **Control Unit (CU):** Fetches and decodes instructions and emits control signals.
* **Arithmetic Logic Unit (ALU):** Performs arithmetic and bitwise logical operations.
* **System Clock:** Produces timing signals on the control bus.
* **Immediate Access Store (IAS):** Holds data/programs the CPU needs.

#### 1.2.2 Registers and Status Flags
* **PC:** Stores the address of the next instruction.
* **MAR:** Stores the RAM address being read/written.
* **MDR:** Holds data retrieved from or waiting to be written to RAM.
* **CIR:** Holds the current instruction being decoded.
* **ACC:** Holds ALU results.
* **SR:** Records status flags (carry, overflow, zero, negative).

#### 1.2.3 Fetch-Decode-Execute (FDE) Cycle and Interrupts
* **Fetch:** MAR → PC; MDR → RAM[MAR]; IR → MDR; PC → PC + 1.
* **Decode:** CU decodes the opcode in IR and generates control signals.
* **Execute:** ALU computes operands and updates status flags.
* **Writeback:** Result saved.
* **Interrupts:** Signals from devices/software; priority is set; ISR services the highest-priority interrupt; the interrupted task continues.

### 1.3 MEMORY AND STORAGE
#### 1.3.1 Memory Hierarchy
* **Tier 1 (CPU Registers):** Flip-flops, ~1–2 KB, under 0.5 ns.
* **Tier 2 (Cache):** L1/L2/L3 (SRAM), 32 KB–128 MB, 1–15 ns.
* **Tier 3 (System Memory):** DRAM, 8–128 GB, 50–100 ns.
* **Tier 4 (Secondary Storage):** NVMe flash SSD, 512 GB–4 TB, ~50,000 ns.
* *(Note: AMAT formula and calculation are intentionally excluded).*

#### 1.3.2 RAM: DRAM vs SRAM
* **DRAM:** Transistor + capacitor, needs refresh, higher density, cheaper, used for main memory.
* **SRAM:** Multiple transistors per bit, no refresh while powered, very fast, lower density, more expensive, used for CPU cache.
* Both are volatile.

#### 1.3.3 ROM Types and Flash Memory
* **PROM:** Can normally be programmed once.
* **EPROM:** Erased with UV light and reprogrammed.
* **EEPROM:** Erased/reprogrammed electrically, often without removing the chip.
* **Flash Memory:** Erases/writes in blocks; used in SSDs, USB drives, and memory cards.

### 1.4 PROCESSORS AND SYSTEMS
#### 1.4.1 Processor Specialisation: CPU vs GPU vs TPU
* **CPU:** Low latency, complex branch prediction, deep out-of-order execution, large cache.
* **GPU:** High throughput, thousands of smaller arithmetic units, SIMT.
* **TPU:** ASIC for matrix multiplication, systolic array of processing elements.

#### 1.4.2 Input/Output (I/O) Systems
* Allow users/external devices to communicate with the computer.
* Input devices send data/instructions; output devices present results.
* I/O controllers manage communication with peripherals.

#### 1.4.3 Embedded Systems
* Perform a specific function inside a larger device with a limited task set.
* Examples include washing machines (receiving programs, monitoring water levels, controlling motors).

#### 1.4.4 CPU Core Types
* **P-cores:** Handle demanding tasks (gaming, complex calculations).
* **E-cores:** Deliver good performance with less power for background/lighter workloads.
* **Multi-core:** Improves multitasking, but performance also depends on clock speed, architecture, and software.

### 1.5 DATA REPRESENTATION AND DISPLAYS
#### 1.5.1 Number Systems
* **Denary:** Base 10 (0–9).
* **Binary:** Base 2 (0–1).
* **Hexadecimal:** Base 16 (0–9, A–F). Binary to hex by grouping four bits.
* Hex is compact and used for memory addresses, machine code, and colour values.

#### 1.5.2 Display Connections: HDMI vs VGA
* **HDMI:** Digital video and audio through one cable; used for modern monitors, TVs, and projectors.
* **VGA:** Analogue video only, no audio, older interface; quality affected by signal quality and cable length.

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