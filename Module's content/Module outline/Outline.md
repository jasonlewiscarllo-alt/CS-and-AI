# All Topics Content Outline

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Scope of this document:** Content outline for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Companion document:** Detailed learning goals, assumptions and scope boundaries are in `All_Topics_Learning_Goals_and_Scope.md`. This outline supplies the topic sequence, planned activities, development status, and a summary of outcomes and prerequisites so that it satisfies the module-outline requirement on its own.  
**Explicit exclusion:** AMAT formula and AMAT calculation are excluded from the Hardware section.

---

## 1. Purpose

This outline structures the full module content across Hardware, Networks and Behavioural AI. It lists topics, subtopics, key content points, suggested activities, scope classification (Core / Optional / Excluded) and current status. Advanced or enrichment material is marked so that core beginner content remains clear.

## 2. Status key

| Status | Meaning |
|---|---|
| Outline only | Structure and key points identified; no full learner-facing prose yet |
| Drafted | Some real content exists |
| Needs revision | Content exists but has known issues |
| Checked | Reviewed and confirmed |
| Removed | Topic removed from Stage 1 |
| Excluded from Stage 1 | Not learner-facing in Stage 1; may be reconsidered later |

## 3. Learning outcomes summary

By the end of the module, absolute beginners should be able to:

| Part | Learners should be able to… |
|---|---|
| **A — Hardware** | Define hardware and distinguish it from software; name main components (CPU, RAM, motherboard, Wi-Fi card, ROM, GPU, TPU) and state their functions; explain bits and voltage levels; identify common logic gates (AND, OR, NOT, XOR, NAND, NOR, XNOR) and read simple truth tables; distinguish combinational and sequential circuits; describe Von Neumann architecture, key registers and status flags; trace the fetch–decode–execute cycle; explain interrupts and ISRs at overview level; describe the memory hierarchy conceptually (no AMAT); compare CPU, GPU and TPU conceptually; describe I/O systems and embedded systems; compare P-cores/E-cores and single/multi-core; convert binary↔denary and binary→hex; explain why hexadecimal is useful; compare DRAM/SRAM, PROM/EPROM/EEPROM and flash, and HDMI/VGA. |
| **B — Networks** | Define a network and its key components; explain packets and packet switching; distinguish TCP and IP; distinguish MAC and IP addresses; label a URL and explain DNS; compare common topologies and choose one for a scenario; explain simplex/half/full-duplex, serial/parallel and synchronous/asynchronous; compare LAN/WAN/MAN and client-server/P2P; identify common malware and cyberattacks and match them to countermeasures; explain why encryption matters and how HTTPS uses symmetric and asymmetric encryption. |
| **C — Behavioural AI** | Define AI in simple terms; explain what “behavioural” means (watching patterns to learn what is normal); name the three core parts (telemetry, pattern recognition, anomaly detection); give one application; state one privacy concern and explain why consent matters; distinguish Behavioural AI from rule-based software; explain the exploration–exploitation trade-off and how reinforcement learning relates conceptually. |
| **D — Integration** | Explain in simple terms how hardware, networks and Behavioural AI connect in one example. |

## 4. Prerequisites

- Basic digital literacy: using files, folders, browsers and common devices.
- No prior knowledge of binary, logic gates, registers or CPU architecture.
- No prior knowledge of networking protocols, topologies or security.
- No prior knowledge of AI, machine learning or behavioural modelling.
- No programming, advanced mathematics or technical vocabulary assumed.
- Basic English reading skills; every technical term is defined in plain language when first used.

## 5. Part A — Hardware

| ID | Topic and subtopics | Key content from the PDF | Suggested activities | Scope | Status / notes |
|---|---|---|---|---|---|
| A1 | Introduction to computer hardware — physical parts; hardware vs software; processing, storage and interaction | Hardware is the physical parts that can be seen and touched; parts work together to process data at high speed, store information and allow user interaction | Classify items as hardware/software; label a simple computer system | Core | Outline only |
| A2 | Hardware components — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU/TPU | CPU as the “main brain”; RAM as short-term volatile workspace; motherboard connects parts using traces; Wi-Fi card sends/receives radio signals; ROM as non-volatile memory for firmware/persistent instructions; GPU handles many parallel tasks for graphics; TPU is a specialised AI chip | Match component to function; compare RAM vs ROM; compare GPU vs TPU | Core | Needs revision — correct PDF’s ROM description (“ROM serves as high-speed working memory” is inaccurate) |
| A3 | Binary logic — bits, voltage levels, logic gates, combinational and sequential circuits | 1 = high voltage, 0 = low voltage; common gates: AND, OR, NOT, XOR, NAND, NOR, XNOR; simple truth tables; combinational circuits (adders, multiplexers); sequential circuits (flip-flops, latches) that lock voltage on clock ticks | Read and complete simple truth tables for AND/OR/NOT/XOR; match all common gate names to their symbols and one-line descriptions; classify a circuit as combinational or sequential | Core | Outline only — full truth tables for all seven gates are **optional enrichment**; detailed logic-circuit design is out of scope |
| A4 | System architecture and Von Neumann architecture — shared memory, system buses, CU, ALU, clock, IAS, registers | Von Neumann architecture: instructions and data share memory connected by system buses; CU fetches/decodes instructions and emits control signals; ALU performs arithmetic and bitwise logical operations; system clock produces timing signals on the control bus; Immediate Access Store holds data/programs the CPU needs; registers include PC, MAR, MDR, CIR, ACC, SR | Label a Von Neumann diagram; explain why a system clock is needed; match each register to its role | Core | Outline only |
| A5 | Registers and status flags — PC, MAR, MDR, CIR, ACC, SR; carry, overflow, zero, negative flags | PC stores address of next instruction; MAR stores RAM address being read/written; MDR holds data retrieved from or waiting to be written to RAM; CIR holds current instruction being decoded; ACC holds ALU results; SR records flags | “Which register holds the next instruction address?”; “Which register holds the current instruction?”; interpret simple flag outcomes | Core | Outline only |
| A6 | Fetch–Decode–Execute cycle and interrupts — fetch, decode, execute, writeback; ISR | Fetch: MAR ← PC; MDR ← RAM[MAR]; IR ← MDR; PC ← PC + 1. Decode: CU decodes opcode in IR and generates control signals. Execute: ALU computes operands and updates status flags. Writeback: result saved. Interrupts: signal from device/software; priority set; ISR services highest-priority interrupt; interrupted task continues | Trace a simple ADD instruction through the FDE cycle; explain a keyboard interrupt | Core | Outline only |
| A7 | Memory hierarchy — registers, cache, system memory, secondary storage; speed, capacity, cost trade-offs | Tier 1 CPU registers (flip-flops, ~1–2 KB, <0.5 ns); Tier 2 L1/L2/L3 cache (SRAM, 32 KB–128 MB, 1–15 ns); Tier 3 system memory (DRAM, 8–128 GB, 50–100 ns); Tier 4 secondary storage (NVMe flash SSD, 512 GB–4 TB, ~50,000 ns) | Order tiers by speed and capacity; explain why cache is small but fast; why secondary storage is large but slow | Core | Outline only — **timings and sizes are illustrative only**; no latency or AMAT calculations are assessed; AMAT formula and AMAT calculation intentionally excluded |
| A8 | Processor specialization: CPU vs GPU vs TPU — latency vs throughput; parallel work; specialised AI chips | CPU: general-purpose, low-latency, good at sequential tasks with a few powerful cores. GPU: many smaller cores for high-throughput parallel work (graphics, AI training). TPU: specialised AI chip (ASIC) designed for matrix/tensor operations. | Compare CPU/GPU/TPU in a table; match a workload to a processor type; explain why GPUs suit graphics/AI workloads | Core | Outline only — branch prediction, out-of-order execution and systolic-array mathematics are **optional background only, not assessed** |
| A9 | Input/Output systems — input devices, processing unit, memory, output devices, I/O controllers | I/O systems allow users/external devices to communicate with the computer; input devices send data/instructions; output devices present results; CPU processes; RAM stores working data; I/O controllers manage communication with peripherals | Walk through “closing a browser tab with a mouse”: input → driver/I/O → CPU processing → monitor output | Core | Outline only |
| A10 | Embedded systems — microcontroller/processor, memory, sensors, actuators, I/O interfaces | Embedded systems perform a specific function inside a larger device; limited task set; e.g., washing machine receiving programme, monitoring water level/temperature and controlling motor | Identify sensors and actuators in a washing machine; classify devices as general-purpose or embedded | Core | Outline only |
| A11 | CPU core types — P-cores vs E-cores; single-core vs multi-core | P-cores handle demanding tasks (gaming, complex calculations); E-cores deliver good performance with less power for background/lighter workloads; single-core has one core; multi-core has two or more; more cores can improve multitasking but performance also depends on clock speed, architecture and software | Scenario: game + music + background apps — how might an OS schedule work across P-cores and E-cores? | Core | Outline only |
| A12 | Number systems — denary, binary, hexadecimal; conversion; why hexadecimal is useful | Denary base 10 (0–9); binary base 2 (0–1); hexadecimal base 16 (0–9, A–F; A=10 … F=15); binary↔denary; binary→hex by grouping four bits; hex is compact and used for memory addresses, machine code, colour values; each hex digit = four bits | Convert 1101₂ to denary; 13₁₀ to binary; 11010110₂ to hex (D6₁₆); explain why hex is shorter | Core | Outline only |
| A13 | RAM: DRAM vs SRAM — volatility; refresh; density; speed; cost; common use | DRAM: transistor + capacitor, needs refresh, higher density, cheaper, main memory. SRAM: multiple transistors per bit, no refresh while powered, very fast, lower density, more expensive, CPU cache. Both volatile | Compare DRAM and SRAM; explain why SRAM is used for cache and DRAM for main memory | Core | Outline only |
| A14 | ROM types: PROM, EPROM, EEPROM; flash memory — non-volatility; programming/erasing | ROM is non-volatile; PROM can normally be programmed once; EPROM erased with UV light and reprogrammed; EEPROM erased/reprogrammed electrically, often without removing the chip; flash memory erases/writes in blocks, used in SSDs, USB drives, memory cards | Match PROM/EPROM/EEPROM to erasing method; explain why ROM is useful for firmware | Core | Outline only — correct PDF table typo “Electrically Programmable ROM” to “Electrically Erasable Programmable ROM” |
| A15 | Display connections: HDMI vs VGA — signal type; video/audio; connector; common use | HDMI: digital video and audio through one cable; modern monitors, TVs, projectors, gaming devices. VGA: analogue video only, no audio, older interface, quality affected by signal quality and cable length | Compare HDMI and VGA; choose a cable for a modern monitor vs an older projector | Core | Outline only |

## 6. Part B — Networks

| ID | Topic and subtopics | Key content | Suggested activities | Scope | Status / notes |
|---|---|---|---|---|---|
| B1 | Network fundamentals — definition, uses, nodes, links, routers, switches | Network = two or more devices connected to share data and resources; nodes = devices; links = wired/wireless pathways; routers connect different networks and forward packets by IP address; switches direct data within a LAN using MAC addresses | Home Wi-Fi example: phone, laptop, printer as nodes; router vs switch matching activity | Core | Checked (in Networks.md §3–4) |
| B2 | Packets and packet switching — header, payload, trailer; packet switching; reassembly | Packet = small chunk of data with header (source/destination/sequence number), payload (actual data), trailer (end marker + error-check bits); packet switching breaks data into packets that travel independently and are reassembled at destination | Trace a photo being split into packets and reassembled; diagram of rerouting around a failed link | Core | Checked (Networks.md §5) |
| B3 | Protocols and addressing — TCP/IP, HTTP/HTTPS, FTP, DNS, Ethernet; MAC address; IP address (IPv4/IPv6); URL anatomy | Protocols = rules for communication; TCP = connection-oriented reliable; IP = connectionless addressing/routing; MAC = 48-bit physical identifier; IP = logical address (IPv4 32-bit, IPv6 128-bit); URL = protocol + subdomain + domain + top-level domain + path; DNS translates domain names to IP addresses | Label a URL; compare MAC and IP addresses; explain why TCP and IP are both needed | Core | Checked (Networks.md §6) |
| B4 | Network topologies — bus, point-to-point, star, mesh, ring, hybrid, tree; pros/cons; selection | Each topology has different trade-offs in cost, reliability, scalability; star isolates failures; bus is cheap but single point of failure; mesh is fault-tolerant but expensive; tree is hierarchical; hybrid combines strengths | “Choose a topology for a school computer lab and justify it”; compare star vs mesh for fault tolerance | Core | Checked (Networks.md §7) |
| B5 | Data flow and transmission — simplex, half-duplex, full-duplex; serial vs parallel; synchronous vs asynchronous | Simplex = one direction; half-duplex = both directions but not simultaneously; full-duplex = both directions simultaneously; serial = one bit at a time (longer distances); parallel = multiple bits simultaneously (short distances, skew/crosstalk issues); synchronous = timed/blocking; asynchronous = not timed/non-blocking | Classify examples: TV broadcast (simplex), walkie-talkie (half-duplex), telephone (full-duplex); compare serial vs parallel | Core | Checked (Networks.md §8) |
| B6 | Network architecture — LAN, WAN, MAN; client-server vs peer-to-peer | LAN = limited area, star topology; WAN = large geographical area, mesh/hybrid; MAN = city/campus, tree; client-server = centralized, fixed roles; P2P = decentralized, each node acts as client and server | Compare LAN vs WAN; match client-server and P2P to examples (web browsing, BitTorrent) | Core | Checked (Networks.md §9) |
| B7 | Network threats and security — malware, cyberattacks, vulnerabilities, countermeasures | Malware: virus, worm, Trojan, spyware, adware, ransomware; cyberattacks: brute-force, packet sniffing, DoS/DDoS, hacking, phishing, pharming, social engineering; vulnerabilities: weak passwords, unpatched software, misconfigured access, removable media; countermeasures: firewall, encryption, antivirus, authentication, VPN, IDS/IPS; symmetric vs asymmetric encryption; HTTPS uses both | Match threat to countermeasure; classify phishing vs pharming; scenario: “repeated password attempts — what defence?” | Core | Checked (Networks.md §10) |

**B8 — Removed from Stage 1.** Advanced networking (OSI/TCP-IP layers in detail, encapsulation, Ethernet framing, subnetting/CIDR, NAT, routing protocols, TCP/UDP details, flow/congestion control) is **out of scope** per the learning-goals and scope document. It is not learner-facing content and has no activities or assessment in Stage 1.

## 7. Part C — Behavioural AI

| ID | Topic and subtopics | Key content | Suggested activities | Scope | Status / notes |
|---|---|---|---|---|---|
| C1 | Introduction to Behavioural AI — definition; AI in simple terms; difference from rule-based software; conceptual notes on reward/exploration | **AI in simple terms:** computer systems that perform tasks that normally need human intelligence (e.g., recognising patterns or making predictions). **Behavioural AI** learns what is normal by watching patterns in user behaviour (telemetry), then flags unusual activity (anomaly detection). It differs from rule-based software, which follows fixed rules written in advance. **Conceptual notes (not algorithms):** reinforcement learning means learning from rewards and penalties; the exploration–exploitation trade-off means balancing trying new actions against using known good ones. “Behaviorist AI” and “Reactive AI” are related historical terms; mention them only as optional context. | Compare a fixed “if password wrong, lock account” rule with a system that learns normal login behaviour; describe the exploration–exploitation trade-off in one everyday example | Core | Outline only — terminology standardised to **“Behavioural AI”**; “Behaviorist AI” optional context only; no MDP/Bellman/Q-learning/DQN |
| C2 | Telemetry and core components — telemetry data; pattern recognition; anomaly detection; user behaviour modelling | Historical and real-time telemetry; pattern recognition (recurring habits, keystrokes, navigation styles, operational baselines); anomaly detection (deviations from normal); user behaviour modelling (dynamic profiles to predict actions/intents) | Example: bank card suddenly used in another country; keystroke rhythm for continuous authentication; diagram: telemetry → pattern → anomaly → action | Core | Outline only |
| C3 | Practical applications — cybersecurity, fraud detection, adaptive UX | Cybersecurity: continuous authentication, insider threat detection; fraud detection: unusual transaction patterns; adaptive UX: personalising interfaces based on interaction trends | Case study: “How could Behavioural AI detect an insider threat?”; design a simple adaptive learning app rule | Core | Outline only — avoid overclaiming real products |
| C5 | Critiques, limitations and ethics — privacy and consent (core); broader ethics (optional) | Core: one privacy concern about collecting behaviour data and why consent matters. Optional enrichment: internal state representation, generalisation, dynamic environments, partial observability, ethical reasoning, unintended consequences | Debate: “Should a school use behavioural AI to detect cheating?”; list privacy safeguards | Core (privacy/consent); Optional (broader ethics) | Outline only — keep core focused on privacy and consent; broader ethics is enrichment |
| C6 | Reactive architectures — subsumption architecture, motor schema, artificial potential fields, finite state machines | Subsumption architecture: layered behaviours with suppression/inhibition; motor schema and APF: vector fields for attraction/repulsion; local minima trap and solutions; FSM: states and transitions | *No Stage 1 activities* | **Excluded from Stage 1** | Outline only — optional future enrichment; advanced vector mathematics and detailed reactive architectures are out of scope for Stage 1 learner-facing content and assessment |

**C4 — Removed as a separate topic.** Its conceptual-only content (reward/penalty and exploration–exploitation) is folded into C1. Algorithmic content — MDP components, Bellman equation, Q-learning, DQN — is **out of scope** and is not learner-facing or assessed in Stage 1.

## 8. Part D — Integration and future trends

| ID | Topic and subtopics | Key content | Suggested activities | Scope | Status / notes |
|---|---|---|---|---|---|
| D1 | Connecting hardware, networks and Behavioural AI — sensors, telemetry, network transfer, anomaly detection | Simple example: a smart doorbell or fitness tracker. Hardware: sensor collects data (e.g., motion, heart rate). Network: device sends telemetry over Wi-Fi to a server. Behavioural AI: the system learns normal patterns and flags unusual activity (e.g., unrecognised visitor at an unusual time, abnormal heart-rate pattern). | Design a simple “smart campus” example: sensor → edge device → network → Behavioural AI anomaly alert. Label which part is hardware, which is network, and which is Behavioural AI. | Core | Outline only — keep example simple; avoid subsumption/APF/robotics navigation (out of scope) |
| D2 | Future trends (brief enrichment) — neuromorphic computing, quantum computing, 5G, federated learning, distributed AI, AI-oriented hardware | Brief survey of emerging trends; AI hardware (CPU vs GPU vs TPU; ASIC, FPGA); distributed and federated learning; 5G and edge AI | Short research task: “Choose one trend and explain one benefit and one limitation” | Optional | Outline only — keep brief; do not displace core content |

## 9. Development status summary

| Part | Status | Notes |
|---|---|---|
| Hardware | Outline only | Content drafted but needs correction (ROM description) and alignment; AMAT exclusion confirmed |
| Networks | Checked (core B1–B7); B8 removed | Core beginner content is checked in Networks.md; advanced networking removed from Stage 1 |
| Behavioural AI | Outline only; C4 removed (content folded into C1); C6 excluded | Terminology standardised; core focuses on telemetry, pattern recognition, anomaly detection, privacy/consent, and conceptual reward/exploration–exploitation; algorithms and reactive architectures excluded |
| Integration / future trends | Outline only | D1 simplified to a sensor → network → anomaly-detection example; D2 optional enrichment only |

## 10. Known gaps and corrections

1. Hardware ROM description in the PDF must be corrected: ROM is non-volatile memory for firmware/persistent instructions, not “high-speed working memory”. **Confirmed.**
2. Hardware ROM table typo: “Electrically Programmable ROM” → “Electrically Erasable Programmable ROM”. **Confirmed.**
3. AMAT formula and calculation are intentionally excluded from the Hardware outline; the memory hierarchy is conceptual only. **Confirmed.**
4. Terminology standardised to **“Behavioural AI”**; “Behaviorist AI” is optional context only. **Resolved.**
5. Networks advanced topics (B8) removed from Stage 1 and marked out of scope. **Resolved.**
6. Behavioural AI algorithms and mathematics (MDP, Bellman, Q-learning, DQN) excluded; **C4 removed as a separate topic**, with conceptual exploration–exploitation and RL content folded into C1. **Resolved.**
7. Reactive architectures (C6) excluded from Stage 1 learner-facing content and assessment. **Resolved.**
8. Images and diagrams should be stored locally in an `assets/` folder before PDF export.
9. Networks.md images referenced as external GitHub URLs must be downloaded and replaced with local relative paths.
10. File names standardised to `All_Topics_Content_Outline.md` and `All_Topics_Learning_Goals_and_Scope.md`; cross-references must match exactly.

## 11. Open decisions (to confirm with teacher)

| # | Decision needed | Current position | Status |
|---|---|---|---|
| 1 | “Behavioural AI” vs “Behaviorist AI” terminology | Use **Behavioural AI** as core term; “Behaviorist AI” optional context | Resolved in outline; confirm with teacher |
| 2 | Hardware register depth: memorise all six registers or understand FDE conceptually? | Teach all six at recognition level; FDE traced conceptually | Open |
| 3 | Logic gates: all gates and truth tables core, or only AND/OR/NOT/XOR? | All common gates identified (AND, OR, NOT, XOR, NAND, NOR, XNOR); AND/OR/NOT/XOR truth tables core; full seven-gate tables optional | Open |
| 4 | Status flags: interpret carry/overflow/zero/negative, or only know they exist? | Interpret simple flag outcomes | Open |
| 5 | TPU depth: systolic-array concept core, enrichment, or omitted? | Optional background only, not assessed | Open |
| 6 | Networks depth: topologies and transmission methods core, or only node/link/router/switch? | Topologies and transmission methods core (B4–B5) | Open |
| 7 | Networks advanced topics: OSI/TCP-IP layers, subnetting, routing protocols core or optional? | Out of scope for Stage 1 (B8 removed) | Resolved in outline; confirm with teacher |
| 8 | Behavioural AI depth: include reinforcement learning at all? | Conceptual reward/penalty and exploration–exploitation only, folded into C1; no algorithms | Resolved in outline; confirm with teacher |
| 9 | Assessment style: multiple-choice/matching vs short written explanations? | Mix planned; confirm weighting | Open |
| 10 | ROM correction confirmation | Corrected to “non-volatile memory for firmware/persistent instructions” | Confirmed |

## 12. Suggested review questions (by part)

**Hardware**
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
13. Convert 1101₂ to denary.
14. Convert 13₁₀ to binary.
15. Convert 11010110₂ to hexadecimal.
16. Why is hexadecimal useful in computing?
17. Compare DRAM and SRAM.
18. Compare PROM, EPROM and EEPROM.
19. Compare HDMI and VGA.

**Networks**
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

**Behavioural AI**
1. How is Behavioural AI fundamentally different from static, rule-based security systems?
2. List and explain the three core components of a Behavioural AI framework (telemetry, pattern recognition, anomaly detection).
3. Give an example of how anomaly detection is used to prevent financial fraud.
4. What is one privacy concern when collecting behaviour data, and why does consent matter?
5. What is the exploration–exploitation trade-off? (Conceptual only — covered in C1.)
6. How does reinforcement learning relate to Behavioural AI? (Conceptual only — covered in C1.)

## 13. Changelog (this revision)

| Change | Reason |
|---|---|
| Added **Learning outcomes summary** and **Prerequisites** sections | Satisfies General Instructions Section B on the outline itself |
| Added **Scope** column (Core / Optional / Excluded) to all topic tables | Makes scope boundaries visible and prevents drift |
| **B8 removed** and replaced with a removal note | Aligns with scope document |
| **C4 removed as a separate topic**; conceptual exploration–exploitation and RL content folded into C1 | Aligns with user instruction; keeps learning goals 7–8 met without a separate assessed topic |
| **C6 relabelled “Excluded from Stage 1”**, activities removed | Aligns with scope document |
| **C1 definition standardised**, AI defined in simple terms, conceptual notes added | Resolves definitional conflict and meets goals |
| **C5 split** into core (privacy/consent) and optional (broader ethics) | Aligns with learning goals |
| **A3 updated**: all common gates named; full seven-gate tables optional; matching activity added | Aligns with scope document and goals |
| **A8 replaced**: beginner CPU/GPU/TPU comparison; advanced internals optional background | Aligns with scope document |
| **A7 note added**: timings illustrative only; no latency/AMAT calculations assessed | Reinforces AMAT exclusion |
| **D1 simplified** to sensor → network → anomaly detection | Aligns with scope document |
| Added **Open decisions** table and **changelog** | Meets “gaps and uncertainties” requirement transparently |
| File names standardised | Fixes broken cross-reference |