# Hardware_Content_Outline.md

# Hardware Content Outline

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Scope of this document:** Hardware only  
**Source basis:** Module PDF, Hardware sections 1–1.13  
**Explicit exclusions:** Networks content, Behaviourist AI content, and the AMAT formula/calculation  

> **Note:** The PDF’s ROM description (“ROM serves as high-speed working memory”) is inaccurate and should be corrected in final content. ROM is non-volatile memory used for firmware/persistent instructions. This outline flags that correction.

---

## 1. Purpose

This outline structures the Hardware component of the module. It covers computer hardware, binary logic, Von Neumann architecture, the fetch–decode–execute cycle, memory hierarchy concepts, processor specialization, I/O systems, embedded systems, CPU core types, number systems, RAM/ROM types, and display connections.

The AMAT formula and AMAT worked calculations are deliberately omitted.

---

## 2. Status key

| Status | Meaning |
|---|---|
| `Outline only` | Structure and key points identified; no full learner-facing prose yet |
| `Drafted` | Some real content exists |
| `Needs revision` | Content exists but has known issues |
| `Checked` | Reviewed and confirmed |

---

## 3. Hardware content outline

| ID | Topic and subtopics | Key content from the PDF | Suggested examples / activities | Status / notes |
|---|---|---|---|---|
| H1 | **Introduction to computer hardware** — physical parts; hardware vs software; processing, storage and interaction | Computer hardware is the physical parts of a computer that can be seen and touched; parts work together to process data at high speed, store information and allow user interaction | Classify items as hardware/software; label a simple computer system | `Outline only` |
| H2 | **Hardware components** — CPU, RAM, motherboard, Wi-Fi card, ROM, GPU/TPU | CPU as the “main brain” that makes decisions and coordinates step-by-step work; RAM as short-term workspace that is fast but volatile; motherboard as foundation connecting parts using traces; Wi-Fi card sends/receives radio signals; ROM as non-volatile memory for persistent instructions/firmware; GPU handles many parallel tasks for graphics; TPU is a specialised AI chip | Match component to function; compare RAM vs ROM; compare GPU vs TPU | `Needs revision` — correct PDF’s ROM description; clarify RAM vs ROM vs storage |
| H3 | **Binary logic** — bits, voltage levels, logic gates, combinational and sequential circuits | Binary digits: 1 = high voltage, 0 = low voltage; logic gates include AND, OR, XOR, NAND, NOR, XNOR; truth tables; combinational circuits such as adders and multiplexers; sequential circuits such as flip-flops and latches that lock voltage on clock ticks | Complete truth tables for AND/OR/XOR/NAND/NOR/XNOR; classify a circuit as combinational or sequential | `Outline only` |
| H4 | **System architecture and Von Neumann architecture** — shared memory, system buses, CU, ALU, clock, IAS, registers | General-purpose computers follow Von Neumann architecture; instructions and data share memory connected by system buses; Control Unit fetches and decodes instructions and emits control signals; ALU performs arithmetic and bitwise logical operations; system clock produces timing signals on the control bus; Immediate Access Store holds data/programs the CPU needs; registers include PC, MAR, MDR, CIR, ACC and SR | Label a Von Neumann diagram; explain why a system clock is needed; match each register to its role | `Outline only` |
| H5 | **Registers and status flags** — PC, MAR, MDR, CIR, ACC, SR; carry, overflow, zero, negative flags | PC stores the address of the next instruction; MAR stores the RAM address being read/written; MDR holds data retrieved from or waiting to be written to RAM; CIR holds the current instruction being decoded; ACC holds ALU results; SR records flags such as carry, overflow, zero and negative | “Which register holds the address of the next instruction?”; “Which register holds the current instruction?”; interpret simple flag outcomes | `Outline only` |
| H6 | **Fetch–Decode–Execute cycle** — fetch, decode, execute, writeback; interrupt service routine | Fetch: MAR ← PC; MDR ← RAM[MAR]; IR ← MDR; PC ← PC + 1. Decode: CU decodes opcode in IR and generates control signals. Execute: ALU computes operands and updates status flags. Writeback: result saved to register or RAM. Interrupts: signal from device/software; priority is set; ISR services highest-priority interrupt; interrupted task continues afterwards | Trace a simple ADD instruction through the FDE cycle; explain what happens when a keyboard interrupt occurs | `Outline only` |
| H7 | **Memory hierarchy** — registers, cache, system memory, secondary storage; speed, capacity, cost trade-offs | Tier 1 CPU registers use flip-flops, capacity ~1–2 KB, latency <0.5 ns; Tier 2 L1/L2/L3 cache uses SRAM, 32 KB–128 MB, 1–15 ns; Tier 3 system memory uses DRAM, 8–128 GB, 50–100 ns; Tier 4 secondary storage uses NVMe flash SSD, 512 GB–4 TB, ~50,000 ns | Order the tiers by speed and capacity; explain why cache is small but fast; explain why secondary storage is large but slow | `Outline only` — **AMAT formula and AMAT calculations intentionally excluded** |
| H8 | **Processor specialization: CPU vs GPU vs TPU** — latency vs throughput; SIMT; ASIC; systolic array concept | CPU: low latency, complex branch prediction, deep out-of-order execution, large cache banks; GPU: high throughput, thousands of smaller arithmetic units, SIMT processing; TPU: ASIC for machine-learning matrix multiplication, using a systolic array of processing elements | Compare CPU/GPU/TPU in a table; explain why GPUs suit graphics and AI workloads; explain TPU as a specialised AI chip | `Outline only` — keep systolic-array maths brief or optional |
| H9 | **Input/Output systems** — input devices, processing unit, memory, output devices, I/O controllers | I/O systems allow users and external devices to communicate with the computer; input devices send data/instructions; output devices present results; CPU processes; RAM stores working data; I/O controllers manage communication with peripherals | Walk through “closing a browser tab with a mouse”: input → communication via driver/I/O → CPU processing → monitor output | `Outline only` |
| H10 | **Embedded systems** — microcontroller/processor, memory, sensors, actuators, I/O interfaces | Embedded systems perform a specific function inside a larger device; usually limited task set; examples include washing machine receiving programme, monitoring water level/temperature and controlling motor | Identify sensors and actuators in a washing machine; classify devices as general-purpose or embedded | `Outline only` |
| H11 | **CPU core types** — P-cores vs E-cores; single-core vs multi-core | Performance cores handle demanding tasks such as gaming and complex calculations; efficiency cores deliver good performance with less power for background/lighter workloads; single-core has one processing core; multi-core has two or more; more cores can improve multitasking but performance also depends on clock speed, architecture and software | Scenario: game + music + background apps — how might an OS schedule work across P-cores and E-cores? | `Outline only` |
| H12 | **Number systems** — denary, binary, hexadecimal; conversion; why hexadecimal is useful | Denary base 10 uses 0–9; binary base 2 uses 0–1; hexadecimal base 16 uses 0–9 and A–F; A=10, B=11, C=12, D=13, E=14, F=15; binary to denary, denary to binary, binary to hexadecimal by grouping into four bits; hexadecimal is compact and used for memory addresses, machine code and colour values; each hex digit represents four binary bits | Convert `1101₂` to denary; convert `13₁₀` to binary; convert `11010110₂` to hexadecimal (`D6₁₆`); explain why hex is shorter than binary | `Outline only` |
| H13 | **RAM: DRAM vs SRAM** — volatility; refresh; density; speed; cost; common use | DRAM stores each bit using a transistor and capacitor; capacitor loses charge, so data must be refreshed; higher density, cheaper per bit, used as main memory. SRAM uses multiple transistors per bit; no periodic refresh while powered; very fast, lower density, more expensive, used for CPU cache. Both DRAM and SRAM are volatile | Compare DRAM and SRAM in a table; explain why SRAM is used for cache and DRAM for main memory | `Outline only` |
| H14 | **ROM types: PROM, EPROM, EEPROM; flash memory** — non-volatility; programming/erasing | ROM is non-volatile and retains contents when power is off; PROM can normally be programmed once; EPROM can be erased with UV light and reprogrammed; EEPROM can be erased/reprogrammed electrically, often without removing the chip; flash memory is related and erases/writes in blocks; used in SSDs, USB drives and memory cards | Match PROM/EPROM/EEPROM to erasing method; explain why ROM is useful for firmware | `Outline only` — correct PDF table typo “Electrically Programmable ROM” to “Electrically Erasable Programmable ROM” |
| H15 | **Display connections: HDMI vs VGA** — signal type; video/audio; connector; common use | HDMI carries digital video and audio through one cable; used with modern monitors, TVs, projectors and gaming devices. VGA carries analogue video only; no audio; older interface; image quality can be affected by signal quality and cable length | Compare HDMI and VGA; choose a cable for a modern monitor vs an older projector | `Outline only` |

---

## 4. Suggested hardware review questions

1. What is the difference between hardware and software?
2. Name three main hardware components and state one function of each.
3. Why is RAM described as volatile?
4. What is the role of the Control Unit?
5. What is the difference between the MAR and the MDR?
6. Which register stores the address of the next instruction?
7. Describe the fetch–decode–execute cycle in three steps.
8. What is an interrupt, and what is an interrupt service routine?
9. Why is cache faster but smaller than main memory?
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

---

## 5. Known gaps and corrections

1. **AMAT calculation is excluded** by request. The memory hierarchy is covered conceptually only.
2. **ROM description in the PDF must be corrected.** ROM is not “high-speed working memory”; it is non-volatile memory for firmware/persistent instructions.
3. **PDF ROM comparison table has a typo:** “Electrically Programmable ROM” should be “Electrically Erasable Programmable ROM”.
4. **Depth of register detail needs confirmation.** Decide whether learners must memorise PC, MAR, MDR, CIR, ACC and SR or only understand the FDE cycle conceptually.
5. **Depth of logic gates needs confirmation.** Decide whether all six gates and truth tables are core, or whether AND/OR/NOT/XOR are sufficient.
6. **TPU systolic-array formula** should remain optional enrichment unless the teacher requires it.
7. **Images and diagrams** should be stored locally in an `assets/` folder before PDF export.
8. **Networks and Behaviourist AI** are excluded from this document.
