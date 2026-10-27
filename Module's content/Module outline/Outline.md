# All_Topics_Content_Outline.md

# All Topics Content Outline

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Scope of this document:** Content outline for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Explicit exclusion:** AMAT formula and AMAT calculation are excluded from the Hardware section

> **Note:** This document is a **content outline**, not a learning-goals document. Learning goals and scope boundaries are provided in a separate file (`All_Topics_Learning_Goals_and_Scope.md`).

---

## 1. Purpose

This outline structures the full module content across Hardware, Networks and Behavioural AI. It lists topics, subtopics, key content points, suggested activities and current status. Advanced or enrichment material is marked so that core beginner content remains clear.

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
| A2 | **Hardware components** — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU/TPU | CPU as the “main brain”; RAM as short-term volatile workspace; motherboard connects parts using traces; Wi-Fi card sends/receives radio signals; ROM as non-volatile memory for firmware/persistent instructions; GPU handles many parallel tasks for graphics; TPU is a specialised AI chip | Match component to function; compare RAM vs ROM; compare GPU vs TPU | `Needs revision` — correct PDF’s ROM description (“ROM serves as high-speed working memory” is inaccurate) |
| A3 | **Binary logic** — bits, voltage levels, logic gates, combinational and sequential circuits | 1 = high voltage, 0 = low voltage; gates: AND, OR, XOR, NAND, NOR, XNOR; truth tables; combinational circuits (adders, multiplexers); sequential circuits (flip-flops, latches) that lock voltage on clock ticks | Complete truth tables for the six gates; classify a circuit as combinational or sequential | `Outline only` |
| A4 | **System architecture and Von Neumann architecture** — shared memory, system buses, CU, ALU, clock, IAS, registers | Von Neumann architecture: instructions and data share memory connected by system buses; CU fetches/decodes instructions and emits control signals; ALU performs arithmetic and bitwise logical operations; system clock produces timing signals on the control bus; Immediate Access Store holds data/programs the CPU needs; registers include PC, MAR, MDR, CIR, ACC, SR | Label a Von Neumann diagram; explain why a system clock is needed; match each register to its role | `Outline only` |
| A5 | **Registers and status flags** — PC, MAR, MDR, CIR, ACC, SR; carry, overflow, zero, negative flags | PC stores address of next instruction; MAR stores RAM address being read/written; MDR holds data retrieved from or waiting to be written to RAM; CIR holds current instruction being decoded; ACC holds ALU results; SR records flags | “Which register holds the next instruction address?”; “Which register holds the current instruction?”; interpret simple flag outcomes | `Outline only` |
| A6 | **Fetch–Decode–Execute cycle and interrupts** — fetch, decode, execute, writeback; ISR | Fetch: MAR ← PC; MDR ← RAM[MAR]; IR ← MDR; PC ← PC + 1. Decode: CU decodes opcode in IR and generates control signals. Execute: ALU computes operands and updates status flags. Writeback: result saved. Interrupts: signal from device/software; priority set; ISR services highest-priority interrupt; interrupted task continues | Trace a simple ADD instruction through the FDE cycle; explain a keyboard interrupt | `Outline only` |
| A7 | **Memory hierarchy** — registers, cache, system memory, secondary storage; speed, capacity, cost trade-offs | Tier 1 CPU registers (flip-flops, ~1–2 KB, <0.5 ns); Tier 2 L1/L2/L3 cache (SRAM, 32 KB–128 MB, 1–15 ns); Tier 3 system memory (DRAM, 8–128 GB, 50–100 ns); Tier 4 secondary storage (NVMe flash SSD, 512 GB–4 TB, ~50,000 ns) | Order tiers by speed and capacity; explain why cache is small but fast; why secondary storage is large but slow | `Outline only` — **AMAT formula and AMAT calculation intentionally excluded** |
| A8 | **Processor specialization: CPU vs GPU vs TPU** — latency vs throughput; SIMT; ASIC; systolic array concept | CPU: low latency, complex branch prediction, deep out-of-order execution, large cache; GPU: high throughput, thousands of smaller arithmetic units, SIMT; TPU: ASIC for matrix multiplication, systolic array of processing elements | Compare CPU/GPU/TPU in a table; explain why GPUs suit graphics/AI workloads; explain TPU as a specialised AI chip | `Outline only` — keep systolic-array maths brief or optional |
| A9 | **Input/Output systems** — input devices, processing unit, memory, output devices, I/O controllers | I/O systems allow users/external devices to communicate with the computer; input devices send data/instructions; output devices present results; CPU processes; RAM stores working data; I/O controllers manage communication with peripherals | Walk through “closing a browser tab with a mouse”: input → driver/I/O → CPU processing → monitor output | `Outline only` |
| A10 | **Embedded systems** — microcontroller/processor, memory, sensors, actuators, I/O interfaces | Embedded systems perform a specific function inside a larger device; limited task set; e.g., washing machine receiving programme, monitoring water level/temperature and controlling motor | Identify sensors and actuators in a washing machine; classify devices as general-purpose or embedded | `Outline only` |
| A11 | **CPU core types** — P-cores vs E-cores; single-core vs multi-core | P-cores handle demanding tasks (gaming, complex calculations); E-cores deliver good performance with less power for background/lighter workloads; single-core has one core; multi-core has two or more; more cores can improve multitasking but performance also depends on clock speed, architecture and software | Scenario: game + music + background apps — how might an OS schedule work across P-cores and E-cores? | `Outline only` |
| A12 | **Number systems** — denary, binary, hexadecimal; conversion; why hexadecimal is useful | Denary base 10 (0–9); binary base 2 (0–1); hexadecimal base 16 (0–9, A–F; A=10 … F=15); binary↔denary; binary→hex by grouping four bits; hex is compact and used for memory addresses, machine code, colour values; each hex digit = four bits | Convert `1101₂` to denary; `13₁₀` to binary; `11010110₂` to hex (`D6₁₆`); explain why hex is shorter | `Outline only` |
| A13 | **RAM: DRAM vs SRAM** — volatility; refresh; density; speed; cost; common use | DRAM: transistor + capacitor, needs refresh, higher density, cheaper, main memory. SRAM: multiple transistors per bit, no refresh while powered, very fast, lower density, more expensive, CPU cache. Both volatile | Compare DRAM and SRAM; explain why SRAM is used for cache and DRAM for main memory | `Outline only` |
| A14 | **ROM types: PROM, EPROM, EEPROM; flash memory** — non-volatility; programming/erasing | ROM is non-volatile; PROM can normally be programmed once; EPROM erased with UV light and reprogrammed; EEPROM erased/reprogrammed electrically, often without removing the chip; flash memory erases/writes in blocks, used in SSDs, USB drives, memory cards | Match PROM/EPROM/EEPROM to erasing method; explain why ROM is useful for firmware | `Outline only` — correct PDF table typo “Electrically Programmable ROM” to “Electrically Erasable Programmable ROM” |
| A15 | **Display connections: HDMI vs VGA** — signal type; video/audio; connector; common use | HDMI: digital video and audio through one cable; modern monitors, TVs, projectors, gaming devices. VGA: analogue video only, no audio, older interface, quality affected by signal quality and cable length | Compare HDMI and VGA; choose a cable for a modern monitor vs an older projector | `Outline only` |

---

## 4. Part B — Networks

| ID | Topic and subtopics | Key content | Suggested activities | Status / notes |
|---|---|---|---|---|
| B1 | **Network fundamentals** — definition, uses, nodes, links, routers, switches | Network = two or more devices connected to share data and resources; nodes = devices; links = wired/wireless pathways; routers connect different networks and forward packets by IP address; switches direct data within a LAN using MAC addresses | Home Wi-Fi example: phone, laptop, printer as nodes; router vs switch matching activity | `Checked` (in Networks.md §3–4) |
| B2 | **Packets and packet switching** — header, payload, trailer; packet switching; reassembly | Packet = small chunk of data with header (source/destination/sequence number), payload (actual data), trailer (end marker + error-check bits); packet switching breaks data into packets that travel independently and are reassembled at destination | Trace a photo being split into packets and reassembled; diagram of rerouting around a failed link | `Checked` (Networks.md §5) |
| B3 | **Protocols and addressing** — TCP/IP, HTTP/HTTPS, FTP, DNS, Ethernet; MAC address; IP address (IPv4/IPv6); URL anatomy | Protocols = rules for communication; TCP = connection-oriented reliable; IP = connectionless addressing/routing; MAC = 48-bit physical identifier; IP = logical address (IPv4 32-bit, IPv6 128-bit); URL = protocol + subdomain + domain + top-level domain + path; DNS translates domain names to IP addresses | Label a URL; compare MAC and IP addresses; explain why TCP and IP are both needed | `Checked` (Networks.md §6) |
| B4 | **Network topologies** — bus, point-to-point, star, mesh, ring, hybrid, tree; pros/cons; selection | Each topology has different trade-offs in cost, reliability, scalability; star isolates failures; bus is cheap but single point of failure; mesh is fault-tolerant but expensive; tree is hierarchical; hybrid combines strengths | “Choose a topology for a school computer lab and justify it”; compare star vs mesh for fault tolerance | `Checked` (Networks.md §7) |
| B5 | **Data flow and transmission** — simplex, half-duplex, full-duplex; serial vs parallel; synchronous vs asynchronous | Simplex = one direction; half-duplex = both directions but not simultaneously; full-duplex = both directions simultaneously; serial = one bit at a time (longer distances); parallel = multiple bits simultaneously (short distances, skew/crosstalk issues); synchronous = timed/blocking; asynchronous = not timed/non-blocking | Classify examples: TV broadcast (simplex), walkie-talkie (half-duplex), telephone (full-duplex); compare serial vs parallel | `Checked` (Networks.md §8) |
| B6 | **Network architecture** — LAN, WAN, MAN; client-server vs peer-to-peer | LAN = limited area, star topology; WAN = large geographical area, mesh/hybrid; MAN = city/campus, tree; client-server = centralized, fixed roles; P2P = decentralized, each node acts as client and server | Compare LAN vs WAN; match client-server and P2P to examples (web browsing, BitTorrent) | `Checked` (Networks.md §9) |
| B7 | **Network threats and security** — malware, cyberattacks, vulnerabilities, countermeasures | Malware: virus, worm, Trojan, spyware, adware, ransomware; cyberattacks: brute-force, packet sniffing, DoS/DDoS, hacking, phishing, pharming, social engineering; vulnerabilities: weak passwords, unpatched software, misconfigured access, removable media; countermeasures: firewall, encryption, antivirus, authentication, VPN, IDS/IPS; symmetric vs asymmetric encryption; HTTPS uses both | Match threat to countermeasure; classify phishing vs pharming; scenario: “repeated password attempts — what defence?” | `Checked` (Networks.md §10) |
| B8 | **Optional enrichment: advanced networking** — OSI/TCP-IP layers, encapsulation, Ethernet framing, IP addressing/subnetting, routing protocols, TCP/UDP details | OSI 7-layer and TCP/IP stack; encapsulation/decapsulation; Ethernet MAC structure and switching; IPv4 addressing, subnet masks, NAT; distance-vector/link-state/path-vector routing; TCP vs UDP; TCP flow/congestion control | Label OSI layers; explain encapsulation; compare TCP and UDP | `Outline only` — **optional enrichment**; advanced subnetting and protocol-stack detail are out of core scope for beginners |

---

## 5. Part C — Behavioural AI

| ID | Topic and subtopics | Key content | Suggested activities | Status / notes |
|---|---|---|---|---|
| C1 | **Introduction to Behavioural AI** — definition; difference from rule-based and generative AI | Behavioural AI (also called Behaviorist AI or Reactive AI) builds intelligent systems by coupling sensory inputs directly to motor actions without complex internal world models; differs from classical deliberative AI and from rule-based software | Compare a fixed “if password wrong, lock account” rule with a system that learns normal login behaviour | `Outline only` — terminology decision needed: “Behavioural AI” vs “Behaviorist AI” |
| C2 | **Telemetry and core components** — telemetry data; pattern recognition; anomaly detection; user behaviour modelling | Historical and real-time telemetry; pattern recognition (recurring habits, keystrokes, navigation styles, operational baselines); anomaly detection (deviations from normal); user behaviour modelling (dynamic profiles to predict actions/intents) | Example: bank card suddenly used in another country; keystroke rhythm for continuous authentication; diagram: telemetry → pattern → anomaly → action | `Outline only` |
| C3 | **Practical applications** — cybersecurity, fraud detection, adaptive UX | Cybersecurity: continuous authentication, insider threat detection; fraud detection: unusual transaction patterns; adaptive UX: personalising interfaces based on interaction trends | Case study: “How could Behavioural AI detect an insider threat?”; design a simple adaptive learning app rule | `Outline only` — avoid overclaiming real products |
| C4 | **Principles and concepts (brief enrichment)** — reinforcement learning, MDP, exploration vs exploitation, Q-learning | RL: agent, environment, action, reward, policy; MDP: states, actions, transition model, reward function, policy; exploration vs exploitation; Q-learning and DQN as examples | Worked conceptual example: robot learns to avoid obstacles using rewards; question: “What is the exploration–exploitation trade-off?” | `Outline only` — **conceptual only**; Bellman equation and MDP mathematics out of scope for beginners |
| C5 | **Critiques, limitations and ethics** — internal state representation; generalisation; dynamic environments; partial observability; ethical reasoning; privacy and consent; unintended consequences | Behaviourist systems lack internal state representation; struggle with generalisation and dynamic/partially observable environments; raise ethical issues around privacy, consent and unintended consequences | Debate: “Should a school use behavioural AI to detect cheating?”; list privacy safeguards | `Outline only` — include balanced treatment of privacy and ethics |
| C6 | **Optional enrichment: reactive architectures** — subsumption architecture, motor schema, artificial potential fields, finite state machines | Subsumption architecture: layered behaviours with suppression/inhibition; motor schema and APF: vector fields for attraction/repulsion; local minima trap and solutions; FSM: states and transitions | Diagram a simple subsumption controller (e.g., Roomba); explain how APF combines attractive and repulsive forces | `Outline only` — **optional enrichment**; advanced vector mathematics out of core scope |

---

## 6. Part D — Integration and future trends

| ID | Topic and subtopics | Key content | Suggested activities | Status / notes |
|---|---|---|---|---|
| D1 | **Connecting hardware, networks and Behavioural AI** — sensors, telemetry, edge processing, latency, bandwidth, cloud, privacy | Example: autonomous edge robotics pod — hardware (SoC with CPU/GPU/TPU, sensors, actuators); networking (5G, UDP telemetry, TCP commands); Behavioural AI (subsumption/APF navigation, collision avoidance) | Design a simple “smart campus” system: sensors → edge device → network → Behavioural AI anomaly detection | `Outline only` — best place to show how the three parts connect |
| D2 | **Future trends (brief enrichment)** — advanced RL, neuromorphic computing, quantum computing, 5G, federated learning, distributed AI, AI-oriented hardware | Brief survey of emerging trends; AI hardware (CPU vs GPU vs TPU; ASIC, FPGA); distributed and federated learning; 5G and edge AI | Short research task: “Choose one trend and explain one benefit and one limitation” | `Outline only` — keep brief; do not displace core content |

---

## 7. Development status summary

| Part | Status | Notes |
|---|---|---|
| Hardware | `Outline only` | Content drafted but needs correction (ROM description, AMAT exclusion confirmed) and alignment |
| Networks | `Checked` (core), `Outline only` (advanced enrichment) | Core beginner content is checked in Networks.md; advanced networking is optional |
| Behavioural AI | `Outline only` | Needs terminology decision, simplification and alignment; advanced reactive architectures optional |
| Integration / future trends | `Outline only` | Enrichment material available but should remain brief |

---

## 8. Known gaps and corrections

1. **Hardware ROM description** in the PDF must be corrected: ROM is non-volatile memory for firmware/persistent instructions, not “high-speed working memory”.
2. **Hardware ROM table typo:** “Electrically Programmable ROM” → “Electrically Erasable Programmable ROM”.
3. **AMAT formula and calculation** are intentionally excluded from the Hardware outline; the memory hierarchy is conceptual only.
4. **Terminology:** “Behavioural AI” vs “Behaviorist AI” must be standardised.
5. **Networks advanced topics** (OSI/TCP-IP layers, subnetting, routing protocols, TCP/UDP details) are marked optional enrichment and should not displace core beginner content.
6. **Behavioural AI advanced mathematics** (Bellman equation, MDP mathematics, Q-learning algorithms) is out of core scope; only conceptual understanding is required.
7. **Images and diagrams** should be stored locally in an `assets/` folder before PDF export.
8. **Networks.md images** referenced as external GitHub URLs must be downloaded and replaced with local relative paths.

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

### Behavioural AI
1. How is Behavioural AI fundamentally different from static, rule-based security systems?
2. List and explain the three core components of a Behavioural AI framework (telemetry, pattern recognition, anomaly detection).
3. Give an example of how anomaly detection is used to prevent financial fraud.
4. What are the primary privacy and ethical concerns when collecting data for behavioural modelling?
5. What is the exploration–exploitation trade-off? (Conceptual only.)
6. How does reinforcement learning relate to Behavioural AI? (Conceptual only.)