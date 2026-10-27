# All Topics Content Outline

**Module:** Hardware, Networks and Behaviourist AI  
**Team:** Max Medium  
**Scope of this document:** Content outline for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Explicit exclusion:** AMAT formula and AMAT calculation are excluded from the Hardware section

> **Terminology note:** This outline uses **Behaviourist AI** (British spelling). The module PDF uses **Behaviorist AI** (American spelling). Both refer to the same field: Brooks-style reactive, behaviour-based AI. The team must keep one spelling consistent in learner-facing materials.

> **Note:** This document is a **content outline**, not a learning-goals document. Learning goals and scope boundaries are in `All_Topics_Learning_Goals_and_Scope.md`.

---

## 1. Purpose

This outline structures the full module across Hardware, Networks and Behaviourist AI. It lists topics, subtopics, key content points, suggested activities and current status.

Part C has been aligned with the module PDF's Section 3 (reactive robotics / Brooks / subsumption / APF / FSM / Q-learning). Behavioural-analytics topics (telemetry, user modelling, anomaly detection, fraud detection, adaptive UX) are **not** part of Part C.

---

## 2. Status key

| Status | Meaning |
|---|---|
| `Outline only` | Structure and key points identified; no full learner-facing prose yet |
| `Drafted` | Some real content exists |
| `Needs revision` | Content exists but has known issues |
| `Checked` | Reviewed and confirmed |

---

## 3. Part A — Hardware

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Status / notes |
|---|---|---|---|---|
| A1 | **Introduction to computer hardware** — physical parts; hardware vs software; processing, storage and interaction | Computer hardware is the physical parts of a computer that can be seen and touched; parts work together to process data at high speed, store information and allow user interaction | Classify items as hardware/software; label a simple computer system | `Outline only` |
| A2 | **Hardware components** — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU/TPU | CPU as the "main brain"; RAM as short-term volatile workspace; motherboard connects parts using traces; Wi-Fi card sends/receives radio signals; ROM as non-volatile memory for firmware/persistent instructions; GPU handles many parallel tasks for graphics; TPU is a specialised AI chip | Match component to function; compare RAM vs ROM; compare GPU vs TPU | `Needs revision` — correct PDF's ROM description |
| A3 | **Binary logic** — bits, voltage levels, logic gates, combinational and sequential circuits | 1 = high voltage, 0 = low voltage; gates: AND, OR, XOR, NAND, NOR, XNOR; truth tables; combinational circuits (adders, multiplexers); sequential circuits (flip-flops, latches) | Complete truth tables for the six gates; classify a circuit | `Outline only` |
| A4 | **System architecture and Von Neumann architecture** — shared memory, system buses, CU, ALU, clock, IAS, registers | Instructions and data share memory connected by system buses; CU fetches/decodes instructions and emits control signals; ALU performs arithmetic and bitwise logical operations; system clock produces timing signals; IAS holds data/programs the CPU needs; registers PC, MAR, MDR, CIR, ACC, SR | Label a Von Neumann diagram; match each register to its role | `Outline only` |
| A5 | **Registers and status flags** — PC, MAR, MDR, CIR, ACC, SR; carry, overflow, zero, negative flags | PC = next instruction address; MAR = RAM address being read/written; MDR = data being moved to/from RAM; CIR = current instruction; ACC = ALU result; SR = status flags | "Which register holds the next instruction address?"; interpret flag outcomes | `Outline only` |
| A6 | **Fetch–Decode–Execute cycle and interrupts** — fetch, decode, execute, writeback; ISR | Fetch: MAR ← PC; MDR ← RAM[MAR]; IR ← MDR; PC ← PC + 1. Decode: CU decodes opcode. Execute: ALU computes operands. Writeback: result saved. Interrupts: priority set; ISR services highest priority; task resumes | Trace a simple ADD; explain a keyboard interrupt | `Outline only` |
| A7 | **Memory hierarchy** — registers, cache, system memory, secondary storage; speed, capacity, cost | Tier 1 CPU registers (flip-flops, ~1–2 KB, <0.5 ns); Tier 2 L1/L2/L3 cache (SRAM, 32 KB–128 MB, 1–15 ns); Tier 3 system memory (DRAM, 8–128 GB, 50–100 ns); Tier 4 secondary storage (NVMe SSD, 512 GB–4 TB, ~50,000 ns) | Order tiers by speed and capacity; explain why cache is small but fast | `Outline only` — **AMAT formula and calculation intentionally excluded** |
| A8 | **Processor specialization: CPU vs GPU vs TPU** — latency vs throughput; SIMT; ASIC; systolic array | CPU: low latency, branch prediction, large cache; GPU: high throughput, SIMT; TPU: ASIC for matrix multiplication, systolic array | Compare CPU/GPU/TPU; explain why GPUs suit graphics/AI | `Outline only` — systolic-array maths brief or optional |
| A9 | **Input/Output systems** — input devices, processing, memory, output devices, I/O controllers | I/O allows users/external devices to communicate; input devices send data; output devices present results; CPU processes; RAM stores; I/O controllers manage peripherals | Walk through closing a browser tab with a mouse | `Outline only` |
| A10 | **Embedded systems** — microcontroller/processor, memory, sensors, actuators, I/O interfaces | Perform a specific function inside a larger device; limited task set; washing machine example | Identify sensors/actuators in a washing machine | `Outline only` |
| A11 | **CPU core types** — P-cores vs E-cores; single-core vs multi-core | P-cores for demanding tasks; E-cores for background with less power; single vs multi-core; performance also depends on clock speed, architecture, software | Game + music + background apps scheduling scenario | `Outline only` |
| A12 | **Number systems** — denary, binary, hexadecimal; conversion; why hexadecimal | Denary base 10; binary base 2; hex base 16 (A=10 … F=15); binary↔denary; binary→hex by four-bit grouping; hex used for memory addresses, machine code, colour values | `1101₂`→denary; `13₁₀`→binary; `11010110₂`→hex | `Outline only` |
| A13 | **RAM: DRAM vs SRAM** — volatility; refresh; density; speed; cost; common use | DRAM: transistor + capacitor, refresh needed, denser, cheaper, main memory; SRAM: multi-transistor, no refresh, fast, less dense, expensive, CPU cache; both volatile | Compare DRAM/SRAM; explain cache vs main memory | `Outline only` |
| A14 | **ROM types: PROM, EPROM, EEPROM; flash** — non-volatility; programming/erasing | ROM non-volatile; PROM once-programmable; EPROM UV-erasable; EEPROM electrically erasable; flash erases/writes in blocks, used in SSDs/USB/memory cards | Match PROM/EPROM/EEPROM to erasing method | `Outline only` — fix PDF table typo |
| A15 | **Display connections: HDMI vs VGA** — signal type; video/audio; connector; common use | HDMI: digital video + audio; modern displays; VGA: analogue video only, no audio, older displays | Compare HDMI/VGA | `Outline only` |

---

## 4. Part B — Networks

| ID | Topic and subtopics | Key content | Suggested activities | Status / notes |
|---|---|---|---|---|
| B1 | **Network fundamentals** — definition, uses, nodes, links, routers, switches | Network = two or more devices connected to share data and resources; nodes = devices; links = wired/wireless pathways; routers connect networks by IP; switches direct within a LAN by MAC | Home Wi-Fi example; router vs switch matching | `Checked` (Networks.md §3–4) |
| B2 | **Packets and packet switching** — header, payload, trailer; reassembly | Header (source/destination/sequence), payload (data), trailer (end + error check); packet switching breaks data into packets travelling independently and reassembled at destination | Trace a photo split into packets; routing-around-failure diagram | `Checked` (Networks.md §5) |
| B3 | **Protocols and addressing** — TCP/IP, HTTP/HTTPS, FTP, DNS, Ethernet; MAC; IPv4/IPv6; URL | Protocols = rules for communication; TCP = connection-oriented reliable; IP = connectionless addressing/routing; MAC = 48-bit physical; IP = logical (IPv4 32-bit, IPv6 128-bit); URL = protocol + subdomain + domain + TLD + path; DNS translates names to IPs | Label a URL; compare MAC/IP; explain why TCP and IP are both needed | `Checked` (Networks.md §6) |
| B4 | **Network topologies** — bus, point-to-point, star, mesh, ring, hybrid, tree; pros/cons; selection | Trade-offs in cost, reliability, scalability; star isolates failures; bus cheap but single point of failure; mesh fault-tolerant but expensive; tree hierarchical; hybrid combines strengths | Choose a topology for a computer lab and justify | `Checked` (Networks.md §7) |
| B5 | **Data flow and transmission** — simplex, half-duplex, full-duplex; serial vs parallel; synchronous vs asynchronous | Simplex one way; half-duplex both ways not simultaneous; full-duplex both ways simultaneous; serial one bit at a time; parallel multiple bits at once (skew/crosstalk); synchronous timed/blocking; asynchronous not timed/non-blocking | Classify TV / walkie-talkie / telephone; compare serial/parallel | `Checked` (Networks.md §8) |
| B6 | **Network architecture** — LAN, WAN, MAN; client-server vs P2P | LAN limited area (star); WAN large area (mesh/hybrid); MAN city/campus (tree); client-server centralized fixed roles; P2P decentralized | Compare LAN/WAN; match client-server and P2P to examples | `Checked` (Networks.md §9) |
| B7 | **Network threats and security** — malware, cyberattacks, vulnerabilities, countermeasures | Virus, worm, Trojan, spyware, adware, ransomware; brute-force, packet sniffing, DoS/DDoS, phishing, pharming, social engineering; weak passwords, unpatched software, misconfigured access, removable media; firewall, encryption, antivirus, authentication, VPN, IDS/IPS | Match threat to countermeasure; classify phishing vs pharming | `Checked` (Networks.md §10) |
| B8 | **Optional enrichment: advanced networking** — OSI/TCP-IP layers, encapsulation, Ethernet framing, subnetting, routing, TCP/UDP detail | Encapsulation/decapsulation; Ethernet MAC structure, CAM table, ARP; IPv4, subnet masks, NAT; distance-vector, link-state, path-vector; TCP vs UDP; TCP flow/congestion control | Label OSI layers; compare TCP and UDP | `Outline only` — **optional enrichment** |

---

## 5. Part C — Behaviourist AI (rewritten for reactive robotics)

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Status / notes |
|---|---|---|---|---|
| C1 | **Introduction to Behaviourist AI** — definition; reactive vs deliberative AI; "intelligence without representation" | Behaviourist AI (also called Behaviorist AI or Reactive AI) builds intelligent autonomous systems by coupling sensory inputs directly to motor actions without relying on complex internal world models or formal logical deliberation; pioneered by Rodney Brooks in the late 1980s | Compare the SMPA loop (deliberative) with the sense–act loop (reactive); human reflex analogy | `Outline only` — rewritten for reactive robotics |
| C2 | **The symbolic crisis** — Physical Symbol System Hypothesis; frame problem; symbol grounding problem; SMPA latency bottleneck | Classical symbolic AI relied on manipulating abstract symbols, but failed in real physical environments due to: (1) **Frame Problem** — impossibility of efficiently updating a central world model with every non-change; (2) **Symbol Grounding Problem** — abstract symbols have no natural link to real sensor signals; (3) **SMPA Latency Bottleneck** — deliberative loops spend too long updating maps and calculating routes, so physical robots freeze or crash when environments change mid-calculation | Explain why a deliberative robot freezes if the environment changes mid-plan; define "symbol grounding" with an example | `Outline only` |
| C3 | **Core axioms of Behaviourist AI** — world as its own model; embodied and situated cognition; tight sensorimotor coupling; emergent behaviour | Four principles (Brooks, "Intelligence Without Representation"): (1) **The World is Its Own Best Model** — query the real environment with sensors instead of maintaining an inaccurate internal map; (2) **Embodied and Situated Cognition** — intelligence must be in a physical body interacting with a physical environment; (3) **Tight Sensorimotor Coupling** — connect sensors directly to actuators via fast parallel channels (Sense → Act); (4) **Emergent Behaviour** — complex smart-looking behaviour emerges from simple reactive rules interacting with an unpredictable environment | Match each axiom to a robot design decision; explain why emergent behaviour is not explicitly programmed | `Outline only` |
| C4 | **Subsumption architecture** — layered behaviours; suppression and inhibition; AFSMs; robotic vacuum case study | Subsumption organises control into parallel task-achieving layers built from **Augmented Finite State Machines (AFSMs)**; higher layers run concurrently above lower survival behaviours; **Suppression**: a higher layer intercepts and replaces the input signal flowing into a lower layer; **Inhibition**: a higher layer blocks or silences the output command emitted by a lower layer; Layers: Layer 0 basic survival (collision avoidance), Layer 1 wandering and exploration, Layer 2 goal seeking. Robotic vacuum: Layer 0 bumper → stop/reverse/rotate 45°; Layer 1 drive forward; Layer 2 dirt sensor → outward spiral | Diagram a 3-layer subsumption controller; explain why Layer 0 overrides remote commands; trace a Roomba through a dirt-detection event | `Outline only` |
| C5 | **Motor schema and artificial potential fields** — attraction, repulsion, net motion vector; local minima trap and solutions | Motor Schema Architecture (Arkin) models control as continuous vector fields; net velocity = sum of attractive force (pull toward goal) and repulsive forces (push from obstacles); repulsion activates only within obstacle influence distance Q*; **Local minima trap** — when attractive and repulsive vectors cancel (F_total = 0) before the goal, the robot gets stuck; solutions: inject random noise vectors (random walks) or switch to wall-following until the gradient clears | Draw attraction/repulsion vectors around a robot; explain why a U-shaped obstacle causes a local minimum; suggest a reactive fix | `Outline only` — vector maths brief or optional |
| C6 | **Decision mechanics** — finite state machines; model-free Q-learning | **FSM**: restricts the agent to one active state at a time and switches on environmental triggers (e.g., PATROL → CHASE → FLEE based on player spotted / health < 20%). **Model-Free Q-Learning** (Operant Conditioning): learns an optimal policy matrix Q(s,a) directly from environmental rewards using a learning rate α and discount factor γ | Design a 3-state FSM for a game enemy; explain Q-learning conceptually as "learn from rewards" without writing the full update equation | `Outline only` — Q-learning update rule is brief enrichment; Bellman equation out of scope |
| C7 | **Limitations and ethics** — internal state representation; generalisation; dynamic environments; partial observability; ethical reasoning; privacy; unintended consequences | Reactive systems lack internal state representation; struggle with generalisation and dynamic/partially observable environments; raise ethical issues around privacy, consent and unintended consequences in modern applications (camera-equipped robots, telemetry from delivery bots) | Debate: "Should a delivery robot record video of pedestrians to improve navigation?"; list privacy safeguards for edge robotics | `Outline only` |
| C8 | **Optional enrichment: advanced reactive architectures** — AFSM detail; APF mathematics; DQN | Full AFSM structure; formal APF equations for U_att, F_att, U_rep, F_rep; Deep Q-Network (DQN) as modern extension | Derive the APF equations; explain DQN vs tabular Q-learning | `Outline only` — optional enrichment |

---

## 6. Part D — Integration and future trends

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Status / notes |
|---|---|---|---|---|
| D1 | **Integrated operational lifecycle** — autonomous edge robotics pod; hardware/network/AI coupling | **Hardware:** SoC with CPU + GPU + TPU/NPU systolic array, SRAM and NVMe storage, LiDAR, ultrasonic proximity sensors, drive motors, connected via system buses. **Networking:** 5G NR transceiver / UDP socket stack; sends telemetry via UDP, receives high-level target coordinates from the Fleet Central Server via reliable TCP. **Behaviourist AI:** onboard Subsumption / APF navigation inside GPU/NPU memory arrays; Layer 0 collision avoidance overrides all remote commands; APF calculates motion vectors toward the target while repelling obstacles; Layer 0 Subsumption instantly halts motors if a pedestrian steps in front, regardless of network delay | Walk through the three lifecycle stages: Hardware Processing → Networking Telemetry → Behaviourist Navigation; explain why UDP for telemetry and TCP for commands | `Outline only` — best place to show how the three parts connect |
| D2 | **Future trends (brief enrichment)** — advanced RL, neuromorphic computing, quantum computing, 5G, federated learning, distributed AI, AI hardware | Brief survey of emerging trends; AI hardware (CPU vs GPU vs TPU; ASIC, FPGA); distributed and federated learning; 5G and edge AI | Short research task: one trend, one benefit, one limitation | `Outline only` — keep brief |

---

## 7. Development status summary

| Part | Status | Notes |
|---|---|---|
| Hardware | `Outline only` | ROM description and AMAT exclusion still to be corrected in learner-facing prose |
| Networks | `Checked` (core), `Outline only` (advanced enrichment) | Core beginner content checked in Networks.md |
| Behaviourist AI | `Outline only` | Rewritten for reactive robotics; no behavioural-analytics content remains |
| Integration / future trends | `Outline only` | Enrichment material brief |

---

## 8. Known gaps and corrections

1. **Hardware ROM description** in the PDF must be corrected: ROM is non-volatile memory for firmware, not "high-speed working memory".
2. **ROM table typo:** "Electrically Programmable ROM" → "Electrically Erasable Programmable ROM".
3. **AMAT formula and calculation** are intentionally excluded from the Hardware outline.
4. **Terminology:** this outline uses **Behaviourist AI**; the PDF uses **Behaviorist AI**. One spelling must be chosen consistently for learner-facing materials.
5. **Part C has been rewritten** from the PDF's Section 3 (reactive robotics). Behavioural-analytics topics (telemetry, user behaviour modelling, anomaly detection, fraud detection, adaptive UX) have been removed from Part C.
6. **Networks advanced topics** (OSI/TCP-IP layers, subnetting, routing, TCP/UDP detail) are optional enrichment only.
7. **Behaviourist AI advanced mathematics** (APF vector equations, Bellman equation, Q-learning update rule, DQN training) is optional enrichment; core scope is conceptual.
8. **Images and diagrams** should be stored locally in an `assets/` folder before PDF export.

---

## 9. Suggested review questions (by part)

### Hardware
1. What is the difference between hardware and software?
2. Name three main hardware components and state one function of each.
3. Why is RAM described as volatile?
4. What is the role of the Control Unit?
5. What is the difference between the MAR and the MDR?
6. Which register stores the address of the next instruction?
7. Describe the fetch–decode–execute cycle in three steps.
8. What is an interrupt, and what is an interrupt service routine?
9. Why is cache faster but smaller than main memory? (Conceptual only — no AMAT calculation.)
10. Compare CPU, GPU and TPU.
11. What is an embedded system? Give one example.
12. What is the difference between a P-core and an E-core?
13. Convert `1101₂` to denary.
14. Convert `13₁₀` to binary.
15. Convert `11010110₂` to hexadecimal.
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
2. What does "The world is its own best model" mean in Behaviourist AI?
3. What is the Sense–Model–Plan–Act loop, and why is it described as a latency bottleneck?
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