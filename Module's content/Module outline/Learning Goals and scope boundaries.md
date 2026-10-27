# Scope and Learning Goals - Hardware, Networks and Behaviourist AI

## Target Learners and Prerequisites

Learners need no prior knowledge of computing. Binary and denary are taught in the Hardware topic (Topic 1), so learners do not need to study them beforehand. At most, they may know that computers use 0s and 1s. Topic 1 builds binary and denary step by step from place value, before it moves on to hardware components, so later topics can use them.

We assume only basic digital literacy: files, folders, browsers, and common devices. We do not assume any programming, advanced mathematics, prior knowledge of networking protocols, or technical vocabulary. Basic English reading skills are assumed; every technical term will be defined in plain language at first use.

## Learning Goals

**By the end of the module, a beginner should be able to do the following.**

### Hardware

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

### Networks

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

### Behaviourist AI

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
41. Explain how hardware, networking and Behaviourist AI connect in the autonomous edge robotics pod.

## Main Topics

The module is built around three main topics, each with its own focus and purpose within the overall learning sequence.

**Topic 1 - Hardware.** This topic introduces binary and denary, taught first so learners can apply them to memory and storage. It covers the physical components of a computer, including the CPU, RAM, and ROM, and explains the Von Neumann architecture, registers, and the fetch-decode-execute cycle. It also distinguishes between different types of memory, such as SRAM and DRAM, and covers input/output systems and display connections.

**Topic 2 - Networks.** This topic defines what a computer network is and identifies its key components, such as nodes, routers, and switches. It explains how data is broken into packets and reassembled, distinguishes between TCP and IP, and covers MAC and IP addressing. It also explores network topologies, data transmission methods, and introduces network threats and basic defences, including encryption.

**Topic 3 - Behaviourist AI.** This topic explains what Behaviourist AI is: Brooks-style reactive robotics where sensory inputs are coupled directly to motor actions. It contrasts this with classical deliberative AI and covers the Sense-Model-Plan-Act loop, Brooks' four core axioms, and the subsumption architecture. It also introduces motor schemas (artificial potential fields), finite state machines, and Q-learning conceptually, finishing with the limitations and ethical concerns of reactive systems.

## Scope Boundaries

Definitions of hardware and software, and the main physical components.
Binary logic, simple truth tables for logic gates, and the Von Neumann architecture.
The fetch-decode-execute cycle and the role of key registers.
Network components, packet switching, and the difference between TCP and IP.
Network topologies, data flow types, and common network threats with basic countermeasures.
The definition of Behaviourist AI, the sense-act loop, and Brooks' four axioms.
The subsumption architecture, artificial potential fields (conceptually), and finite state machines.

What gets brief mention only:

* Hexadecimal, binary addition, and negative numbers in binary.
* How text, images and sound are stored as bits.
* Internal workings of the CPU and pipeline hazards.
* Layered network models (OSI/TCP-IP) and packet structure.
* The mathematics of encryption and advanced cyberattack mechanics.
* Behaviourist AI extras: behaviour trees, formal APF equations, and the Q-learning update rule.

Our target learner is an absolute beginner with no programming or AI background. Our goals are for them to explain the connection between hardware, networks, and reactive robotics, and to understand how Behaviourist AI operates in dynamic environments.