# All Topics Content Outline — Hardware, Networks and Behaviourist AI

**Module:** Hardware, Networks and Behaviourist AI  
**Team:** Max Medium  
**Scope of this document:** Content outline for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Explicit exclusion:** AMAT formula and AMAT calculation are excluded from the Hardware section

**Terminology note:** This module teaches **Behaviourist AI** (British spelling; American spelling: **Behaviorist AI**). In this document, Behaviourist AI means **Brooks-style reactive, behaviour-based AI**: autonomous systems that couple sensory inputs directly to motor actions without complex internal world models. It does **not** mean behavioural analytics (telemetry profiling, user behaviour modelling, anomaly detection, fraud detection, adaptive UX), which is explicitly out of scope for Part C. The team standardises on **Behaviourist AI** for all learner-facing materials.

**Note:** This document is a content outline, not a learning-goals document. Learning goals and scope boundaries are provided in the separate file All_Topics_Learning_Goals_and_Scope.html.

---

## 1. Purpose

This outline structures the full module across Hardware, Networks and **Behaviourist AI**. It lists topics, subtopics, key content points, suggested activities and current status.

Part C is aligned with the module PDF's Section 3 (reactive robotics / Brooks / subsumption / APF / FSM / Q-learning). Behavioural-analytics topics (telemetry profiling, user behaviour modelling, anomaly detection, fraud detection, adaptive UX) are **not** part of Part C.

---

## 2. Status key

| Status | Meaning |
|---|---|
| **Outline only** | Structure and key points identified; no full learner-facing prose yet |
| **Drafted** | Some real content exists |
| **Needs revision** | Content exists but has known issues |
| **Checked** | Reviewed and confirmed |

---

## 3. Part A — Hardware

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Status / notes |
|---|---|---|---|---|
| **A1** | Introduction to computer hardware — physical parts; hardware vs software; processing, storage and interaction | Computer hardware is the physical parts of a computer that can be seen and touched; parts work together to process data at high speed, store information and allow user interaction | Classify items as hardware/software; label a simple computer system | Outline only |
| **A2** | Hardware components — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU/TPU | CPU as the “main brain”; RAM as short-term volatile workspace; motherboard connects parts using traces; Wi-Fi card sends/receives radio signals; ROM as non-volatile memory for firmware/persistent instructions; GPU handles many parallel tasks for graphics; TPU is a specialised AI chip | Match component to function; compare RAM vs ROM; compare GPU vs TPU | Needs revision — correct PDF's ROM description (“ROM serves as high-speed working memory” is inaccurate) |
| **A3** | Binary logic — bits, voltage levels, logic gates, combinational and sequential circuits | 1 = high voltage, 0 = low voltage; gates: AND, OR, XOR, NAND, NOR, XNOR; truth tables; combinational circuits (adders, multiplexers); sequential circuits (flip-flops, latches) that lock voltage on clock ticks | Complete truth tables for the six gates; classify a circuit as combinational or sequential | Outline only |
| **A4** | System architecture and Von Neumann architecture — shared memory, system buses, CU, ALU, clock, IAS, registers | Instructions and data share memory connected by system buses; CU fetches/decodes instructions and emits control signals; ALU performs arithmetic and bitwise logical operations; system clock produces timing signals on the control bus; Immediate Access Store holds data/programs the CPU needs; registers include PC, MAR, MDR, CIR, ACC, SR | Label a Von Neumann diagram; explain why a system clock is needed; match each register to its role | Outline only |
| **A5** | Registers and status flags — PC, MAR, MDR, CIR, ACC, SR; carry, overflow, zero, negative flags | PC stores the address of the next instruction; MAR stores the RAM address being read/written; MDR holds data retrieved from or waiting to be written to RAM; CIR holds the current instruction being decoded; ACC holds ALU results; SR records flags | “Which register holds the next instruction address?”; “Which register holds the current instruction?”; interpret simple flag outcomes | Outline only |
| **A6** | Fetch-Decode-Execute cycle and interrupts — fetch, decode, execute, writeback; ISR | Fetch: MAR ← PC; MDR ← RAM[MAR]; IR ← MDR; PC ← PC + 1. Decode: CU decodes opcode in IR and generates control signals. Execute: ALU computes operands and updates status flags. Writeback: result saved. Interrupts: signal from device/software; priority set; ISR services highest-priority interrupt; interrupted task continues | Trace a simple ADD instruction through the FDE cycle; explain a keyboard interrupt | Outline only |
| **A7** | Memory hierarchy — registers, cache, system memory, secondary storage; speed, capacity, cost trade-offs | Tier 1 CPU registers (flip-flops, ~1–2 KB, under 0.5 ns); Tier 2 L1/L2/L3 cache (SRAM, 32 KB–128 MB, 1–15 ns); Tier 3 system memory (DRAM, 8–128 GB, 50–100 ns); Tier 4 secondary storage (NVMe flash SSD, 512 GB–4 TB, ~50,000 ns) | Order tiers by speed and capacity; explain why cache is small but fast; why secondary storage is large but slow | Outline only — AMAT formula and AMAT calculation intentionally excluded |
| **A8** | Processor specialisation: CPU vs GPU vs TPU — latency vs throughput; SIMT; ASIC; systolic array concept | CPU: low latency, complex branch prediction, deep out-of-order execution, large cache; GPU: high throughput, thousands of smaller arithmetic units, SIMT; TPU: ASIC for matrix multiplication, systolic array of processing elements | Compare CPU/GPU/TPU in a table; explain why GPUs suit graphics/AI workloads; explain TPU as a specialised AI chip | Outline only — keep systolic-array maths brief or optional |
| **A9** | Input/Output systems — input devices, processing unit, memory, output devices, I/O controllers | I/O systems allow users/external devices to communicate with the computer; input devices send data/instructions; output devices present results; CPU processes; RAM stores working data; I/O controllers manage communication with peripherals | Walk through “closing a browser tab with a mouse”: input → driver/I/O → CPU processing → monitor output | Outline only |
| **A10** | Embedded systems — microcontroller/processor, memory, sensors, actuators, I/O interfaces | Embedded systems perform a specific function inside a larger device; limited task set; e.g., washing machine receiving programme, monitoring water level/temperature and controlling motor | Identify sensors and actuators in a washing machine; classify devices as general-purpose or embedded | Outline only |
| **A11** | CPU core types — P-cores vs E-cores; single-core vs multi-core | P-cores handle demanding tasks (gaming, complex calculations); E-cores deliver good performance with less power for background/lighter workloads; single-core has one core; multi-core has two or more; more cores can improve multitasking but performance also depends on clock speed, architecture and software | Scenario: game + music + background apps — how might an OS schedule work across P-cores and E-cores? | Outline only |
| **A12** | Number systems — denary, binary, hexadecimal; conversion; why hexadecimal is useful | Denary base 10 (0–9); binary base 2 (0–1); hexadecimal base 16 (0–9, A–F; A = 10 … F = 15); binary → denary; binary → hex by grouping four bits; hex is compact and used for memory addresses, machine code, colour values; each hex digit = four bits | Convert 1101₂ to denary; 13₁₀ to binary; 11010110₂ to hex (D6₁₆); explain why hex is shorter | Outline only |
| **A13** | RAM: DRAM vs SRAM — volatility; refresh; density; speed; cost; common use | DRAM: transistor + capacitor, needs refresh, higher density, cheaper, main memory. SRAM: multiple transistors per bit, no refresh while powered, very fast, lower density, more expensive, CPU cache. Both volatile | Compare DRAM and SRAM; explain why SRAM is used for cache and DRAM for main memory | Outline only |
| **A14** | ROM types: PROM, EPROM, EEPROM; flash memory — non-volatility; programming/erasing | ROM is non-volatile; PROM can normally be programmed once; EPROM erased with UV light and reprogrammed; EEPROM erased/reprogrammed electrically, often without removing the chip; flash memory erases/writes in blocks, used in SSDs, USB drives, memory cards | Match PROM/EPROM/EEPROM to erasing method; explain why ROM is useful for firmware | Outline only — correct PDF table typo “Electrically Programmable ROM” to “Electrically Erasable Programmable ROM” |
| **A15** | Display connections: HDMI vs VGA — signal type; video/audio; connector; common use | HDMI: digital video and audio through one cable; modern monitors, TVs, projectors, gaming devices. VGA: analogue video only, no audio, older interface, quality affected by signal quality and cable length | Compare HDMI and VGA; choose a cable for a modern monitor vs an older projector | Outline only |

---

## 4. Part B — Networks

| ID | Topic and subtopics | Key content | Suggested activities | Status / notes |
|---|---|---|---|---|
| **B1** | Network fundamentals — definition, uses, nodes, links, routers, switches | Network = two or more devices connected to share data and resources; nodes = devices; links = wired/wireless pathways; routers connect different networks and forward packets by IP address; switches direct data within a LAN using MAC addresses | Home Wi-Fi example: phone, laptop, printer as nodes; router vs switch matching activity | Checked (Networks.md §3–4) |
| **B2** | Packets and packet switching — header, payload, trailer; packet switching; reassembly | Packet = small chunk of data with header (source/destination/sequence number), payload (actual data), trailer (end marker + error-check bits); packet switching breaks data into packets that travel independently and are reassembled at destination | Trace a photo being split into packets and reassembled; diagram of rerouting around a failed link | Checked (Networks.md §5) |
| **B3** | Protocols and addressing — TCP/IP, HTTP/HTTPS, FTP, DNS, Ethernet; MAC address; IP address (IPv4/IPv6); URL anatomy | Protocols = rules for communication; TCP = connection-oriented reliable; IP = connectionless addressing/routing; MAC = 48-bit physical identifier; IP = logical address (IPv4 32-bit, IPv6 128-bit); URL = protocol + subdomain + domain + top-level domain + path; DNS translates domain names to IP addresses | Label a URL; compare MAC and IP addresses; explain why TCP and IP are both needed | Checked (Networks.md §6) |
| **B4** | Network topologies — bus, point-to-point, star, mesh, ring, hybrid, tree; pros/cons; selection | Each topology has different trade-offs in cost, reliability, scalability; star isolates failures; bus is cheap but single point of failure; mesh is fault-tolerant but expensive; tree is hierarchical; hybrid combines strengths | “Choose a topology for a school computer lab and justify it”; compare star vs mesh for fault tolerance | Checked (Networks.md §7) |
| **B5** | Data flow and transmission — simplex, half-duplex, full-duplex; serial vs parallel; synchronous vs asynchronous | Simplex = one direction; half-duplex = both directions but not simultaneously; full-duplex = both directions simultaneously; serial = one bit at a time (longer distances); parallel = multiple bits simultaneously (short distances, skew/crosstalk issues); synchronous = timed/blocking; asynchronous = not timed/non-blocking | Classify examples: TV broadcast (simplex), walkie-talkie (half-duplex), telephone (full-duplex); compare serial vs parallel | Checked (Networks.md §8) |
| **B6** | Network architecture — LAN, WAN, MAN; client-server vs peer-to-peer | LAN = limited area, star topology; WAN = large geographical area, mesh/hybrid; MAN = city/campus, tree; client-server = centralised, fixed roles; P2P = decentralised, each node acts as client and server | Compare LAN vs WAN; match client-server and P2P to examples (web browsing, BitTorrent) | Checked (Networks.md §9) |
| **B7** | Network threats and security — malware, cyberattacks, vulnerabilities, countermeasures | Malware: virus, worm, Trojan, spyware, adware, ransomware; cyberattacks: brute-force, packet sniffing, DoS/DDoS, hacking, phishing, pharming, social engineering; vulnerabilities: weak passwords, unpatched software, misconfigured access, removable media; countermeasures: firewall, encryption, antivirus, authentication, VPN, IDS/IPS; symmetric vs asymmetric encryption; HTTPS uses both | Match threat to countermeasure; classify phishing vs pharming; scenario: “repeated password attempts — what defence?” | Checked (Networks.md §10) |
| **B8** | Optional enrichment: advanced networking — OSI/TCP-IP layers, encapsulation, Ethernet framing, IP addressing/subnetting, routing protocols, TCP/UDP details | OSI 7-layer and TCP/IP stack; encapsulation/decapsulation; Ethernet MAC structure and switching; IPv4 addressing, subnet masks, NAT; distance-vector/link-state/path-vector routing; TCP vs UDP; TCP flow/congestion control | Label OSI layers; explain encapsulation; compare TCP and UDP | Outline only — optional enrichment; advanced subnetting and protocol-stack detail are out of core scope for beginners |

---

## 5. Part C — Behaviourist AI (reactive robotics)

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Status / notes |
|---|---|---|---|---|
| **C1** | Introduction to Behaviourist AI — definition; reactive vs deliberative AI; “intelligence without representation” | Behaviourist AI (also called behaviour-based AI or reactive AI) builds intelligent autonomous systems by coupling sensory inputs directly to motor actions without relying on complex internal world models or formal logical deliberation; pioneered by Rodney Brooks in the late 1980s | Compare the SMPA loop (deliberative) with the sense–act loop (reactive); human reflex analogy | Outline only — rewritten for reactive robotics |
| **C2** | The symbolic crisis — Physical Symbol System Hypothesis; frame problem; symbol grounding problem; SMPA latency bottleneck | Classical symbolic AI relied on manipulating abstract symbols, but failed in real physical environments due to: (1) Frame Problem — impossibility of efficiently updating a central world model with every non-change; (2) Symbol Grounding Problem — abstract symbols have no natural link to real sensor signals; (3) SMPA Latency Bottleneck — deliberative loops spend too long updating maps and calculating routes, so physical robots freeze or crash when environments change mid-calculation | Explain why a deliberative robot freezes if the environment changes mid-plan; define “symbol grounding” with an example | Outline only |
| **C3** | Core axioms of Behaviourist AI — world as its own model; embodied and situated cognition; tight sensorimotor coupling; emergent behaviour | Four principles (Brooks, “Intelligence Without Representation”): (1) The World is Its Own Best Model — query the real environment with sensors instead of maintaining an inaccurate internal map; (2) Embodied and Situated Cognition — intelligence must be in a physical body interacting with a physical environment; (3) Tight Sensorimotor Coupling — connect sensors directly to actuators via fast parallel channels (Sense → Act); (4) Emergent Behaviour — complex smart-looking behaviour emerges from simple reactive rules interacting with an unpredictable environment | Match each axiom to a robot design decision; explain why emergent behaviour is not explicitly programmed | Outline only |
| **C4** | Subsumption architecture — layered behaviours; suppression and inhibition; AFSM; robotic vacuum case study | Subsumption organises control into parallel task-achieving layers built from Augmented Finite State Machines (AFSMs); higher layers run concurrently above lower survival behaviours; Suppression: a higher layer intercepts and replaces the input signal flowing into a lower layer; Inhibition: a higher layer blocks or silences the output command emitted by a lower layer; Layers: Layer 0 basic survival (collision avoidance), Layer 1 wandering and exploration, Layer 2 goal seeking. Robotic vacuum: Layer 0 bumper → stop/reverse/rotate 45°; Layer 1 drive forward; Layer 2 dirt sensor → outward spiral | Diagram a 3-layer subsumption controller; explain why Layer 0 overrides remote commands; trace a Roomba through a dirt-detection event | Outline only |
| **C5** | Motor schema and artificial potential fields — attraction, repulsion, net motion vector; local minima trap and solutions | Motor Schema Architecture (Arkin) models control as continuous vector fields; net velocity = sum of attractive force (pull toward goal) and repulsive forces (push from obstacles); repulsion activates only within obstacle influence distance Q*; Local minima trap — when attractive and repulsive vectors cancel (F_total = 0) before the goal, the robot gets stuck; solutions: inject random noise vectors (random walks) or switch to wall-following until the gradient clears | Draw attraction/repulsion vectors around a robot; explain why a U-shaped obstacle causes a local minimum; suggest a reactive fix | Outline only — vector maths brief or optional |
| **C6** | Decision mechanics — finite state machines; model-free Q-learning | FSM: restricts the agent to one active state at a time and switches on environmental triggers (e.g., PATROL → CHASE → FLEE based on player spotted / health under 20%). Model-Free Q-Learning (Operant Conditioning): learns an optimal policy matrix Q(s,a) directly from environmental rewards using a learning rate α and discount factor γ | Design a 3-state FSM for a game enemy; explain Q-learning conceptually as “learn from rewards” without writing the full update equation | Outline only — Q-learning update rule is brief enrichment; Bellman equation out of scope |
| **C7** | Limitations and ethics — internal state representation; generalisation; dynamic environments; partial observability; ethical reasoning; privacy; unintended consequences | Reactive systems lack internal state representation; struggle with generalisation and dynamic/partially observable environments; raise ethical issues around privacy, consent and unintended consequences in modern applications (camera-equipped robots, telemetry from delivery bots) | Debate: “Should a delivery robot record video of pedestrians to improve navigation?”; list privacy safeguards for edge robotics | Outline only |
| **C8** | Optional enrichment: advanced reactive architectures — AFSM detail; APF mathematics; DQN | Full AFSM structure; formal APF equations for U_att, F_att, U_rep, F_rep; Deep Q-Network (DQN) as modern extension | Derive the APF equations; explain DQN vs tabular Q-learning | Outline only — optional enrichment |

---

## 6. Part D — Integration and future trends

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Status / notes |
|---|---|---|---|---|
| **D1** | Integrated operational lifecycle — autonomous edge robotics pod; hardware/network/AI coupling | Hardware: SoC with CPU + GPU + TPU/NPU systolic array, SRAM and NVMe storage, LiDAR, ultrasonic proximity sensors, drive motors, connected via system buses. Networking: 5G NR transceiver / UDP socket stack; sends telemetry via UDP, receives high-level target coordinates from the Fleet Central Server via reliable TCP. **Behaviourist AI:** onboard Subsumption / APF navigation inside GPU/NPU memory arrays; Layer 0 collision avoidance overrides all remote commands; APF calculates motion vectors toward the target while repelling obstacles; Layer 0 Subsumption instantly halts motors if a pedestrian steps in front, regardless of network delay | Walk through the three lifecycle stages: Hardware Processing → Networking Telemetry → Behaviourist Navigation; explain why UDP for telemetry and TCP for commands | Outline only — best place to show how the three parts connect |
| **D2** | Future trends (brief enrichment) — advanced RL, neuromorphic computing, quantum computing, 5G, federated learning, distributed AI, AI hardware | Brief survey of emerging trends; AI hardware (CPU vs GPU vs TPU; ASIC, FPGA); distributed and federated learning; 5G and edge AI | Short research task: one trend, one benefit, one limitation | Outline only — keep brief |

---

## 7. Development status summary

| Part | Status | Notes |
|---|---|---|
| **Hardware** | Outline only | ROM description and AMAT exclusion still to be corrected in learner-facing prose |
| **Networks** | Checked (core), Outline only (advanced enrichment) | Core beginner content checked in Networks.md |
| **Behaviourist AI** | Outline only | Aligned with the PDF's Section 3 (reactive robotics); no behavioural-analytics content remains |
| **Integration / future trends** | Outline only | Enrichment material brief |

---

## 8. Known gaps and corrections

1. Hardware ROM description in the PDF must be corrected: ROM is non-volatile memory for firmware, not “high-speed working memory”.
2. ROM table typo: “Electrically Programmable ROM” → “Electrically Erasable Programmable ROM”.
3. AMAT formula and calculation are intentionally excluded from the Hardware outline.
4. **Terminology:** this outline uses **Behaviourist AI**. The earlier module PDF header used **Behavioural AI**; the team has standardised on **Behaviourist AI** for all learner-facing materials. Where the official course module title retains the word “Behavioural”, the title is kept but this outline governs the content terminology.
5. Part C is aligned with the PDF's Section 3 (reactive robotics). Behavioural-analytics topics (telemetry profiling, user behaviour modelling, anomaly detection, fraud detection, adaptive UX) have been removed from Part C and appear only as explicit exclusions.
6. Networks advanced topics (OSI/TCP-IP layers, subnetting, routing, TCP/UDP detail) are optional enrichment only.
7. Behaviourist AI advanced mathematics (APF vector equations, Bellman equation, Q-learning update rule, DQN training) is optional enrichment; core scope is conceptual.
8. Images and diagrams must be stored locally in `assets/diagrams/` before PDF export.

---

## 9. Suggested review questions (by part)

### Hardware

1. What is the difference between hardware and software?
2. Name three main hardware components and state one function of each.
3. Why is RAM described as volatile?
4. What is the role of the Control Unit?
5. What is the difference between the MAR and the MDR?
6. Which register stores the address of the next instruction?
7. Describe the fetch-decode-execute cycle in three steps.
8. What is an interrupt, and what is an interrupt service routine?
9. Why is cache faster but smaller than main memory? (Conceptual only — no AMAT calculation.)
10. Compare CPU, GPU and TPU.
11. What is an embedded system? Give one example.
12. What is the difference between a P-core and an E-core?
13. Convert 1101 to denary.
14. Convert 13₁₀ to binary.
15. Convert 110110110 to hexadecimal.
16. Why is hexadecimal useful in computing?
17. Compare DRAM and SRAM.
18. Compare PROM, EPROM and EEPROM.
19. Compare HDMI and VGA.

### Networks

1. What is a network? Name its key components.
2. What are the three parts of a packet and what does each do?
3. What is packet switching and why is it efficient?
4. What is the difference between TCP and IP?
5. What is the difference between a MAC address and an IP address?
6. What are the main parts of a URL?
7. Compare star and mesh topologies.
8. What is the difference between simplex, half-duplex and full-duplex?
9. What is the difference between serial and parallel transmission?
10. What is the difference between synchronous and asynchronous transmission?
11. What is the difference between a LAN and a WAN?
12. What is the difference between client-server and peer-to-peer?
13. Name three types of malware and one countermeasure for each.
14. Name two cyberattacks and one defence for each.
15. Why is encryption important for network security?

### Behaviourist AI

1. What is the difference between classical deliberative AI and Behaviourist AI?
2. What does “The world is its own best model” mean in Behaviourist AI?
3. What is the Sense-Model-Plan-Act loop, and why is it described as a latency bottleneck?
4. What is the frame problem, and why does it affect classical symbolic AI?
5. What is the symbol grounding problem?
6. State the four core principles of Brooks' Behaviourist AI.
7. What is embodied and situated cognition?
8. What is tight sensorimotor coupling?
9. What is emergent behaviour in a reactive system?
10. What is the subsumption architecture?
11. What is the difference between suppression and inhibition in subsumption?
12. In the robotic vacuum example, what does Layer 0 do, Layer 1 do and Layer 2 do?
13. How does the motor schema / artificial potential field approach combine attractive and repulsive forces?
14. What is the local minima trap, and how can a reactive system escape it?
15. What is a finite state machine, and how does it control agent behaviour?
16. What is Q-learning, and how does it relate to Behaviourist AI?
17. Why is Behaviourist AI described as reactive rather than deliberative?
18. What are two limitations of Behaviourist AI?
19. Why is privacy relevant to modern edge robotics, even though it was not central to Brooks' original work?
20. Explain how hardware, networking and Behaviourist AI connect in the autonomous edge robotics pod.

---

## 10. References

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