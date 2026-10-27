# All Topics — Learning Goals, Content Outline and Scope Boundaries

**Module:** Hardware, Networks and Behaviourist AI  
**Team:** Max Medium  
**Document purpose:** Combines learning goals, content outline (topics, subtopics, questions, answers) and scope boundaries for all three module parts  
**Source basis:** Module PDF (Sections 1–4); Networks.md; existing planning documents  
**Explicit exclusion:** AMAT formula and AMAT calculation are out of scope for Hardware

**Terminology note:** This module teaches **Behaviourist AI** (British spelling; American spelling: **Behaviorist AI**). In this document, Behaviourist AI means **Brooks-style reactive, behaviour-based AI**: autonomous systems that couple sensory inputs directly to motor actions without complex internal world models. It does **not** mean behavioural analytics (telemetry profiling, user behaviour modelling, anomaly detection, fraud detection, adaptive UX), which is explicitly out of scope for Part C. The team standardises on **Behaviourist AI** for all learner-facing materials.

---

## 1. Target learners and assumptions

**Target learners:** Absolute beginners who can use a computer for everyday tasks (email, web browsing, social media) but have not studied computer hardware, networking or AI in detail.

### Assumed background

- Basic digital literacy: files, folders, browsers, common devices.
- No prior knowledge of binary, logic gates, registers or CPU architecture.
- No prior knowledge of networking protocols, topologies or security.
- No prior knowledge of AI, machine learning or reactive robotics.
- No programming, advanced mathematics or technical vocabulary assumed.
- Basic English reading skills; every technical term defined in plain language at first use.

### Learner needs

- Concrete analogies and step-by-step diagrams.
- Short, focused explanations with frequent checks for understanding.
- Activities requiring no prior technical knowledge.
- Clear separation between essential concepts and optional enrichment.

---

## 2. Learning goals

### Part A — Hardware

1. Define computer hardware as the physical parts of a computer that can be seen and touched, and distinguish it from software.
2. Name main hardware components — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU and TPU — and state the basic function of each.
3. Explain binary logic — computers use bits, with 1 representing high voltage and 0 representing low voltage.
4. Identify common logic gates — AND, OR, XOR, NAND, NOR and XNOR — and read simple truth tables.
5. Distinguish combinational and sequential circuits — adders and multiplexers vs flip-flops and latches.
6. Describe Von Neumann architecture — shared memory for instructions and data, system buses, Control Unit, ALU, system clock, Immediate Access Store.
7. Explain the roles of key registers — PC, MAR, MDR, CIR, ACC, SR — and the status flags carry, overflow, zero and negative.
8. Trace the fetch-decode-execute cycle — fetch, decode, execute, writeback — for a simple instruction.
9. Explain interrupts and interrupt service routines — what an interrupt is, priority handling, task resumption.
10. Describe the memory hierarchy conceptually — registers, cache, system memory, secondary storage — in terms of speed, capacity and cost trade-offs, without AMAT calculation.
11. Compare CPU, GPU and TPU — CPU for low-latency sequential work; GPU for high-throughput parallel work; TPU as a specialised AI chip.
12. Describe I/O systems — input devices, processing, memory, output devices and I/O controllers.
13. Define embedded systems and identify their main components — microcontroller/processor, memory, sensors, actuators, I/O interfaces.
14. Compare CPU core types — P-cores vs E-cores; single-core vs multi-core.
15. Convert between binary and denary, and convert binary to hexadecimal by grouping four bits.
16. Explain why hexadecimal is useful — compact representation of memory addresses, machine code and colour values; each hex digit represents four bits.
17. Compare DRAM and SRAM — refresh, density, speed, cost, common use.
18. Compare PROM, EPROM and EEPROM, and explain flash memory.
19. Compare HDMI and VGA — digital vs analogue signal, audio support, connector type, common use.

### Part B — Networks

20. Define a computer network and identify key components: nodes, links, routers, switches.
21. Explain packets and packet switching — header, payload, trailer; independent travel and reassembly.
22. Distinguish TCP and IP — TCP connection-oriented and reliable; IP connectionless addressing and routing.
23. Explain MAC addresses and IP addresses — MAC as 48-bit physical identifier; IP as logical address (IPv4 32-bit, IPv6 128-bit); state the difference.
24. Describe the structure of a URL — protocol, subdomain, domain name, top-level domain, path — and explain how DNS translates domain names into IP addresses.
25. Compare common network topologies — bus, point-to-point, star, mesh, ring, hybrid, tree — and choose an appropriate topology for a scenario.
26. Explain simplex, half-duplex and full-duplex data flow with everyday examples.
27. Compare serial and parallel transmission, and synchronous and asynchronous transmission.
28. Compare LAN, WAN and MAN, and client-server and peer-to-peer models.
29. Identify common malware and cyberattacks and match them to appropriate countermeasures.
30. Explain why encryption is important — symmetric vs asymmetric encryption, and how HTTPS uses both.

### Part C — Behaviourist AI (reactive robotics)

31. Define Behaviourist AI as building autonomous systems that couple sensory inputs directly to motor actions without complex internal world models.
32. Distinguish Behaviourist AI from classical deliberative (cognitivist) AI and from static rule-based software.
33. Explain the Sense-Model-Plan-Act (SMPA) loop and its latency bottleneck.
34. Explain the frame problem and the symbol grounding problem.
35. State Brooks' four core axioms — the world is its own best model; embodied and situated cognition; tight sensorimotor coupling; emergent behaviour.
36. Describe the subsumption architecture — layered behaviours, the difference between suppression and inhibition, and the robotic vacuum example.
37. Explain motor schema / artificial potential fields conceptually — attraction to goal, repulsion from obstacles, and the local minima trap.
38. Explain how a finite state machine controls agent behaviour, and explain Q-learning conceptually as learning from rewards.
39. Give one real-world example of Behaviourist AI (e.g., a robotic vacuum).
40. State one limitation and one ethical concern of Behaviourist AI (including privacy in modern edge robotics).
41. Explain how hardware, networking and Behaviourist AI connect in the autonomous edge robotics pod (Section 4 of the PDF).

---

## 3. Content outline — Part C (Behaviourist AI) with topics, subtopics, questions and answers

### C1. Introduction to Behaviourist AI

**Subtopics:** definition; reactive vs deliberative AI; “intelligence without representation”.

**Key content:** Behaviourist AI (also called behaviour-based AI or reactive AI) builds intelligent autonomous systems by coupling sensory inputs directly to motor actions without relying on complex internal world models or formal logical deliberation. Pioneered by Rodney Brooks in the late 1980s.

**Activity:** Compare the SMPA loop (deliberative) with the sense–act loop (reactive); human reflex analogy.

**Status:** Outline only.

### C2. The symbolic crisis

**Subtopics:** Physical Symbol System Hypothesis; frame problem; symbol grounding problem; SMPA latency bottleneck.

**Key content:** Classical symbolic AI relied on manipulating abstract symbols, but failed in real physical environments due to:
1. **Frame Problem** — impossibility of efficiently updating a central world model with every non-change.
2. **Symbol Grounding Problem** — abstract symbols have no natural link to real sensor signals.
3. **SMPA Latency Bottleneck** — deliberative loops spend too long updating maps and calculating routes, so physical robots freeze or crash when environments change mid-calculation.

**Activity:** Explain why a deliberative robot freezes if the environment changes mid-plan; define “symbol grounding” with an example.

**Status:** Outline only.

### C3. Core axioms of Behaviourist AI

**Subtopics:** world as its own model; embodied and situated cognition; tight sensorimotor coupling; emergent behaviour.

**Key content:** Four principles (Brooks, “Intelligence Without Representation”):
1. **The World is Its Own Best Model** — query the real environment with sensors instead of maintaining an inaccurate internal map.
2. **Embodied and Situated Cognition** — intelligence must be in a physical body interacting with a physical environment.
3. **Tight Sensorimotor Coupling** — connect sensors directly to actuators via fast parallel channels (Sense → Act).
4. **Emergent Behaviour** — complex smart-looking behaviour emerges from simple reactive rules interacting with an unpredictable environment.

**Activity:** Match each axiom to a robot design decision; explain why emergent behaviour is not explicitly programmed.

**Status:** Outline only.

### C4. Subsumption architecture

**Subtopics:** layered behaviours; suppression and inhibition; AFSM; robotic vacuum case study.

**Key content:** Subsumption organises control into parallel task-achieving layers built from Augmented Finite State Machines (AFSMs); higher layers run concurrently above lower survival behaviours.
- **Suppression:** a higher layer intercepts and replaces the input signal flowing into a lower layer.
- **Inhibition:** a higher layer blocks or silences the output command emitted by a lower layer.
- **Layers:** Layer 0 basic survival (collision avoidance), Layer 1 wandering and exploration, Layer 2 goal seeking.
- **Robotic vacuum:** Layer 0 bumper → stop/reverse/rotate 45°; Layer 1 drive forward; Layer 2 dirt sensor → outward spiral.

**Activity:** Diagram a 3-layer subsumption controller; explain why Layer 0 overrides remote commands; trace a Roomba through a dirt-detection event.

**Status:** Outline only.

### C5. Motor schema and artificial potential fields

**Subtopics:** attraction; repulsion; net motion vector; local minima trap and solutions.

**Key content:** Motor Schema Architecture (Arkin) models control as continuous vector fields; net velocity = sum of attractive force (pull toward goal) and repulsive forces (push from obstacles); repulsion activates only within obstacle influence distance Q*. **Local minima trap** — when attractive and repulsive vectors cancel (F_total = 0) before the goal, the robot gets stuck. Solutions: inject random noise vectors (random walks) or switch to wall-following until the gradient clears.

**Activity:** Draw attraction/repulsion vectors around a robot; explain why a U-shaped obstacle causes a local minimum; suggest a reactive fix.

**Status:** Outline only — vector maths brief or optional.

### C6. Decision mechanics

**Subtopics:** finite state machines; model-free Q-learning.

**Key content:**
- **FSM:** restricts the agent to one active state at a time and switches on environmental triggers (e.g., PATROL → CHASE → FLEE based on player spotted / health under 20%).
- **Model-Free Q-Learning (Operant Conditioning):** learns an optimal policy matrix Q(s,a) directly from environmental rewards using a learning rate α and discount factor γ.

**Activity:** Design a 3-state FSM for a game enemy; explain Q-learning conceptually as “learn from rewards” without writing the full update equation.

**Status:** Outline only — Q-learning update rule is brief enrichment; Bellman equation out of scope.

### C7. Limitations and ethics

**Subtopics:** internal state representation; generalisation; dynamic environments; partial observability; ethical reasoning; privacy; unintended consequences.

**Key content:** Reactive systems lack internal state representation; struggle with generalisation and dynamic/partially observable environments; raise ethical issues around privacy, consent and unintended consequences in modern applications (camera-equipped robots, telemetry from delivery bots).

**Activity:** Debate “Should a delivery robot record video of pedestrians to improve navigation?”; list privacy safeguards for edge robotics.

**Status:** Outline only.

### C8. Optional enrichment — advanced reactive architectures

**Subtopics:** AFSM detail; APF mathematics; DQN.

**Key content:** Full AFSM structure; formal APF equations for U_att, F_att, U_rep, F_rep; Deep Q-Network (DQN) as modern extension.

**Activity:** Derive the APF equations; explain DQN vs tabular Q-learning.

**Status:** Outline only — optional enrichment.

---

## 4. Beginner questions and answers — Part C (Behaviourist AI)

**Q1. What does “Behaviourist AI” mean?**
A: It means AI designed around observable behaviour — sensory inputs and motor actions, coupled directly by rules or reflexes — rather than trying to reproduce internal human thoughts. The classic example is Brooks-style reactive robotics: a robot that senses and acts without building a detailed internal world model.

**Q2. How does a Behaviourist AI system sense, decide and act?**
A: Sensors receive input; a set of reactive rules, a state machine or the current state decides what to do; an actuator performs the action; the loop repeats immediately. There is no long planning stage — this is the sense–act loop.

**Q3. What is a state, and what makes a game character change from one state to another?**
A: A state is a named behaviour mode, such as patrol, chase or attack. A transition happens when a condition or event is met, such as seeing the player or losing health.

**Q4. What is the difference between a behaviour tree and a state machine?**
A: A state machine uses explicit states and transitions; a behaviour tree organises tasks hierarchically using sequences, selectors and tasks.

**Q5. What does “subsumption” mean?**
A: It is a layered approach where simple behaviours run together and a lower-level behaviour, such as avoiding obstacles, can override a higher-level behaviour such as wandering. Suppression replaces the input to a lower layer; inhibition blocks the output of a lower layer.

**Q6. How does Q-learning learn from rewards?**
A: The agent tries actions, receives rewards or penalties, and gradually adjusts a table of action-values Q(s,a) so that actions leading to higher reward are chosen more often. It learns from observable consequences, not from an internal model of the world.

**Q7. Why is Behaviourist AI described as reactive rather than deliberative?**
A: Because it couples sensing directly to acting, with little or no internal planning. Deliberative AI builds a world model, plans, then acts — which is slow and brittle in fast-changing environments.

**Q8. What is the frame problem?**
A: The difficulty of updating a central world model efficiently when only some things change. Classical AI tried to represent everything; Behaviourist AI avoids the problem by not maintaining a central model at all — the world is its own best model.

**Q9. What is the symbol grounding problem?**
A: Abstract symbols in a computer have no natural connection to real-world sensor signals. A robot that only manipulates symbols cannot know what “red” or “obstacle” actually means without grounding those symbols in sensory experience.

**Q10. What are two limitations of Behaviourist AI?**
A: It lacks internal state representation, so it struggles with tasks that need memory or planning; and it generalises poorly to new or partially observable environments.

**Q11. Why is privacy relevant to modern edge robotics, even though it was not central to Brooks' original work?**
A: Modern reactive robots often carry cameras and sensors and send telemetry to the cloud. Even though the AI is reactive, the data it collects can identify people and reveal behaviour, so consent, retention and anonymisation matter.

**Q12. Explain how hardware, networking and Behaviourist AI connect in the autonomous edge robotics pod.**
A: The hardware (SoC with CPU + GPU/TPU, sensors, motors) provides sensing and actuation; the network (5G, UDP for telemetry, TCP for commands) connects the pod to the fleet server; Behaviourist AI (subsumption and APF running on the onboard processor) turns sensor input into motor commands instantly, with Layer 0 collision avoidance overriding remote commands if a pedestrian steps in front.

---

## 5. Scope boundaries

| Part | Core — must teach | Brief introduction — optional enrichment | Out of scope — excluded from Stage 1 |
|---|---|---|---|
| **Hardware** | Hardware vs software; main components; bits and voltage levels; common logic gates and simple truth tables; combinational vs sequential circuits; Von Neumann architecture; CU, ALU, system clock, IAS; key registers PC/MAR/MDR/CIR/ACC/SR; status flags; FDE cycle; interrupts and ISR overview; memory hierarchy tiers without AMAT calculation; CPU vs GPU vs TPU conceptually; I/O systems; embedded systems; P-core/E-core, single/multi-core; binary–denary and binary–hex conversion; why hex is useful; DRAM vs SRAM; PROM/EPROM/EEPROM and flash; HDMI vs VGA | Detailed register-transfer notation; full truth tables for all six gates; detailed cache mapping; bus width/speed calculations; TPU systolic-array concept and PE formula; HDMI version differences; NVMe protocol details; detailed logic-circuit design | AMAT formula and AMAT calculation; memory-latency calculations; advanced digital logic design; CPU pipeline hazards and detailed out-of-order execution; branch-predictor algorithms; TPU systolic-array mathematics; electrical engineering |
| **Networks** | Network definition; nodes/links/router/switch; packets and packet switching; TCP vs IP; MAC vs IP; URL anatomy and DNS; common topologies with pros/cons; simplex/half/full-duplex; serial vs parallel; synchronous vs asynchronous; LAN/WAN/MAN; client-server vs P2P; malware and cyberattacks with countermeasures; encryption basics | Client-server vs P2P in more detail; additional malware types; advanced encryption concepts; basic routing concepts | Protocol stacks (OSI/TCP-IP layers) in detail; subnetting and CIDR; NAT; detailed routing protocols (RIP, OSPF, BGP); TCP flow/congestion control; detailed cyberattack mechanics; packet sniffing tools |
| **Behaviourist AI** | Definition of Behaviourist AI (reactive, sense–act); reactive vs deliberative distinction; SMPA loop and its latency bottleneck; frame problem; symbol grounding problem; Brooks' four axioms (world as its own model; embodied/situated cognition; tight sensorimotor coupling; emergent behaviour); subsumption architecture (layers, suppression vs inhibition, AFSM concept); robotic vacuum case study; motor schema / APF conceptually (attraction, repulsion, local minima trap); finite state machines; Q-learning conceptually (learn from rewards); limitations and ethics; privacy in modern edge robotics | AFSM detail; formal APF vector equations; Q-learning update rule (α, γ); DQN; layered arbitration mechanics; T-maze / path-planning examples | Full APF calculus and derivations; Bellman equation; full Q-learning algorithm implementation; DQN training; advanced robotics kinematics; neuromorphic computing mathematics; **behavioural-analytics topics (telemetry profiling, user behaviour modelling, anomaly detection, fraud detection, adaptive UX)** |
| **Integration** | One example connecting hardware → network → Behaviourist AI (autonomous edge robotics pod: SoC + sensors + 5G/UDP/TCP + Subsumption/APF) | Future trends (neuromorphic computing, quantum computing, 5G, federated learning) as brief enrichment | Detailed system design; advanced distributed AI; hardware/software co-design |

---

## 6. AMAT exclusion statement

The AMAT formula and AMAT calculation are intentionally excluded from the Hardware learning goals and scope. The memory hierarchy may be taught conceptually using the tier table, but learners are not required to calculate Average Memory Access Time.

---

## 7. Uncertainties to confirm

1. **Terminology spelling:** the team uses **Behaviourist AI** (British). The module PDF uses **Behaviorist AI** (American). Confirm that British spelling is acceptable for learner-facing materials, or switch to the PDF's American spelling throughout.
2. **Hardware depth:** Should learners memorise all registers (PC, MAR, MDR, CIR, ACC, SR), or only understand the FDE cycle conceptually?
3. **Hardware logic gates:** All six gates and truth tables core, or only AND/OR/NOT/XOR?
4. **Hardware status flags:** Should learners interpret carry/overflow/zero/negative flags, or only know that flags exist?
5. **Hardware TPU depth:** Systolic-array concept core, brief enrichment, or omitted?
6. **Networks depth:** Should beginners learn topologies and transmission methods, or is the basic node/link/router/switch model enough?
7. **Networks advanced topics:** Are OSI/TCP-IP layers, subnetting and routing protocols core or optional enrichment?
8. **Behaviourist AI depth:** Should beginners learn the Q-learning update rule at all, or only “learn from rewards” conceptually?
9. **Behaviourist AI APF depth:** Should formal APF equations be core or brief enrichment?
10. **Assessment style:** Multiple-choice and matching, or short written explanations?
11. **ROM correction:** Confirm the PDF's ROM description will be corrected to “non-volatile memory for firmware/persistent instructions”.

---

## 8. Next steps

1. Correct the Hardware ROM description and the “Electrically Programmable ROM” typo.
2. Confirm that **Behaviourist AI** (British) is the accepted spelling for learner-facing materials.
3. Produce simple diagrams for Von Neumann architecture, FDE cycle, memory hierarchy, CPU/GPU/TPU comparison, packet switching, network topologies, subsumption layers, APF vectors around a robot, and the autonomous edge robotics pod.
4. Write one fully developed model topic per part — recommended: Hardware “The Fetch-Decode-Execute Cycle”; Networks “What is a Packet?”; Behaviourist AI “Subsumption Architecture and the Robotic Vacuum”.
5. Add a glossary with plain-language definitions for all technical terms.
6. Confirm hardware register/logic-gate/TPU depth, networks advanced-topic depth and Behaviourist AI APF/Q-learning depth with the teacher.
7. Keep AMAT formula and calculations excluded from all learner-facing hardware materials.
8. Record all assistance and verification in the project and personal logs.

---

## 9. References

1. Watson, D., & Williams, H. (2016a). *AI and Computer Science Textbook, IGCSE & O Level* (2nd ed.). [Publisher details to be confirmed].
2. Watson, D., & Williams, H. (2016b). *Computer Science Textbook, AS & A Level*. [Publisher details to be confirmed].
3. Max Medium. (2026). *Module PDF: Hardware, Networks and Behaviourist AI*. Team source document.
4. Max Medium. (2026). *Networks.md*. Team draft.