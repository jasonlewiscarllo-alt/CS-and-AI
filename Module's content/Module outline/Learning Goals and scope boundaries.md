# All Topics Learning Goals and Scope Boundaries

**Module:** Hardware, Networks and Behaviourist AI  
**Team:** Max Medium  
**Scope of this document:** Learning goals and scope boundaries for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Explicit exclusion:** AMAT formula and AMAT calculation are out of scope for Hardware

> **Terminology note:** This document uses **Behaviourist AI** (British spelling). The module PDF uses **Behaviorist AI** (American spelling). Both refer to the same field: Brooks-style reactive, behaviour-based AI. One spelling must be chosen for learner-facing materials.

> **Note:** This document is separate from the content outline (`All_Topics_Content_Outline.md`). It defines what learners should achieve and what is inside/outside scope.

---

## 1. Target learners and assumptions

**Target learners:** Absolute beginners who can use a computer for everyday tasks (email, web browsing, social media) but have not studied computer hardware, networking or AI in detail.

**Assumed background:**

- Basic digital literacy: files, folders, browsers, common devices.
- No prior knowledge of binary, logic gates, registers or CPU architecture.
- No prior knowledge of networking protocols, topologies or security.
- No prior knowledge of AI, machine learning or reactive robotics.
- No programming, advanced mathematics or technical vocabulary assumed.
- Basic English reading skills; every technical term defined in plain language at first use.

**Learner needs:**

- Concrete analogies and step-by-step diagrams.
- Short, focused explanations with frequent checks for understanding.
- Activities requiring no prior technical knowledge.
- Clear separation between essential concepts and optional enrichment.

---

## 2. Learning goals

### Part A — Hardware

1. **Define computer hardware** as the physical parts of a computer that can be seen and touched, and distinguish it from software.
2. **Name main hardware components** — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU and TPU — and state the basic function of each.
3. **Explain binary logic** — computers use bits, with 1 representing high voltage and 0 representing low voltage.
4. **Identify common logic gates** — AND, OR, XOR, NAND, NOR and XNOR — and read simple truth tables.
5. **Distinguish combinational and sequential circuits** — adders and multiplexers vs flip-flops and latches.
6. **Describe Von Neumann architecture** — shared memory for instructions and data, system buses, Control Unit, ALU, system clock, Immediate Access Store.
7. **Explain the roles of key registers** — PC, MAR, MDR, CIR, ACC, SR — and the status flags carry, overflow, zero and negative.
8. **Trace the fetch–decode–execute cycle** — fetch, decode, execute, writeback — for a simple instruction.
9. **Explain interrupts and interrupt service routines** — what an interrupt is, priority handling, task resumption.
10. **Describe the memory hierarchy conceptually** — registers, cache, system memory, secondary storage — in terms of speed, capacity and cost trade-offs, **without AMAT calculation**.
11. **Compare CPU, GPU and TPU** — CPU for low-latency sequential work; GPU for high-throughput parallel work; TPU as a specialised AI chip.
12. **Describe I/O systems** — input devices, processing, memory, output devices and I/O controllers.
13. **Define embedded systems** and identify their main components — microcontroller/processor, memory, sensors, actuators, I/O interfaces.
14. **Compare CPU core types** — P-cores vs E-cores; single-core vs multi-core.
15. **Convert between binary and denary**, and **convert binary to hexadecimal** by grouping four bits.
16. **Explain why hexadecimal is useful** — compact representation of memory addresses, machine code and colour values; each hex digit represents four bits.
17. **Compare DRAM and SRAM** — refresh, density, speed, cost, common use.
18. **Compare PROM, EPROM and EEPROM**, and explain flash memory.
19. **Compare HDMI and VGA** — digital vs analogue signal, audio support, connector type, common use.

### Part B — Networks

20. **Define a computer network** and identify key components: nodes, links, routers, switches.
21. **Explain packets and packet switching** — header, payload, trailer; independent travel and reassembly.
22. **Distinguish TCP and IP** — TCP connection-oriented and reliable; IP connectionless addressing and routing.
23. **Explain MAC addresses and IP addresses** — MAC as 48-bit physical identifier; IP as logical address (IPv4 32-bit, IPv6 128-bit); state the difference.
24. **Describe the structure of a URL** — protocol, subdomain, domain name, top-level domain, path — and explain how DNS translates domain names into IP addresses.
25. **Compare common network topologies** — bus, point-to-point, star, mesh, ring, hybrid, tree — and choose an appropriate topology for a scenario.
26. **Explain simplex, half-duplex and full-duplex data flow** with everyday examples.
27. **Compare serial and parallel transmission**, and **synchronous and asynchronous transmission**.
28. **Compare LAN, WAN and MAN**, and **client-server and peer-to-peer models**.
29. **Identify common malware and cyberattacks** and match them to appropriate countermeasures.
30. **Explain why encryption is important** — symmetric vs asymmetric encryption, and how HTTPS uses both.

### Part C — Behaviourist AI (reactive robotics)

31. **Define Behaviourist AI** as building autonomous systems that couple sensory inputs directly to motor actions without complex internal world models.
32. **Distinguish Behaviourist AI** from classical deliberative (cognitivist) AI and from static rule-based software.
33. **Explain the Sense–Model–Plan–Act (SMPA) loop** and its latency bottleneck.
34. **Explain the frame problem** and the **symbol grounding problem**.
35. **State Brooks' four core axioms** — the world is its own best model; embodied and situated cognition; tight sensorimotor coupling; emergent behaviour.
36. **Describe the subsumption architecture** — layered behaviours, the difference between **suppression** and **inhibition**, and the robotic vacuum example.
37. **Explain motor schema / artificial potential fields conceptually** — attraction to goal, repulsion from obstacles, and the local minima trap.
38. **Explain how a finite state machine controls agent behaviour**, and **explain Q-learning conceptually** as learning from rewards.
39. **Give one real-world example of Behaviourist AI** (e.g., a robotic vacuum).
40. **State one limitation and one ethical concern** of Behaviourist AI (including privacy in modern edge robotics).
41. **Explain how hardware, networking and Behaviourist AI connect** in the autonomous edge robotics pod (Section 4 of the PDF).

---

## 3. Scope boundaries

| Part | Core — must teach | Brief introduction — optional enrichment | Out of scope — excluded from Stage 1 |
|---|---|---|---|
| **Hardware** | Hardware vs software; main components; bits and voltage levels; common logic gates and simple truth tables; combinational vs sequential circuits; Von Neumann architecture; CU, ALU, system clock, IAS; key registers PC/MAR/MDR/CIR/ACC/SR; status flags; FDE cycle; interrupts and ISR overview; memory hierarchy tiers **without AMAT calculation**; CPU vs GPU vs TPU conceptually; I/O systems; embedded systems; P-core/E-core, single/multi-core; binary↔denary and binary→hex conversion; why hex is useful; DRAM vs SRAM; PROM/EPROM/EEPROM and flash; HDMI vs VGA | Detailed register-transfer notation; full truth tables for all six gates; detailed cache mapping; bus width/speed calculations; TPU systolic-array concept and PE formula; HDMI version differences; NVMe protocol details; detailed logic-circuit design | **AMAT formula and AMAT calculation**; memory-latency calculations; advanced digital logic design; CPU pipeline hazards and detailed out-of-order execution; branch-predictor algorithms; TPU systolic-array mathematics; electrical engineering |
| **Networks** | Network definition; nodes/links/router/switch; packets and packet switching; TCP vs IP; MAC vs IP; URL anatomy and DNS; common topologies with pros/cons; simplex/half/full-duplex; serial vs parallel; synchronous vs asynchronous; LAN/WAN/MAN; client-server vs P2P; malware and cyberattacks with countermeasures; encryption basics | Client-server vs P2P in more detail; additional malware types; advanced encryption concepts; basic routing concepts | Protocol stacks (OSI/TCP-IP layers) in detail; subnetting and CIDR; NAT; detailed routing protocols (RIP, OSPF, BGP); TCP flow/congestion control; detailed cyberattack mechanics; packet sniffing tools |
| **Behaviourist AI** | Definition of Behaviourist AI (reactive, sense→act); reactive vs deliberative distinction; SMPA loop and its latency bottleneck; frame problem; symbol grounding problem; Brooks' four axioms (world as its own model; embodied/situated cognition; tight sensorimotor coupling; emergent behaviour); subsumption architecture (layers, suppression vs inhibition, AFSM concept); robotic vacuum case study; motor schema / APF conceptually (attraction, repulsion, local minima trap); finite state machines; Q-learning conceptually (learn from rewards); limitations and ethics; privacy in modern edge robotics | AFSM detail; formal APF vector equations; Q-learning update rule (α, γ); DQN; layered arbitration mechanics; T-maze / path-planning examples | Full APF calculus and derivations; Bellman equation; full Q-learning algorithm implementation; DQN training; advanced robotics kinematics; neuromorphic computing mathematics; behavioural-analytics topics (telemetry, user modelling, anomaly detection, fraud detection, adaptive UX) |
| **Integration** | One example connecting hardware → network → Behaviourist AI (autonomous edge robotics pod: SoC + sensors + 5G/UDP/TCP + Subsumption/APF) | Future trends (neuromorphic computing, quantum computing, 5G, federated learning) as brief enrichment | Detailed system design; advanced distributed AI; hardware/software co-design |

---

## 4. AMAT exclusion statement

The **AMAT formula and AMAT calculation are intentionally excluded** from the Hardware learning goals and scope. The memory hierarchy may be taught conceptually using the tier table, but learners are **not** required to calculate Average Memory Access Time.

---

## 5. Uncertainties to confirm

1. **Terminology:** "Behaviourist AI" is the standard term in this document; the PDF uses "Behaviorist AI". Confirm British or American spelling for learner-facing materials.
2. **Hardware depth:** Should learners memorise all registers (PC, MAR, MDR, CIR, ACC, SR), or only understand the FDE cycle conceptually?
3. **Hardware logic gates:** All six gates and truth tables core, or only AND/OR/NOT/XOR?
4. **Hardware status flags:** Should learners interpret carry/overflow/zero/negative flags, or only know that flags exist?
5. **Hardware TPU depth:** Systolic-array concept core, brief enrichment, or omitted?
6. **Networks depth:** Should beginners learn topologies and transmission methods, or is the basic node/link/router/switch model enough?
7. **Networks advanced topics:** Are OSI/TCP-IP layers, subnetting and routing protocols core or optional enrichment?
8. **Behaviourist AI depth:** Should beginners learn the Q-learning update rule at all, or only "learn from rewards" conceptually?
9. **Behaviourist AI APF depth:** Should formal APF equations be core or brief enrichment?
10. **Assessment style:** Multiple-choice and matching, or short written explanations?
11. **ROM correction:** Confirm the PDF's ROM description will be corrected to "non-volatile memory for firmware/persistent instructions".

---

## 6. Next steps

1. Correct the Hardware ROM description and the "Electrically Programmable ROM" typo.
2. Confirm the spelling standard: "Behaviourist AI" or "Behaviorist AI".
3. Produce simple diagrams for Von Neumann architecture, FDE cycle, memory hierarchy, CPU/GPU/TPU comparison, packet switching, network topologies, subsumption layers, APF vectors around a robot, and the autonomous edge robotics pod.
4. Write one fully developed model topic per part — recommended: Hardware "The Fetch–Decode–Execute Cycle"; Networks "What is a Packet?"; Behaviourist AI "Subsumption Architecture and the Robotic Vacuum".
5. Add a glossary with plain-language definitions for all technical terms.
6. Confirm hardware register/logic-gate/TPU depth, networks advanced-topic depth and Behaviourist AI APF/Q-learning depth with the teacher.
7. Keep AMAT formula and calculations excluded from all learner-facing hardware materials.
8. Record all assistance and verification in the project and personal logs.