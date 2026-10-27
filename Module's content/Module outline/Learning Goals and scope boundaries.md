# All_Topics_Learning_Goals_and_Scope.md

# All Topics Learning Goals and Scope Boundaries

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Scope of this document:** Learning goals and scope boundaries for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Explicit exclusion:** AMAT formula and AMAT calculation are out of scope for Hardware

> **Note:** This document is separate from the content outline (`All_Topics_Content_Outline.md`). It defines what learners should achieve and what is inside/outside the scope.

---

## 1. Target learners and assumptions

**Target learners:** Absolute beginners who can use a computer for everyday tasks (email, web browsing, social media) but have not studied computer hardware, networking or AI in detail.

**Assumed background:**

- Basic digital literacy: using files, folders, browsers and common devices.
- No prior knowledge of binary, logic gates, registers or CPU architecture.
- No prior knowledge of networking protocols, topologies or security.
- No prior knowledge of AI, machine learning or behavioural modelling.
- No programming, advanced mathematics or technical vocabulary assumed.
- Basic English reading skills; every technical term should be defined in plain language when first used.

**Learner needs:**

- Concrete analogies and step-by-step diagrams.
- Short, focused explanations with frequent checks for understanding.
- Activities that require no prior technical knowledge.
- Clear separation between essential concepts and optional enrichment.

---

## 2. Learning goals

By the end of the module, absolute beginners should be able to:

### Part A — Hardware

1. **Define computer hardware** as the physical parts of a computer that can be seen and touched, and distinguish it from software.
2. **Name main hardware components** — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU and TPU — and state the basic function of each.
3. **Explain binary logic** — that computers use bits, with 1 representing high voltage and 0 representing low voltage.
4. **Identify common logic gates** — AND, OR, XOR, NAND, NOR and XNOR — and read simple truth tables.
5. **Distinguish combinational and sequential circuits** — combinational circuits such as adders and multiplexers; sequential circuits such as flip-flops and latches.
6. **Describe Von Neumann architecture** — shared memory for instructions and data, system buses, Control Unit, ALU, system clock and Immediate Access Store.
7. **Explain the roles of key registers** — PC, MAR, MDR, CIR, ACC and SR — and the status flags carry, overflow, zero and negative.
8. **Trace the fetch–decode–execute cycle** — fetch, decode, execute and writeback — for a simple instruction.
9. **Explain interrupts and interrupt service routines** — what an interrupt is, how priority is handled, and how the interrupted task resumes.
10. **Describe the memory hierarchy conceptually** — registers, cache, system memory and secondary storage — in terms of speed, capacity and cost trade-offs, **without AMAT calculation**.
11. **Compare CPU, GPU and TPU** — CPU for low-latency sequential work; GPU for high-throughput parallel work; TPU as a specialised AI chip.
12. **Describe I/O systems** — input devices, processing, memory, output devices and I/O controllers.
13. **Define embedded systems** and identify their main components — microcontroller/processor, memory, sensors, actuators and I/O interfaces.
14. **Compare CPU core types** — P-cores vs E-cores; single-core vs multi-core.
15. **Convert between binary and denary**, and **convert binary to hexadecimal** by grouping four bits.
16. **Explain why hexadecimal is useful** — compact representation of memory addresses, machine code and colour values; each hex digit represents four bits.
17. **Compare DRAM and SRAM** — refresh, density, speed, cost and common use.
18. **Compare PROM, EPROM and EEPROM**, and explain flash memory as a related technology.
19. **Compare HDMI and VGA** — digital vs analogue signal, audio support, connector type and common use.

### Part B — Networks

20. **Define a computer network** as two or more devices connected to share data and resources, and identify key components: nodes, links, routers and switches.
21. **Explain packets and packet switching** — the roles of header, payload and trailer; how packets travel independently and are reassembled.
22. **Distinguish TCP and IP** — TCP as connection-oriented and reliable; IP as connectionless addressing and routing.
23. **Explain MAC addresses and IP addresses** — MAC as a 48-bit physical identifier; IP as a logical address (IPv4 32-bit, IPv6 128-bit); state the difference.
24. **Describe the structure of a URL** — protocol, subdomain, domain name, top-level domain and path — and explain how DNS translates domain names into IP addresses.
25. **Compare common network topologies** — bus, point-to-point, star, mesh, ring, hybrid and tree — and choose an appropriate topology for a given scenario.
26. **Explain simplex, half-duplex and full-duplex data flow** using everyday examples.
27. **Compare serial and parallel transmission**, and **synchronous and asynchronous transmission**.
28. **Compare LAN, WAN and MAN**, and **client-server and peer-to-peer models**.
29. **Identify common malware and cyberattacks** — virus, worm, Trojan, spyware, adware, ransomware; brute-force, packet sniffing, DoS/DDoS, phishing, pharming, social engineering — and match them to appropriate countermeasures.
30. **Explain why encryption is important** — symmetric vs asymmetric encryption, and how HTTPS uses both.

### Part C — Behavioural AI

31. **Define artificial intelligence (AI)** in simple terms, and give one everyday example.
32. **Explain what “behavioural” means in Behavioural AI** — that the system watches what users do (patterns) to learn what is normal.
33. **Name the three core parts of Behavioural AI** — collecting data about behaviour (telemetry), spotting patterns, and noticing when something is unusual (anomaly detection).
34. **Give one example of how Behavioural AI is used** — e.g., detecting unusual bank transactions, or flagging suspicious login behaviour.
35. **State one privacy concern** about collecting behaviour data, and explain why consent matters.
36. **Explain the difference between Behavioural AI and rule-based software** — rule-based systems follow fixed rules; Behavioural AI learns from observed behaviour.
37. **Describe the exploration–exploitation trade-off conceptually** — balancing trying new actions against using known good actions.
38. **Explain how reinforcement learning relates to Behavioural AI conceptually** — learning from rewards and penalties.

### Part D — Integration

39. **Explain in simple terms how hardware, networks and Behavioural AI connect** — for example, a sensor collects data (hardware), sends it over a network, and an AI system looks for unusual patterns.

---

## 3. Scope boundaries

| Part | Core — must teach | Brief introduction — optional enrichment | Out of scope — excluded from Stage 1 |
|---|---|---|---|
| **Hardware** | Hardware vs software; main components (CPU, RAM, motherboard, Wi-Fi card, ROM, GPU/TPU); bits and voltage levels; common logic gates and simple truth tables; combinational vs sequential circuits; Von Neumann architecture; CU, ALU, system clock and IAS; key registers PC/MAR/MDR/CIR/ACC/SR; status flags; FDE cycle; interrupts and ISR overview; memory hierarchy tiers **without AMAT calculation**; CPU vs GPU vs TPU conceptually; I/O systems; embedded systems; P-core/E-core and single/multi-core; binary↔denary and binary→hex conversion; why hexadecimal is useful; DRAM vs SRAM; PROM/EPROM/EEPROM and flash; HDMI vs VGA | Detailed register-transfer notation; full truth tables for all six gates; detailed cache mapping; bus width/speed calculations; TPU systolic-array concept and PE formula; HDMI version differences; NVMe protocol details; detailed logic-circuit design | **AMAT formula and AMAT calculation**; memory-latency calculations; advanced digital logic design; CPU pipeline hazards and detailed out-of-order execution; branch-predictor algorithms; TPU systolic-array mathematics; electrical engineering |
| **Networks** | Network definition; nodes/links/router/switch; packets and packet switching; TCP vs IP; MAC vs IP; URL anatomy and DNS; common topologies (bus, point-to-point, star, mesh, ring, hybrid, tree) with pros/cons; simplex/half/full-duplex; serial vs parallel; synchronous vs asynchronous; LAN/WAN/MAN; client-server vs P2P; malware and cyberattacks with countermeasures; encryption basics | Client-server vs P2P in more detail; additional malware types; advanced encryption concepts; basic routing concepts | Protocol stacks (OSI/TCP-IP layers) in detail; subnetting and CIDR; NAT; detailed routing protocols (RIP, OSPF, BGP); TCP flow/congestion control; detailed cyberattack methods (DDoS mechanics, pharming mechanics); packet sniffing tools |
| **Behavioural AI** | AI definition; behavioural = watching patterns; three core parts (telemetry, pattern recognition, anomaly detection); one application; one privacy concern; difference from rule-based software; exploration–exploitation trade-off conceptually; reinforcement learning conceptually | More detail on reinforcement learning; user behaviour modelling; adaptive UX; insider threat detection; fraud detection case studies; ethical reasoning | MDP mathematics; Bellman equation; Q-learning algorithms; DQN; detailed subsumption architecture; motor schema and artificial potential fields mathematics; advanced robotics |
| **Integration** | One example connecting hardware → network → AI | Future trends (neuromorphic computing, quantum computing, 5G, federated learning) as brief enrichment | Detailed system design; advanced distributed AI; hardware/software co-design |

---

## 4. AMAT exclusion statement

The **AMAT formula and AMAT calculation are intentionally excluded** from the Hardware learning goals and scope. The memory hierarchy may be taught conceptually using the tier table — registers, cache, system memory and secondary storage — but learners are **not** required to calculate Average Memory Access Time.

---

## 5. Uncertainties to confirm

1. **Terminology:** Should absolute beginners be taught “Behavioural AI” or “Behaviorist AI”, or both with a clear explanation?
2. **Hardware depth:** Should learners memorise all registers (PC, MAR, MDR, CIR, ACC, SR), or only understand the FDE cycle conceptually?
3. **Hardware logic gates:** Are all six gates and truth tables core, or only AND/OR/NOT/XOR?
4. **Hardware status flags:** Should learners interpret carry/overflow/zero/negative flags, or only know that flags exist?
5. **Hardware TPU depth:** Should the systolic-array concept be core, brief enrichment, or omitted?
6. **Networks depth:** Should beginners learn network topologies and data transmission methods, or is the basic node/link/router/switch model enough?
7. **Networks advanced topics:** Are OSI/TCP-IP layers, subnetting and routing protocols core or optional enrichment?
8. **Behavioural AI depth:** Should beginners learn about reinforcement learning at all, or focus only on pattern recognition and anomaly detection?
9. **Assessment style:** Should activities be multiple-choice and matching, or short written explanations?
10. **ROM correction:** Confirm that the PDF’s ROM description will be corrected to “non-volatile memory for firmware/persistent instructions”.

---

## 6. Next steps

1. Correct the Hardware ROM description and the “Electrically Programmable ROM” typo.
2. Standardise the term “Behavioural AI” vs “Behaviorist AI”.
3. Produce simple diagrams for Von Neumann architecture, the FDE cycle, memory hierarchy, CPU/GPU/TPU comparison, packet switching, network topologies, and the three Behavioural AI components.
4. Write one fully developed model topic per part — recommended: Hardware “The Fetch–Decode–Execute Cycle”; Networks “What is a Packet?”; Behavioural AI “What is Behavioural AI?”.
5. Add a glossary with plain-language definitions for all technical terms.
6. Confirm hardware register/logic-gate/TPU depth and networks advanced-topic depth with the teacher.
7. Keep AMAT formula and calculations excluded from all learner-facing hardware materials.
8. Record all assistance and verification in the project and personal logs.
