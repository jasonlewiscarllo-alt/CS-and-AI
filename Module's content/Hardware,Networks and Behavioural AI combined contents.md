# Hardware, Networks & Behavioural AI — Combined Study Guide

**Three beginner-friendly modules in one volume.** Version 3.0.

> **About this file**
>
> This file joins the three module sources in `modules/` into one document so it can be read straight through. It is generated from those files, so edit the module files, not this one. Figure and section numbers restart at the start of each module.

## Contents of this volume

- **Module 1 — Computer Hardware & Microarchitecture** (source: `modules/hardware/hardware.md`)
- **Module 2 — Networks** (source: `modules/networks/networks.md`)
- **Stage 8 — Behavioural AI (Reinforcement Learning)** (source: `modules/behavioural-ai/behavioural-ai.md`)

Each module begins with its own cover, contents list, learning outcomes and study plan, and ends with its mind map, case studies, end-of-module test with mark scheme, learning material list, glossary and references.

---

<!-- ===================== Module 1 — Computer Hardware & Microarchitecture ===================== -->

MODULE 1

# Computer Hardware &amp; Microarchitecture

A beginner-first textbook chapter — Version 3.0 (revised)

Aligned with Cambridge IGCSE Computer Science 0478 / O Level 2210 and AS &amp; A Level 9618 Integrated with D. Watson &amp; H. Williams, *Cambridge IGCSE and O Level Computer Science* and *Cambridge International AS &amp; A Level*

*Computer Science* Part of: Hardware, Networks and Behaviourist AI

# Contents

- Module overview and learning outcomes
- How to study this module
- 1.1 Physical parts of a computer
- 1.2 Number systems and data units
- 1.3 Binary logic
- 1.4 System architecture and the Von Neumann engine
- 1.5 The fetch–decode–execute cycle, interrupts and pipelining
- 1.6 Memory hierarchy and cache
- 1.7 RAM, ROM and storage technologies
- 1.8 Buffers and virtual memory
- 1.9 Input and output devices
- 1.10 Network hardware and cloud storage
- 1.11 Embedded systems, monitoring and control
- 1.12 Processor specialisation and CPU core types
- 1.13 Module summary and mind map
- 1.14 Case studies
- 1.15 Exam-style mixed practice with answers
- 1.16 End-of-module test with answers
- 1.17 Learning material list
- 1.18 Glossary
- 1.19 References and attribution

# What's New in This Edition — Module 1: Computer Hardware

This edition fills the gaps found when the module was checked against the Cambridge IGCSE 0478 and AS &amp; A Level 9618 syllabuses it is aligned with. Sections marked A Level go beyond IGCSE.

| New section | Where it is | What it adds |
|---|---|---|
| 1.3.4–1.3.8 Truth tables | After Section 1.3 | NOT gate table, three-input truth tables, circuit → table, problem statement → expression, the full adder |
| 1.3.9–1.3.11 Boolean algebra, Karnaugh maps, flip-flops (A Level) | After Section 1.3 | Laws incl. De Morgan, simplification, K-maps, SR and JK flip-flop truth tables |
| 1.5.5–1.5.11 Assembly language | After Section 1.5 | The full Cambridge instruction set incl. ADD, LDD, LDR, LDM, LDI, LDX, STO, CMP, JPE/JPN; trace tables; bit manipulation; two-pass assembler |
| 1.9.5 Sensors in detail | After Section 1.9 | Fourteen sensor types; the LDR (light-dependent resistor); automatic street light |
| 1.12.3–1.12.4 RISC/CISC and parallel processing (A Level) | After Section 1.12 | RISC vs CISC; Flynn's SISD/SIMD/MISD/MIMD; massively parallel computers |
| Glossary supplement | After Section 1.18 | New key terms |

> **How to find the new material**
>
> New sections keep the module's numbering and are inserted straight after the section they extend, so cross- references in the original text still work. Every new heading carries a green `NEW` label, and new figures are numbered with a letter (for example Figure 8A follows Figure 8). New key terms are collected in a glossary supplement placed straight after the module glossary.

# Module overview and learning outcomes

This module introduces the physical components of a computer and the microarchitectural principles that let those components execute instructions. It starts with the parts you can touch, establishes the binary number system (the language all hardware speaks), and builds upward through logic gates, the Von Neumann model, the fetch–decode– execute cycle, the memory hierarchy, input/output devices, networks, embedded systems, monitoring and control, and processor specialisation.

**Prerequisite knowledge:** none beyond everyday familiarity with a computer. Binary is taught in Section 1.2 before any section that uses it, and every new term is defined before it is used.

> **By the end of this module you should be able to:**
>
> 1. Identify the major internal components of a computer and state the role of each.
>
> 2. Convert between binary, denary and hexadecimal, and explain why hexadecimal is used.
>
> 3. State and use the units of data: bit, nibble, byte, KB, MB, GB, TB.
>
> 4. Explain how transistors form logic gates and how gates form combinational and sequential circuits.
>
> 5. Identify the registers and buses of the Von Neumann architecture and explain the role of each.
>
> 6. Trace the fetch–decode–execute (FDE) cycle stage by stage, naming the registers and buses active at each
>
> step.
>
> 7. Explain how interrupts and the interrupt service routine (ISR) work, and how pipelining speeds up instruction throughput.
>
> 8. Explain why the memory hierarchy exists and compare DRAM and SRAM.
>
> 9. Distinguish PROM, EPROM and EEPROM, and state appropriate uses for each.
>
> 10. Explain what buffers and virtual memory are, and why they exist.
>
> 11. Describe the principles of operation of common input and output devices, including sensors and actuators, and compare HDMI and VGA.
>
> 12. Compare local storage with cloud storage, and describe the network hardware that makes cloud storage possible.
>
> 13. Describe embedded systems, real-time constraints, and monitoring/control systems.
>
> 14. Compare CPU, GPU and TPU architectures in terms of latency and throughput.

## How to study this module

Every section follows the same rhythm, so you always know what to do next:

1. **Read the objectives** (blue box) so you know the target.

2. **Read the explanation** and study each figure. Redraw the figure from memory when you finish the section.

3. **Follow the worked example** (purple box) line by line with a pencil.

4. **Do the activity** (orange box) *before* reading the checked answer (green box).

5. **Answer the exam-style question** (red box) in full sentences, then compare with the mark scheme.

> **Suggested study plan (about 6 weeks, 3 sessions per week)**
>
> | Week | Sections | Focus | Self-check |
> |---|---|---|---|
> | 1 | 1.1, 1.2 | Components; binary, denary, hex conversions | Convert 10 numbers each way without a calculator |
> | 2 | 1.3, 1.4 | Logic gates, truth tables; registers and buses | Draw the Von Neumann diagram from memory |
> | 3 | 1.5, 1.6 | FDE trace, interrupts, pipelining; memory hierarchy | Trace an ADD instruction register by register |
> | 4 | 1.7, 1.8, 1.9 | RAM/ROM types; buffers, virtual memory; I/O devices | Make a one-page comparison table for DRAM/SRAM/ROM types |
> | 5 | 1.10, 1.11, 1.12 | Networks, cloud, embedded systems, CPU/GPU/TPU | Explain a washing machine as a control system |
> | 6 | 1.13 – 1.16 | Mind map, case studies, mixed practice, test | Sit the end-of-module test under timed conditions |
>
> **Learning suggestions:** (1) Use *retrieval practice*: close the book and write down everything you remember, then check. (2) Use *spaced repetition*: re-do the activities after 1 day, 1 week and 1 month. (3) Explain each concept aloud to someone else — if you cannot, you have found a gap. (4) Always show working in conversions; marks are usually awarded for method. (5) Pair each new term with a one-line everyday analogy (for example: a register is a sticky note on your desk, RAM is the desk, storage is the filing cabinet).

# Section 1.1 — Physical Parts of a Computer

> **Learning objectives**
>
> By the end of this section you should be able to name the main physical components inside a computer, state the purpose of each, and explain the difference between hardware, firmware, software and data.

## 1.1.1 What hardware actually means

**Hardware** is the set of physical parts of a computer that you can see, touch and (usually) move. It is contrasted with **software**, the instructions and data the hardware carries out and stores. Software has no physical form of its own; it exists as patterns stored in hardware.

| Term | Meaning | Example |
|---|---|---|
| Hardware | The physical parts | The CPU chip |
| Software | Programs and data stored as patterns in hardware | A web browser |
| Firmware | Software permanently stored in hardware, usually in ROM, and rarely changed | The BIOS/UEFI that starts a computer |
| Data | Raw facts that programs process | The numbers in a spreadsheet |

A computer works only when all four cooperate. The hardware provides the physical capability, the firmware starts the machine, the software tells the hardware what to do, and the data is what gets processed.

## 1.1.2 The motherboard

The **motherboard** is the large circuit board that everything else plugs into. Its purpose is not to *do* computing itself but to *connect* the parts that do, and to supply them with power and communication pathways. It holds the CPU socket, the RAM slots, expansion slots for add-on cards, the **chipset** (support chips managing communication), storage connectors, input/output connectors, and the firmware chip holding the BIOS/UEFI.

Connections between components are made by **traces**: thin copper pathways printed into the board. Traces carry both electrical power and electrical signals. When a diagram shows a line between the CPU and RAM, that line represents a set of traces forming a **bus**, explained in Section 1.4.

> **Why this matters**
>
> A fast CPU connected by a slow or narrow pathway cannot perform at its full speed. The motherboard and its traces are part of the performance story.

![Figure 1 — Motherboard block diagram. Traces carry both electricity and signals between components.](modules/hardware/figures/fig001-motherboard-block-diagram-traces-carry-both-elec.png)

*Figure 1 — Motherboard block diagram. Traces carry both electricity and signals between components.*

## 1.1.3 The CPU

The **Central Processing Unit (CPU)** fetches instructions, decodes them and executes them. Inside are the Control Unit (CU), the Arithmetic Logic Unit (ALU), registers, and cache memory.

## 1.1.4 RAM: the workspace

**Random Access Memory (RAM)** is the short-term workspace. Programs and data currently in use are loaded into RAM for fast access. RAM is **volatile**: its contents are lost when power is removed.

> **Why RAM exists**
>
> SSDs and hard drives are much slower than the CPU. Without RAM, the CPU would spend most of its time waiting. RAM is the intermediate workspace fast enough to keep the CPU busy. Section 1.6 explains this speed
>
> gap.

## 1.1.5 ROM: permanent start-up instructions

**Read-Only Memory (ROM)** is **non-volatile**: it keeps its contents when power is switched off. ROM stores firmware, such as the BIOS/UEFI that starts the computer and checks the hardware before loading the operating system.

## 1.1.6 Secondary storage

- **HDD (hard disk drive)**: magnetic spinning platters; large capacity, relatively cheap, slower, sensitive to movement.

- **SSD (solid-state drive)**: flash memory chips, no moving parts; faster, quieter, more shock-resistant, more expensive per gigabyte.

- **USB flash drives and memory cards**: portable flash storage.

## 1.1.7 GPU and TPU

A **GPU (Graphics Processing Unit)** contains hundreds or thousands of small arithmetic units that operate concurrently, making it effective for graphics rendering and parallel numerical work. A **TPU (Tensor Processing Unit)** is an ASIC (application-specific integrated circuit) designed to accelerate machine-learning matrix operations. Its core is a **systolic** **array**: a grid of processing elements through which data flows in a regular rhythm.

## 1.1.8 The system clock

The **system clock** produces timing signals measured in hertz (Hz); 1 GHz is one billion ticks per second. Clock speed is one of three IGCSE performance factors, alongside cache size and number of cores.

## 1.1.9 Other common components

- **PSU**: converts mains electricity into DC voltages.

- **Cooling system**: fans, heat sinks or liquid cooling remove heat.

- **Expansion cards**: add graphics, Wi-Fi, sound, etc.

- **Case**: protects components and supports airflow.

> **Activity 1.1 — Identify the component**
>
> | Job | Component |
> |---|---|
> | Holds the program currently running | ? |
> | Starts the computer before the OS loads | ? |
> | Performs arithmetic | ? |
> | Connects all components | ? |
> | Keeps files when power is off | ? |

> **Checked answers**
>
> | Job | Component |
> |---|---|
> | Holds the program currently running | RAM |
> | Starts the computer before the OS loads | ROM / firmware |
> | Performs arithmetic | ALU |
> | Connects all components | Motherboard |
> | Keeps files when power is off | Secondary storage |

> **Exam-style practice**
>
> **Question (2 marks).** Explain why RAM is described as volatile.
>
> **Checked answer.** RAM loses its contents when power is removed **(1)**, because it relies on electrical charge that is not maintained without power **(1)**.

## 1.1.10 Motherboard form factors

A **form factor** is a standard that defines a motherboard's physical dimensions, mounting-hole positions, and the layout

of expansion slots and connectors. Form factors exist so that cases, power supplies and add-on cards from different manufacturers fit together. Without a recognised form factor, every case and PSU would have to be custom-made.

| Form factor | Typical size | Expansion slots | Typical use |
|---|---|---|---|
| EATX (Extended ATX) | ~305 x 330 mm | Up to 7 | Workstations, servers, multi-GPU builds |
| ATX (standard) | ~305 x 244 mm | Up to 7 | Desktop PCs, gaming builds |

| Form factor | Typical size | Expansion slots | Typical use |
|---|---|---|---|
| Micro-ATX (mATX) | ~244 x 244 mm | Up to 4 | Smaller desktops, budget builds |
| Mini-ITX | ~170 x 170 mm | 1–2 | Small-form-factor PCs, home theatre, embedded |

![Figure 2 — Relative sizes of the four main motherboard form factors.](modules/hardware/figures/fig002-relative-sizes-of-the-four-main-motherboard-form.png)

*Figure 2 — Relative sizes of the four main motherboard form factors.*

> **Worked example — choosing a form factor**
>
> A user needs a gaming PC with two graphics cards, four RAM modules and a large air cooler. EATX or full ATX is best: more expansion slots, more RAM slots, and enough clearance for cooling. A user building a small home-
>
> theatre PC should choose Mini-ITX: it fits a compact case but limits slots and cooling options.

> **Activity 1.1.10 — Match the form factor**
>
> | Scenario | Best form factor | Reason |
> |---|---|---|
> | Dual-GPU scientific workstation | ? | ? |
> | Standard office desktop | ? | ? |
> | Small home-theatre PC | ? | ? |
> | Budget family PC | ? | ? |

> **Checked answers**
>
> | Scenario | Best form factor | Reason |
> |---|---|---|
> | Dual-GPU scientific workstation | EATX or ATX | Most expansion slots; room for cooling and power delivery |
> | Standard office desktop | ATX | Standard, widely available, enough slots |
> | Small home-theatre PC | Mini-ITX | Smallest footprint, fits compact cases |
> | Budget family PC | Micro-ATX | Cheaper, smaller, enough slots for basic use |

> **Exam-style practice**
>
> **Question (2 marks).** Explain why motherboard form factors are standardised.
>
> **Checked answer.** Standardisation ensures cases, power supplies and expansion cards fit together across manufacturers **(1)**, reducing cost and allowing upgrades **(1)**.

## 1.1.11 Power supply unit: internal mechanics

The **power supply unit (PSU)** converts the high-voltage alternating current (AC) from a wall socket into the low-voltage direct current (DC) that the computer's components need. The conversion happens in four stages.

![Figure 3 — The four stages of AC-to-DC conversion inside a PSU.](modules/hardware/figures/fig003-the-four-stages-of-ac-to-dc-conversion-inside-a.png)

*Figure 3 — The four stages of AC-to-DC conversion inside a PSU.*

> **Worked example — why smoothing matters**
>
> After rectification the DC output still pulses: the diodes only allow current one way, but the voltage drops to zero between peaks. A smoothing capacitor charges during the peaks and discharges between them, filling the gaps. Without smoothing, sensitive components would receive a rippled supply and could malfunction.

> **Activity 1.1.11 — Order the stages**
>
> | Stage | Position (1–4) | What it does |
> |---|---|---|
> | Voltage regulator | ? | ? |
> | Transformer | ? | ? |
> | Smoothing capacitor | ? | ? |
> | Rectifier | ? | ? |

> **Checked answers**
>
> | Stage | Position | What it does |
> |---|---|---|
> | Transformer | 1 | Steps AC voltage down |
> | Rectifier | 2 | Converts AC to pulsating DC |
> | Smoothing capacitor | 3 | Removes ripple |
> | Voltage regulator | 4 | Holds stable DC output |

> **Exam-style practice**
>
> **Question (3 marks).** Describe how a PSU converts AC to DC.
>
> **Checked answer.** Transformer steps voltage down **(1)**; rectifier converts AC to DC using diodes **(1)**; smoothing capacitors remove ripple and a regulator holds a steady output **(1)**.

## 1.1.12 PSU internal components

Opening a PSU (only safely, with the unit unplugged and discharged) reveals a circuit board with several distinct components. Each plays a role in conversion, filtering or protection.

| Component | Function |
|---|---|
| Transformer | Steps the AC voltage down using magnetic induction between coils. |
| Rectifier diodes | Allow current to flow in one direction only, converting AC to pulsating DC. |
| Capacitors | Store charge and smooth out voltage ripple; also filter noise. |
| Resistors | Limit current and divide voltage; used in sensing circuits. |
| Rotary switch | On some older PSUs, selects the input voltage (110 V or 230 V). |
| Heatsinks | Dissipate heat from power transistors and diodes. |
| Fan | Moves air through the unit to keep components within safe temperatures. |
| Protection circuits | Shut down the PSU on over-voltage, over-current or short-circuit. |

> **Activity 1.1.12 — Match the component to its role**
>
> Match each component to its role: transformer, rectifier diodes, capacitors, resistors, rotary switch. Roles: (a) selects input voltage, (b) limits current, (c) smooths ripple, (d) converts AC to pulsating DC, (e) steps voltage down.

> **Checked answers**
>
> Transformer → (e). Rectifier diodes → (d). Capacitors → (c). Resistors → (b). Rotary switch → (a).

> **Exam-style practice**
>
> **Question (2 marks).** State the function of the rectifier diodes in a PSU.
>
> **Checked answer.** They allow current to flow in one direction only **(1)**, converting AC into pulsating DC **(1)**.

## 1.1.13 Graphics card (GPU) components

A graphics card is an expansion card that contains a GPU and its supporting components. It handles graphics rendering and highly parallel numerical work. A modern graphics card has seven main parts.

| Part | Function |
|---|---|
| 1. GPU chip | The processor itself; contains thousands of shader cores that execute rendering and parallel computation. |
| 2. VRAM | Dedicated video memory that stores textures, framebuffers and working data for the GPU. |

| Part | Function |
|---|---|
| 3. PCIe interface | The edge connector that plugs into the motherboard and carries data between CPU and GPU. |
| 4. Heatsink + fan | Removes heat generated by the GPU chip and VRAM. |
| 5. 6/8-pin auxiliary power connectors | Supply extra power beyond what the PCIe slot provides; needed for high-end GPUs. |
| 6. Monitor outputs | HDMI, DisplayPort, DVI and other connectors that send video to displays. |
| 7. Video BIOS | Firmware that initialises the card at start-up and controls clock speeds and voltages. |

![Figure 4 — The seven main parts of a graphics card.](modules/hardware/figures/fig004-the-seven-main-parts-of-a-graphics-card.png)

*Figure 4 — The seven main parts of a graphics card.*

> **Worked example — why auxiliary power matters**
>
> A high-end GPU can draw 250 W or more, but the PCIe slot provides only 75 W. Without the 6-pin and 8-pin auxiliary connectors, the card would not receive enough power and would throttle or fail to start. The PSU's PCIe power cables plug into these connectors.

> **Activity 1.1.13 — Match the GPU part**
>
> | Function | Part |
> |---|---|
> | Stores textures and framebuffers | ? |
> | Connects the card to the motherboard | ? |
> | Supplies extra power beyond the slot | ? |
> | Initialises the card at start-up | ? |
> | Removes heat from the GPU | ? |

> **Checked answers**
>
> VRAM; PCIe interface; 6/8-pin connectors; Video BIOS; heatsink + fan.

> **Exam-style practice**
>
> **Question (2 marks).** Explain why high-end GPUs need auxiliary power connectors.
>
> **Checked answer.** They draw more power than the PCIe slot can supply **(1)**; the 6- or 8-pin connectors deliver the extra current from the PSU **(1)**.

# Section 1.2 — Number Systems and Data Units

> **Learning objectives**
>
> Explain what a bit is, convert between binary and denary, convert between binary and hexadecimal, and use the units bit, nibble, byte, KB, MB, GB and TB.

## 1.2.1 What is a bit?

A **bit** is a single binary digit: 0 or 1. In hardware these are two voltage levels. A bit is an abstraction for a two-state circuit; using only two widely separated voltage levels makes circuits reliable against noise, heat and manufacturing variation. **Binary** is the base-2 number system using only 0 and 1. **Denary** is the everyday base-10 system.

## 1.2.2 Units of data

| Unit | Size | Example use |
|---|---|---|
| bit | 1 binary digit | one flag |
| nibble | 4 bits | one hex digit |
| byte | 8 bits | one ASCII character |
| KB (kilobyte) | 1024 bytes | short text file |
| MB | 1024 KB | photo |
| GB | 1024 MB | video / RAM |
| TB | 1024 GB | SSD / HDD |

> **Convention note**
>
> In this module 1 KB = 1024 bytes because 1024 = 2<sup>10</sup>. This is the convention used in Cambridge papers. Storage manufacturers sometimes use 1000 bytes per KB. The IEC names the power-of-two units kibibyte (KiB), mebibyte
>
> (MiB) and so on. Use 1024 in exams unless told otherwise.

## 1.2.3 Binary place values

Each bit position has a value that is double the one to its right. To convert binary to denary, add the place values wherever there is a 1.

![Figure 5 — Binary place-value chart: 10110101 = 181.](modules/hardware/figures/fig005-binary-place-value-chart-10110101-181.png)

*Figure 5 — Binary place-value chart: 10110101 = 181.*

> **Worked example — 1011 to denary**
>
> 1011<sub>2</sub> = 1×2<sup>3</sup> + 0×2<sup>2</sup> + 1×2<sup>1</sup> + 1×2<sup>0</sup> = 8 + 0 + 2 + 1 = 11<sub>10</sub>

> **Worked example — 45 to binary**
>
> Find the largest place value that fits and subtract: 45 = 32 + 8 + 4 + 1, so put a 1 in the 32, 8, 4 and 1 columns: 45<sub>10</sub> = 00101101<sub>2</sub> (8 bits), or 101101<sub>2</sub> without leading zeros.

## 1.2.4 Hexadecimal

**Hexadecimal** uses 0–9 and A–F (base 16), where A = 10, B = 11, C = 12, D = 13, E = 14, F = 15. Each hex digit represents exactly four bits (one nibble), so hex is a compact, less error-prone way to write binary. It is used for memory addresses, machine code and colour codes.

> **Worked example — B7 to denary**
>
> B7<sub>16</sub> = 11 × 16 + 7 = 176 + 7 = 183<sub>10</sub>

![Figure 6 — Binary to hex grouping: 1101 0110 = D6.](modules/hardware/figures/fig006-binary-to-hex-grouping-1101-0110-d6.png)

*Figure 6 — Binary to hex grouping: 1101 0110 = D6.*

## 1.2.5 Conversion practice

| Task | Answer |
|---|---|
| 10110<sub>2</sub> to denary | 16 + 4 + 2 = 22<sub>10</sub> |
| 45<sub>10</sub> to binary | 101101<sub>2</sub> |
| 11101101<sub>2</sub> to hex | 1110 = E, 1101 = D, so ED<sub>16</sub> |
| B7<sub>16</sub> to denary | 183<sub>10</sub> |
| 2C<sub>16</sub> to binary | 0010 1100 = 00101100<sub>2</sub> |
| 3 bytes = ? bits / nibbles | 24 bits, 6 nibbles |

> **Activity 1.2 — Try it yourself**
>
> Convert: (a) 11001<sub>2</sub> to denary; (b) 100<sub>10</sub> to binary; (c) 3F<sub>16</sub> to denary; (d) 10101111<sub>2</sub> to hex.

> **Checked answers**
>
> (a) 16 + 8 + 1 = 25. (b) 64 + 32 + 4 = 01100100<sub>2</sub>. (c) 3 × 16 + 15 = 63. (d) 1010 = A, 1111 = F, so AF<sub>16</sub>.

> **Exam-style practice**
>
> **Question (2 marks).** Explain why hexadecimal is used for memory addresses.
>
> **Checked answer.** Each hex digit represents four binary bits **(1)**, so long binary addresses become short and less error-prone **(1)**.

# Section 1.3 — Binary Logic

> **Learning objectives**
>
> Explain how transistors form logic gates, state the function of standard gates, complete truth tables, distinguish combinational from sequential circuits, and explain the half-adder.

## 1.3.1 From transistors to gates

A **transistor** is a tiny electronic switch. Combining transistors forms **logic gates**: circuits whose output depends on the inputs according to a fixed rule. A **truth table** lists every input combination and the corresponding output.

![Figure 7 — Standard logic gate symbols.](modules/hardware/figures/fig007-standard-logic-gate-symbols.png)

*Figure 7 — Standard logic gate symbols.*

| A | B | AND | OR | XOR | NAND | NOR | XNOR |
|---|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 1 | 1 | 1 | 0 | 0 |
| 1 | 0 | 0 | 1 | 1 | 1 | 0 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 | 0 | 1 |

**Memory aids:** AND outputs 1 only if *both* inputs are 1. OR outputs 1 if *at least one* input is 1. XOR outputs 1 if the inputs are *different*. NOT inverts a single input. NAND, NOR and XNOR are AND, OR and XOR followed by NOT.

## 1.3.2 Combinational and sequential circuits

**Combinational circuits** depend only on the current inputs (adders, multiplexers, decoders). **Sequential circuits** depend on the current inputs *and* stored state, updated on clock ticks (flip-flops, latches). Flip-flops are the physical basis of registers and memory cells.

## 1.3.3 The half-adder

A half-adder adds two single bits, producing a **Sum** and a **Carry**.

![Figure 8 — Half-adder: XOR gives the Sum, AND gives the Carry.](modules/hardware/figures/fig008-half-adder-xor-gives-the-sum-and-gives-the-carry.png)

*Figure 8 — Half-adder: XOR gives the Sum, AND gives the Carry.*

| A | B | Sum (XOR) | Carry (AND) |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

This matches binary addition: 1 + 1 = 10<sub>2</sub> (sum 0, carry 1). A **full adder** adds three bits (A, B and a carry-in) and

chaining full adders forms the adder inside the ALU.

> **Activity 1.3 — Build a half-adder**
>
> Using AND and XOR gates, draw a half-adder and complete the outputs for A = 1, B = 1. Then complete the truth table for the expression NOT (A AND B).

> **Checked answer**
>
> Sum = 1 XOR 1 = 0; Carry = 1 AND 1 = 1. NOT (A AND B) is NAND: 1, 1, 1, 0 for AB = 00, 01, 10, 11.

> **Exam-style practice**
>
> **Question (3 marks).** Complete the truth table output for XOR when A = 0, B = 1; A = 1, B = 1; and state what the XOR output means.
>
> **Checked answer.** 0 XOR 1 = 1 **(1)**; 1 XOR 1 = 0 **(1)**; output is 1 only when the inputs differ **(1)**.

# Section 1.3 (continued) — Truth Tables, Boolean Algebra and Flip-Flops

> **Learning objectives (new in this edition)**
>
> Complete truth tables for NOT and for any logic expression or circuit with up to three inputs; write a logic expression from a problem statement; explain the full adder; simplify expressions with Boolean algebra and Karnaugh maps; and complete truth tables for SR and JK flip-flops.

## 1.3.4 The NOT gate and reading a truth table `NEW`

The two-input table in Section 1.3.1 has no column for **NOT**, because NOT has only one input. Its truth table has just two rows: the output is always the opposite of the input. A NOT gate is also called an **inverter**.

| A | NOT A |
|---|---|
| 0 | **1** |
| 1 | **0** |

| Gate | Cambridge written form | Boolean form |
|---|---|---|
| NOT | NOT A | A̅ |
| AND | A AND B | A.B |
| OR | A OR B | A + B |
| XOR | A XOR B | A ⊕ B |
| NAND | NOT (A AND B) | A̅.̅B̅ |
| NOR | NOT (A OR B) | A̅ +̅ B̅ |

**How many rows?** A truth table with *n* inputs needs 2<sup>n</sup> rows: 2 rows for one input, 4 for two inputs, 8 for three inputs. Always list the inputs in binary counting order (000, 001, 010 … 111) so that you never miss or repeat a row. In Cambridge papers the input columns are usually labelled A, B, C and the output X, Q or P.

## 1.3.5 Truth tables for three-input expressions `NEW`

For a longer expression, add a **working column** for each part, then combine the working columns. Working columns are not required in the exam, but they prevent most mistakes.

> **Worked example — X = (A AND B) OR (NOT C)**
>
> Step 1: write the 8 input rows. Step 2: work out A AND B. Step 3: work out NOT C. Step 4: X is 1 if either working column is 1.
>
> | A | B | C | A AND B | NOT C | X |
> |---|---|---|---|---|---|
> | 0 | 0 | 0 | 0 | 1 | **1** |
> | 0 | 0 | 1 | 0 | 0 | **0** |
> | 0 | 1 | 0 | 0 | 1 | **1** |
> | 0 | 1 | 1 | 0 | 0 | **0** |
> | 1 | 0 | 0 | 0 | 1 | **1** |
> | 1 | 0 | 1 | 0 | 0 | **0** |
> | 1 | 1 | 0 | 1 | 1 | **1** |
> | 1 | 1 | 1 | 1 | 0 | **1** |

## 1.3.6 From a logic circuit to a truth table `NEW`

To work out what a circuit does, label the output of every gate with a letter, then fill in one working column per gate from left to right. The circuit below is P = (A OR B) AND NOT (B AND C).

![Figure 8A — D = A OR B, E = B AND C, F = NOT E, P = D AND F.](modules/hardware/figures/fig8a-d-a-or-b-e-b-and-c-f-not-e-p-d-and-f.png)

*Figure 8A — D = A OR B, E = B AND C, F = NOT E, P = D AND F.*

| A | B | C | D = A OR B | E = B AND C | F = NOT E | P = D AND F |
|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 0 | 1 | **0** |
| 0 | 0 | 1 | 0 | 0 | 1 | **0** |
| 0 | 1 | 0 | 1 | 0 | 1 | **1** |
| 0 | 1 | 1 | 1 | 1 | 0 | **0** |
| 1 | 0 | 0 | 1 | 0 | 1 | **1** |
| 1 | 0 | 1 | 1 | 0 | 1 | **1** |
| 1 | 1 | 0 | 1 | 0 | 1 | **1** |
| 1 | 1 | 1 | 1 | 1 | 0 | **0** |

**Check by meaning:** when B = 0, P = A; when B = 1, P = NOT C. Reading a circuit for its meaning like this is a quick way to check your table.

## 1.3.7 From a problem statement to an expression `NEW`

Exam questions often describe a system in words. Turn each condition into a letter (1 = true), then join the conditions with AND, OR and NOT exactly as the words do.

> **Worked example — a burglar alarm**
>
> An alarm X sounds if the system is armed (S = 1) *and* either the door is open (D = 1) *or* a window is open (W = 1). Expression: **X = S AND (D OR W)**.
>
> | S | D | W | D OR W | X |
> |---|---|---|---|---|
> | 0 | 0 | 0 | 0 | **0** |
> | 0 | 0 | 1 | 1 | **0** |
> | 0 | 1 | 0 | 1 | **0** |
> | 0 | 1 | 1 | 1 | **0** |
> | 1 | 0 | 0 | 0 | **0** |
> | 1 | 0 | 1 | 1 | **1** |
> | 1 | 1 | 0 | 1 | **1** |
> | 1 | 1 | 1 | 1 | **1** |

## 1.3.8 The full adder `NEW`

A half-adder (Section 1.3.3) cannot accept a carry from the column to its right. A **full adder** adds three bits: A, B and a carry-in (C<sub>in</sub>). It is built from two half-adders and an OR gate.

Sum = A ⊕ B ⊕ C<sub>in</sub>      C<sub>out</sub> = (A . B) + (C<sub>in</sub> . (A ⊕ B))

| A | B | Cin | A+B+Cin | Sum | Cout |
|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | **0** | **0** |
| 0 | 0 | 1 | 1 | **1** | **0** |
| 0 | 1 | 0 | 1 | **1** | **0** |
| 0 | 1 | 1 | 2 | **0** | **1** |
| 1 | 0 | 0 | 1 | **1** | **0** |
| 1 | 0 | 1 | 2 | **0** | **1** |
| 1 | 1 | 0 | 2 | **0** | **1** |
| 1 | 1 | 1 | 3 | **1** | **1** |

![Figure 8B — A full adder = two half-adders + OR.](modules/hardware/figures/fig8b-a-full-adder-two-half-adders-or.png)

*Figure 8B — A full adder = two half-adders + OR.*

The Sum column is 1 when an *odd* number of inputs are 1; C<sub>out</sub> is 1 when *two or more* are 1. Chaining eight full

adders, each passing its C<sub>out</sub> to the next C<sub>in</sub>, gives an 8-bit adder: this is how the ALU adds binary numbers.

## 1.3.9 Boolean algebra (A Level) `NEW`

Boolean algebra lets you simplify an expression so the circuit needs fewer gates. Fewer gates mean lower cost, less power and less heat. Here . means AND, + means OR, and a bar means NOT.

| Law | AND form | OR form |
|---|---|---|
| Identity | A . 1 = A | A + 0 = A |
| Null (annulment) | A . 0 = 0 | A + 1 = 1 |
| Idempotent | A . A = A | A + A = A |
| Inverse (complement) | A . A̅ = 0 | A + A̅ = 1 |
| Double complement | NOT (NOT A) = A | — |
| Commutative | A . B = B . A | A + B = B + A |
| Associative | (A . B) . C = A . (B . C) | (A + B) + C = A + (B + C) |
| Distributive | A . (B + C) = A.B + A.C | A + B.C = (A + B) . (A + C) |
| Absorption | A . (A + B) = A | A + A.B = A |
| De Morgan | A̅ .̅ B̅ = A̅ + B̅ | A̅ +̅ B̅ = A̅ . B̅ |

**De Morgan in words:** “break the bar, change the sign”. When you split a bar over a group, AND becomes OR (or OR becomes AND).

> **Worked example — simplify X = A.B + A.B̅**
>
> X = A.B + A.B̅ = A.(B + B̅) *(distributive)* = A.1 *(inverse)* = **A** *(identity)*. Two AND gates, a NOT gate and an OR gate reduce to a single wire.
>
> Second example: A̅ +̅ B̅ + A = A̅.B̅ + A *(De Morgan)* = (A + A̅).(A + B̅) *(distributive, OR form)* = 1.(A + B̅) = **A + B̅**.

## 1.3.10 Karnaugh maps (A Level) `NEW`

A **Karnaugh map (K-map)** is a truth table redrawn as a grid so that neighbouring cells differ by exactly one bit. You loop groups of 1s; each group becomes one simple AND term. The rules:

- Columns and rows use **Gray code** order: 00, 01, 11, 10 (not 00, 01, 10, 11).

- Groups must be rectangles containing 1, 2, 4 or 8 cells (powers of 2) and only 1s.

- Make groups as large as possible and use as few groups as possible; groups may overlap.

- The map wraps around: the left and right edges are neighbours.

- In each group, keep only the variables that do *not* change; write them ANDed together. OR the groups.

![Figure 8C — Two groups of two: P = A.B + B.C.](modules/hardware/figures/fig8c-two-groups-of-two-p-a-b-b-c.png)

*Figure 8C — Two groups of two: P = A.B̅ + B.C̅.*

> **Worked example — reading the map**
>
> **Green group** (row A = 1, columns 00 and 01): A stays 1, B stays 0, C changes → term A.B̅. **Orange group** (column 10, both rows): A changes, B stays 1, C stays 0 → term B.C̅. So **P = A.B̅ + B.C̅**, which matches the meaning found in Section 1.3.6 (B = 0 gives A; B = 1 gives NOT C).

## 1.3.11 Flip-flop truth tables (A Level) `NEW`

A **flip-flop** is a sequential circuit that stores one bit (Section 1.3.2). Its output Q depends on the inputs *and* on what Q was before, so its truth table includes the previous state. Q̅ is always the opposite of Q.

### SR flip-flop (made from two NOR gates)

| S | R | Q | Meaning |
|---|---|---|---|
| 0 | 0 | **Q (no change)** | **Hold / store** |
| 1 | 0 | **1** | **Set** |
| 0 | 1 | **0** | **Reset** |
| 1 | 1 | **—** | **Invalid: avoid** |

### JK flip-flop (clocked)

| J | K | Q after clock pulse | Meaning |
|---|---|---|---|
| 0 | 0 | **Q (no change)** | **Hold** |
| 1 | 0 | **1** | **Set** |
| 0 | 1 | **0** | **Reset** |
| 1 | 1 | **Q̅ (toggle)** | **Toggle** |

The JK flip-flop fixes the SR flip-flop's invalid state: with J = K = 1 the output toggles on each clock pulse instead of becoming unpredictable. Because it changes only on a clock pulse, every flip-flop in a register updates at the same moment. A register of eight flip-flops stores one byte.

> **Activity 1.3B — Truth tables**
>
> (a) Complete the truth table for X = NOT (A OR B) AND C. (b) A greenhouse fan F turns on if the temperature is high (T = 1) or the humidity is high (H = 1), but never when the door is open (D = 1). Write the expression for F. (c) Simplify Y = A.B + A̅.B using Boolean algebra.

> **Checked answers**
>
> | A | B | C | NOT (A OR B) | X |
> |---|---|---|---|---|
> | 0 | 0 | 0 | 1 | **0** |
> | 0 | 0 | 1 | 1 | **1** |
> | 0 | 1 | 0 | 0 | **0** |
> | 0 | 1 | 1 | 0 | **0** |
> | 1 | 0 | 0 | 0 | **0** |
> | 1 | 0 | 1 | 0 | **0** |
> | 1 | 1 | 0 | 0 | **0** |
> | 1 | 1 | 1 | 0 | **0** |
>
> (a) X = 1 only for A = 0, B = 0, C = 1. (b) F = (T OR H) AND NOT D. (c) Y = B.(A + A̅) = B.1 = **B**.

> **Exam-style practice**
>
> **Question (4 marks).** Draw the truth table for the full adder and explain why the ALU uses full adders rather than half-adders.
>
> **Checked answer.** Correct Sum column (0,1,1,0,1,0,0,1) **(1)**; correct C<sub>out</sub> column (0,0,0,1,0,1,1,1) **(1)**; a full adder
>
> accepts a carry-in from the previous column **(1)**, so adders can be chained to add multi-bit numbers **(1)**.
>
> **Question (3 marks).** Use a Karnaugh map to simplify X = A̅.B.C + A.B.C + A.B.C̅.
>
> **Checked answer.** 1s at 011, 111, 110 **(1)**; groups: column BC = 11 (both rows) gives B.C; row A = 1, columns 11 and 10 gives A.B **(1)**; X = B.C + A.B **(1)**.

# Section 1.4 — System Architecture and the Von Neumann Engine

> **Learning objectives**
>
> Explain the stored-program concept, identify the main parts of the Von Neumann architecture, explain each register, and explain the three system buses.

## 1.4.1 The stored-program concept

The **Von Neumann architecture** stores both instructions and data in the same memory. This is the **stored-program** **concept**, proposed in the 1940s. It made general-purpose computing possible: to change what a computer does you change the program in memory rather than rewire the machine.

> **The Von Neumann bottleneck**
>
> Because instructions and data share the same memory and buses, the CPU cannot fetch an instruction and a data value at exactly the same instant. Cache memory (Section 1.6) reduces its impact.

![Figure 9 — Von Neumann architecture. Main memory is the Immediate Access Store (IAS).](modules/hardware/figures/fig009-von-neumann-architecture-main-memory-is-the-imme.png)

*Figure 9 — Von Neumann architecture. Main memory is the Immediate Access Store (IAS).*

## 1.4.2 Core subcomponents

- **Control Unit (CU)**: fetches and decodes instructions and emits control signals that coordinate the other parts.

- **ALU**: performs arithmetic and bitwise logical operations.

- **Registers and cache**: very small, very fast storage inside the CPU.

- **Immediate Access Store (IAS)**: the Cambridge term for **main memory (RAM)**, the memory the CPU can access directly. It holds the running program and its data.

- **System clock**: timing signals sent on the control bus.

## 1.4.3 Registers

| Register | Purpose |
|---|---|
| PC (Program Counter) | Address of the next instruction |
| MAR (Memory Address Register) | Address currently being read or written |
| MDR (Memory Data Register) | Data or instruction just retrieved from (or about to be written to) memory |
| CIR (Current Instruction Register) | Instruction currently being decoded and executed |
| ACC (Accumulator) | Intermediate ALU results |
| SR (Status Register) | Status flags: Carry, Overflow, Zero, Negative |

## 1.4.4 Status flags

- **Carry** = 1 if a carry out of the most significant bit (MSB) occurred.

- **Overflow** = 1 if the signed result cannot be represented.

- **Zero** = 1 if the result is zero.

- **Negative** = 1 if the result is negative (MSB = 1 in two's complement).

Flags let the CPU make decisions such as “jump if zero”.

## 1.4.5 System buses

| Bus | Direction | Function |
|---|---|---|
| Address bus | CPU to memory (one-way) | Carries the memory address; its width determines the maximum addressable memory. |
| Data bus | Two-way | Carries data and instructions; its width determines the number of bits per transfer. |
| Control bus | Two-way | Carries clock ticks and commands (READ, WRITE, INTERRUPT). |

> **Worked example — address bus width**
>
> With *n* address lines the bus can carry 2*<sup>n</sup>* different addresses. An 8-bit address bus addresses 2<sup>8</sup> = 256 locations. A 32-bit bus addresses 2<sup>32</sup> = 4 294 967 296 locations, which is 4 GiB if each location holds one byte.

> **Activity 1.4 — Match the register**
>
> | Job | Register |
> |---|---|
> | Holds the address of the next instruction | ? |
> | Holds the instruction being decoded | ? |
> | Holds data read from memory | ? |
> | Holds the address being read | ? |
> | Holds ALU results | ? |
> | Holds Zero/Carry flags | ? |

> **Checked answers**
>
> PC, CIR, MDR, MAR, ACC, SR.

> **Exam-style practice**
>
> **Question (2 marks).** State the role of the Program Counter.
>
> **Checked answer.** Holds the address of the next instruction **(1)**; incremented after each fetch **(1)**.
>
> **Question (2 marks).** A computer has a 16-bit address bus. State how many memory locations it can address.
>
> **Checked answer.** 2<sup>16</sup> **(1)** = 65 536 locations **(1)**.

# Section 1.5 — The Fetch–Decode–Execute Cycle, Interrupts and Pipelining

> **Learning objectives**
>
> Describe each FDE stage, name the registers and buses used, explain interrupts and the ISR, and explain how instructions are encoded and how pipelining improves throughput.

![Figure 10 — The FDE cycle. Writeback is shown as a separate stage; some syllabi merge it into Execute.](modules/hardware/figures/fig010-the-fde-cycle-writeback-is-shown-as-a-separate-s.png)

*Figure 10 — The FDE cycle. Writeback is shown as a separate stage; some syllabi merge it into Execute.*

## 1.5.1 Step by step

### Fetch

1. PC → MAR via the address bus.

2. READ signal on the control bus.

3. Memory → MDR via the data bus.

4. MDR → CIR.

5. PC incremented.

### Decode

The CU decodes the opcode in the CIR and generates control signals.

### Execute

The ALU performs the operation and the SR flags are updated.

### Writeback

The result is stored in the ACC or written to memory.

## 1.5.2 Worked trace — ADD

| Step | Action | Registers / buses |
|---|---|---|
| 1 | Copy address 200 from PC to MAR | PC, MAR, address bus |
| 2 | Send READ | Control bus |
| 3 | Memory contents to MDR | Data bus, MDR |
| 4 | MDR to CIR; PC incremented | CIR, PC |
| 5 | CU decodes ADD | CU, CIR |
| 6 | Fetch the operand into MDR (address in MAR) | MAR, MDR, buses |

| Step | Action | Registers / buses |
|---|---|---|
| 7 | ALU adds the operand to ACC | ALU, ACC |
| 8 | Update flags | SR |

## 1.5.3 Interrupts

An **interrupt** is a signal that causes the processor to suspend its current task and service an event. Causes: a timing signal, I/O completion, a user action, a hardware fault or a software error. At the end of each FDE cycle the processor checks for interrupts. The **Interrupt Service Routine (ISR)** services the highest-priority interrupt: the processor saves its state, runs the ISR, restores the state and continues. An interrupt does **not** restart the computer.

![Figure 11 — Interrupt handling.](modules/hardware/figures/fig011-interrupt-handling.png)

*Figure 11 — Interrupt handling.*

## 1.5.4 Instruction format, assembly and pipelining

An **instruction** has two parts: an **opcode** (which operation to perform) and an **operand** (the data or the address of the data). The set of all instructions a CPU understands is its **instruction set architecture (ISA)**. **Machine code** is instructions in binary; **assembly language** uses short mnemonics (LDA, ADD, STO, JMP) that an **assembler** translates to machine code, one assembly instruction to one machine instruction.

| Addressing mode | Operand meaning | Example |
|---|---|---|
| Immediate | The operand is the value itself | ADD #5 adds the number 5 |
| Direct | The operand is the address of the value | ADD 200 adds the contents of address 200 |
| Indirect | The operand is the address of an address | ADD (200): address 200 holds the address of the data |
| Indexed | Operand address + contents of an index register | Used for arrays |

**Pipelining** overlaps the stages of consecutive instructions so that, while one instruction is being executed, the next is being decoded and the one after is being fetched. It raises *throughput* (instructions completed per unit time) but does not shorten the time for a single instruction. Branches can disrupt a pipeline because the CPU may have fetched the wrong instructions.

![Figure 12 — Pipelining five instructions through a three-stage pipeline.](modules/hardware/figures/fig012-pipelining-five-instructions-through-a-three-sta.png)

*Figure 12 — Pipelining five instructions through a three-stage pipeline.*

> **Worked example — pipeline speed-up**
>
> Five instructions, three stages, one clock cycle per stage. Without pipelining: 5 × 3 = 15 cycles. With pipelining: the first instruction finishes after 3 cycles, then one more completes every cycle, so the total is 3 + (5 − 1) = 7 cycles. Speed-up = 15 / 7 ≈ 2.1.

> **Activity 1.5 — Order the FDE stages**
>
> | Scrambled step | Position |
> |---|---|
> | Instruction decoded and executed | ? |
> | Address copied PC → MAR | ? |
> | PC incremented | ? |
> | Memory → MDR | ? |
> | MDR → CIR | ? |

> **Checked answer**
>
> PC→MAR (1), Memory→MDR (2), MDR→CIR (3), PC incremented (4), decode/execute (5). (Some textbooks increment the PC straight after PC→MAR; either is accepted if the order within the fetch is consistent.)

> **Exam-style practice**
>
> **Question (3 marks).** Explain what happens when an interrupt is received.
>
> **Checked answer.** Save the current state **(1)**; service the highest-priority interrupt via the ISR **(1)**; restore the state and continue **(1)**.
>
> **Question (2 marks).** Four instructions pass through a three-stage pipeline. Calculate the number of clock cycles needed.
>
> **Checked answer.** 3 + (4 − 1) **(1)** = 6 cycles **(1)**.

# Section 1.5 (continued) — Assembly Language and the Cambridge Instruction Set

> **Learning objectives (new in this edition)**
>
> Use the Cambridge AS &amp; A Level (9618) assembly instruction set, including **ADD**, **LDD** and **LDR**; explain immediate, direct, indirect and indexed addressing with the matching load instruction; trace a program that uses compare and jump instructions; use bit manipulation; and describe the two-pass assembler.

## 1.5.5 The Cambridge instruction set `NEW`

Section 1.5.4 introduced mnemonics such as LDA. Real processors and different textbooks name instructions differently. Cambridge 9618 exam papers always use the set below, and it is printed in the question paper. It uses two registers you can program: the **accumulator (ACC)**, where results are formed, and the **index register (IX)**, which holds an offset for indexed addressing.

**Operand notation:** `#n` = denary number (immediate), `Bn` = binary number, `&n` = hexadecimal number, `<address>` = a memory address. So `ADD #12`, `ADD B00001100` and `ADD &0C` all add twelve.

| Instruction | Addressing | What it does |
|---|---|---|
| **LDM** #n | Immediate | Load the number n into ACC. |
| **LDD** &lt;address&gt; | Direct | Load the *contents* of the given address into ACC. |
| **LDI** &lt;address&gt; | Indirect | The given address holds another address; load the contents of that second address into ACC. |
| **LDX** &lt;address&gt; | Indexed | Form the address &lt;address&gt; + IX; load the contents of that address into ACC. |
| **LDR** #n | Immediate | Load the number n into **IX** (not ACC). |
| **MOV** &lt;register&gt; | Register | Copy the contents of ACC into the given register (IX). |
| **STO** &lt;address&gt; | Direct | Store the contents of ACC at the given address. |
| **ADD** &lt;address&gt; | Direct | Add the contents of the given address to ACC. |
| **ADD** #n / Bn / &amp;n | Immediate | Add the number n to ACC. |
| **SUB** &lt;address&gt; | Direct | Subtract the contents of the given address from ACC. |
| **SUB** #n / Bn / &amp;n | Immediate | Subtract the number n from ACC. |
| **INC** &lt;register&gt; | Register | Add 1 to ACC or IX. |
| **DEC** &lt;register&gt; | Register | Subtract 1 from ACC or IX. |
| **JMP** &lt;address&gt; | Direct | Jump to the given address (unconditional). |
| **CMP** &lt;address&gt; | Direct | Compare ACC with the contents of the given address. |
| **CMP** #n | Immediate | Compare ACC with the number n. |
| **CMI** &lt;address&gt; | Indirect | The given address holds another address; compare ACC with the contents of that second address. |

| Instruction | Addressing | What it does |
|---|---|---|
| **JPE** &lt;address&gt; | Direct | After a compare: jump to the address if the compare was **True** (equal). |
| **JPN** &lt;address&gt; | Direct | After a compare: jump to the address if the compare was **False** (not equal). |
| **IN** | — | Key in a character and store its ASCII value in ACC. |
| **OUT** | — | Output the character whose ASCII value is in ACC. |
| **END** | — | Return control to the operating system. |

> **Common confusion — LDD vs LDM vs LDR**
>
> **LDM #200** puts the *number* 200 into ACC. **LDD 200** goes to *address* 200 and puts whatever is stored there into ACC. **LDR #2** puts the number 2 into the *index register*, not ACC. The extra letter tells you the mode: M = iMmediate value, D = Direct, I = Indirect, X = indeXed, R = index Register. (Do not confuse the instruction LDR with an LDR light sensor, Section 1.9.5.)

## 1.5.6 The load instructions side by side `NEW`

All five worked examples below use the same memory contents.

| Address | Contents |
|---|---|
| 200 | 205 |
| 201 | 3 |
| 202 | 17 |
| 203 | 9 |
| 204 | 12 |
| 205 | 42 |
| 206 | 7 |

| Instruction | Reasoning | Result |
|---|---|---|
| LDM #200 | Immediate: the operand is the value | ACC = 200 |
| LDD 200 | Direct: contents of 200 | ACC = 205 |
| LDI 200 | Address 200 holds 205; contents of 205 | ACC = 42 |
| LDR #2 | Immediate into the index register | IX = 2 |
| LDR #2 then LDX 200 | Address 200 + IX = 202; contents of 202 | ACC = 17 |

**Why indexed addressing exists.** LDR and LDX together let one instruction step through an array: set IX to 0 with LDR #0, read element 0 with LDX, then INC IX and repeat. The base address in the instruction never changes; only IX does.

## 1.5.7 ADD and SUB: direct and immediate `NEW`

| Instruction | Meaning | ACC after |
|---|---|---|
| LDM #10 | load the number 10 | 10 |
| ADD 201 | add contents of 201 (3) | 13 |
| ADD #5 | add the number 5 | 18 |
| SUB B00000100 | subtract binary 100 = 4 | 14 |
| ADD &amp;0A | add hex 0A = 10 | 24 |

The ADD in the FDE trace of Section 1.5.2 is `ADD <address>`: the address goes PC → MAR, the value comes back through the MDR, and the ALU adds it to ACC.

## 1.5.8 Worked trace — LDD, ADD, STO `NEW`

> **Worked example — add two numbers and store the total**
>
> Memory before: 200 = 25, 201 = 17, 202 = 0. The program starts at address 100.
>
> | Address | Instruction | ACC | Memory 202 |
> |---|---|---|---|
> | 100 | LDD 200 | 25 | 0 |
> | 101 | ADD 201 | 42 | 0 |
> | 102 | STO 202 | 42 | 42 |
> | 103 | END | 42 | 42 |
>
> LDD copies 25 into ACC; ADD adds the contents of 201 to give 42; STO writes 42 into address 202.

## 1.5.9 Loops: compare and jump with indexed addressing `NEW`

A loop needs three things: something that changes each time (IX and a counter), a compare (CMP) and a conditional jump (JPN or JPE). This program totals four numbers stored at addresses 310–313.

| Address | Instruction | Comment |
|---|---|---|
| 100 | LDR #0 | IX ← 0 (start of the array) |
| 101 | LDX 310 | ACC ← contents of (310 + IX) |
| 102 | ADD 300 | ACC ← ACC + running total |
| 103 | STO 300 | store the new running total |
| 104 | INC IX | move to the next array element |
| 105 | LDD 302 | ACC ← counter |
| 106 | INC ACC | counter + 1 |
| 107 | STO 302 | store the counter |
| 108 | CMP #4 | have we added 4 numbers? |
| 109 | JPN 101 | if not, go back to 101 |
| 110 | END | stop |

> **Worked example — full trace table**
>
> Memory before: 300 (total) = 0, 302 (counter) = 0, 310–313 = 5, 8, 2, 6. Each row shows the values after that instruction has executed.
>
> | Addr | Instruction | ACC | IX | 300 | 302 | Compare / jump |
> |---|---|---|---|---|---|---|
> | 100 | LDR #0 | 0 | 0 | 0 | 0 |  |

> | Addr | Instruction | ACC | IX | 300 | 302 | Compare / jump |
> |---|---|---|---|---|---|---|
> | 101 | LDX 310 | 5 | 0 | 0 | 0 |  |
> | 102 | ADD 300 | 5 | 0 | 0 | 0 |  |
> | 103 | STO 300 | 5 | 0 | 5 | 0 |  |
> | 104 | INC IX | 5 | 1 | 5 | 0 |  |
> | 105 | LDD 302 | 0 | 1 | 5 | 0 |  |
> | 106 | INC ACC | 1 | 1 | 5 | 0 |  |
> | 107 | STO 302 | 1 | 1 | 5 | 1 |  |
> | 108 | CMP #4 | 1 | 1 | 5 | 1 | False |
> | 109 | JPN 101 | 1 | 1 | 5 | 1 | jump to 101 |
> | 101 | LDX 310 | 8 | 1 | 5 | 1 |  |
> | 102 | ADD 300 | 13 | 1 | 5 | 1 |  |
> | 103 | STO 300 | 13 | 1 | 13 | 1 |  |
> | 104 | INC IX | 13 | 2 | 13 | 1 |  |
> | 105 | LDD 302 | 1 | 2 | 13 | 1 |  |
> | 106 | INC ACC | 2 | 2 | 13 | 1 |  |
> | 107 | STO 302 | 2 | 2 | 13 | 2 |  |
> | 108 | CMP #4 | 2 | 2 | 13 | 2 | False |
> | 109 | JPN 101 | 2 | 2 | 13 | 2 | jump to 101 |
> | 101 | LDX 310 | 2 | 2 | 13 | 2 |  |
> | 102 | ADD 300 | 15 | 2 | 13 | 2 |  |
> | 103 | STO 300 | 15 | 2 | 15 | 2 |  |
> | 104 | INC IX | 15 | 3 | 15 | 2 |  |
> | 105 | LDD 302 | 2 | 3 | 15 | 2 |  |
> | 106 | INC ACC | 3 | 3 | 15 | 2 |  |
> | 107 | STO 302 | 3 | 3 | 15 | 3 |  |
> | 108 | CMP #4 | 3 | 3 | 15 | 3 | False |
> | 109 | JPN 101 | 3 | 3 | 15 | 3 | jump to 101 |
> | 101 | LDX 310 | 6 | 3 | 15 | 3 |  |
> | 102 | ADD 300 | 21 | 3 | 15 | 3 |  |
> | 103 | STO 300 | 21 | 3 | 21 | 3 |  |
> | 104 | INC IX | 21 | 4 | 21 | 3 |  |

> | Addr | Instruction | ACC | IX | 300 | 302 | Compare / jump |
> |---|---|---|---|---|---|---|
> | 105 | LDD 302 | 3 | 4 | 21 | 3 |  |
> | 106 | INC ACC | 4 | 4 | 21 | 3 |  |
> | 107 | STO 302 | 4 | 4 | 21 | 4 |  |
> | 108 | CMP #4 | 4 | 4 | 21 | 4 | True |
> | 109 | JPN 101 | 4 | 4 | 21 | 4 | no jump |
> | 110 | END | 4 | 4 | 21 | 4 |  |

> Final total in address 300 = **21** (5 + 8 + 2 + 6). The loop ran four times because JPN jumped back while the counter was not equal to 4.

## 1.5.10 Bit manipulation `NEW`

The 9618 set also contains logical and shift instructions. They work on ACC one bit at a time and are used to test, set or clear individual bits, for example status flags from a sensor or device.

| Instruction | What it does | Example: ACC = 01101100 before | ACC after |
|---|---|---|---|
| **AND** #n / Bn / &amp;n, or AND &lt;address&gt; | Bitwise AND: a **mask** that clears bits (keep only bits where the mask is 1) | AND B00001111 | 00001100 |
| **OR** #n / Bn / &amp;n, or OR &lt;address&gt; | Bitwise OR: **sets** bits to 1 where the mask is 1 | OR B10000000 | 11101100 |
| **XOR** #n / Bn / &amp;n, or XOR &lt;address&gt; | Bitwise XOR: **toggles** bits where the mask is 1 | XOR B11111111 | 10010011 |
| **LSL** #n | Logical shift left n places; zeros enter on the right | LSL #2 (on 00010110 = 22) | 01011000 = 88 |
| **LSR** #n | Logical shift right n places; zeros enter on the left | LSR #1 (on 01011000 = 88) | 00101100 = 44 |

A logical shift left by n multiplies an unsigned number by 2<sup>n</sup>; a shift right divides by 2<sup>n</sup> (any remainder is lost). Bits shifted off the end are lost, so a large number shifted left can overflow.

> **Worked example — testing one bit**
>
> A sensor stores its status in address 400. Bit 3 (value 8) is 1 when the sensor is faulty. `LDD 400`, `AND #8`, `CMP #8`,
>
> `JPE 500`. The AND clears every bit except bit 3; if the result equals 8, bit 3 was set and the program jumps to the fault routine at 500.

## 1.5.11 The two-pass assembler `NEW`

Programmers write **labels** (names such as LOOP or TOTAL) instead of numeric addresses. A label can be used before it is defined (a forward reference), so the assembler reads the program twice.

| Pass | What the assembler does |
|---|---|
| Pass 1 | Reads every line; removes comments and white space; adds each label to the **symbol table** with the address it stands for; keeps a count of addresses as it goes. |
| Pass 2 | Reads the program again; replaces each mnemonic with its binary opcode (from the opcode table); replaces each label with its address from the symbol table; outputs the machine code (object code). |

| Label (symbol) | Address |
|---|---|
| LOOP | 101 |
| TOTAL | 300 |
| COUNT | 302 |

Symbol table for the program in Section 1.5.9 if it were written with labels: `LOOP: LDX 310` … `JPN LOOP`.

> **Activity 1.5B — Load and add**
>
> Memory: 50 = 53, 51 = 4, 52 = 9, 53 = 20. IX = 1. Give ACC after each instruction, starting again each time: (a) LDM #50 (b) LDD 50 (c) LDI 50 (d) LDX 51 (e) LDD 51 then ADD 52 (f) LDD 53 then SUB #5.

> **Checked answers**
>
> (a) 50 (b) 53 (c) 20 (address 50 holds 53, which holds 20) (d) 9 (address 51 + 1 = 52) (e) 4 + 9 = 13 (f) 20 − 5 = 15.

> **Exam-style practice**
>
> **Question (4 marks).** Explain the difference between `LDD 200` and `LDR #200`, and describe how LDR is used with LDX to process an array.
>
> **Checked answer.** LDD uses direct addressing: it loads the contents of address 200 into ACC **(1)**. LDR uses immediate addressing: it loads the number 200 into the index register **(1)**. LDR #0 sets IX to the first element; LDX &lt;base&gt; loads the element at base + IX **(1)**; INC IX moves to the next element and a CMP/JPN loop repeats it **(1)**.
>
> **Question (2 marks).** ACC holds 00110101. State the contents of ACC after LSL #1 and explain the effect on the denary value.
>
> **Checked answer.** 01101010 **(1)**; the value is doubled, 53 → 106 **(1)**.

# Section 1.6 — Memory Hierarchy and Cache

> **Learning objectives**
>
> Explain why a hierarchy exists, compare registers, cache, RAM and storage, explain locality, and explain how cache works.

Fast memory is expensive and small; large memory is cheap and slow. Computers therefore combine several kinds of memory in layers, keeping the most-needed data in the fastest layer. This is the **memory hierarchy**.

![Figure 13 — Memory hierarchy pyramid.](modules/hardware/figures/fig013-memory-hierarchy-pyramid.png)

*Figure 13 — Memory hierarchy pyramid.*

| Tier | Type | Technology | Capacity | Latency |
|---|---|---|---|---|
| 1 | Registers | Flip-flops | ~1–2 KB | &lt; 0.5 ns |
| 2 | Cache | SRAM | 32 KB – 128 MB | 1–15 ns |
| 3 | RAM | DRAM | 8–128 GB | 50–100 ns |
| 4 | Storage | Flash SSD | 512 GB – 4 TB | ~50 000 ns |

## 1.6.1 Locality

**Temporal locality:** recently used data is likely to be reused soon. **Spatial locality:** data near recently used data is likely to be used soon. Cache exploits both by keeping recent data and by fetching neighbouring data together. A **cache hit** means the data is in cache; a **cache miss** means it must be fetched from a slower tier.

> **Worked example — cache benefit**
>
> If 90% of accesses hit cache (1 ns) and 10% miss and go to RAM (80 ns): Average = 0.9 × 1 + 0.1 × 80 = 0.9 + 8 = **8.9 ns**.
>
> This is far better than 80 ns for every access.

> **Activity 1.6 — Rank the access**
>
> Rank register, L1 cache, RAM and SSD from fastest to slowest. Then recalculate the average access time if the hit rate falls to 80%.

> **Checked answer**
>
> register → L1 cache → RAM → SSD. At an 80% hit rate: 0.8 × 1 + 0.2 × 80 = 0.8 + 16 = 16.8 ns, almost twice as slow, which shows why hit rate matters.

> **Exam-style practice**
>
> **Question (2 marks).** Explain why cache sits between the CPU and main memory.
>
> **Checked answer.** Cache is faster and holds frequently used data close to the CPU **(1)**, reducing the average wait
>
> time **(1)**.

# Section 1.7 — RAM, ROM and Storage Technologies

> **Learning objectives**
>
> Compare DRAM and SRAM, explain their uses, distinguish PROM, EPROM and EEPROM, and explain flash memory.

## 1.7.1 DRAM vs SRAM

**DRAM** (dynamic RAM) uses one transistor and one capacitor per bit. The capacitor leaks charge, so each cell must be **refreshed** periodically. DRAM is dense and cheap, so it is used for main memory. **SRAM** (static RAM) uses several transistors (commonly six) per bit; it needs no refresh while powered. It is fast but expensive and bulky, so it is used

for cache and registers.

![Figure 14 — DRAM versus SRAM cells (simplified).](modules/hardware/figures/fig014-dram-versus-sram-cells-simplified.png)

*Figure 14 — DRAM versus SRAM cells (simplified).*

| Feature | DRAM | SRAM |
|---|---|---|
| Storage | 1 transistor + 1 capacitor | Multi-transistor latch |
| Refresh | Yes | No (while powered) |
| Speed | Slower | Faster |
| Cost per bit | Lower | Higher |
| Density | High | Lower |
| Typical use | Main memory | Cache |

## 1.7.2 ROM types

| Type | Programmed | Erased | Typical use |
|---|---|---|---|
| ROM (mask) | At the factory | Never | Fixed firmware in mass-produced devices |
| PROM | Once, by the user | Cannot be erased | Small production runs |
| EPROM | By the user | Ultraviolet light; chip usually removed | Prototyping |
| EEPROM | By the user | Electrically, often in-circuit | Firmware updated in place, e.g. BIOS settings |

**Flash memory** is EEPROM-related, erased and written in blocks. It is used in SSDs, USB drives and memory cards.

> **Activity 1.7 — Choose the memory**
>
> | Situation | Best choice | Reason |
> |---|---|---|
> | Main memory | ? | ? |
> | L3 cache | ? | ? |
> | Firmware updated in-circuit | ? | ? |
> | USB drive | ? | ? |

> **Checked answers**
>
> | Situation | Best choice | Reason |
> |---|---|---|
> | Main memory | DRAM | Dense and cheap per bit |
> | L3 cache | SRAM | Fast, no refresh |
> | Firmware updated in-circuit | EEPROM | Electrically erasable in place |
> | USB drive | Flash | Non-volatile, block erase, portable |

> **Exam-style practice**
>
> **Question (2 marks).** Firmware must be updated without removing the chip. State the ROM type and justify it.
>
> **Checked answer.** EEPROM **(1)**, because it can be erased and reprogrammed electrically in-circuit **(1)**.

# Section 1.8 — Buffers and Virtual Memory

> **Learning objectives**
>
> Define a buffer, distinguish buffers from cache, and explain virtual memory, paging and swapping.

## 1.8.1 Buffers

A **buffer** is temporary storage used during data transfer between devices with different speeds. Examples: keyboard buffer, printer buffer, video-streaming buffer and double buffering of display frames.

![Figure 15 — A buffer smoothing speed differences.](modules/hardware/figures/fig015-a-buffer-smoothing-speed-differences.png)

*Figure 15 — A buffer smoothing speed differences.*

> **Buffer vs cache**
>
> A **cache** speeds up *repeated* access to the same data. A **buffer** smooths a *speed mismatch* during a transfer; the data is usually read once, in order.

## 1.8.2 Virtual memory

**Virtual memory** uses secondary storage as extra RAM. The operating system divides memory into fixed-size **pages** and moves them between RAM and a **swap file** (page file). A **page fault** occurs when a required page is not in RAM. **Thrashing** is excessive swapping, where the system spends more time moving pages than running programs.

![Figure 16 — Virtual memory: pages swapped between RAM and the swap file.](modules/hardware/figures/fig016-virtual-memory-pages-swapped-between-ram-and-the.png)

*Figure 16 — Virtual memory: pages swapped between RAM and the swap file.*

**How it works:** the OS checks whether a page is in RAM; if not, a page fault occurs, an unneeded page is written to the swap file, and the required page is read into RAM. This is much slower than RAM but allows programs larger than RAM

to run. Adding more RAM reduces page faults.

> **Activity 1.8 — Buffer or cache?**
>
> | Scenario | Buffer or cache? | Why |
> |---|---|---|
> | Keyboard holds key presses | ? | ? |
> | CPU holds recently used data | ? | ? |
> | Video player stores data ahead | ? | ? |
> | L1 holds loop instructions | ? | ? |

> **Checked answers**
>
> | Scenario | Answer | Why |
> |---|---|---|
> | Keyboard holds key presses | Buffer | Speed mismatch with the CPU |
> | CPU holds recently used data | Cache | Temporal locality |
> | Video player stores data ahead | Buffer | Smooths network variation |
> | L1 holds loop instructions | Cache | Repeated use of the same instructions |

> **Exam-style practice**
>
> **Question (3 marks).** Explain how virtual memory allows a program larger than RAM to run.
>
> **Checked answer.** The OS divides memory into pages **(1)**; unused pages are moved to secondary storage **(1)**; needed pages are swapped back into RAM **(1)**.

# Section 1.9 — Input and Output Devices

> **Learning objectives**
>
> Describe the principles of operation of common input and output devices, including sensors, actuators, printers and displays, and compare HDMI and VGA.

## 1.9.1 Input devices

An **input device** converts data from the outside world into a digital signal the computer can process.

| Device | Principle of operation | Typical use |
|---|---|---|
| Keyboard | Key presses close circuits, generating a unique code (e.g. ASCII). | Text and number entry |
| Mouse | Movement is detected by a sensor and translated into cursor movement; buttons register clicks. | Pointing and selection |
| Microphone | Converts sound waves into electrical signals, then into digital data via an ADC (analogue-to-digital converter). | Voice input, audio recording |
| Barcode scanner | Shines light on a barcode; the reflected light pattern is converted into a digital code. | Retail, inventory |
| QR code scanner | A camera captures the QR pattern; software decodes the data. | Mobile payments, advertising |
| Digital camera | A lens focuses light onto a sensor (CCD/CMOS) that converts it into digital pixels. | Photography, video |
| 2D / 3D scanner | 2D scans documents; 3D scans objects using lasers or structured light. | Document archiving, 3D modelling |
| Touchscreen | Detects touch via capacitive or resistive layers; position is calculated by a microprocessor. | Smartphones, kiosks |
| Sensors | Measure physical quantities (light, temperature, pressure, moisture) and output a signal. | Monitoring and control systems |

## 1.9.2 Output devices

An **output device** presents processed results.

| Device | Principle of operation | Typical use |
|---|---|---|
| Inkjet printer | Sprays tiny droplets of ink onto paper. | Home/office printing |
| Laser printer | A laser charges a drum; toner adheres to the charge and is fused onto paper. | High-volume printing |
| 3D printer | Builds objects layer by layer from plastic, resin or metal. | Prototyping, manufacturing |
| 2D / 3D cutter | 2D cuts flat material; 3D cuts or sculpts objects. | Sign-making, fabrication |
| Speakers / headphones | Convert electrical signals into sound waves. | Audio output |
| Actuators | Electromechanical devices (motors, valves, relays) that produce physical action. | Control systems |
| LCD / LED display | LCD uses liquid crystals; LED uses light-emitting diodes as backlight or pixels. | Monitors, TVs, phones |

| Device | Principle of operation | Typical use |
|---|---|---|
| LCD / DLP projector | Projects an image onto a screen using LCD panels or DLP micromirrors. | Presentations, cinema |

## 1.9.3 HDMI vs VGA

| Feature | HDMI | VGA |
|---|---|---|
| Signal | Digital | Analogue |
| Audio | Yes (when supported) | No |
| Connector | Compact, flat | 15-pin D-sub |
| Typical use | Modern displays and TVs | Older displays and projectors |

## 1.9.4 Worked example — a mouse click

> **Mouse click**
>
> Mouse → I/O controller → device driver → CPU executes → display controller updates the monitor. The CPU does not “see” the mouse directly; the device driver translates between the hardware and the operating system.

> **Activity 1.9 — Match the device**
>
> | Task | Most suitable device | Reason |
> |---|---|---|
> | Enter text into a word processor | ? | ? |
> | Read a product barcode at checkout | ? | ? |
> | Print a high-volume office document | ? | ? |
> | Produce a physical prototype | ? | ? |

> **Checked answers**
>
> Keyboard (text entry); barcode scanner (fast, accurate); laser printer (high volume, low cost per page); 3D printer (layered construction).

> **Exam-style practice**
>
> **Question (2 marks).** Compare HDMI and VGA in signal type and audio support.
>
> **Checked answer.** HDMI is digital and carries audio **(1)**; VGA is analogue and does not carry audio **(1)**.

# Section 1.9 (continued) — Sensors in Detail

## 1.9.5 Types of sensor, including the LDR `NEW`

A **sensor** is an input device that measures a physical quantity and sends a signal to a microprocessor. Most sensors produce an **analogue** signal (a continuously varying voltage), so an **ADC (analogue-to-digital converter)** is needed before the processor can use the reading. Sensors only measure; they never make decisions. The processor compares the reading with a stored value and, in a control system, switches an actuator (Section 1.11.3).

| Sensor | What it measures | Typical application |
|---|---|---|
| Acoustic (sound) | Sound level | Detecting breaking glass in a burglar alarm |
| Accelerometer | Acceleration and tilt | Phone screen rotation, airbag crash detection |
| Flow | Rate of flow of a liquid or gas | Water pipes, fuel lines |
| Gas | Concentration of a gas (e.g. CO2, CO) | Carbon monoxide alarm, greenhouse CO2 control |
| Humidity | Water vapour in the air | Greenhouse, museum climate control |
| Infrared (IR) / PIR | Infrared radiation; movement of a warm body | Intruder alarm, automatic doors |
| Level | Height of a liquid or solid in a container | Fuel tank gauge, washing machine water level |
| **Light (LDR)** | Light intensity | Automatic street lights, screen brightness, greenhouse lighting |
| Magnetic field | Strength of a magnetic field | Phone compass, anti-lock brake wheel-speed sensors |
| Moisture | Water content of soil or a surface | Irrigation control |
| pH | Acidity or alkalinity | Aquariums, chemical plants, soil testing |
| Pressure | Force on a surface | Burglar-alarm pressure mats, tyre pressure |
| Proximity | Whether an object is near | Parking sensors, phone screen turning off at the ear |
| Temperature (thermistor) | Temperature | Central heating, ovens, greenhouses |

**The LDR (light-dependent resistor).** An LDR is a resistor whose resistance changes with light: in bright light its resistance is **low**; in darkness its resistance is **high**. It is placed in a potential-divider circuit so that the change in resistance becomes a change in voltage, which the ADC converts to a number.

![Figure 16A — The LDR changes resistance; the processor, not the sensor, makes the decision.](modules/hardware/figures/fig16a-the-ldr-changes-resistance-the-processor-not-the.png)

*Figure 16A — The LDR changes resistance; the processor, not the sensor, makes the decision.*

> **Worked example — an automatic street light**
>
> (1) The LDR measures light intensity continuously. (2) The ADC converts the analogue reading to digital. (3) The microprocessor compares the value with a stored threshold. (4) If the value shows it is darker than the threshold, the microprocessor sends a signal to switch the lamp on; otherwise it switches it off. (5) The process repeats. A short delay is often added so a passing car's headlights do not switch the lamp off.

> **Activity 1.9B — Choose the sensor**
>
> Name the most suitable sensor: (a) a car's automatic headlights, (b) a smart irrigation system, (c) an alarm that detects a person walking into a room, (d) a fish tank that keeps the water at the right acidity, (e) a car that warns the driver when it is close to a wall.

> **Checked answers**
>
> (a) Light (LDR) (b) Moisture (c) Infrared / PIR (motion) (d) pH (e) Proximity.

> **Exam-style practice**
>
> **Question (2 marks).** Describe how the resistance of an LDR changes with light intensity.
>
> **Checked answer.** Resistance decreases as light intensity increases **(1)**; resistance is high in the dark **(1)**.

# Section 1.10 — Network Hardware and Cloud Storage

> **Learning objectives**
>
> Define LAN and WAN, identify common network hardware, explain packets, and compare local and cloud storage.

## 1.10.1 Networks

A **LAN (Local Area Network)** covers a small area such as a home, school or office. A **WAN (Wide Area Network)** covers a large area such as cities or countries; the Internet is the best-known WAN. Networks allow resource sharing, communication and central management. The *Networks* module in this series covers them in depth.

## 1.10.2 Network hardware

| Device | Role |
|---|---|
| NIC (network interface card) | Connects a device to a network; converts data into signals. Each NIC has a unique MAC address. |
| Switch | Forwards data within a LAN to the intended device only. |
| Router | Connects different networks and forwards packets between them. |
| WAP (wireless access point) | Provides wireless access to a wired network. |
| Modem | Converts signals between the service provider's line and the local network. |
| Firewall | Monitors and controls traffic for security. |

Data is broken into **packets**: small units with addressing information. Packets let many devices share a network efficiently.

## 1.10.3 Cloud storage

**Cloud storage** stores data on provider servers accessed over a network. The user's device sends data to a data centre; the provider stores it and makes it available to authorised devices.

| Feature | Local storage | Cloud storage |
|---|---|---|
| Location | User device | Provider servers |
| Access | Direct | Requires a network |
| Capacity | Limited by the device | Often scalable |
| Sharing | Manual | Easy via links |
| Main risk | Device loss or damage | Account security, provider outage |
| Cost | One-off hardware | Subscription or usage-based |

**Advantages of cloud:** access from multiple devices, easy backup, scalable capacity, collaboration. **Disadvantages:** depends on a network, ongoing cost, privacy and security concerns, provider lock-in.

> **Activity 1.10 — Local or cloud?**
>
> | Scenario | Better choice | Reason |
> |---|---|---|
> | Editing a video while travelling | ? | ? |
> | Sharing a group project | ? | ? |
> | Backing up important photos | ? | ? |
> | Storing an OS for fast boot | ? | ? |

> **Checked answers**
>
> Local (no reliable network, low latency); cloud (easy sharing); cloud (off-site backup); local (low latency needed).

> **Exam-style practice**
>
> **Question (2 marks).** State one advantage and one disadvantage of cloud storage.
>
> **Checked answer.** Advantage: access from multiple devices or automatic backup **(1)**. Disadvantage: depends on an internet connection or raises security concerns **(1)**.

# Section 1.11 — Embedded Systems, Monitoring and Control

> **Learning objectives**
>
> Define an embedded system, identify its components, explain real-time constraints, and distinguish monitoring from control systems.

## 1.11.1 Embedded systems

An **embedded system** is a computer dedicated to a specific function inside a larger device. Components: microcontroller/processor, memory, sensors, actuators and I/O interfaces. Examples: washing machine, car control system, smart speaker, traffic light. Unlike a general-purpose PC, its program is fixed in ROM/flash and rarely changes.

## 1.11.2 Real-time constraints

**Hard real-time:** missing the deadline is a failure (e.g. an airbag controller). **Soft real-time:** missing the deadline degrades quality but is not catastrophic (e.g. video streaming).

## 1.11.3 Monitoring and control

A **monitoring system** observes and reports. A **control system** observes and acts automatically. **Sensors** measure, **actuators** act, and **feedback** uses the measured result to adjust future action.

| System type | Job | Example |
|---|---|---|
| Monitoring | Observe and report | Temperature display |
| Control | Observe and act | Thermostat switching a heater |
| Combined | Observe, report and act | Smart thermostat |

## 1.11.4 Worked example — greenhouse

Temperature sensor → microcontroller compares with the target → heater actuator switched on if too cold → vent/fan switched on if too warm → repeat (feedback). Note that the sensor produces an analogue signal, so an ADC converts it to digital before the microcontroller can use it.

![Figure 17 — A monitoring-and-control feedback loop.](modules/hardware/figures/fig017-a-monitoring-and-control-feedback-loop.png)

*Figure 17 — A monitoring-and-control feedback loop.*

> **Activity 1.11 — Identify sensors and actuators**
>
> | System | Sensor | Actuator |
> |---|---|---|
> | Washing machine | ? | ? |
> | Greenhouse | ? | ? |
> | Anti-lock brakes | ? | ? |
> | Smart speaker | ? | ? |

> **Checked answers**
>
> | System | Sensor | Actuator |
> |---|---|---|
> | Washing machine | Water level / temperature | Motor / valve |
> | Greenhouse | Temperature | Heater / vent |
> | Anti-lock brakes | Wheel speed | Brake-pressure modulator |
> | Smart speaker | Microphone | Speaker |

> **Exam-style practice**
>
> **Question (3 marks).** Describe three components of an embedded washing-machine system and their roles.
>
> **Checked answer.** Microcontroller executes the program **(1)**; sensor monitors water level/temperature **(1)**; actuator drives the motor/valve **(1)**.

# Section 1.12 — Processor Specialisation and CPU Core Types

> **Learning objectives**
>
> Compare CPU, GPU and TPU in latency and throughput, and distinguish P-cores from E-cores.

## 1.12.1 CPU, GPU, TPU

**Latency** is the delay before a result is available; **throughput** is the amount of work completed per unit time. A

processor can be designed to favour one or the other.

| Processor | Design goal | Best at | Limitation |
|---|---|---|---|
| CPU | Low latency | Sequential, branchy code (operating system, general programs) | Lower parallel throughput |
| GPU | High throughput | Graphics, parallel numerical work (SIMT: single instruction, multiple threads) | Weak on branchy sequential code |
| TPU | Very high throughput for tensor maths | Matrix multiplication for machine learning | Narrow specialisation |
| Microcontroller | Predictable, low power | Dedicated control tasks with hard real-time deadlines | Small memory, limited speed |

## 1.12.2 P-cores and E-cores

**P-cores** (performance cores) prioritise speed on demanding tasks. **E-cores** (efficiency cores) prioritise power efficiency on background tasks. More cores help only if the workload can be split to use them.

> **Activity 1.12 — Choose the processor**
>
> For each scenario choose from: CPU, GPU, TPU, microcontroller.
>
> | Scenario | Best choice | Reason |
> |---|---|---|
> | Running a word processor | ? | ? |
> | Rendering 3D game frames | ? | ? |
> | Training a neural network | ? | ? |
> | Anti-lock braking control | ? | ? |

> **Checked answers**
>
> CPU (sequential, general purpose); GPU (parallel pixels); TPU (matrix maths); microcontroller (hard real-time,
>
> dedicated control).

> **Exam-style practice**
>
> **Question (4 marks).** Compare CPU, GPU and TPU for running an OS, rendering graphics and training a neural network.
>
> **Checked answer.** CPU for the OS (sequential) **(1)**; GPU for graphics (parallel pixels) **(1)**; TPU for training (matrix multiplication) **(1)**; each balances latency and throughput differently **(1)**.

# Section 1.12 (continued) — RISC, CISC and Parallel Processing

> **Learning objectives (new in this edition)**
>
> Compare RISC and CISC processors; explain why RISC suits pipelining; describe Flynn's four basic architectures (SISD, SIMD, MISD, MIMD); and explain massively parallel computers.

## 1.12.3 RISC and CISC processors (A Level) `NEW`

A processor's instruction set (Section 1.5.4) can follow one of two design philosophies. A **CISC** (Complex Instruction Set Computer) provides many powerful instructions, some of which do several steps at once. A **RISC** (Reduced Instruction Set Computer) provides fewer, simpler instructions, each taking one clock cycle, and builds complex operations from several of them.

| Feature | RISC | CISC |
|---|---|---|
| Number of instructions | Fewer, simpler | Many, some complex |
| Instruction length / format | Fixed length, few formats | Variable length, many formats |
| Clock cycles per instruction | Usually one | Often several |
| Addressing modes | Few | Many |
| Memory access | Only LOAD and STORE use memory (load– store) | Many instructions can work directly on memory |
| Registers | Many general-purpose registers | Fewer registers |
| Control unit | Hardwired: fast | Often microprogrammed |
| Pipelining | Easy: every instruction takes the same time | Harder: instructions vary in length and time |
| Program in RAM | More instructions, so larger | Fewer instructions, so smaller |
| Work done by | The compiler (more instructions to generate) | The hardware (complex circuits) |
| Examples | ARM (phones, tablets, Apple M-series), RISC-V | Intel and AMD x86 (most desktop PCs) |

> **Worked example — multiplying two numbers in memory**
>
> Multiply the value at address 2:3 by the value at 5:2 and store the result back at 2:3.
>
> **CISC:** one instruction, `MULT 2:3, 5:2`. The hardware loads both values, multiplies and stores; it takes several clock cycles but the program is one line.
>
> **RISC:** four simple instructions, `LOAD A, 2:3` · `LOAD B, 5:2` · `PROD A, B` · `STORE 2:3, A`. Each takes about one cycle and they flow neatly through a pipeline.

Modern designs blur the line: x86 CISC processors translate complex instructions internally into RISC-like micro- operations so they can be pipelined. RISC's low power use is why ARM dominates phones and embedded systems (Section 1.11).

## 1.12.4 Parallel processing and Flynn's classification (A Level) `NEW`

**Parallel processing** means using more than one processing unit at the same time on a task. Michael Flynn classified computer architectures by how many **instruction streams** and **data streams** they handle at once.

![Figure 17A — The four basic computer architectures.](modules/hardware/figures/fig17a-the-four-basic-computer-architectures.png)

*Figure 17A — The four basic computer architectures.*

**Massively parallel computers** link a very large number of processors (thousands or more), each with its own memory, by a fast network so they can work on separate parts of one huge problem at the same time: weather forecasting, climate modelling, protein folding and training large AI models. They are MIMD machines. A problem only speeds up if it can be split into parts that run independently: this is the same idea as the P-core/E-core point in Section 1.12.2 and the GPU's SIMT design in Section 1.12.1.

> **Activity 1.12B — Classify**
>
> Classify each as SISD, SIMD, MISD or MIMD: (a) a GPU brightening every pixel of an image with the same instruction, (b) an early single-core PC, (c) an 8-core laptop running a browser, a game and a virus scan, (d) three flight computers performing the same check on the same sensor data and voting on the result.

> **Checked answers**
>
> (a) SIMD (b) SISD (c) MIMD (d) MISD.

> **Exam-style practice**
>
> **Question (4 marks).** Explain two differences between RISC and CISC processors and why RISC processors are well suited to pipelining.
>
> **Checked answer.** RISC has fewer, simpler instructions / CISC many complex ones **(1)**; RISC instructions are fixed length and take one cycle / CISC variable length and several cycles **(1)**. Because every RISC instruction is the same length and takes the same time **(1)**, each pipeline stage stays full and evenly timed **(1)**.

# Section 1.13 — Module Summary and Mind Map

![Figure 18 — Mind map of Module 1: Computer Hardware and Microarchitecture.](modules/hardware/figures/fig018-mind-map-of-module-1-computer-hardware-and-micro.png)

*Figure 18 — Mind map of Module 1: Computer Hardware and Microarchitecture.*

| Topic | Core comparison |
|---|---|
| 1.2 Binary / denary / hex | Base and bit grouping; units bit to TB |
| 1.3 Logic | Gates, truth tables, half-adder |
| 1.4 Von Neumann | Registers and three buses; IAS = main memory |
| 1.5 FDE | Stage order; interrupts/ISR; pipelining |
| 1.6 Memory hierarchy | Speed vs capacity vs cost; locality |
| 1.7 RAM/ROM | DRAM vs SRAM; PROM/EPROM/EEPROM; flash |
| 1.8 Buffers / virtual memory | Transfer storage; RAM + secondary storage |
| 1.9 I/O devices | Input principles; output principles; HDMI vs VGA |
| 1.10 Networks / cloud | Network hardware; local vs cloud |
| 1.11 Embedded / control | Specific function; real-time; sensors, actuators, feedback |
| 1.12 Processors | Latency vs throughput; P-core vs E-core |

# Section 1.14 — Case Studies

Case studies apply several sections at once. Attempt each in writing before reading the model answer.

> **Case study 1 — “Why is my laptop so slow?”**
>
> A student's laptop has 4 GB of RAM and a hard disk drive. With 20 browser tabs and a video call open, the machine freezes and the disk light stays on.
>
> **Task:** explain the cause and suggest two upgrades.

> **Model answer**
>
> RAM is full, so the OS uses **virtual memory**: pages are swapped between RAM and the swap file on the slow HDD. Constant swapping is **thrashing**; the CPU waits for the disk. Upgrade 1: add RAM, so fewer page faults occur. Upgrade 2: replace the HDD with an SSD (flash, no moving parts, far lower latency), so swapping is faster. Also relevant: the CPU cache cannot help because the working set is too large.

> **Case study 2 — a smart greenhouse controller**
>
> A school builds a greenhouse that keeps temperature between 18 °C and 26 °C and waters plants when soil moisture falls below a threshold.
>
> **Task:** identify the sensors, actuators and the type of system; state whether the real-time constraint is hard or soft.

> **Model answer**
>
> Sensors: temperature and soil-moisture. Actuators: heater, vent/fan motor, water valve. It is a **control system** (it acts as well as observes) built on an **embedded** microcontroller using a **feedback** loop; because it can also display and log readings it is a combined system. Deadlines are **soft** real-time: a few seconds' delay does not cause
>
> failure. An ADC converts the analogue sensor signals to digital.

> **Case study 3 — specifying a video-editing PC**
>
> A student wants a PC for 4K video editing with two monitors and room to upgrade later.
>
> **Task:** recommend a motherboard form factor, memory, storage and processing hardware, and justify each choice.

> **Model answer**
>
> **ATX** motherboard: enough expansion slots and RAM slots for upgrades. **32 GB+ DRAM**: large video files live in RAM while editing. **NVMe SSD** for the project (low latency) plus a large HDD or cloud storage for archive. A **GPU** with plenty of VRAM accelerates rendering and effects through parallel processing, and needs auxiliary power connectors, so the **PSU** must have enough wattage and the right PCIe power cables. A multi-core CPU with several **P-cores** for encoding. Good cooling because sustained load generates heat.

# Section 1.15 — Exam-Style Mixed Practice with Full Answers

| # | Marks | Question | Mark-scheme answer |
|---|---|---|---|
| 1 | 2 | Explain why hexadecimal is used for memory addresses. | Each hex digit = 4 bits; compact and less error-prone. |
| 2 | 4 | Describe the fetch stage of the FDE cycle. | PC→MAR via address bus; READ on control bus; memory→MDR via data bus; MDR→CIR; PC incremented. |
| 3 | 3 | Explain what happens when an interrupt is received. | Save state; service the highest-priority interrupt with its ISR; restore state and continue. |
| 4 | 2 | Explain why cache sits between the CPU and main memory. | Faster; holds frequently used data close to the CPU; reduces wait time. |
| 5 | 3 | Explain how virtual memory allows a larger program to run. | Pages moved to secondary storage and swapped back when needed. |
| 6 | 2 | State one advantage and one disadvantage of cloud storage. | Access from multiple devices; depends on network / security risk. |
| 7 | 3 | Describe three components of an embedded washing-machine system. | Microcontroller executes the program; sensor monitors water/temperature; actuator drives motor/valve. |
| 8 | 2 | Compare HDMI and VGA in signal type and audio support. | HDMI digital + audio; VGA analogue, no audio. |
| 9 | 4 | Compare CPU, GPU and TPU for an OS, graphics and neural-network training. | CPU (sequential OS), GPU (parallel graphics), TPU (matrix training); different latency/throughput balances. |
| 10 | 2 | State the difference between a P-core and an E-core. | P-core: high performance; E-core: lower power for background work. |

# Section 1.16 — End-of-Module Test

Total: 50 marks. Suggested time: 50 minutes. Attempt without notes, then mark yourself with the answers below.

## Questions

1. Convert 11010110<sub>2</sub> to denary and to hexadecimal. [2]

2. Convert 4B<sub>16</sub> to binary. [1]

3. A file is 3 MB. How many bytes is this (use 1024)? [2]

4. State the output of NAND when A = 1 and B = 1, and of XOR when A = 1 and B = 1. [2]

5. Complete the half-adder outputs for A = 1, B = 0. [2]

6. State what the MAR and MDR hold. [2]

7. A computer has a 20-bit address bus. How many locations can it address? [2]

8. Which bus is one-way, and in which direction? [2]

9. Six instructions run through a three-stage pipeline. How many cycles are needed? [2]

10. Calculate average access time: 95% cache hits at 2 ns, 5% misses at 100 ns. [2]

11. Give two differences between DRAM and SRAM. [2]

12. State which ROM type allows in-circuit electrical reprogramming. [1]

13. Distinguish a buffer from a cache. [2]

14. Describe thrashing. [2]

15. Name two input devices and their principle of operation. [4]

16. Explain the role of the rectifier in a PSU. [2]

17. Give two reasons a GPU needs auxiliary power connectors. [2]

18. Distinguish hard and soft real-time with an example of each. [4]

19. Explain why the Von Neumann bottleneck occurs and one way to reduce it. [3]

20. Explain the difference between latency and throughput. [2]

## Mark scheme

| # | Answer |
|---|---|
| 1 | 214; D6. |
| 2 | 0100 1011. |
| 3 | 3 × 1024 × 1024 = 3 145 728 bytes. |
| 4 | NAND = 0; XOR = 0. |
| 5 | Sum = 1; Carry = 0. |
| 6 | MAR: address being accessed; MDR: data/instruction transferred to or from memory. |
| 7 | 2<sup>20</sup> = 1 048 576. |
| 8 | Address bus, CPU to memory. |
| 9 | 3 + (6 − 1) = 8 cycles. |
| 10 | 0.95 × 2 + 0.05 × 100 = 1.9 + 5 = 6.9 ns. |
| 11 | DRAM needs refresh, slower, cheaper, main memory; SRAM no refresh, faster, dearer, cache. |
| 12 | EEPROM. |

| # | Answer |
|---|---|
| 13 | Buffer smooths speed mismatch during transfer; cache speeds repeated access to frequently used data. |
| 14 | Excessive swapping of pages between RAM and storage; performance collapses as time is spent swapping. |
| 15 | e.g. Keyboard: key press closes a circuit, generating a code. Barcode scanner: reflected light pattern converted to a code. |
| 16 | Diodes let current flow one way, converting AC to pulsating DC. |
| 17 | Draws more than the 75 W the PCIe slot supplies; extra current delivered from the PSU. |
| 18 | Hard: missing the deadline is failure, e.g. airbag. Soft: missing degrades quality, e.g. video streaming. |
| 19 | Instructions and data share one memory and bus so they cannot be fetched at the same instant; cache reduces the impact. |
| 20 | Latency: delay for one result; throughput: work completed per unit time. |

Scoring: 45–50 outstanding; 40–44 excellent; 32–39 good; 25–31 fair; below 25 revisit the sections above.

# Section 1.17 — Learning Material List

Suggested resources for further study. Titles are given so you can search for them; check that each is current before relying on it.

| Resource | Type | Use it for |
|---|---|---|
| Watson &amp; Williams, *Cambridge IGCSE and O Level* *Computer Science* (Hodder) | Textbook | Core reading for Sections 1.1–1.12 at IGCSE level |
| Watson &amp; Williams, *Cambridge International AS &amp; A* *Level Computer Science* (Hodder) | Textbook | Processor fundamentals, pipelining and system software at A Level |
| Cambridge syllabuses 0478 / 2210 / 9618 | Syllabus | Checking exactly what may be asked |
| Crash Course Computer Science (YouTube series) | Video | Short animated explanations of logic gates, the CPU, memory and instructions |
| Ben Eater, 8-bit computer series (YouTube) | Video | Seeing registers, buses and the FDE cycle built from simple parts |
| Nand2Tetris (nand2tetris.org) | Course | Building a computer from NAND gates upward |
| Khan Academy, Computer Science and Computing | Course | Binary, logic and how computers work, with practice questions |
| Computerphile (YouTube) | Video | Short talks on memory, caches and processors |

# Section 1.18 — Glossary

| Term | Definition |
|---|---|
| **Actuator** | Output device producing physical action. |
| **Address bus** | One-way bus carrying memory addresses. |
| **ALU** | Arithmetic Logic Unit; performs arithmetic and logic. |
| **ASIC** | Application-specific integrated circuit. |
| **Bit** | A single binary digit. |
| **Buffer** | Temporary storage during data transfer. |
| **Bus** | Set of parallel wires carrying signals. |
| **Cache** | Small fast memory holding frequently used data. |
| **Cloud storage** | Data stored on remote servers accessed over a network. |
| **Control bus** | Bus carrying timing and command signals. |
| **Control system** | System that observes and acts automatically. |
| **CPU** | Central Processing Unit. |
| **CU** | Control Unit. |
| **Data bus** | Two-way bus carrying data and instructions. |
| **Denary** | Base-10 number system. |
| **DRAM** | Dynamic RAM; needs refresh. |
| **EEPROM** | Electrically erasable programmable ROM. |
| **Embedded system** | Computer dedicated to a specific function. |
| **EPROM** | Erasable programmable ROM (UV light). |
| **Feedback** | Using a measured output to adjust action. |
| **Firmware** | Software stored permanently in hardware. |
| **Flash memory** | Non-volatile memory erased in blocks. |
| **FDE cycle** | Fetch–Decode–Execute cycle. |
| **GPU** | Graphics Processing Unit. |
| **HDMI** | Digital video and audio connection. |
| **Hexadecimal** | Base-16 number system. |
| **IAS** | Immediate Access Store: main memory (RAM). |
| **ISA** | Instruction set architecture: the instructions a CPU understands. |
| **Interrupt** | Signal causing the processor to suspend its current task. |
| **ISR** | Interrupt Service Routine. |
| **LAN** | Local Area Network. |
| **Latency** | Delay before data is available. |

| Term | Definition |
|---|---|
| **Logic gate** | Circuit implementing a logical operation. |
| **MAR** | Memory Address Register. |
| **MDR** | Memory Data Register. |
| **Monitoring system** | System that observes and reports. |
| **Motherboard** | Main circuit board connecting components. |
| **Nibble** | 4 bits. |
| **NIC** | Network Interface Card. |
| **Opcode** | Part of an instruction specifying the operation. |
| **Operand** | Data, or the address of data, used by an instruction. |
| **Packet** | Small unit of network data. |
| **Page** | Fixed-size block moved between RAM and storage. |
| **Pipelining** | Overlapping the stages of consecutive instructions. |
| **PC** | Program Counter. |
| **P-core / E-core** | Performance core / efficiency core. |
| **PROM** | Programmable ROM (usually once). |
| **RAM** | Volatile working memory. |
| **Register** | Fast storage inside the CPU. |
| **ROM** | Non-volatile memory for firmware. |
| **Router** | Connects different networks. |
| **SIMT** | Single Instruction, Multiple Threads. |
| **SRAM** | Static RAM; no refresh while powered. |
| **Status Register** | Holds condition flags. |
| **Swap file** | Storage area used for virtual memory. |
| **Switch** | Connects devices in a LAN. |
| **Systolic array** | Grid of processing elements for matrix operations. |
| **Thrashing** | Excessive swapping. |
| **Throughput** | Tasks completed per unit time. |
| **TPU** | Tensor Processing Unit. |
| **Transistor** | Tiny electronic switch. |
| **Virtual memory** | Using secondary storage as extra RAM. |
| **VGA** | Older analogue video connection. |
| **Volatile** | Loses contents when power is removed. |
| **WAN** | Wide Area Network. |

# Section 1.18 (continued) — Glossary Supplement

Key terms introduced in this edition, in alphabetical order.

| Term | Definition |
|---|---|
| **Accumulator (ACC)** | Register where arithmetic and logic results are formed. |
| **ADD** | Assembly instruction: add a number (ADD #n) or the contents of an address (ADD &lt;address&gt;) to ACC. |
| **Boolean algebra** | Rules for simplifying logic expressions (. = AND, + = OR, bar = NOT). |
| **CISC** | Complex Instruction Set Computer: many complex, variable-length instructions. |
| **De Morgan's laws** | NOT (A AND B) = NOT A OR NOT B; NOT (A OR B) = NOT A AND NOT B. |
| **Flip-flop** | Sequential circuit that stores one bit (SR or JK). |
| **Full adder** | Circuit adding three bits (A, B, carry-in) to give Sum and carry-out. |
| **Index register (IX)** | Register holding an offset added to an address in indexed addressing. |
| **Karnaugh map** | Grid form of a truth table used to simplify logic expressions by grouping 1s. |
| **LDD** | Assembly instruction: load the contents of a given address into ACC (direct addressing). |
| **LDI** | Load using indirect addressing: the given address holds the address of the data. |
| **LDM** | Load a number into ACC (immediate addressing). |
| **LDR (instruction)** | Load a number into the index register IX (immediate addressing). |
| **LDR (sensor)** | Light-dependent resistor: resistance falls as light intensity rises. |
| **LDX** | Load using indexed addressing: address = operand + IX. |
| **Logical shift** | Moving all bits left (LSL) or right (LSR); zeros enter at the other end. |
| **Mask** | Bit pattern used with AND, OR or XOR to clear, set or toggle chosen bits. |
| **Massively parallel** **computer** | Very many processors with their own memory working on parts of one problem. |
| **MIMD / SIMD / MISD /** **SISD** | Flynn's classes of architecture by number of instruction and data streams. |
| **RISC** | Reduced Instruction Set Computer: few simple, fixed-length, one-cycle instructions. |
| **Symbol table** | Assembler table linking each label to its address. |
| **Two-pass assembler** | Assembler that reads source twice: pass 1 builds the symbol table, pass 2 translates. |

## Section 1.19 — References and attribution

1. Watson, D. and Williams, H. *Cambridge IGCSE and O Level Computer Science*. Hodder Education. Chapters on binary systems, logic gates, computer architecture, input/output devices, and memory and data storage.

2. Watson, D. and Williams, H. *Cambridge International AS &amp; A Level Computer Science*. Hodder Education. Chapters on hardware, processor fundamentals and system software.

3. Cambridge IGCSE Computer Science 0478 / O Level Computer Science 2210 syllabus.

4. Cambridge International AS &amp; A Level Computer Science 9618 syllabus.

Revision notes (v3.0): corrected the definition of the IAS (main memory, not registers and cache); added pipelining, instruction format and addressing modes; made figure numbering sequential; replaced unrendered LaTeX with plain notation; replaced the Activity 1.12 option set so every answer is available; fixed table widths; removed a dangling reference to a conversion helper; added learning suggestions, mind map, case

studies, end-of-module test and learning material list. All conversion calculations, truth tables and latency figures were recomputed.


---

<!-- ===================== Module 2 — Networks ===================== -->

MODULE 2

# Networks

A beginner-first study guide — Version 2.0 (revised)

Part of: Hardware, Networks and Behaviourist AI Aligned with Cambridge IGCSE / O Level / AS &amp; A Level Computer Science networking content

# Contents

- Module overview and learning outcomes
- How to study this module
- 1\. What a network is
- 2\. Components of a network
- 3\. Packets and packet switching
- 4\. Protocols, layers and addressing
- 5\. Network topologies
- 6\. Data flow and transmission
- 7\. Network architecture
- 8\. Network threats and security
- 9\. Worked examples
- 10\. Structured learner activities
- 11\. Mind map and summary
- 12\. Case studies
- 13\. Review questions with answers
- 14\. End-of-module test
- 15\. Learning material list
- 16\. Glossary
- 17\. References

# What's New in This Edition — Module 2: Networks

This edition adds topics from the Cambridge IGCSE 0478 and AS &amp; A Level 9618 networking and data-transmission content that the first version did not cover.

| New section | Where it is | What it adds |
|---|---|---|
| 3.4–3.5 Circuit switching | After Section 3 | How circuit switching works; full comparison with packet switching |
| 4.6 Types of IP address | After Section 4 | Public vs private, NAT, static vs dynamic, DHCP (DORA), subnet masks |
| 6.5 Error detection | After Section 6 | Parity check, parity block, checksum, echo check, ARQ, check digits |
| Glossary supplement | After Section 16 | New key terms |

> **How to find the new material**
>
> New sections keep the module's numbering and are inserted straight after the section they extend, so cross- references in the original text still work. Every new heading carries a green `NEW` label, and new figures are numbered with a letter (for example Figure 8A follows Figure 8). New key terms are collected in a glossary supplement placed straight after the module glossary.

# Module overview and learning outcomes

Almost everything you do on a computer or phone involves a network. This module explains what networks are made of, how data is cut into packets and delivered, the rules (protocols) and addresses that make delivery possible, how devices can be arranged, how data flows over a link, how networks are classified, and how they are attacked and defended.

> **By the end of this module you should be able to:**
>
> 1. Define a computer network and identify its key components (nodes, links, routers, switches).
>
> 2. Explain how packets carry data, including the roles of the header, payload and trailer.
>
> 3. Distinguish between TCP and IP, and explain why both are needed.
>
> 4. Explain MAC addresses and IP addresses, and state the difference between them.
>
> 5. Describe the structure of a URL and how DNS translates domain names into IP addresses.
>
> 6. Compare common network topologies (bus, point-to-point, star, mesh, ring, hybrid, tree) and choose an appropriate topology for a scenario.
>
> 7. Explain simplex, half-duplex and full-duplex data flow.
>
> 8. Compare serial and parallel transmission, and synchronous and asynchronous transmission and communication.
>
> 9. Compare LAN, WAN and MAN, and compare client–server and peer-to-peer models.
>
> 10. Identify common malware and cyberattacks, and match them to appropriate countermeasures.

## How to study this module

1. Read the learning objectives, then the explanation, studying each diagram.

2. Cover the answer in each **Quick review** and write your own first.

3. Do every worked example with pencil and paper.

4. Finish with the activities, case studies and the end-of-module test.

> **Suggested study plan (about 4 weeks)**
>
> | Week | Sections | Focus |
> |---|---|---|
> | 1 | 1–3 | Network basics, components, packets |
> | 2 | 4–5 | Protocols, addressing, topologies |
> | 3 | 6–7 | Data flow, transmission, LAN/WAN/MAN, client–server vs P2P |
> | 4 | 8–14 | Security, activities, case studies, test |
>
> **Learning suggestions:** (1) Draw each topology from memory and list one advantage and one disadvantage. (2) Use an analogy for every protocol (post office, phone book, language). (3) Use a real tool: on your own computer, run `ping` and `tracert` / `traceroute` to see packets cross routers. (4) Teach the packet-switching puzzle analogy to a friend. (5) Revisit the threat–countermeasure table until you can reproduce it.

# 1. What a Network Is

A network is like a group of friends sharing ideas. A **computer network** is two or more devices, such as phones, laptops or printers, connected so they can share information and resources. Devices talk over physical cables or wireless signals such as Wi-Fi. Networks can be small, like the one in your home, or huge, connecting devices across countries. Every time you send a message, share a photo or browse the web you are using a network. Networks save time and resources by letting devices share one internet connection, a printer or files.

A more formal definition: a computer network is a collection of computing devices connected by communication links that allow the exchange of data and the sharing of resources. A network is defined by three things:

1. The **hardware** that forms its nodes: computers, routers, switches and access points.

2. The **physical or wireless media** that carry signals: cables or radio.

3. The **protocols** that govern how data is formatted, addressed, transmitted and received.

> **Quick review 1 — What is a computer network and what are its key components?**
>
> A computer network is two or more devices connected so they can share information and resources. Key components: **nodes** (devices), **links** (wired or wireless pathways), **routers** (connect different networks and forward data between them) and **switches** (direct data to the intended device within a LAN).

# 2. Components of a Network

![Figure 1 — Components of a small network. Links join nodes to a switch; the router connects the LAN to other networks.](modules/networks/figures/fig001-components-of-a-small-network-links-join-nodes-t.png)

*Figure 1 — Components of a small network. Links join nodes to a switch; the router connects the LAN to other networks.*

## 2.1 Nodes (devices)

A **node** is any device connected to a network that can send, receive or process data (laptops, phones, printers, servers). *Example:* in a home Wi-Fi setup the phone, laptop and printer are all nodes.

## 2.2 Links (connections)

Links connect devices so they can communicate. **Wired links** use physical cables such as Ethernet (copper) or fibre-

optic cable. **Wireless links** use radio signals such as Wi-Fi or Bluetooth. Without links, devices would be isolated. *Example:* a laptop plugged into a router by Ethernet uses a wired link; a phone on the same router over Wi-Fi uses a wireless link.

## 2.3 Routers

A **router** connects different networks and forwards data between them. It examines the destination **IP address** in each

packet to decide where to send it next and selects an appropriate path. *Example:* when you open a website your home router forwards your request toward the internet and delivers the reply back to your device.

## 2.4 Switches

A **switch** connects multiple devices within a local area network (LAN). It learns which **MAC address** is on which port and sends data only to the intended device, instead of to every device as an older hub does. *Example:* in a school

computer lab a document sent to a network printer on the same switch is forwarded directly to the printer.

| Device | Works with | Connects | Sends data to |
|---|---|---|---|
| Hub (older) | Nothing: repeats signals | Devices in one LAN | Every port |
| Switch | MAC addresses | Devices in one LAN | Only the intended port |
| Router | IP addresses | Different networks | The next hop toward the destination |
| Wireless access point | Radio signals | Wireless devices to a wired network | Wireless clients |

> **Quick review 2 — Router or switch?**
>
> (a) A device sending your request from your home to the internet is a **router**. (b) A device that sends a file only to one printer in the same lab is a **switch**. The difference: a switch uses MAC addresses inside one LAN; a router uses IP addresses between networks.

# 3. Packets and Packet Switching

## 3.1 What is a packet?

A **packet** is a small part of a larger piece of data sent over a network. Each packet has a **header**, a **payload** and a **trailer**.

![Figure 2 — The three parts of a packet.](modules/networks/figures/fig002-the-three-parts-of-a-packet.png)

*Figure 2 — The three parts of a packet.*

- **Header:** stores where the packet must go and who sent it, plus a sequence number that helps the receiver reassemble the data.

- **Payload:** the actual data being carried.

- **Trailer:** marks the end of the packet and holds error-detection bits so the receiver can check that it arrived intact.

> **A note on real protocols**
>
> The header/payload/trailer model is the standard teaching model. In real protocols the layout varies: an IPv4 packet has a header but no trailer (its error check, the checksum, is inside the header), while an Ethernet frame has a header and a trailer (the frame check sequence). The model is still correct as a general description of how data is wrapped for transmission.

## 3.2 Packet switching

When a photo, video or message is sent, the data is divided into packets. They travel through routers until they reach the destination, where the receiving device puts them back together, like building a puzzle whose pieces were posted separately. Because many devices can send packets at the same time over shared links, the network is used efficiently: one connection does not hog the whole network. This method is called **packet switching**.

packets 1, 3, 5

> R1
>
> R3
>
> A
>
> B

> receiver
>
> R2
>
> R4

sender

![Figure 3 — Packets can take different routes. If a router or link fails, packets are rerouted around the problem.](modules/networks/figures/fig003-packets-can-take-different-routes-if-a-router-or.png)

*Figure 3 — Packets can take different routes. If a router or link fails, packets are rerouted around the problem.*

## 3.3 Worked example — sending a photo

**Scenario:** you send a 3 MB photo to a friend.

| Step | What happens |
|---|---|
| 1 | The photo is divided into small chunks. Each chunk becomes the payload of a packet. |
| 2 | A header is added to each packet: destination, source and a sequence number (1, 2, 3, ...) so the packets can be put back in order. |
| 3 | A trailer is added to mark the end and help check for errors. |
| 4 | The packets are sent. Routers forward each packet along a suitable path; packets may take different routes. |
| 5 | The packets arrive, possibly out of order. The receiver reads the sequence numbers and reassembles the payloads in order. |
| 6 | The photo is displayed. If a packet is missing or damaged, the receiver asks for it to be sent again. |

**Why this works:** if the network sent the whole photo as one piece, a single problem could stop everything. With packets, only a small piece is affected and the rest still arrive.

> **Quick review 3 — What are the three parts of a packet and what does each do?**
>
> **Header:** source address, destination address and sequence number. **Payload:** the data being carried. **Trailer:** end marker and error-detection bits.

# 3. Packets and Packet Switching (continued)

## 3.4 Circuit switching `NEW`

Packet switching is not the only way to send data. In **circuit switching** a complete, dedicated path (a *circuit*) is set up between sender and receiver **before** any data is sent. The whole bandwidth of that path is reserved for the two devices until the communication ends, even during silences. The traditional landline telephone network (PSTN) works this way.

1. **Set up:** a route through the switches is established and reserved.

2. **Transfer:** all data travels along the same path, in order, with no reassembly needed.

3. **Tear down:** the circuit is released so others can use it.

![Figure 3A — One path is reserved end to end for the whole call. Compare Figure 3, where packets take different routes.](modules/networks/figures/fig3a-one-path-is-reserved-end-to-end-for-the-whole-ca.png)

*Figure 3A — One path is reserved end to end for the whole call. Compare Figure 3, where packets take different routes.*

## 3.5 Circuit switching vs packet switching `NEW`

| Feature | Circuit switching | Packet switching |
|---|---|---|
| Path | One dedicated path set up before sending | No set path; each packet routed separately |
| Bandwidth | Reserved for the whole connection, even when idle | Shared; used only when packets are sent |
| Order of arrival | Always in order | May arrive out of order; reassembled using sequence numbers |
| Delay | Set-up delay at the start, then constant and predictable | No set-up, but delay can vary with congestion |
| If a link fails | The connection is lost and must be set up again | Packets are rerouted around the fault |
| Efficiency | Wasteful for bursty data such as web pages | Efficient use of links |
| Security | Harder to intercept: single private path | Packets cross many routers, so encryption is needed |
| Typical use | Traditional landline calls, some dedicated leased lines | The internet, email, web, video streaming, VoIP |

> **Worked example — choosing a method**
>
> **A live phone call over a landline:** circuit switching suits it because speech must arrive in order with a constant, small delay, and the line is in use for the whole call. **Loading a web page:** data comes in short bursts with long

> gaps while you read, so reserving a circuit would waste bandwidth; packet switching shares the links among many users. (Internet calls, VoIP, use packet switching and smooth out the variable delay with a buffer.)

> **Quick review — circuit or packet?**
>
> Circuit switching sets up and reserves one path before sending; data arrives in order with constant delay, but bandwidth is wasted when idle. Packet switching splits data into packets that share links and take any route; it is efficient and resilient but packets may arrive out of order and delays vary.

> **Exam-style practice**
>
> **Question (4 marks).** Explain two advantages of packet switching over circuit switching for sending an email.
>
> **Checked answer.** No dedicated path has to be set up / bandwidth is not reserved **(1)**, so links are shared and used efficiently **(1)**; if a link fails packets are rerouted **(1)**, so the email still arrives **(1)**.

# 4. Protocols, Layers and Addressing

## 4.1 Protocols

**Protocols** are the rules and standards that devices follow to communicate over a network. They define how data is formatted, transmitted, received and understood. Because devices use different hardware and software, they need common rules: protocols work like a shared language.

| Protocol | Purpose |
|---|---|
| TCP (Transmission Control Protocol) | Reliable, ordered delivery of data between two programs. |
| UDP (User Datagram Protocol) | Fast, connectionless delivery with no guarantee; used for live video, voice and games. |
| IP (Internet Protocol) | Addressing and routing of packets across networks. |
| HTTP / HTTPS | Transfer web pages between browsers and servers; HTTPS adds encryption. |
| FTP | Transfer files between computers. |
| SMTP, POP3, IMAP | Send (SMTP) and receive (POP3, IMAP) email. |
| DHCP | Automatically gives a device an IP address when it joins a network. |
| DNS | Translates domain names into IP addresses. |
| Ethernet / Wi-Fi | Deliver frames between devices on a local network. |

## 4.2 TCP and IP: why both?

> **The difference**
>
> **IP** is *connectionless*: it addresses each packet and routers send it toward its destination, like a postal address on a letter. It does not guarantee delivery or order, so packets can be lost, duplicated or arrive in a different order. **TCP** is *connection-oriented*: it sets up a connection before sending data, numbers the data, detects missing or out-of-
>
> order packets, asks for retransmission and puts the data back in order. TCP is layered on top of IP to provide the reliability IP lacks. IP does not cause the jumbling; it simply does not prevent it.

## 4.3 The layered model

Network software is organised in layers, each doing one job and using the layer below. When you send data, each layer adds its own header (the model in Section 3); the receiver removes them in reverse order.

![Figure 4 — The TCP/IP model. A switch works mainly at the link layer; a router at the internet layer.](modules/networks/figures/fig004-the-tcp-ip-model-a-switch-works-mainly-at-the-li.png)

*Figure 4 — The TCP/IP model. A switch works mainly at the link layer; a router at the internet layer.*

> **Quick review 4 — Why do we need both TCP and IP?**
>
> IP gets packets across networks using addresses but makes no promises. TCP adds reliable, ordered delivery on top. Without IP packets would not find their destination; without TCP the data might arrive incomplete or jumbled.

## 4.4 Identification of devices

### MAC address (Media Access Control)

A **MAC address** is a 48-bit physical identifier assigned by the manufacturer to a Network Interface Card (NIC) and normally fixed for the life of the card (it can be overridden in software). It is usually written as six hexadecimal pairs,

for example `00:1A:2B:3C:4D:5E` . It identifies a specific hardware interface so devices on the *same local network* can send data directly to each other.

### IP address (Internet Protocol address)

An **IP address** is a logical address given to a device when it joins a network; it can change when the device joins a different network. It lets data be routed across many interconnected networks.

| Version | Length | Written as |  | Example | Notes |
|---|---|---|---|---|---|
| IPv4 | 32 bits | Four denary numbers 0–255 separated by dots (dotted decimal) |  | `93.184.216.34` About 4.3 billion addresses: | running out |
| IPv6 | 128 bits | Eight groups of four hexadecimal digits |  | `2001:0db8:85a3:0000:0000:8` Vastly larger address space; `a2e:0370:7334` replacing IPv4 gradually |  |
|  |  |  | **MAC address** |  | **IP address** |
| Assigned by |  |  | Manufacturer (hardware) |  | Network / software (e.g. DHCP) |
| Size |  |  | 48 bits |  | 32 bits (IPv4) or 128 bits (IPv6) |
| Permanence |  |  | Normally fixed to the NIC |  | Can change with the network |
| Used by |  |  | Switches, within one LAN |  | Routers, between networks |
| Analogy |  |  | Your name |  | Your current postal address |

> **Quick review 5 — MAC vs IP address**
>
> A MAC address is a 48-bit hardware identifier set by the manufacturer and used within a LAN. An IP address is a logical address given to a device by the network and used for routing between networks; it can change when the device moves.

### 4.5 URL and DNS

A **URL (Uniform Resource Locator)** is the address of a resource on the internet. It is divided into: **protocol** (how data is

transferred, e.g. HTTP or HTTPS), **subdomain** (an area of a site, `www` being the most common), **domain name** (the human-readable name of the site), **top-level domain** (purpose or country, e.g. .com, .org, .edu, .uk) and optionally a **path** to a page.

![Figure 5 — Anatomy of the URL https://www.bbc.co.uk/news.](modules/networks/figures/fig005-anatomy-of-the-url-https-www-bbc-co-uk-news.png)

*Figure 5 — Anatomy of the URL https://www.bbc.co.uk/news.*

| Part | Value | Explanation |
|---|---|---|
| Protocol | https | Secure web protocol |
| Subdomain | www | World Wide Web |
| Domain name | bbc | The organisation |
| Second-level domain | co | Commercial organisation (UK convention) |
| Top-level domain (country code) | uk | United Kingdom |
| Path | /news | The page on the site |

Computers route by IP address, not by name, so the **Domain Name System (DNS)** acts as a phone book: your device asks a DNS server for the IP address of the domain, then connects to that address.

> **How DNS works, step by step**
>
> 1. You type `www.example.com` . 2. Your device checks its own cache; if it has no answer it asks the DNS resolver (usually run by your ISP). 3. The resolver asks other DNS servers until it finds the address. 4. The resolver returns the IP address, e.g. `93.184.216.34` . 5. Your browser opens a connection to that IP address and requests the page.

> **Quick review 6 — How does DNS work?**
>
> DNS translates human-readable domain names into IP addresses. When you type a domain name, a DNS server looks up the matching IP address so your device can contact the right web server.

# 4. Protocols, Layers and Addressing (continued)

## 4.6 Types of IP address `NEW`

Section 4.4 explained what an IP address is. IP addresses are also described in two independent ways: **public or** **private** (where the address can be used) and **static or dynamic** (whether it changes).

### Public and private IP addresses

A **public IP address** is unique across the whole internet and is assigned by your Internet Service Provider (ISP). A **private IP address** is used only inside a LAN; the same private addresses are reused in millions of homes and schools, so they cannot be reached directly from the internet. Three IPv4 ranges are reserved for private use:

| Private range | Example | Typical use |
|---|---|---|
| 10.0.0.0 – 10.255.255.255 | 10.4.12.7 | Large organisations |
| 172.16.0.0 – 172.31.255.255 | 172.20.1.5 | Medium networks |
| 192.168.0.0 – 192.168.255.255 | 192.168.1.37 | Home and small-office routers |

Your home router has **two** addresses: a public one facing the internet and a private one (often 192.168.1.1) facing your devices. **Network Address Translation (NAT)** in the router swaps the private address in each outgoing packet for the router's public address, and keeps a table so replies are sent back to the right device. NAT lets many devices share one public IPv4 address, which slows down the running-out of IPv4 addresses, and hides internal devices from the internet.

![Figure 5A — NAT: three private addresses share the router's single public address.](modules/networks/figures/fig5a-nat-three-private-addresses-share-the-router-s-s.png)

*Figure 5A — NAT: three private addresses share the router's single public address.*

### Static and dynamic IP addresses

|  | Static IP address | Dynamic IP address |
|---|---|---|
| Meaning | Set manually and does not change | Given automatically each time a device connects; may change |
| Assigned by | A network administrator or the ISP (often for a fee) | A DHCP server (in your router, or at the ISP) |
| Advantages | Always found at the same address; reliable for servers, printers, remote access | No manual setup; addresses reused, so fewer needed; harder to target |
| Disadvantages | Must be configured by hand; a fixed target for attackers; may cost more | Address can change, so not suited to hosting a website or server |
| Typical use | Web and email servers, network printers, CCTV | Laptops, phones, home internet connections |

**DHCP (Dynamic Host Configuration Protocol)** hands out dynamic addresses in four messages, remembered as **DORA**: the new device broadcasts a **Discover**; the DHCP server sends an **Offer**; the device sends a **Request** for that address; the server sends an **Acknowledge** and *leases* the address for a set time.

### Network part and host part: subnet masks

An IPv4 address has two parts: the **network ID** (which network) and the **host ID** (which device on that network). A **subnet mask** shows where the split is: the 1 bits mark the network part. 255.255.255.0, written **/24**, means the first 24 bits (three numbers) are the network ID. **Subnetting** divides one large network into smaller sub-networks, for example one per department, to reduce traffic and improve security.

> **Worked example — 192.168.1.37 /24**
>
> Subnet mask 255.255.255.0. Network ID = 192.168.1.0; host ID = 37. The last 8 bits are for hosts: 2<sup>8</sup> = 256 combinations, minus 2 (the all-0s network address and the all-1s broadcast address 192.168.1.255) = **254** **usable host addresses**. A device at 192.168.2.10 is on a different network, so packets to it must go through the router.

> **Quick review — four kinds of address**
>
> Public: unique on the internet, from the ISP. Private: used only inside a LAN (10.x, 172.16–31.x, 192.168.x), reused everywhere, translated by NAT. Static: fixed, set by hand, for servers. Dynamic: leased by DHCP, may change, for ordinary devices.

> **Exam-style practice**
>
> **Question (3 marks).** A school web server is given a static public IP address. Explain why.
>
> **Checked answer.** Public so it can be reached from anywhere on the internet **(1)**; static so its address never changes **(1)**, so DNS records pointing to it stay correct and users can always find it **(1)**.

# 5. Network Topologies

**Network topology** is the physical or logical arrangement of nodes and links in a network. The choice affects performance, scalability, reliability and cost. *Physical* topology is how cables are laid out; *logical* topology is how data actually flows.

![Figure 6 — Six basic topologies (a hybrid is a combination of these).](modules/networks/figures/fig006-six-basic-topologies-a-hybrid-is-a-combination-o.png)

*Figure 6 — Six basic topologies (a hybrid is a combination of these).*

## 5.1 Bus topology

All devices share a single backbone cable. Collisions are managed by protocols such as **CSMA/CD** (Carrier Sense Multiple Access with Collision Detection): a device listens first, and if two devices transmit together they detect the collision, stop, and retry after a random delay.

> **Advantages**
>
> - Cheapest: least cabling
>
> - Simple to set up and extend for small networks
>
> - No central hub or switch needed

> **Disadvantages**
>
> - Backbone break takes the whole network down
>
> - Performance falls as devices are added (collisions)
>
> - Hard to locate faults
>
> - Low security: every device can see all traffic

## 5.2 Point-to-point topology

A dedicated link connects exactly two devices, with no intermediate switches.

> **Advantages**
>
> - Simple to set up and manage
>
> - All the link's capacity is reserved for the two devices
>
> - Low latency; private channel, harder to intercept

> **Disadvantages**
>
> - Poor scalability: each extra device needs its own link
>
> - Single point of failure
>
> - Cost grows quickly when many sites must be linked

## 5.3 Star topology

Every device connects independently to a central hub, switch or router. This is the most common wired LAN layout today.

> **Advantages**
>
> - A failed cable affects only one device
>
> - Easy to add or remove devices
>
> - Easy troubleshooting and central management
>
> - A switch sends data only to the intended device

> **Disadvantages**
>
> - The central device is a single point of failure
>
> - More cable than a bus
>
> - The central device can become a bottleneck

## 5.4 Mesh topology

Each device connects directly to several others. In a **full mesh** of *N* nodes there are N(N−1)/2 links; a **partial mesh** connects only some pairs.

> **Advantages**
>
> - Very fault tolerant: traffic reroutes around a failure
>
> - No single point of failure
>
> - High capacity; hard to intercept

> **Disadvantages**
>
> - Expensive: many cables and ports (10 nodes need 45 links)
>
> - Complex to set up and maintain
>
> - High power use

## 5.5 Ring topology

Each device connects to exactly two others, forming a closed loop. Data travels one way round, often controlled by a **token** that gives the holder permission to transmit.

> **Advantages**
>
> - No collisions with token passing
>
> - Every device gets a fair turn
>
> - Predictable performance; less cable than a star

> **Disadvantages**
>
> - A single break or failed node can stop the ring (unless it is dual-ring)
>
> - Harder troubleshooting
>
> - Higher latency as data passes through every node
>
> - Adding a device can disrupt the network

## 5.6 Hybrid topology

Combines two or more basic topologies, such as stars joined in a ring or a mesh. Most large real networks are hybrids.

> **Advantages**
>
> - Flexible and customisable
>
> - Faults contained to one segment
>
> - Redundancy where it matters most
>
> - Scales by adding segments

> **Disadvantages**
>
> - Expensive hardware
>
> - Complex design and setup
>
> - Hard to diagnose across different layouts

![Figure 7 — A hybrid topology.](modules/networks/figures/fig007-a-hybrid-topology.png)

*Figure 7 — A hybrid topology.*

## 5.7 Tree topology

A hierarchy of root, branch and leaf nodes combining star and bus ideas, like a company or school structure.

> **Advantages**
>
> - Scales by adding branches
>
> - Faults in one branch stay local
>
> - Structured and easy to manage in groups

> **Disadvantages**
>
> - Root or top-level failure affects large parts
>
> - Expensive backbone cabling
>
> - Higher levels can become bottlenecks

## 5.8 Topology comparison table

| Topology | Cost | Reliability | Scalability | Key weakness |
|---|---|---|---|---|
| Bus | Low | Low | Low | Backbone failure; collisions |
| Point-to-point | Low (2 devices) | Low | Low | Only two devices |
| Star | Medium | High (per device) | High | Central device |
| Ring | Medium | Medium | Medium | One break can stop the ring |
| Mesh | High | Very high | Medium (links grow fast) | Cost and complexity |
| Tree | Medium | Medium | High | Root failure |
| Hybrid | High | Very high | Very high | Complexity |

## 5.9 Choosing a topology

> **Worked example**
>
> **Scenario:** a school builds a new computer lab with 30 computers.
>
> **Recommended:** star topology. Each computer connects to a central switch, so one failed cable or computer affects only that device, and computers are easy to add or remove.
>
> For a small business with 10 staff and a limited budget the same reasoning applies: a star costs a little more cable than a bus but is reliable and easy to extend.

> **Quick review 7 — What is network topology and what are the common types?**
>
> The physical or logical arrangement of nodes and links. Common types: bus, point-to-point, star, mesh, ring, hybrid and tree, each trading off cost, complexity, fault tolerance and scalability.

# 6. Data Flow and Transmission

## 6.1 Types of data flow

### Simplex

![Diagram](modules/networks/figures/diagram-p021-2.png)

Data travels in one direction only. *Examples:* traditional TV broadcast; a keyboard sending input to a computer.

### Full-duplex

![Diagram](modules/networks/figures/diagram-p021-4.png)

Both directions at the same time. *Examples:* a telephone conversation; a video call; a switched Ethernet link.

### Half-duplex

![Diagram](modules/networks/figures/diagram-p021-3.png)

Both directions, but not at the same time; the devices take turns. *Example:* walkie-talkies.

## 6.2 Methods of data transmission

![Figure 8 — Serial and parallel transmission.](modules/networks/figures/fig008-serial-and-parallel-transmission.png)

*Figure 8 — Serial and parallel transmission.*

**Serial transmission** sends data one bit at a time along a single channel. It is slower per channel but works well over longer distances and needs less cabling. *Examples:* USB, SATA, Ethernet and most modern cables. **Parallel transmission** sends many bits at the same time along multiple channels. It is faster over short distances and matches how computers work inside. An old printer port used a 25-pin connector: 8 data lines, 4 control lines, 5 status lines and 8

grounds.

**Why parallel is not used for long distances: skew** (bits arriving at slightly different times because wires differ in length) and **crosstalk** (interference between adjacent wires) make it unreliable. This is why modern fast links are serial.

## 6.3 Synchronous and asynchronous: two related meanings

The words *synchronous* and *asynchronous* are used at two levels. Do not mix them up.

### (a) At the transmission level: how sender and receiver agree on timing

|  | Synchronous transmission | Asynchronous transmission |
|---|---|---|
| Timing | Sender and receiver share a **clock signal** (or the clock is recovered from the data) | No shared clock |
| How data is sent | A continuous stream in **blocks / frames**, with synchronisation characters at the start of each block | One **byte at a time**, each framed by a **start bit** and a **stop bit** |
| Gaps | None within a block | Random gaps between bytes are allowed |
| Overhead | Low | Higher (2 extra bits per byte) |
| Speed | Fast | Slower |
| Typical use | High-speed links, large transfers | Keyboards, serial ports, simple devices |

![Figure 9 — An asynchronous frame carrying one byte.](modules/networks/figures/fig009-an-asynchronous-frame-carrying-one-byte.png)

*Figure 9 — An asynchronous frame carrying one byte.*

### (b) At the communication / processing level: whether the caller waits

In **synchronous communication** (blocking), a client sends a request to a server and waits for the response before continuing; both sides must be active at the same time, like a phone call. In **asynchronous communication** (non- blocking), the client sends the request and carries on with other work; the reply is dealt with when it arrives, like sending a text message that the other person answers whenever they are ready. Asynchronous designs scale better

because more work can be done in the same time.

> **Quick review 8 — Synchronous or asynchronous?**
>
> (a) Sending a byte with start and stop bits: asynchronous transmission. (b) Two devices sharing a clock and sending a block of data: synchronous transmission. (c) Placing an online order and carrying on browsing while it is processed: asynchronous communication. (d) A phone call where both people must be on the line: synchronous communication.

## 6.4 Bandwidth and latency

**Bandwidth** is the maximum amount of data a link can carry per second (e.g. 100 Mbit/s). **Latency** is the delay for data to travel from sender to receiver (e.g. 20 ms). A link can have high bandwidth but high latency, like a wide road that is very long. Video streaming needs bandwidth; online gaming needs low latency.

> **Worked example — download time**
>
> A 600 MB file is downloaded over a 100 Mbit/s link. 600 MB = 600 × 8 = 4800 Mbit. Time = 4800 / 100 = 48 seconds (ignoring overheads and latency).

> **Quick review 9 — Serial vs parallel; the three types of flow**
>
> **Serial** sends one bit at a time on a single channel, suiting longer distances with less cabling; **parallel** sends many bits at once on multiple channels, faster over short distances only. Flow types: **simplex** (one way), **half-duplex** (both ways, alternating), **full-duplex** (both ways at once).

# 6. Data Flow and Transmission (continued)

## 6.5 Error detection `NEW`

Interference (electrical noise), loss of signal and collisions can change bits while data is being transmitted: a 1 arrives as a 0, data goes missing, or extra bits appear. The trailer in a packet (Section 3.1) holds error-check data. These are the main methods, as listed in the Cambridge IGCSE syllabus.

### Parity check

Before sending, the sender and receiver agree on **even** or **odd** parity. One bit of each byte (usually the most significant bit) is the **parity bit**, set so that the total number of 1s is even (even parity) or odd (odd parity). The receiver counts the 1s; if the count is wrong, an error has occurred.

> **Worked example — adding a parity bit**
>
> Data bits 1011001 contain 4 ones. **Even parity:** parity bit = 0, byte sent = **01011001** (still 4 ones, even). **Odd** **parity:** parity bit = 1, byte sent = **11011001** (5 ones, odd).
>
> **Limitation:** if *two* bits are flipped, the number of 1s stays even (or odd), so the error is not detected. Parity also cannot show *which* bit is wrong.

### Parity block (parity byte)

Several bytes are sent as a block. Each byte has its own parity bit, and an extra **parity byte** is added at the end, holding a parity bit for each *column*. If one bit is corrupted, the failing row and the failing column cross at the wrong bit, so it can be found and **corrected**.

> **Worked example — finding and correcting one bad bit (even parity)**
>
> Four bytes were sent with even parity on every row and every column. One bit was corrupted on the way. Bit 1 of each byte is the parity bit.
>
> |  | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | Row check |
> |---|---|---|---|---|---|---|---|---|---|
> | Byte 1 | 0 | 1 | 1 | 0 | 1 | 0 | 0 | 1 | ✔ even |
> | Byte 2 | 1 | 0 | 1 | 1 | 0 | 1 | 0 | 0 | ✔ even |
> | Byte 3 | 0 | 0 | 1 | 1 | **0** | 1 | 0 | 0 | **✘ odd** |
> | Byte 4 | 1 | 1 | 0 | 0 | 0 | 0 | 1 | 1 | ✔ even |
> | Parity byte | 0 | 0 | 1 | 0 | 0 | 0 | 1 | 0 |  |
> | Column check | ✔ | ✔ | ✔ | ✔ | **✘** | ✔ | ✔ | ✔ |  |
>
> Byte 3 has an odd number of 1s and column 5 fails, so the error is the bit at byte 3, column 5. The receiver flips it back from 0 to 1 and the data is corrected without resending.

### Checksum

The sender calculates a value from the whole block of data using an agreed algorithm and sends it with the data. The receiver repeats the calculation; if its result differs from the checksum received, there is an error and the data is requested again.

> **Worked example — a simple checksum**
>
> Algorithm: add the bytes, keep the remainder after dividing by 256. Bytes: 151, 72, 203, 30. Sum = 456; 456 MOD 256 = **200**, sent as the checksum. If the receiver's total MOD 256 is not 200, an error has occurred. (Real checksums use more robust algorithms, but the idea is the same.)

### Echo check

The receiver sends the data straight back to the sender, which compares it with the original. If they differ, the data is sent again. Weakness: the sender cannot tell whether the error happened on the way there or on the way back, and the amount of data sent is doubled.

### Automatic Repeat reQuest (ARQ)

After receiving data, the receiver checks it (for example with a parity check or checksum) and sends a **positive** **acknowledgement (ACK)** if it is correct, or a **negative acknowledgement** if not. The sender starts a **timer (timeout)** each time it sends. If no ACK arrives before the timeout, or a negative acknowledgement arrives, it resends the data automatically. TCP (Section 4.2) uses acknowledgements and timeouts in this way.

![Figure 9A — No ACK arrives for packet 2 before the timeout, so the sender resends it.](modules/networks/figures/fig9a-no-ack-arrives-for-packet-2-before-the-timeout-s.png)

*Figure 9A — No ACK arrives for packet 2 before the timeout, so the sender resends it.*

### Check digit

A **check digit** is an extra digit calculated from the other digits of a number and added to the end. It catches errors made when a number is *entered* (typed or scanned), such as a wrong digit or two digits swapped. Barcodes and ISBN book numbers use check digits.

> **Worked example — ISBN-13 check digit**
>
> First 12 digits: 978030640615. Multiply the digits alternately by 1 and 3 and add: total = 93. 93 MOD 10 = 3; check digit = 10 − 3 = **7** (if the remainder is 0 the check digit is 0). Full ISBN: 9780306406157. A scanner repeats the calculation; if the result does not match the last digit, the number is rejected.

| Method | Detects errors in | Can correct? | Main weakness |
|---|---|---|---|
| Parity check | Transmission | No | Misses an even number of flipped bits |
| Parity block | Transmission | Yes, a single bit | Extra byte per block |
| Checksum | Transmission | No: data resent | Some errors cancel out in simple sums |

| Method | Detects errors in | Can correct? | Main weakness |
|---|---|---|---|
| Echo check | Transmission | No: data resent | Doubles traffic; unclear which direction failed |
| ARQ | Transmission | No: data resent automatically | Delays while waiting for timeouts |
| Check digit | Data entry | No | Some unusual errors not detected |

> **Quick review — error detection**
>
> Parity counts 1s (even/odd); a parity block can locate and correct a single bit; a checksum is a value calculated from the data and compared; an echo check sends the data back; ARQ uses ACKs and timeouts to resend; a check digit validates numbers on entry.

> **Exam-style practice**
>
> **Question (3 marks).** The byte 1101 0110 is received by a system using odd parity. State whether an error has been detected and explain why parity cannot detect all errors.
>
> **Checked answer.** The byte has 5 ones, which is even, so an error is detected **(1)**. If two bits are flipped **(1)** the number of 1s stays odd, so the check still passes **(1)**.

# 7. Network Architecture

## 7.1 Types of network by size

![Figure 10 — Networks classified by the area they cover.](modules/networks/figures/fig010-networks-classified-by-the-area-they-cover.png)

*Figure 10 — Networks classified by the area they cover.*

### LAN (Local Area Network)

A collection of connected devices in one physical location such as a home or office, covering a single, limited area. A LAN can range from one user at home to thousands of users and devices in an enterprise, and can include wired and wireless devices. Modern wired LANs are **most often built as a star** around a switch, because a failed cable or computer affects only that device and new devices are simply plugged in without taking the network offline.

### WAN (Wide Area Network)

Connects computers and smaller networks over large geographical areas such as different cities, countries or continents. WANs usually rely on telecommunications companies and ISPs to carry data over long distances. Because they need **redundant paths**, WAN backbones are typically a **partial mesh or hybrid**: if an undersea cable is cut, traffic

reroutes another way. *Example:* a company with offices in Tokyo, Singapore and London joins them with a WAN. The internet is the best-known WAN, a “network of networks”. Compared with a LAN a WAN usually has more complex infrastructure and is more expensive to maintain.

### MAN (Metropolitan Area Network)

Connects multiple LANs across a city, town or large campus; larger than a LAN but smaller than a WAN. It often uses high-speed fibre-optic links and is commonly laid out as a **fibre ring or a tree** (a central root branching to departments, schools or stations). *Example:* a university with several buildings across a city linking the networks of its library, laboratories and administration.

> **Be careful with “uses”**
>
> The topologies above are what each network type *commonly* uses, not rules. Large networks are almost always hybrids of several topologies. In exams, give the reason with the topology (for example “WAN: mesh, because redundant paths let traffic reroute”).

|  | LAN | MAN | WAN |
|---|---|---|---|
| Area | Single site | City or campus | Cities, countries, continents |
| Typical owner | Individual or organisation | Organisation or city authority | Telecoms companies, ISPs |
| Common topology | Star | Ring / tree | Partial mesh / hybrid |
| Speed | Very high | High | Lower, varies |

|  | LAN | MAN | WAN |
|---|---|---|---|
| Cost and complexity | Low | Medium | High |

## 7.2 Network service models

![Figure 11 — Client–server and peer-to-peer models.](modules/networks/figures/fig011-client-server-and-peer-to-peer-models.png)

*Figure 11 — Client–server and peer-to-peer models.*

### Client–server

A centralised architecture in which a dedicated computer (the **server**) stores data, manages resources and processes

requests, while other devices (the **clients**) request and use those services. Roles are fixed. *Examples:* websites (web browser to a web server over HTTP/HTTPS), email (Gmail or Outlook to mail servers), streaming (Netflix to user devices), cloud storage. *Used for:* managing heavy traffic, centralised security and backups, enterprise databases.

### Peer-to-peer (P2P)

A decentralised architecture in which every participant (a **peer**) has equal status and acts as both client and server. Peers share resources directly with each other without a central authority. *Examples:* BitTorrent file sharing, where you download fragments from many other users while uploading fragments to others; two laptops on a home network sharing a file directly.

|  | Client–server | Peer-to-peer |
|---|---|---|
| Control | Centralised | Decentralised |
| Roles | Fixed: client or server | Every peer is both |
| Security and backup | Easy to manage centrally | Harder: each peer is responsible |
| Cost | Server hardware and admin | Low |
| Failure | Server failure affects everyone | No single point of failure |
| Scales with users | Needs server capacity | More peers can add capacity |

> **Quick review 10 — LAN vs WAN; client–server vs P2P**
>
> A LAN covers a single limited area (often a star, cheaper and simpler); a WAN covers large areas (often mesh or hybrid, more complex and costly). In client–server, roles are fixed and a server provides services to clients; in P2P every node is both client and server and no central authority is needed.

# 8. Network Threats and Security

## 8.1 Malware

**Malware** is malicious software designed to infiltrate, damage or gain unauthorised access to systems.

| Malware | What it is | How it spreads | Countermeasure |
|---|---|---|---|
| Virus | Attaches itself to a host file or program and replicates; corrupts, modifies or deletes data | Needs user action (opening the infected file) | Antivirus / anti-malware; do not open unknown files |
| Worm | Standalone program that self-replicates across networks without a host file | Exploits network vulnerabilities; no user action needed | Firewall, patches, antivirus |
| Trojan horse | Malicious code disguised as useful software; creates backdoors | User is tricked into installing it | Antivirus, install only trusted software |
| Spyware | Secretly monitors activity (keystrokes, screenshots, browsing) and reports it | Bundled with other software or from malicious sites | Anti-malware, firewall |
| Adware | Shows unwanted pop-up adverts and may redirect the browser | Bundled with free software | Anti-malware, careful installation |
| Ransomware | Encrypts files or locks the drive and demands a ransom for the key | Phishing e-mails, malicious downloads | Regular offline backups, antivirus, patching |

## 8.2 Cyberattacks

| Attack | Description | Defence |
|---|---|---|
| Brute-force / dictionary | Trying every possible password or a list of common words until one works | Strong passwords, multi-factor authentication (MFA), account lockout |
| Data interception (packet sniffing) | Eavesdropping on data as it travels, using sniffers | Encryption (HTTPS, VPN) |
| DoS / DDoS | Flooding a server with requests from one source (DoS) or from a **botnet** of infected computers (DDoS) so it crashes or is unavailable | IDS/IPS, firewalls and rate-limiting, traffic filtering |
| Hacking / unauthorised access | Gaining illegal entry to view, delete or change data | Authentication, firewalls, access rights, patching |
| Phishing | Fraudulent e-mails, SMS (smishing) or calls (vishing) that mimic real organisations to steal data | User awareness training, spam filters, MFA |
| Pharming | Malicious code or DNS manipulation silently redirects users from a real site to a fake copy | Anti-malware, checking the HTTPS padlock and URL, secure DNS |
| Social engineering | Manipulating trust, fear, curiosity or authority so people break procedures or reveal secrets | Training, verification procedures |

## 8.3 System and network vulnerabilities

| Vulnerability | Why it is dangerous | Countermeasure |
|---|---|---|
| Weak or default passwords | Easily guessed (e.g. 123456, admin) | Robust password policy, password manager, MFA |

| Vulnerability | Why it is dangerous | Countermeasure |
|---|---|---|
| Unpatched / outdated software | Known flaws remain open | Automated patch management |

Misconfigured access rights Users have more privilege than needed Least-privilege access, regular audits

Removable media Infected USB drives bypass the firewall Disable auto-run, scan media, restrict ports

## 8.4 Common types of network security

1. **Firewall:** monitors and controls incoming and outgoing traffic against rules; blocks unauthorised connections. It also blocks malware from sending data out.

2. **Encryption:** converts readable *plaintext* into *ciphertext* so unauthorised people cannot understand it; HTTPS uses it to protect web traffic.

3. **Antivirus / anti-malware:** detects, quarantines and removes malicious programs using signatures and behaviour

analysis.

4. **Authentication:** verifies identity before granting access: passwords, fingerprints, multi-factor authentication.

5. **VPN (Virtual Private Network):** an encrypted tunnel between a device and a VPN endpoint, protecting data across untrusted networks.

6. **IDS / IPS:** an intrusion detection system detects and reports suspicious traffic; an intrusion prevention system can also block it.

## 8.5 How encryption works

**Symmetric encryption** uses the same key to encrypt and decrypt: it is fast but the key must be shared securely. **Asymmetric encryption** uses a pair of keys: a **public key** (shared openly) encrypts and the matching **private key** (kept secret) decrypts; it solves the key-sharing problem but is slower. **HTTPS** uses both: the browser and server use asymmetric encryption to agree a symmetric *session key*, then switch to the faster symmetric encryption for the data (this is part of the TLS protocol).

> **Worked example — a Caesar cipher (symmetric)**
>
> Key = shift by 3. Plaintext `NETWORK` becomes ciphertext `QHWZRUN` (N→Q, E→H, T→W, W→Z, O→R, R→U, K→N). The same key (3) is used backwards to decrypt. Real encryption such as AES works the same way in principle but is vastly stronger.

## 8.6 Threat–countermeasure mapping

| Threat | Countermeasure | How it works |
|---|---|---|
| Virus, worm, Trojan, spyware | Antivirus / anti-malware | Scans files and memory to detect, quarantine and remove malicious software |
| Ransomware | Regular backups (and antivirus) | Allows recovery of encrypted files without paying |
| Brute-force attack | MFA and account lockout | Requires a second check; locks the account after repeated failures |
| Data interception | Encryption (HTTPS) and VPN | Eavesdroppers see only unreadable ciphertext |
| DoS / DDoS | IDS/IPS and firewall rate-limiting | Detects abnormal floods and filters or limits them |
| Phishing / pharming | User awareness training and authentication | Teaches users to recognise fakes; verifies identity |

| Threat | Countermeasure | How it works |
|---|---|---|
| Weak or default passwords | Robust password policy | Minimum length, complexity, no factory defaults |
| Unpatched software | Automated patch management | Updates fix known vulnerabilities before attackers exploit them |

> **Quick review 11 — Malware and attacks**
>
> Three malware types with a countermeasure: virus (antivirus), worm (firewall and antivirus), ransomware (backups and antivirus). Two attacks with a defence: brute force (MFA and lockout), packet sniffing (encryption, VPN). Also: DDoS (IDS/IPS), phishing (awareness training and authentication).

# 9. Worked Examples

> **Worked example 1 — tracing a packet**
>
> **Scenario:** a 1 MB message is sent from your laptop to a web server and the network splits it into 100 packets.
>
> | Step | What happens | Key concept |
> |---|---|---|
> | 1 | The message is divided into 100 packets; each header holds source IP, destination IP and sequence number (1–100) | Packetisation |
> | 2 | A trailer is added to each packet for error checking | Error detection |
> | 3 | The laptop sends the packets to your router, which reads the destination IP in each header and forwards it toward the internet | Routing |
> | 4 | Packets cross several routers; some take faster routes and arrive out of order | Packet switching |
> | 5 | The server uses the sequence numbers to reassemble the data in order | Reassembly |
> | 6 | If a packet is lost, TCP detects the gap and requests retransmission | Reliability (TCP) |

> **Worked example 2 — choosing a topology**
>
> **Scenario:** a small business with 10 employees and a limited budget needs a network where one broken cable does not stop everyone working.
>
> | Consideration | Analysis | Decision |
> |---|---|---|
> | Budget | Limited | Star uses more cable than bus but is affordable for 10 devices |
> | Reliability | One broken cable must not affect everyone | Star isolates failures to individual devices |
> | Scalability | More staff may join | Star makes it easy to add devices |
> | Recommendation | Star topology | Best balance of cost, reliability and scalability |

> **Worked example 3 — breaking down a URL**
>
> URL: `https://www.bbc.co.uk/news` . Protocol: https. Subdomain: www. Domain name: bbc. Second-level domain: co. Top-level (country) domain: uk. Path: /news.

> **Worked example 4 — how many links in a full mesh?**
>
> A company wants to link 8 offices in a full mesh. Links = N(N−1)/2 = 8 × 7 / 2 = **28 links**. Adding a ninth office needs 8 more, giving 36. This rapid growth is why full meshes are only used for small, critical networks.

> **Worked example 5 — an asynchronous byte**
>
> Sending the ASCII letter A (01000001) asynchronously: start bit 0, then the 8 data bits, then stop bit 1: 0 01000001 1 = 10 bits. Efficiency = 8 / 10 = 80%.

# 10. Structured Learner Activities

> **Activity 1 — Label the parts of a packet**
>
> Draw or describe a packet with three parts. Label each part and write one sentence explaining its purpose.

> **Expected outcome**
>
> Header: source address, destination address, sequence number; helps the packet reach the right device and be reassembled in order. Payload: the data. Trailer: end marker and error-detection bits.

> **Activity 2 — Choose a topology**
>
> A university is building a campus network connecting five buildings across a city. If one building's connection fails,
>
> the others must keep working. Which topology would you recommend and why?

> **Expected outcome**
>
> Mesh or hybrid. A mesh gives multiple redundant paths so traffic reroutes around a failure. A hybrid could use a star inside each building (devices to a local switch) with a mesh between buildings. Bus or ring would be unsuitable because one failure could affect the whole network.

> **Activity 3 — Match the threat to the countermeasure**
>
> Match: virus, brute-force attack, packet sniffing, DDoS, ransomware, phishing.

> **Expected outcome**
>
> Virus → antivirus. Brute force → MFA and lockout. Packet sniffing → encryption/VPN. DDoS → IDS/IPS. Ransomware → backups. Phishing → user awareness training.

> **Activity 4 — Break down a URL**
>
> For `https://store.example.co.uk/product/123`, identify each part.

> **Expected outcome**
>
> Protocol https; subdomain store; domain name example; second-level domain co; top-level domain uk; path /product/123.

> **Activity 5 — Classify the data flow**
>
> State simplex, half-duplex or full-duplex: (1) a TV broadcast, (2) a telephone conversation, (3) a walkie-talkie, (4) a keyboard sending input, (5) a video call.

> **Expected outcome**
>
> (1) Simplex. (2) Full-duplex. (3) Half-duplex. (4) Simplex. (5) Full-duplex.

> **Activity 6 — Choose the transmission method**
>
> State serial or parallel and why: (1) a keyboard on a 2 m USB cable, (2) data between two buildings 500 m apart, (3) an older printer on a 25-pin cable.

> **Expected outcome**
>
> (1) Serial: USB is serial and works well with fewer wires. (2) Serial: parallel suffers skew and crosstalk over long distances. (3) Parallel: older printer cables used parallel over short distances.

> **Activity 7 — Synchronous or asynchronous?**
>
> Decide the type and give a reason: (1) a keyboard sending a byte with a start and stop bit, (2) a high-speed link sending a block of data with a shared clock, (3) a web page that loads comments in the background while you
>
> keep reading.

> **Expected outcome**
>
> (1) Asynchronous transmission: start and stop bits, no shared clock. (2) Synchronous transmission: shared clock, block of data. (3) Asynchronous communication: the browser does not wait (non-blocking).

> **Activity 8 — Spot the errors**
>
> A student writes: “IP guarantees that packets arrive in order. A switch sends data using IP addresses. A MAC address changes every time you join Wi-Fi.” Correct all three statements.

> **Expected outcome**
>
> IP does not guarantee order; TCP provides ordered, reliable delivery. A switch uses MAC addresses; a router uses IP addresses. A MAC address is normally fixed to the NIC; the IP address changes when you join a network.

# 11. Mind Map and Summary

![Figure 12 — Mind map of the Networks module.](modules/networks/figures/fig012-mind-map-of-the-networks-module.png)

*Figure 12 — Mind map of the Networks module.*

| Section | Key idea to remember |
|---|---|
| Network | Devices + links + protocols that exchange data and share resources |
| Packet | Header (who, where, order) + payload (data) + trailer (end, error check) |
| TCP / IP | IP routes packets; TCP makes delivery reliable and ordered |
| MAC / IP | MAC = hardware, used in a LAN; IP = logical, used between networks |
| Topology | Arrangement of nodes and links; star is the default for LANs |
| Data flow | Simplex, half-duplex, full-duplex |
| Transmission | Serial vs parallel; synchronous vs asynchronous |
| LAN / MAN / WAN | Area covered: single site, city, wide area |
| Security | Know each threat and its matching countermeasure |

# 12. Case Studies

> **Case study 1 — “The school Wi-Fi is down”**
>
> A school has a star network: 40 classroom computers connect to a switch in each of four corridors; the four switches connect to one central switch, which connects to a router and the internet. On Monday the whole of
>
> corridor B loses access, but the other corridors work.
>
> **Tasks:** (a) name the topology of the whole school network, (b) say where the fault probably lies, (c) say what would happen if the central switch failed, and (d) suggest an improvement.

> **Model answer**
>
> (a) A **tree/hybrid** of stars (star within each corridor, stars joined to a central switch). (b) Corridor B's switch, or its link to the central switch, because only that branch is affected. (c) Everything would lose connection to each other and to the internet: the central switch is a single point of failure. (d) Add a second link or a second central
>
> switch (redundancy), moving toward a partial mesh between the switches.

> **Case study 2 — a phishing e-mail**
>
> An employee receives an e-mail that appears to come from the company's bank, asking her to click a link and confirm her password. The link text shows the real bank name, but hovering shows `http://secure-bank-`
>
> `login.example-site.com` .
>
> **Tasks:** identify the attack, three warning signs and the countermeasures.

> **Model answer**
>
> **Phishing** (a social-engineering attack). Warning signs: the real link does not match the displayed name; it uses http rather than https; urgent request for credentials; unexpected message. Countermeasures: user awareness training, never entering passwords from e-mail links, spam filters, and multi-factor authentication so a stolen password alone is not enough. If the link redirected through altered DNS to a fake site without any e-mail, that would be **pharming**.

> **Case study 3 — streaming a live match**
>
> A sports club streams a live match to thousands of viewers. Viewers complain of buffering and delays.
>
> **Tasks:** explain which of bandwidth and latency matters, whether TCP or UDP suits live video, and which architecture the stream uses.

> **Model answer**
>
> Both matter, but streaming needs enough **bandwidth** for the video bitrate and low, steady latency for liveness. **UDP** is often used for live video because a slightly late packet is better dropped than waiting for TCP
>
> retransmission, though many services use TCP-based protocols with buffering. The stream is **client–server**: a few servers (often many copies spread around the world) serve thousands of clients. A DDoS attack would be a serious risk, so IDS/IPS and traffic filtering are important.

# 13. Review Questions with Answers

### Question 1. What is the difference between TCP and IP?

> **Answer:** TCP is a connection-oriented protocol that ensures reliable, in-order delivery. IP is a connectionless protocol that handles addressing and routing. TCP is layered on top of IP to provide the reliability IP lacks.

### Question 2. What is the difference between a router and a switch?

> **Answer:** A router connects different networks and forwards data between them using destination IP addresses. A switch connects devices within a LAN and forwards data to the intended device using MAC addresses.

### Question 3. What is the difference between a virus and a worm?

> **Answer:** A virus attaches to a host file and needs user action to spread. A worm is standalone, self-replicates and spreads across networks without a host file or user action.

### Question 4. What is the difference between phishing and pharming?

> **Answer:** Phishing sends fraudulent messages that trick users into revealing information; it relies on user action. Pharming silently redirects users from legitimate websites to fake copies, for example by manipulating DNS.

### Question 5. Which topology would you recommend for a school computer lab, and why?

> **Answer:** Star: each computer connects to a central switch, so one failed cable or computer only affects that node, and computers are easy to add or remove.

### Question 6. Why is packet switching efficient?

> **Answer:** Data is split into small packets that can use any available route; many devices can send at the same time; if a router or link fails, packets reroute.

### Question 7. What is the difference between symmetric and asymmetric encryption?

> **Answer:** Symmetric uses one shared key for encryption and decryption (fast). Asymmetric uses a public key to encrypt and a private key to decrypt (solves key sharing but slower). HTTPS uses asymmetric encryption to exchange a symmetric session key, then symmetric encryption for the data.

### Question 8. What is the difference between a LAN and a WAN?

> **Answer:** A LAN connects devices in a single limited area such as a home or office. A WAN connects networks over large geographical areas such as cities or countries.

### Question 9. What is the difference between client–server and peer-to-peer?

> **Answer:** In client–server, a server provides resources and clients use them (fixed roles, centralised). In P2P every node has equal status and acts as both client and server (decentralised).

**Question 10. Name the three network types and the topology each commonly uses, with a reason.**

> **Answer:** LAN: star (isolates failures, easy to expand). WAN: mesh or hybrid (redundant paths so traffic reroutes). MAN: ring or tree (a fibre ring or a hierarchy from a central root to departments across a city).

### Question 11. What are the three parts of a packet?

> **Answer:** Header (source, destination, sequence number), payload (the data), trailer (end marker and error-check bits).

### Question 12. What is the difference between a MAC address and an IP address?

> **Answer:** A MAC address is a 48-bit hardware identifier assigned by the manufacturer, normally fixed. An IP address is a logical address given by the network that can change.

### Question 13. What is a URL and what are its main parts?

> **Answer:** The address of a resource on the internet: protocol, subdomain, domain name, top-level domain and path.

### Question 14. What are the three types of data flow?

> **Answer:** Simplex (one direction), half-duplex (both directions, alternating), full-duplex (both directions at once).

### Question 15. What is the difference between serial and parallel transmission?

> **Answer:** Serial: one bit at a time on one channel; suits long distances and needs less cabling. Parallel: many bits at once on many channels; faster but only for short distances because of skew and crosstalk.

**Question 16. Distinguish synchronous and asynchronous transmission.**

> **Answer:** Synchronous: sender and receiver share a clock and data is sent in continuous blocks. Asynchronous: no shared clock; each byte is framed by a start bit and a stop bit, with gaps allowed.

### Question 17. What is a DDoS attack and how can it be defended against?

> **Answer:** A flood of requests from a botnet of infected computers overwhelms a server so it crashes or becomes unavailable. Defence: IDS/IPS and firewalls that identify abnormal floods and filter or rate-limit them.

### Question 18. What is social engineering?

> **Answer:** Manipulating human psychology (trust, fear, curiosity, authority) to persuade people to break security
>
> procedures or reveal confidential information. It targets people, not technical systems.

### Question 19. Why is encryption important for network security?

> **Answer:** It converts readable data into ciphertext so eavesdroppers who capture packets see only unreadable data; HTTPS and VPNs use it to protect data in transit.

**Question 20. Name three topologies with one advantage and one disadvantage of each.**

> **Answer:** Star: isolated failures / central device is a single point of failure. Bus: cheap, least cabling / backbone break stops everything. Mesh: fault tolerant / expensive and complex.

# 14. End-of-Module Test

Total: 49 marks. Suggested time: 45 minutes. Attempt without notes, then mark yourself against the answers.

## Questions

1. Define a computer network and name its three defining elements. [3]

2. State the function of a switch and the address it uses. [2]

3. A 2.4 MB file is split into packets carrying 1200 bytes of payload each. Using 1 MB = 1 000 000 bytes, how many packets are needed? [2]

4. State two items stored in a packet header. [2]

5. Explain why TCP is used on top of IP. [2]

6. Give the number of bits in a MAC address, an IPv4 address and an IPv6 address. [3]

7. Explain the role of DNS. [2]

8. Identify the protocol, domain name and path in `https://learn.example.edu/course/net` . [3]

9. A full mesh connects 12 nodes. How many links does it need? [2]

10. Give one advantage and one disadvantage of a bus topology. [2]

11. State the type of data flow for: (a) radio broadcast, (b) walkie-talkie, (c) video call. [3]

12. Why is parallel transmission unsuitable over long distances? [2]

13. An asynchronous system sends 8-bit characters with 1 start bit and 1 stop bit. Calculate the efficiency. [2]

14. Distinguish a LAN from a WAN. [2]

15. State two differences between client–server and peer-to-peer networks. [2]

16. Describe how ransomware works and one countermeasure. [3]

17. Explain how a firewall protects a network. [2]

18. Explain how HTTPS uses both symmetric and asymmetric encryption. [3]

19. Download time: a 450 MB file on a 90 Mbit/s link. Calculate in seconds. [3]

20. Recommend a topology for a hospital linking 6 critical buildings so that no single failure isolates a building. Justify. [4]

## Mark scheme

| # | Answer |
|---|---|
| 1 | Two or more devices connected to share data and resources; hardware (nodes), media/links, protocols. |
| 2 | Forwards data only to the intended device within a LAN; MAC address. |
| 3 | 2 400 000 / 1200 = 2000 packets. |
| 4 | Any two of source address, destination address, sequence number. |
| 5 | IP gives no guarantee of delivery or order; TCP adds retransmission and reordering for reliable delivery. |
| 6 | 48; 32; 128. |
| 7 | Translates a domain name into the IP address of the server so a connection can be made. |
| 8 | https; example (with learn as subdomain, .edu TLD); /course/net. |
| 9 | 12 × 11 / 2 = 66. |
| 10 | Advantage: cheap/least cabling. Disadvantage: one backbone break stops the network (or collisions). |

| # | Answer |
|---|---|
| 11 | Simplex; half-duplex; full-duplex. |
| 12 | Skew and crosstalk make bits arrive at different times and corrupt each other. |
| 13 | 8 / 10 = 80%. |
| 14 | LAN: single limited area such as a building; WAN: large geographical areas such as countries. |
| 15 | Any two: centralised vs decentralised; fixed vs equal roles; server cost vs low cost; central security vs per-peer. |
| 16 | Encrypts or locks files and demands payment; countermeasure: regular offline backups (or antivirus). |
| 17 | Monitors incoming and outgoing traffic against rules and blocks unauthorised connections. |
| 18 | Asymmetric encryption exchanges a session key securely; symmetric encryption with that key protects the data because it is faster. |
| 19 | 450 × 8 = 3600 Mbit; 3600 / 90 = 40 s. |
| 20 | Mesh (or partial mesh/hybrid): multiple paths mean traffic reroutes after a failure; no single point of failure (accept cost as a drawback). |

# 15. Learning Material List

Suggested resources. Titles are given so you can find them; check each is current before relying on it.

| Resource | Type | Use it for |
|---|---|---|
| Watson &amp; Williams, *Cambridge IGCSE and O Level* *Computer Science* (Hodder Education) | Textbook | Core network content: protocols, topologies, security |
| Watson &amp; Williams, *Cambridge International AS &amp; A* *Level Computer Science* (Hodder Education) | Textbook | Protocols, packet switching, security at A Level |
| Kurose &amp; Ross, *Computer Networking: A Top-Down* *Approach* | Textbook | Deeper treatment of layers, TCP/IP, DNS (beyond syllabus) |
| Cloudflare Learning Center (cloudflare.com/learning) | Web articles | Short explainers on DNS, DDoS, HTTPS, firewalls |
| Cisco Networking Academy, *Networking Basics* | Course | Hands-on introduction to LANs, switches and routers |
| Computerphile (YouTube) | Video | Short talks on TCP, encryption and the internet |
| Cisco Packet Tracer (free simulator) | Software | Build and test a star or hybrid network without hardware |
| Wireshark (free packet analyser) | Software | See real packet headers; compare with the teaching model |
| RFC 791 (IP), RFC 793 (TCP), RFC 1035 (DNS) | Standards | Primary sources on the protocols |

# 16. Glossary

| Term | Definition |
|---|---|
| **Asynchronous transmission** | Data sent one byte at a time, each framed by a start and stop bit, with no shared clock. |
| **Bandwidth** | Maximum data a link can carry per second. |
| **Botnet** | A network of compromised computers controlled remotely by an attacker. |
| **Ciphertext** | Encrypted data, unreadable without the key. |
| **Client–server** | A centralised model where a server provides resources and clients use them. |
| **Crosstalk** | Interference between adjacent wires in parallel transmission. |
| **CSMA/CD** | Carrier Sense Multiple Access with Collision Detection: a method used on bus/shared Ethernet to manage collisions. |
| **DHCP** | Protocol that automatically assigns IP addresses. |
| **DNS** | System that translates domain names into IP addresses. |
| **Encryption** | Converting plaintext into ciphertext so unauthorised users cannot understand it. |
| **Header** | Part of a packet holding control information such as source, destination and sequence number. |
| **IP address** | Logical address given to a device when it joins a network. |
| **Latency** | Delay for data to travel from sender to receiver. |
| **LAN** | Local Area Network: devices in a single limited area. |
| **Link** | The wired or wireless pathway connecting nodes. |
| **MAC address** | Unique 48-bit hardware identifier of a NIC. |
| **MAN** | Metropolitan Area Network: LANs across a city or large campus. |
| **Malware** | Malicious software designed to infiltrate, damage or gain unauthorised access. |
| **NIC** | Network Interface Card: connects a device to a network. |
| **Node** | Any device connected to a network. |
| **Packet** | A small chunk of data with a header, payload and (in the teaching model) a trailer. |
| **Packet switching** | Breaking data into packets, sending them along available routes and reassembling them. |
| **Payload** | The actual data carried by a packet. |
| **Peer-to-peer** | A decentralised model where each node is both client and server. |
| **Pharming** | Redirecting users from legitimate sites to fake copies. |
| **Phishing** | Social-engineering attack tricking users into revealing sensitive information. |
| **Protocol** | Rules and standards that devices follow to communicate. |
| **Router** | Connects different networks and forwards data using IP addresses. |
| **Skew** | Bits arriving at different times in parallel transmission. |
| **Switch** | Connects devices within a LAN and forwards data using MAC addresses. |
| **Synchronous transmission** | Sender and receiver share a clock; data sent in continuous blocks. |

# 16. Glossary Supplement

Key terms introduced in this edition, in alphabetical order.

| Term | Definition |
|---|---|
| **ARQ** | Automatic Repeat reQuest: acknowledgements and timeouts trigger automatic resending. |
| **Check digit** | Extra digit calculated from a number to detect data-entry errors. |
| **Checksum** | Value calculated from a block of data and sent with it to detect errors. |
| **Circuit switching** | A dedicated path is set up and reserved before data is sent. |
| **DHCP** | Protocol that leases dynamic IP addresses (Discover, Offer, Request, Acknowledge). |
| **Dynamic IP address** | Address assigned automatically by DHCP that may change. |
| **Echo check** | Receiver returns the data to the sender for comparison. |
| **NAT** | Network Address Translation: router swaps private addresses for its public address. |
| **Parity bit** | Bit added so the number of 1s is even (even parity) or odd (odd parity). |
| **Parity block** | Row and column parity that can locate and correct a single-bit error. |
| **Private IP address** | Address used only inside a LAN (10.x, 172.16–31.x, 192.168.x). |
| **Public IP address** | Address unique on the internet, assigned by the ISP. |
| **Static IP address** | Address set manually that does not change. |
| **Subnet mask** | Shows which bits of an IP address are the network part, e.g. 255.255.255.0 (/24). |
| **Timeout** | Time a sender waits for an acknowledgement before resending. |

| Term | Definition |
|---|---|
| **TCP** | Connection-oriented protocol giving reliable, in-order delivery. |
| **Topology** | Physical or logical arrangement of nodes and links. |
| **Trailer** | Part of a packet marking its end and carrying error-check bits. (IPv4 has no trailer; Ethernet frames do.) |
| **UDP** | Connectionless, fast transport protocol with no delivery guarantee. |
| **Unicast** | Data sent from one device to one specific destination device. |
| **URL** | The address of a resource on the internet. |
| **WAN** | Wide Area Network: networks over large geographical areas. |

## 17. References

1. Watson, D. and Williams, H. *Cambridge IGCSE and O Level Computer Science*. Hodder Education.

2. Watson, D. and Williams, H. *Cambridge International AS &amp; A Level Computer Science*. Hodder Education.

3. Kurose, J. F. and Ross, K. W. *Computer Networking: A Top-Down Approach*. Pearson.

4. Postel, J. (1981). RFC 791: Internet Protocol. IETF.

5. Postel, J. (1981). RFC 793: Transmission Control Protocol. IETF.

6. Mockapetris, P. (1987). RFC 1035: Domain Names – Implementation and Specification. IETF.

7. Cloudflare Learning Center, articles on DNS, DDoS attacks and HTTPS. cloudflare.com/learning.

8. Cisco Networking Academy, *Networking Basics* course materials.

Revision notes (v2.0): removed project-management sections and inline citation tags from the learner text; replaced missing diagrams with drawn figures; made every quick-review box distinct; corrected the glossary note on trailers; clarified TCP versus IP; described LAN/WAN/MAN topologies

as “commonly” used; rewrote synchronous versus asynchronous at both the transmission and communication levels; added UDP, DHCP, the TCP/IP layers, bandwidth and latency; added mind map, case studies, end-of-module test and learning material list; replaced patent and generic-website references with textbooks and standards. Please check the reference list against your assignment's citation requirements before submission.


---

<!-- ===================== Stage 8 — Behavioural AI (Reinforcement Learning) ===================== -->

# Behavioural AI: Reinforcement Learning for Beginners

**Stage 8 · Part of *Hardware, Networks and Behavioural AI***
Version 3.0, beginner edition (24 November 2026)

> **Start here**
>
> This module teaches how a computer can **learn by trial and error**, the same way you learn a new video game: try something, see what happens, and do more of what works. You do not need any programming or machine-learning knowledge. If you can add, multiply and work out an average, you can follow every example.
>
> Every section starts with **The big idea** in one or two sentences. Read that first. The maths always comes *after* the explanation in words, and every number in the examples is worked out step by step.

## Contents

- Module overview, learners and learning outcomes
- How to study this module
- Our two running examples
- The eight symbols you need (read first)
- 1\. What Behavioural AI is
- 2\. The learning loop and the grid world
- 3\. What makes reinforcement learning different
- 4\. Describing a problem: states, actions, rewards (the MDP)
- 5\. Chance, plans and values
- 6\. Learning with or without a map (model-based vs model-free)
- 7\. The Bellman equation: the one idea behind everything
- 8\. Dynamic programming (1): measuring a plan
- 9\. Dynamic programming (2): improving a plan
- 10\. Value iteration
- 11\. Policy iteration
- 12\. On-policy and off-policy
- 13\. Learning from experience: the algorithm families, Monte Carlo and TD
- 14\. Q-learning
- 15\. SARSA and Deep Q-Networks
- 16\. Learning the plan directly: REINFORCE
- 17\. Actor–critic
- 18\. Real-world applications and reward design
- 19\. Mind map and summary
- 20\. Case studies
- 21\. Mixed practice
- 22\. End-of-module test with mark scheme
- 23\. Learning material list
- 24\. Glossary
- 25\. References and revision notes

---

# Module Overview

## What this module is about

**Behavioural AI** (in this module) means AI that learns *what to do* by acting in a world and getting a score, called a **reward**, for how well things went. Nobody tells it the right answer. It has to find out by trying. The technical name for this is **reinforcement learning (RL)**.

The module follows one path: first we describe a problem clearly (Sections 1–6), then we learn the single equation that every method uses (Section 7), then we solve small problems when we know all the rules (Sections 8–11), and finally we learn when the rules are unknown and the agent must learn from experience (Sections 12–17). We finish with real uses, ethics, case studies and a test (Sections 18–25).

## Who this is for

- **Intended learners:** first- and second-year college students, including those outside computer science, who want to understand how game-playing and robot-controlling AI learns.
- **Prerequisites:** basic arithmetic (adding, multiplying decimals), the idea of an average, and reading a simple table. No programming. No calculus: the only formulas with advanced symbols are in boxes marked **Going deeper (optional)**, which you can skip.

## Learning outcomes

| # | By the end of this module you can… | Where it is assessed |
|---|---|---|
| LO1 | Explain what Behavioural AI is and how it differs from supervised and unsupervised learning. | Section 1; Activity 1.1; Test Q1 |
| LO2 | Describe the agent–environment loop and name its five parts. | Section 2; Activity 2.1; Test Q2 |
| LO3 | Write down a small problem as states, actions, rewards and chances (an MDP) and explain the Markov property. | Sections 4–5; Activities 4.1, 5.2; Test Q4 |
| LO4 | Explain the Bellman equation in words and do a one-step calculation by hand. | Section 7; Activity 7.1; Test Q7–Q8 |
| LO5 | Tell model-based from model-free learning, and trace policy evaluation, value iteration and policy iteration on a small grid. | Sections 6, 8–11; Activities 8.1, 10.1, 11.1; Test Q5–Q6, Q9–Q10 |
| LO6 | Explain how an agent learns from experience (Monte Carlo, TD, Q-learning, SARSA, DQN, REINFORCE, actor–critic), say which are on- or off-policy, and predict the cliff-walk behaviour. | Sections 12–17; Activities 12.1, 13.3, 14.1, 15.1, 17.1; Test Q11–Q19, Q21 |
| LO7 | Design a reward for a real application, predict one behaviour you did not intend, and name an ethical consequence. | Section 18; Activities 18.1, 18.2; Case studies; Test Q20 |

**How the parts fit together.** Every outcome has a worked example (watch it done), an activity with a checked answer (do it yourself) and a quick check question. The end-of-module test covers all seven outcomes.

## How to study this module

| Week | Sections | Focus | Do this |
|---|---|---|---|
| 1 | 1–3 | What RL is; the loop; exploring | Activities 1.1–3.1; explain the loop to a friend in two minutes |
| 2 | 4–6 | Describing problems; values; maps | Write the states, actions and rewards for a game you know |
| 3 | 7–9 | Bellman; measuring and improving a plan | Redo the 2×2 grid tables by hand without looking |
| 4 | 10–12 | Value and policy iteration; on/off-policy | Do the corridor activities; classify four algorithms |
| 5 | 13–17 | Learning from experience | Trace one update of each algorithm by hand |
| 6 | 18–22 | Real uses, case studies, test | Take the test closed-book, then mark it |

> **Learning suggestions**
>
> - Draw the 2×2 grid on paper once and keep it beside you for every section.
> - Always try the calculation **before** you read the answer.
> - Read the words first, then the formula. If a formula scares you, read the **Formula in words** line again.
> - After each section, try to say **Remember** from memory. If you cannot, re-read the big idea.
> - Skip every **Going deeper (optional)** box on your first read. Come back to them later if you want more.
> - After Section 15, try the free CliffWalking or FrozenLake environment in Gymnasium (see Section 23) and watch the values change.

### Core path and optional boxes

Everything outside a **Going deeper (optional)** box is the core course: it is complete, checked and enough for the test. The optional boxes show the full mathematical form for readers who want it. The test never requires them.

---

# Our Two Running Examples

> **The big idea**
>
> We use one everyday story (a mouse learning a maze) to build intuition, and one tiny puzzle (the 2×2 grid) for every calculation. Keep both in mind.

## Example 1: a mouse learning a maze

Imagine a mouse placed at the entrance of a maze, with a piece of cheese hidden at the far end. Nobody shows it the way. At every junction it can go left, right or straight on. The only "reward" is the cheese at the end.

- At first it wanders randomly, bumps into walls and takes a long time to find the cheese.
- Slowly it remembers which turns led to the cheese sooner, and takes them more often.
- After many runs it goes straight to the cheese without a wrong turn.

That is reinforcement learning. Psychologists studied exactly this kind of maze learning in animals in the early 1900s, and the computer methods in this module grew out of the same idea.

## Example 2: the 2×2 grid world

Even a small maze has too many junctions to calculate by hand, so for every worked example we shrink it to four squares.

![The 2×2 grid world. The agent starts at (0,0); the goal (1,1) is the top-right square.](modules/behavioural-ai/figures/grid-world-2x2.png)

*Figure 1. The 2×2 grid world. Squares are named (x, y): x counts across, y counts up.*

| Part | In the grid world |
|---|---|
| Squares (states) | (0,0) start, (1,0), (0,1), (1,1) goal |
| Moves (actions) | **Right** (x + 1) or **Up** (y + 1). Walking into the edge leaves you where you are. |
| Points (reward) | +1 for stepping onto the goal (1,1); 0 for every other move |
| End | The game ends as soon as you reach the goal |
| Discount γ | 0.9 (Section 5.3 explains this) |

**Two maze ↔ grid matches to remember:** reaching the goal square is like finding the cheese; a move into the edge is like the mouse running into a wall: it stays where it is and wastes time.

---

# The Eight Symbols You Need

You do not need to memorise this. Come back whenever a symbol appears.

| Symbol | Say it as | Meaning in plain words |
|---|---|---|
| s, s′ | "s", "s-prime" | The current situation (state) and the next one |
| a | "a" | An action (a move) |
| r | "r" | The reward (points) just received |
| γ | "gamma" | The **discount**: how much a reward one step in the future is worth now (e.g. 0.9 = 90%) |
| α | "alpha" | The **learning rate**: how big a step each update takes (e.g. 0.5 = halfway) |
| V(s) | "V of s" | The **value** of a state: how many points you expect to collect from here on |
| Q(s, a) | "Q of s, a" | The value of taking action a in state s, then carrying on |
| ← | "becomes" | Update: x ← x + 1 means "x becomes x + 1" |

> **Going deeper (optional): the other symbols**
>
> These appear only in optional boxes. **G<sub>t</sub>**: the return from step t. **π(a | s)**: the chance the plan picks action a in state s ("|" means "given"). **P(s′ | s, a)**: the chance of landing in s′ after doing a in s. **Σ**: "add up over all". **max<sub>a</sub>**: "the biggest over all actions". **E[·]**: the average in the long run. **δ** (delta): the surprise, target minus estimate. **θ** (theta): the adjustable numbers inside a plan. **∇** (nabla): the direction that increases a quantity fastest.

---

# 1. What Behavioural AI Is

> **The big idea**
>
> Behavioural AI learns what to do from rewards, by trial and error, without being shown the right answer.

## 1.1 Learning from consequences

Most AI you hear about learns from examples with answers attached: "this photo is a cat". Behavioural AI is different. It is never told the right move. It acts, gets a reward afterwards, and changes its behaviour to get more reward next time.

The name comes from **behaviourism** in psychology (Pavlov, Thorndike, Skinner): behaviour that is followed by a reward happens more often; behaviour followed by punishment happens less. A dog that gets a treat for sitting learns to sit. **Reinforcement learning** is the computer version of that idea.

![Three families of machine learning: supervised, unsupervised and reinforcement learning.](modules/behavioural-ai/figures/three-families-of-ml.png)

*Figure 2. The three families of machine learning. This module is about the third.*

| Family | What it is given | Everyday example |
|---|---|---|
| Supervised learning | Examples **with** the right answer | A spam filter trained on emails marked "spam" or "not spam" |
| Unsupervised learning | Examples **without** answers; it finds groups | Grouping shoppers by what they buy |
| Reinforcement learning | **No** answers, only a reward after acting | A mouse that learns a maze because it finds cheese at the end |

## 1.2 Key words

| Word | Meaning | In the maze |
|---|---|---|
| **Agent** | The learner that makes decisions | The mouse |
| **Environment** | Everything outside the agent | The maze |
| **State (s)** | A description of the situation right now | Which junction the mouse is at |
| **Action (a)** | A choice the agent can make | Go left, right or straight on |
| **Reward (r)** | Points given after an action; higher is better | +1 for reaching the cheese |
| **Policy (π)** | The agent's plan: which action to take in each state | "At the first junction, turn left" |
| **Value** | How many points the agent expects from here on | "From this junction the cheese is close" |
| **Episode** | One complete run from start to finish | One run from the entrance to the cheese |

> **Check Q1.1. A chess program is trained on millions of positions, each with the "correct" move. Is that behavioural AI?**
>
> **Answer.** No, that is supervised learning (it is given the right answers). A behavioural-AI chess program would play games and only be told win, lose or draw, then work out which moves helped.

> **Activity 1.1 — Name the parts**
>
> A robot vacuum learns to clean a room. It can go forward, turn left, turn right or stop. It gets +1 when it cleans a dirty patch, −5 when it bumps furniture and 0 otherwise. Name the agent, environment, actions, rewards and one possible state.

> **Answer**
>
> Agent = the vacuum's control program. Environment = the room, furniture and dirt. Actions = forward, left, right, stop. Rewards = +1, −5, 0. One possible state = "where I am, which way I face, and what my dirt sensor reads".

> **Remember**
>
> RL = learn from rewards by trial and error. No right answers are given.

---

# 2. The Learning Loop and the Grid World

> **The big idea**
>
> Every RL system repeats one loop: look, act, the world changes, get a reward, learn. Then do it again.

## 2.1 The agent–environment loop

![The agent–environment loop: the agent sends an action; the environment returns a new state and a reward.](modules/behavioural-ai/figures/agent-environment-loop.png)

*Figure 3. The agent–environment loop.*

1. **Look** — the agent sees the current state s.
2. **Act** — it picks an action a using its current policy.
3. **Change** — the world moves to a new state s′.
4. **Reward** — the world gives a reward r.
5. **Learn** — the agent updates what it knows, then the loop repeats from the new state.

In the maze: the mouse is at a junction → turns left → arrives in a new corridor → finds the cheese, +1 → remembers "turning left there was good" → carries on next time from the start.

> **Going deeper (optional): time-step notation**
>
> Textbooks number the steps. S<sub>t</sub> is the state at step t, A<sub>t</sub> the action, and R<sub>t+1</sub> and S<sub>t+1</sub> the reward and state that follow. One step of experience is written (S<sub>t</sub>, A<sub>t</sub>, R<sub>t+1</sub>, S<sub>t+1</sub>), or simply (s, a, r, s′).

## 2.2 Worked example: one game in the grid world

> **Worked example — one episode**
>
> Start at (0,0). Move **Right** → now at (1,0), reward 0. Move **Up** → now at (1,1), the goal, reward +1. The game ends.
>
> Written as steps of experience (s, a, r, s′): Step 1: ((0,0), Right, 0, (1,0)). Step 2: ((1,0), Up, +1, (1,1)).

> **Check Q2.1. The agent is at (1,0) and chooses Up. What is the next state and reward?**
>
> **Answer.** Next state (1,1); reward +1; the game ends.

> **Activity 2.1 — Trace a game**
>
> Starting at (0,0), the agent does Right, Right, Up. (a) Write the square after each move. (b) Write the reward after each move. (c) What is the total reward?

> **Answer**
>
> (a) (0,0) → Right → (1,0) → Right → (1,0) (hit the edge, stayed) → Up → (1,1). (b) 0, 0, +1. (c) Total = 1. The second Right was wasted: exactly the kind of mistake learning should remove.

> **Remember**
>
> Look → act → change → reward → learn, again and again.

---

# 3. What Makes Reinforcement Learning Different

> **The big idea**
>
> RL is hard for three reasons: nobody gives the right answer, rewards often come late, and the agent must choose between using what it knows and trying something new.

## 3.1 Three special features

1. **Trial and error.** The agent is never told the correct action; it must try things and see what happens.
2. **Delayed reward.** The reward for a good move may come much later. The mouse only gets the cheese at the very end, but the turn that really mattered may have been the first one at the entrance. Working out which earlier actions deserve the credit is called the **credit assignment problem**.
3. **The agent's actions change what it sees next.** If it never goes into a cave, it never learns what is inside.

> **Common mistake**
>
> "RL is just supervised learning with rewards as labels." No. A label says *what the right answer was*. A reward only says *how good the result was*. If a chess agent wins, every move gets some credit, even the bad ones.

## 3.2 Exploration vs exploitation

- **Exploitation:** do what currently looks best.
- **Exploration:** try something else, because it might be better.

If you always order your usual dish at a restaurant (exploiting), you will never find out that another dish is even better (exploring). The usual compromise is called **ε-greedy** (say "epsilon-greedy"): most of the time do the best-known action, but with a small chance ε (for example 0.1, so 1 time in 10) do a random action instead. ε is often lowered over time: explore a lot early, then mostly exploit.

> **Worked example — two slot machines**
>
> Machine A paid 1 on its first pull, so the agent's estimate for A is 1. Machine B has never been tried, so its estimate is 0. A purely greedy agent pulls A forever. Suppose B really pays 5 on average: the greedy agent never finds out. With ε = 0.1, about one pull in ten is random, so B gets tried, its estimate rises, and the agent switches to B.

> **Check Q3.1. Why is "always exploit" dangerous?**
>
> **Answer.** The agent may never discover a better action and can get stuck with a mediocre plan for ever.

> **Activity 3.1 — Predict what happens**
>
> A learner sets ε = 0 from the very start. Predict what happens to learning, then suggest one fix.

> **Answer**
>
> With ε = 0 the agent never explores. If all estimates start equal (for example 0) it keeps picking the same arbitrary action; if that action is poor it never finds the good one. Fix: keep ε above 0 for a while, or start all estimates high ("optimistic") so untried actions look attractive and get tried.

> **Remember**
>
> No right answers, late rewards, and a balance between exploring and exploiting.

---

# 4. Describing a Problem: States, Actions, Rewards

> **The big idea**
>
> Before a computer can learn, we must describe the problem precisely: the situations, the moves, the points and the chances. That description is called a Markov Decision Process (MDP).

## 4.1 Why we need a precise description

"Get to the goal" is clear to a person but not to a computer. To calculate anything, we list exactly what the situations are, what moves exist and what each move earns. Every method in this module works on such a list.

## 4.2 The five parts of an MDP

| Part | Question it answers | 2×2 grid |
|---|---|---|
| **States** | What situations can happen? | (0,0), (1,0), (0,1), (1,1) |
| **Actions** | What can the agent do? | Right, Up |
| **Transitions** | Where does each move lead (and with what chance)? | Every move works for certain, or is blocked by the edge |
| **Rewards** | How many points does each move earn? | +1 for entering (1,1), otherwise 0 |
| **Discount γ** | How much is a later reward worth now? | 0.9 |

> **Going deeper (optional): the formal tuple**
>
> An MDP is written (S, A, P, R, γ): the set of states S, the set of actions A, the transition probabilities P(s′ | s, a), the reward R(s, a, s′) and the discount γ.

## 4.3 The Markov property

The **Markov property** means: *the current state tells you everything you need to decide what happens next; the history adds nothing extra.*

In the grid, knowing your square is enough. In chess, the board position is enough. But in a card game, the cards in your hand are **not** enough, because you also need to know which cards have already been played.

> **Why this matters**
>
> Choosing what goes into the state is a design decision. If the state leaves out something important, the agent cannot tell apart two situations that need different actions, and learning becomes much harder.

> **Check Q4.1. In a card game, is "the cards in my hand" a good enough state?**
>
> **Answer.** No. You also need which cards have been played, because that changes what can still be drawn.

> **Activity 4.1 — Describe a corridor**
>
> A 1×3 corridor has cells 1, 2, 3. Cell 3 is the goal (+1 for entering, game ends). Actions: Left, Right. Walking into a wall leaves you in place (reward 0). Write (a) the states, (b) the actions, (c) where Right from cell 1 leads and where Left from cell 1 leads, (d) the reward for Right from cell 2.

> **Answer**
>
> (a) {1, 2, 3}. (b) {Left, Right}. (c) Right from 1 → cell 2 (for certain); Left from 1 → stays in 1 (blocked). (d) +1, because it enters the goal.

> **Remember**
>
> An MDP = states + actions + transitions + rewards + discount. "Markov" = the present state is enough.

---

# 5. Chance, Plans and Values

> **The big idea**
>
> Moves can be uncertain, a plan (policy) says what to do in each state, and a value says how many points a state is worth if you follow the plan.

## 5.1 When moves are uncertain

Real worlds are not perfectly predictable: a robot's wheels slip, a door in the maze is sometimes stuck. We describe this with chances.

> **Worked example — a slippery grid**
>
> Suppose Right works 8 times out of 10, and 2 times out of 10 the agent slips and stays put. Then from (0,0), Right leads to (1,0) with chance 0.8 and stays at (0,0) with chance 0.2. The chances for one move always add up to 1 (0.8 + 0.2 = 1).

## 5.2 Policy: the agent's plan

A **policy** is the agent's plan: for every state, which action to take. "In (0,0) go Right; in (1,0) go Up" is a policy. A plan can also be random, for example "go Right 70% of the time". The **optimal policy** is the plan that collects the most reward.

## 5.3 The discount γ: why later points are worth less

Points you get later count for a little less than points you get now. With γ = 0.9, a reward one step away is worth 90% of its size, two steps away 0.9 × 0.9 = 0.81 (81%), and so on. There are three reasons:

1. **Uncertainty:** something far in the future might not happen.
2. **Sooner is better:** reaching the goal in fewer moves is usually what we want.
3. **Maths:** in a game that never ends, the total stays a finite number.

> **Worked example — cheese at the end of the maze**
>
> The mouse gets 0, 0, 0 for its first three moves and then +10 for reaching the cheese on the fourth move. With γ = 0.9 that +10, three steps after the first reward, is worth 0.9 × 0.9 × 0.9 × 10 = 0.729 × 10 = **7.29** now. With γ = 0.5 it would be worth only 0.125 × 10 = **1.25**: a smaller γ makes the agent care much less about far-away rewards.

## 5.4 The return and the value

The **return** is the total of all the rewards from now on, each one discounted by how far away it is:

**Formula in words:** return = this reward + 0.9 × next reward + 0.81 × the one after + …

The **value** V(s) of a state is the return you expect if you start there and follow your plan. **Q(s, a)** is the same, but you first take action a and then follow the plan.

> **Worked example — computing a value by hand**
>
> Plan: "in (0,0) go Right; in (1,0) go Up". From (0,0) you get 0 (moving to (1,0)) and then +1 (moving into the goal). So V((0,0)) = 0 + 0.9 × 1 = **0.9**.
>
> From (1,0) the very next move earns +1, so V((1,0)) = **1**. The goal itself has V((1,1)) = **0**, because the game is over and nothing more can be collected.

> **Common mistake**
>
> The +1 for reaching the goal belongs to the square **before** the goal, not to the goal. That is why V((1,0)) = 1 but V((1,1)) = 0. This is the most common beginner error in this module.

> **Going deeper (optional): the formal definitions**
>
> Return: G<sub>t</sub> = R<sub>t+1</sub> + γR<sub>t+2</sub> + γ²R<sub>t+3</sub> + … State value: V<sub>π</sub>(s) = E<sub>π</sub>[G<sub>t</sub> | S<sub>t</sub> = s]. Action value: Q<sub>π</sub>(s, a) = E<sub>π</sub>[G<sub>t</sub> | S<sub>t</sub> = s, A<sub>t</sub> = a]. E means "average over many runs", needed when moves are uncertain.

> **Check Q5.1. With a plan that goes Right from (0,1), what is V((0,1))?**
>
> **Answer.** Right enters the goal and earns +1, then nothing more: V = 1 + 0.9 × 0 = 1.

> **Activity 5.1 — Change the discount**
>
> Using the plan from the worked example, what is V((0,0)) if γ = 0.5? Explain the change in one sentence.

> **Answer**
>
> V((0,0)) = 0 + 0.5 × 1 = 0.5. The reward is one step away, so a smaller γ shrinks it more.

> **Activity 5.2 — Find the error**
>
> A student describes a card game with the state "the cards in the player's hand". A classmate says this breaks the Markov property. Who is right, and how should the state be fixed?

> **Answer**
>
> The classmate is right. Two situations with the same hand but different cards already played need different actions. Fix: add the cards already played, the discard pile and the opponent's visible cards to the state.

> **Remember**
>
> Policy = plan. γ makes later rewards smaller. Value = the points you expect from here if you follow the plan.

---

# 6. Learning With or Without a Map

> **The big idea**
>
> A "model" is the agent's map of how the world works. Model-based agents plan with the map; model-free agents learn good habits directly from experience.

## 6.1 What a model is

A **model** answers: "if I am here and do this, where will I end up and how many points will I get?" For the grid, the model is the table in Example 2 (Our Two Running Examples).

![Model-based learning plans with a map of the world; model-free learning learns values or habits directly from experience.](modules/behavioural-ai/figures/model-based-vs-model-free.png)

*Figure 4. Model-based versus model-free learning.*

- **Model-based:** the agent has (or learns) the map, then plans by imagining moves ahead.
- **Model-free:** the agent never builds a map; it learns which actions are good straight from experience.

## 6.2 An everyday comparison

A **model-based** person in a new city studies the map first, then plans routes without walking them. A **model-free** person just learns "leave home, turn left, arrive at work" by repetition. No map, but the habit works, until a road closes and they have to find a detour by trial and error.

In the maze: a mouse that has explored before and remembers the layout can plan a route in its head (model-based); a mouse that simply repeats "left, left, right" because it worked last time is model-free.

> **Check Q6.1. A robot vacuum has a stored floor plan and calculates a route from it. Model-based or model-free?**
>
> **Answer.** Model-based: the floor plan is the model, and the route is planned on it.

> **Activity 6.1 — Choose an approach**
>
> Robot A works in a fixed warehouse with an accurate stored floor plan. Robot B works in a new building every week with no map. Which should be model-based and which model-free? Give one reason each.

> **Answer**
>
> Robot A: model-based, because an accurate map already exists, so planning on it is efficient. Robot B: model-free, because there is no map and building one every week is costly, so it learns directly from experience.

> **Remember**
>
> Model = map of the world. Sections 8–11 have the map; Sections 13–17 do not.

---

# 7. The Bellman Equation: The One Idea Behind Everything

> **The big idea**
>
> The value of where you are = the reward for your next step + the discounted value of where you land. Every method in this module is a way of using this one sentence.

## 7.1 The idea in one sentence

Think of the mouse at a junction: "how good is this junction?" equals "the reward I get for my next move" plus "90% of how good the next junction is". You do not have to think about the whole game at once, only one step plus the value of what comes next.

**Formula in words:** value here = reward now + γ × value of the next state.

For the grid, where every move has a certain result, that is simply:

**V(s) = r + γ × V(s′)**

## 7.2 The best possible value

If you can choose your action, work out "reward + γ × next value" for **each** action and keep the **biggest**:

**best V(s) = the largest of ( r + γ × V(s′) ) over all actions**

The best possible values are written V\* (say "V-star").

> **Worked example — one Bellman step**
>
> In the 2×2 grid, suppose we already know V\*((1,0)) = 1 and V\*((0,1)) = 1. What is V\*((0,0))?
>
> - Right: reward 0, land in (1,0) → 0 + 0.9 × 1 = 0.9
> - Up: reward 0, land in (0,1) → 0 + 0.9 × 1 = 0.9
>
> The biggest is 0.9, so V\*((0,0)) = **0.9**. Both moves are equally good: there can be more than one best plan.

> **Going deeper (optional): the general Bellman equations**
>
> When moves are uncertain and the plan may be random, we average over both. Expectation form (fixed plan π): V<sub>π</sub>(s) = Σ<sub>a</sub> π(a | s) Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V<sub>π</sub>(s′) ]. Optimality form: V\*(s) = max<sub>a</sub> Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V\*(s′) ]. The action-value version, Q\*(s, a) = Σ<sub>s′</sub> P(s′ | s, a) [ R + γ max<sub>a′</sub> Q\*(s′, a′) ], is what Q-learning (Section 14) learns from experience.

## 7.3 Why it is so powerful

"Get the most points over the whole game" sounds impossible to calculate. Bellman turns it into a small step repeated many times: "best next move, given how good the next state is". Sections 8–17 are all different ways of repeating that small step.

> **Check Q7.1. Suppose V\*((1,0)) = 1 but V\*((0,1)) = 0. What is the best action from (0,0), and V\*((0,0))?**
>
> **Answer.** Right: 0 + 0.9 × 1 = 0.9. Up: 0 + 0.9 × 0 = 0. Right is best and V\*((0,0)) = 0.9.

> **Activity 7.1 — Find the error**
>
> A classmate writes the Bellman equation as "V(s) = r + V(s′)". Compared with this section, what is missing? Give three things (one is in the main text, two are in the optional box).

> **Answer**
>
> (1) The discount γ in front of V(s′). (2) The choice of the best action (or, for a fixed plan, the average over the plan's actions). (3) The average over the possible next states when moves are uncertain.

> **Remember**
>
> Value here = reward now + γ × value next. For the best value, try every action and keep the biggest.

---

# 8. Dynamic Programming (1): Measuring a Plan

> **The big idea**
>
> If we have the map, we can work out how good a plan is by applying the Bellman sentence to every square, over and over, until the numbers stop changing.

## 8.1 What "dynamic programming" means here

**Dynamic programming (DP)** means solving a big problem by solving small pieces and reusing the answers. Here the small piece is the Bellman step from Section 7. DP needs the map (the model), so it is **model-based**.

## 8.2 The question: how good is this plan?

**Policy evaluation** answers one question: *for a fixed plan, what is the value of each square?* It measures the plan; it does not change it.

## 8.3 The method, step by step

1. Start with every value at 0.
2. Do a **sweep**: for every square, recompute value = reward + γ × value of the square the plan leads to. Use the values from the *previous* sweep on the right-hand side.
3. Repeat sweeps until no value changes (or changes by less than a tiny amount, such as 0.001).

## 8.4 Worked example: sweeps on the 2×2 grid

Plan: "go Right if you can; otherwise go Up". So (0,0) goes Right, (1,0) goes Up (Right is blocked) and (0,1) goes Right. γ = 0.9.

| Sweep | V((1,1)) goal | V((1,0)) | V((0,1)) | V((0,0)) |
|---|---|---|---|---|
| 0 (start) | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 2 | 0 | 1 | 1 | 0.9 |
| 3 | 0 | 1 | 1 | 0.9 (no change: finished) |

> **Worked example — how each number was found**
>
> **Sweep 1.** (1,0): the plan goes Up into the goal, reward +1, so V = 1 + 0.9 × 0 = **1**. (0,1): the plan goes Right into the goal, so V = **1**. (0,0): the plan goes Right to (1,0), reward 0, and the *old* value of (1,0) is still 0, so V = 0 + 0.9 × 0 = **0**.
>
> **Sweep 2.** Only (0,0) changes: 0 + 0.9 × 1 = **0.9**, now using the sweep-1 value of (1,0).
>
> **Sweep 3.** Nothing changes, so we stop.

![Value spreads backwards from the goal, one square per sweep.](modules/behavioural-ai/figures/value-spreads-backwards.png)

*Figure 5. Value travels backwards from the goal, one step per sweep. Squares next to the goal fill in first.*

> **Check Q8.1. Why does V((1,0)) become 1 in sweep 1, and not 0?**
>
> **Answer.** The +1 is earned on the move from (1,0) into the goal, so it counts in the value of (1,0). The goal itself is worth 0.

> **Activity 8.1 — One more sweep**
>
> Start from the finished values above, but change γ to 0.5. Do one sweep. What are the new values?

> **Answer**
>
> V((1,1)) = 0; V((1,0)) = 1; V((0,1)) = 1; V((0,0)) = 0 + 0.5 × 1 = 0.5. The squares next to the goal keep 1; the start square drops because its reward is one step away and is discounted more.

> **Activity 8.2 — Find the error**
>
> A student reports these sweep-2 values with γ = 0.9 (and V((1,0)) = 1 from sweep 1): V((1,0)) = 0, V((0,1)) = 1, V((0,0)) = 0.5. Find the errors and correct them.

> **Answer**
>
> V((1,0)) = 0 is wrong: the plan goes Up into the goal, so V((1,0)) = 1 + 0.9 × 0 = 1. Then V((0,0)) = 0 + 0.9 × 1 = 0.9, not 0.5. Correct values: 0, 1, 1, 0.9.

> **Going deeper (optional): the update as a formula**
>
> V(s) ← Σ<sub>a</sub> π(a | s) Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V(s′) ], applied to every state in each sweep. Using the previous sweep's values on the right is called a synchronous sweep.

> **Remember**
>
> Policy evaluation = sweep the Bellman sentence over every square until the values settle. Value flows backwards from the goal.

---

# 9. Dynamic Programming (2): Improving a Plan

> **The big idea**
>
> Once you know the values, look at each square and ask: "is there a move that does better than my plan's move?" If yes, switch to it.

## 9.1 The idea

At each square, try every action once, using the values you already have: score = reward + γ × value of where you land. Pick the action with the highest score. This is called being **greedy** with respect to the values.

## 9.2 Why it always helps

The **policy improvement theorem** promises that the new plan is never worse than the old one, in any square. If nothing changes, the plan was already the best possible. This is why "measure, then improve" works.

> **Worked example — improving the Section 8.4 plan**
>
> Values: V((0,0)) = 0.9, V((1,0)) = 1, V((0,1)) = 1, goal = 0. γ = 0.9.
>
> - **At (0,0):** Right → 0 + 0.9 × 1 = 0.9; Up → 0 + 0.9 × 1 = 0.9. A tie, so the plan is already as good as possible here.
> - **At (1,0):** Up → 1 + 0.9 × 0 = 1; Right is blocked, so you stay: 0 + 0.9 × 1 = 0.9. Up is best (1 > 0.9).
> - **At (0,1):** Right → 1; Up is blocked: 0 + 0.9 × 1 = 0.9. Right is best.
>
> No square changes, so this plan is already optimal.

> **Going deeper (optional): argmax**
>
> The improved plan is π′(s) = argmax<sub>a</sub> Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V<sub>π</sub>(s′) ]. "argmax" means "the action that gives the biggest value" (the action itself, not the number). If Q(Left) = 2 and Q(Right) = 5, argmax is Right.

> **Check Q9.1. If V((0,1)) were 0.5 instead of 1, which action would improvement choose at (0,0)?**
>
> **Answer.** Right: 0 + 0.9 × 1 = 0.9, versus Up: 0 + 0.9 × 0.5 = 0.45. Right wins.

> **Remember**
>
> Improve = at every square, switch to the move with the best "reward + γ × next value". It can never make things worse.

---

# 10. Value Iteration

> **The big idea**
>
> Value iteration skips the separate "measure the plan" stage: at every square it immediately uses the best move. It is the Bellman "keep the biggest" step, swept again and again.

## 10.1 How it works

1. Start with every value at 0.
2. In each sweep, for every square, try every action and keep the **biggest** reward + γ × next value (using last sweep's values).
3. Stop when the values stop changing.
4. Read off the plan: in each square, pick the action that gave the biggest number.

## 10.2 Worked example: the 2×2 grid

| Sweep | V((1,1)) goal | V((1,0)) | V((0,1)) | V((0,0)) |
|---|---|---|---|---|
| 0 (start) | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 0 |
| 2 | 0 | 1 | 1 | 0.9 |
| 3 | 0 | 1 | 1 | 0.9 (finished) |

**Reading off the plan.** At (0,0) Right and Up both give 0.9, so either is best. At (1,0) Up is best. At (0,1) Right is best.

> **Worked example — value iteration on the 1×3 corridor**
>
> Cells 1, 2, 3; cell 3 is the goal (+1 for entering); actions Left and Right; walls leave you in place; γ = 0.9. The goal's value is always 0.
>
> | Sweep | V(1) | V(2) | V(3) |
> |---|---|---|---|
> | 0 | 0 | 0 | 0 |
> | 1 | 0 | 1 | 0 |
> | 2 | 0.9 | 1 | 0 |
> | 3 | 0.9 | 1 | 0 (finished) |
>
> **Sweep 1.** Cell 2: Right = 1 + 0.9 × 0 = 1; Left = 0 + 0.9 × 0 = 0 → keep 1. Cell 1: Right = 0 + 0.9 × 0 = 0 (cell 2 was still 0); Left = 0 → 0.
> **Sweep 2.** Cell 1: Right = 0 + 0.9 × 1 = 0.9 → 0.9. The best plan is Right in both cells.

> **Going deeper (optional): why it always finishes**
>
> The update is V<sub>k+1</sub>(s) ← max<sub>a</sub> Σ<sub>s′</sub> P(s′ | s, a) [ R(s, a, s′) + γ V<sub>k</sub>(s′) ]. When γ < 1, each sweep shrinks the difference between any two guesses by at least the factor γ (mathematicians call this a **contraction**), so the values must settle on one final answer (a **fixed point**).

> **Check Q10.1. Why does V((0,0)) stay 0 in sweep 1?**
>
> **Answer.** Sweep 1 uses the old values, and at the start (1,0) and (0,1) were both 0. Value moves back one square per sweep.

> **Activity 10.1 — Change the discount**
>
> Run value iteration on the 2×2 grid with γ = 0.5. What is the final V\*((0,0))? Why did it change?

> **Answer**
>
> V\*((1,0)) = 1, V\*((0,1)) = 1, V\*((0,0)) = 0 + 0.5 × 1 = 0.5. It is smaller because its reward is one step away and is discounted more when γ is smaller.

> **Activity 10.2 — Choose a method**
>
> A grid world has 10,000 squares. Would you try value iteration or policy iteration (Section 11) first? Why?

> **Answer**
>
> Value iteration first: each sweep is cheap, while each round of policy iteration must fully measure the plan, which is expensive with 10,000 squares. Policy iteration is worth trying if you already have a good starting plan, because it then finishes in very few rounds.

> **Remember**
>
> Value iteration = repeat "keep the biggest reward + γ × next value" everywhere until it settles, then read off the plan.

---

# 11. Policy Iteration

> **The big idea**
>
> Policy iteration alternates two stages, measure the plan, then improve it, until the plan stops changing.

## 11.1 The method

1. Start with any plan (for example "always Right").
2. **Measure:** work out the plan's values (Section 8).
3. **Improve:** at each square switch to the best move (Section 9).
4. If no square changed, stop: the plan is optimal. Otherwise go back to step 2.

![Value iteration and policy iteration are two routes to the same optimal plan.](modules/behavioural-ai/figures/value-vs-policy-iteration.png)

*Figure 6. Two routes to the same optimal plan.*

## 11.2 Value iteration vs policy iteration

| | Value iteration | Policy iteration |
|---|---|---|
| What repeats | One "keep the biggest" sweep | Full measuring, then improving |
| When is the plan read off? | At the end | At every improve step |
| Cost per round | Cheap, but many rounds | Expensive, but few rounds |
| Stops when | Values stop changing | The plan stops changing |
| Good for | Very large worlds | When measuring is affordable or a good starting plan exists |

Both reach the same best plan. Choosing between them is about speed, not correctness.

> **Worked example — policy iteration on the 2×2 grid (γ = 0.9)**
>
> **Start:** plan = "always Right".
>
> **Measure.** (0,1): Right enters the goal → V = 1. (1,0): Right is blocked, so the agent stays for ever and earns nothing → V = 0. (0,0): Right leads to (1,0), worth 0 → V = 0 + 0.9 × 0 = 0.
>
> **Improve.** At (1,0): Up = 1 + 0.9 × 0 = 1 versus Right = 0 + 0.9 × 0 = 0 → switch to **Up**. At (0,1): Right = 1 versus Up (blocked) = 0.9 × 1 = 0.9 → keep **Right**. At (0,0): Right = 0.9 × 0 = 0 versus Up = 0.9 × 1 = 0.9 → switch to **Up**.
>
> **Measure the new plan.** V((1,0)) = 1, V((0,1)) = 1, V((0,0)) = 0.9 × 1 = 0.9.
>
> **Improve again.** At (0,0) Right = 0.9 and Up = 0.9 tie, so keep Up. Nothing changes, so the plan is optimal. It took two improve steps.

> **Check Q11.1. Why does policy iteration stop when the plan stops changing, but value iteration stops when the values stop changing?**
>
> **Answer.** Policy iteration keeps an explicit plan, so "no move changed" is a clear stopping signal. Value iteration has no explicit plan until the end, so it watches the values instead.

> **Activity 11.1 — Policy iteration on the corridor**
>
> On the 1×3 corridor (goal +1 for entering cell 3, γ = 0.9), start with the plan "always Left". Run policy iteration. If two actions tie, keep the current one.

> **Answer**
>
> **Measure:** V(1) = V(2) = V(3) = 0 (the agent never reaches the goal). **Improve:** at 2, Right = 1 beats Left = 0 → Right; at 1, Right = 0.9 × 0 = 0 ties Left → keep Left. **Measure** (1: Left, 2: Right): V(2) = 1, V(1) = 0 (Left keeps it stuck). **Improve:** at 1, Right = 0.9 × 1 = 0.9 beats Left = 0 → Right. **Measure** (Right, Right): V(2) = 1, V(1) = 0.9. **Improve:** no change. Best plan: Right in both cells, with values (0.9, 1).

> **Remember**
>
> Policy iteration = measure → improve → repeat until the plan stops changing.

---

# 12. On-Policy and Off-Policy

> **The big idea**
>
> While learning, an agent may *behave* one way (with some random exploring) but be *learning about* a different plan (the best one). If the two are the same, it is on-policy; if they differ, it is off-policy.

> **Why this comes before the algorithms**
>
> The algorithms in Sections 13–17 are described as on-policy or off-policy, so we define the words first.

## 12.1 Two plans inside one agent

- The **behaviour policy** is the plan the agent actually follows while learning, for example ε-greedy with its random moves.
- The **target policy** is the plan the agent is trying to learn.

**On-policy:** the two are the same. The agent learns the value of exactly what it is doing, random mistakes included. Examples: SARSA, REINFORCE.

**Off-policy:** the two are different. The agent explores, but learns about the best plan. Examples: Q-learning, DQN.

| | On-policy | Off-policy |
|---|---|---|
| Behaviour vs target | The same | Different |
| What the update looks at next | The action actually taken next | The best possible next action |
| Examples | SARSA, REINFORCE | Q-learning, DQN |
| Can it learn from old data or another agent's data? | Not directly | Yes |
| What it learns | The value of the plan it really follows, mistakes included | The best plan, even while exploring |

## 12.2 In everyday terms

Think of a learner driver. Learning **on-policy** is like judging the routes you really drive, wrong turns included. Learning **off-policy** is like watching your own drives (or someone else's) but always asking "what would the *best* route have been?". Neither is always better: off-policy can reuse old experience; on-policy is often steadier and more realistic about the mistakes you will really make.

> **Check Q12.1. A robot explores with ε-greedy and learns with Q-learning. Is the plan it follows the same as the plan it is learning?**
>
> **Answer.** No. It behaves ε-greedily (sometimes random) but learns the best, fully greedy plan. That is off-policy.

> **Activity 12.1 — Classify the algorithm**
>
> Say whether each is on-policy or off-policy and what its update "looks at next": (a) SARSA, (b) Q-learning, (c) REINFORCE, (d) DQN.

> **Answer**
>
> (a) On-policy; the next action actually taken. (b) Off-policy; the best next action. (c) On-policy; the full return from its own episode. (d) Off-policy; the best next action, using a slowly updated copy of its network (Section 15.3).

> **Remember**
>
> On-policy learns about what it does. Off-policy learns about the best thing it could do.

---

# 13. Learning From Experience: The Algorithm Families, Monte Carlo and TD

> **The big idea**
>
> Without a map, an agent must learn values from what actually happens. It can wait for the end of a game and average the real total (Monte Carlo), or update after every single step using its next guess (TD). Everything after this section builds on TD.

## 13.1 The three families (a map of the rest of the module)

Up to Section 11 the agent knew the map. From now on it does not: it only has its own **experience**.

![The three model-free families: value-based, policy-based and actor–critic, with example algorithms.](modules/behavioural-ai/figures/three-model-free-families.png)

*Figure 7. The three model-free families and their example algorithms.*

| Family | What it keeps | What it learns from | Sections |
|---|---|---|---|
| **Value-based** | A score Q(s, a) for each move | The surprise (TD error) after each step | 14–15 |
| **Policy-based** | The plan itself, as adjustable numbers | The total reward of whole games | 16 |
| **Actor–critic** | Both a plan (actor) and a score-keeper (critic) | The critic's surprise after each step | 17 |

> **Check Q13.1. Which family suits a smooth action such as a steering angle, and why?**
>
> **Answer.** Policy-based or actor–critic. Value-based methods must find the best of all actions, which is awkward when there are infinitely many angles; a plan can output an angle directly.

## 13.2 The learning rate: the step every update takes

All the methods from here on update in the same way: they nudge the old estimate part of the way towards a better guess called the **target**.

**Formula in words:** new estimate = old estimate + α × (target − old estimate)

The gap "target − old estimate" is the **surprise**: how wrong we were. α, the learning rate, says how much of the gap to close. With α = 0.5 we move halfway; with α = 0.1 we move a tenth of the way, which is slower but steadier.

> **Everyday version**
>
> You guess your bus journey takes 20 minutes. Today it takes 30. You do not throw your old guess away, and you do not trust one day completely either. With α = 0.5 you move halfway: new guess = 20 + 0.5 × (30 − 20) = **25 minutes**. Every method from here on learns exactly like this.

![An update moves the old estimate part of the way towards the target.](modules/behavioural-ai/figures/update-step-toward-target.png)

*Figure 8. One update with α = 0.5: the old estimate 0.2 moves halfway towards the target 1.0, giving 0.6.*

## 13.3 Monte Carlo: wait until the end and average

**Monte Carlo (MC)** learning plays a whole game, then looks back: for each square it visited, it adds up the actual discounted rewards that followed (the **return**). That return is the target. Over many games, the values become the average of what really happened. No map is needed.

Everyday version: you only update your guess of how long your journey home takes **when you arrive**, using the real total time.

**Formula in words:** new V(square) = old V + α × (actual return after that square − old V)

Because the return is only known when the game ends, MC **updates only after the game finishes**, and so it only works for tasks that end.

> **Worked example — Monte Carlo on the 2×2 grid**
>
> The game from Activity 2.1: (0,0) —Right→ (1,0), reward 0; (1,0) —Right (blocked)→ (1,0), reward 0; (1,0) —Up→ goal, reward +1. γ = 0.9, α = 0.5, all values start at 0.
>
> | Step | Square | Actual return after this step | Return |
> |---|---|---|---|
> | 1 | (0,0) | 0 + 0.9 × 0 + 0.81 × 1 | 0.81 |
> | 2 | (1,0) | 0 + 0.9 × 1 | 0.9 |
> | 3 | (1,0) | 1 | 1 |
>
> **Updates** (using the first time each square was visited): V((0,0)) = 0 + 0.5 × (0.81 − 0) = **0.405**. V((1,0)) = 0 + 0.5 × (0.9 − 0) = **0.45**.
>
> After just one game, the reward at the end has already reached the start square.

> **Going deeper (optional): first-visit and every-visit**
>
> If a square is visited twice in one game, **first-visit MC** uses only the return after the first visit (as above); **every-visit MC** uses all of them. Every-visit would average 0.9 and 1 for (1,0), giving 0.95. Formally: V(S<sub>t</sub>) ← V(S<sub>t</sub>) + α [G<sub>t</sub> − V(S<sub>t</sub>)].

## 13.4 TD learning: update after every step

Waiting until the end is slow, and impossible if the game never ends. **Temporal-difference (TD)** learning updates after **every single step**. It does not know the full return yet, so it uses a shortcut target: the reward it just got plus γ × its *current guess* for the next square.

Everyday version: on your journey home you **update your arrival estimate at every stop**. If the first stop took longer than usual, you already know you will be late. You do not wait until you get home.

**Formula in words:** new V(here) = old V(here) + α × (reward + γ × V(next) − old V(here))

The bracket, target minus old guess, is the **TD error**, written δ ("delta"). It is the surprise from Figure 8. Using a guess to improve a guess is called **bootstrapping**; dynamic programming did the same (Section 8), but with the map instead of real experience. The goal's value is always 0.

> **Worked example — TD on the same game, played twice**
>
> γ = 0.9, α = 0.5, all values start at 0. Each row is one step, and the value changes immediately.
>
> | Game | Step | Target = reward + 0.9 × V(next) | δ = target − old | New value |
> |---|---|---|---|---|
> | 1 | (0,0) → (1,0) | 0 + 0.9 × 0 = 0 | 0 − 0 = 0 | V((0,0)) = 0 |
> | 1 | (1,0) → (1,0) | 0 + 0.9 × 0 = 0 | 0 − 0 = 0 | V((1,0)) = 0 |
> | 1 | (1,0) → goal | 1 (goal is worth 0) | 1 − 0 = 1 | V((1,0)) = 0.5 |
> | 2 | (0,0) → (1,0) | 0 + 0.9 × 0.5 = 0.45 | 0.45 − 0 = 0.45 | V((0,0)) = 0.225 |
> | 2 | (1,0) → (1,0) | 0 + 0.9 × 0.5 = 0.45 | 0.45 − 0.5 = −0.05 | V((1,0)) = 0.475 |
> | 2 | (1,0) → goal | 1 | 1 − 0.475 = 0.525 | V((1,0)) = 0.7375 |
>
> In game 1 only (1,0) changes, because only the last step had a reward. In game 2 the value spreads one more step back, to (0,0). This is the same "value flows backwards" pattern as Figure 5, but learned from experience instead of the map. With more games (and α made smaller over time), a learner following the Section 8.4 plan reaches the Section 8.4 values: V((1,0)) = 1 and V((0,0)) = 0.9.

> **Going deeper (optional): TD(0) in symbols**
>
> V(S<sub>t</sub>) ← V(S<sub>t</sub>) + α [ R<sub>t+1</sub> + γ V(S<sub>t+1</sub>) − V(S<sub>t</sub>) ], and δ = R<sub>t+1</sub> + γV(S<sub>t+1</sub>) − V(S<sub>t</sub>). The "0" in TD(0) means it looks just one step ahead.

## 13.5 From scoring squares to choosing moves

Sections 13.3–13.4 *score* squares for a fixed plan (**prediction**). To *improve* the plan without a map (**control**), the agent scores moves, Q(s, a), instead of squares, because choosing a move from square values would need the map to look ahead. Using the TD idea on Q gives the next two algorithms:

- **SARSA** (on-policy): target = reward + γ × Q(next square, the move actually taken next).
- **Q-learning** (off-policy): target = reward + γ × Q(next square, the best next move).

REINFORCE (Section 16) instead uses the Monte Carlo idea: the full return of the game.

## 13.6 DP vs Monte Carlo vs TD

| | Dynamic programming | Monte Carlo | TD |
|---|---|---|---|
| Needs the map? | Yes | No | No |
| Learns from | The map: all possible next squares | Whole games | Single steps |
| Target | Reward + γ × next value, averaged using the map | The actual return | Reward + γ × current guess of next value |
| Updates | Each sweep | After each game | After each step |
| Uses a guess to update a guess? | Yes | No | Yes |
| Works if the game never ends? | Yes | No | Yes |
| How noisy? | Not noisy (no sampling) | Noisy: one game's return can vary a lot | Steadier, but starts from rough guesses |
| Leads to | Value and policy iteration (10–11) | REINFORCE (16) | SARSA, Q-learning, DQN, actor–critic (14–17) |

![How far each method looks: DP looks one step at every possibility; MC follows one game to the end; TD takes one real step.](modules/behavioural-ai/figures/dp-mc-td-compared.png)

*Figure 9. How far each method looks ahead to build its target.*

> **Check Q13.3. Why can Monte Carlo not be used for a task that never ends?**
>
> **Answer.** The return is only known when the game ends, so MC would never get to make an update.

> **Activity 13.3 — One MC update and one TD update**
>
> V(s) = 0.4, γ = 0.9, α = 0.1. (a) A game from s produced a return of 1.0. What is the new V(s) with Monte Carlo? (b) Instead, one step from s gave reward 0 and the next square has V = 0.8. What are δ and the new V(s) with TD?

> **Answer**
>
> (a) 0.4 + 0.1 × (1.0 − 0.4) = 0.4 + 0.06 = **0.46**. (b) Target = 0 + 0.9 × 0.8 = 0.72; δ = 0.72 − 0.4 = 0.32; new V = 0.4 + 0.1 × 0.32 = **0.432**.

> **Exam-style practice**
>
> **Question (4 marks).** Compare Monte Carlo and TD learning, giving one advantage of each.
>
> **Checked answer.** MC updates from the actual full return at the end of a game **(1)**; TD updates after every step using reward + γ × the current guess of the next value **(1)**. MC advantage: it does not rely on other guesses, so it is correct on average **(1)**. TD advantage: it learns during the game, works when the game never ends, and is less noisy **(1)**.

> **Remember**
>
> Every update: new = old + α × (target − old). MC's target is the real total at the end; TD's target is reward + γ × next guess, after every step.

---

# 14. Q-Learning

> **The big idea**
>
> Q-learning keeps a score for every move in every square. After each step it nudges that score towards "the reward I just got + γ × the best score available next". In the end, the best move in each square is simply the one with the highest score.

## 14.1 The Q-table

Think of a table with a row for every square and a column for every move. Each cell holds Q(s, a): "how good is this move here?". At the start every cell is 0. The agent plays, and after every step it updates one cell.

| Square | Q(·, Right) | Q(·, Up) |
|---|---|---|
| (0,0) | starts 0 | starts 0 |
| (1,0) | starts 0 | starts 0 |
| (0,1) | starts 0 | starts 0 |

Once learning is done, the plan is: in each square, pick the column with the bigger number.

## 14.2 The update rule

**Formula in words:** new Q(here, move) = old Q + α × (reward + γ × best Q in the next square − old Q)

It is the same "step towards the target" as Figure 8. The target uses the **best** score in the next square. For the goal, the best next score is 0 because the game is over.

> **Worked example — one Q-learning update**
>
> Old Q(s, a) = 0.2. The agent gets reward r = 1 and lands on the goal, so the best next score is 0. γ = 0.9, α = 0.5.
>
> 1. Target = 1 + 0.9 × 0 = 1
> 2. Surprise (TD error) = 1 − 0.2 = 0.8
> 3. New Q = 0.2 + 0.5 × 0.8 = **0.6**
>
> These are exactly the numbers in Figure 8.

> **Going deeper (optional): the update in symbols**
>
> Q(s, a) ← Q(s, a) + α [ r + γ max<sub>a′</sub> Q(s′, a′) − Q(s, a) ]. max<sub>a′</sub> Q(s′, a′) means "the biggest Q-value over all moves a′ in the next state s′".

## 14.3 Exploring while learning

If the agent always picked its highest score, it might never try a move that is secretly better (Section 3.2). So it behaves ε-greedily: mostly the best move, sometimes a random one, with ε lowered over time.

## 14.4 Why Q-learning is off-policy

Its target uses the **best** next move, even if the agent is about to take a random one. So it learns about the best plan while behaving in an exploratory way: off-policy (Section 12).

> **Common mistake**
>
> "Q-learning always takes the greedy move." No. It *learns about* the greedy (best) plan, but it *behaves* ε-greedily so that it keeps exploring.

> **Check Q14.1. Why is Q-learning called off-policy?**
>
> **Answer.** Its target uses the best possible next move, whatever the agent actually does next, so it learns the best plan while behaving exploratorily.

> **Activity 14.1 — Trace a Q-learning update**
>
> Old Q(s, a) = 1.5, reward r = 0, γ = 0.9, best Q in the next square = 2, α = 0.1. Find the target, the surprise and the new Q.

> **Answer**
>
> Target = 0 + 0.9 × 2 = 1.8. Surprise = 1.8 − 1.5 = 0.3. New Q = 1.5 + 0.1 × 0.3 = **1.53**.

> **Activity 14.2 — Explain a decision**
>
> An engineer wants a robot vacuum to learn from data already recorded by other vacuums in the building. She chooses Q-learning, not SARSA. Explain why.

> **Answer**
>
> Q-learning is off-policy, so it can learn from data produced by a different behaviour (the other vacuums). SARSA is on-policy: its updates assume the actions came from its own current plan, so it cannot directly reuse other agents' data.

> **Remember**
>
> Q-learning: score every move; target = reward + γ × best next score; learns the best plan while exploring.

---

# 15. SARSA and Deep Q-Networks

> **The big idea**
>
> SARSA is Q-learning's careful twin: its target uses the move it will *really* take next, mistakes included. DQN replaces the Q-table with a neural network so the idea works in huge worlds such as video games played from the screen.

## 15.1 SARSA

**Formula in words:** new Q(here, move) = old Q + α × (reward + γ × Q(next square, the move actually taken next) − old Q)

The name lists the five things one update uses: **S**tate, **A**ction, **R**eward, next **S**tate, next **A**ction. Because it uses the move it really takes, SARSA is **on-policy**.

> **Worked example — Q-learning and SARSA side by side**
>
> In the 2×2 grid the agent is at (0,0), moves Up to (0,1) and gets reward 0. Old Q((0,0), Up) = 0.5, α = 0.1, γ = 0.9. In (0,1) the scores are Q(Right) = 1 and Q(Up) = 0 (Up hits the edge). This time the exploring agent is going to choose **Up** next.
>
> - **Q-learning** uses the *best* next score, 1: target = 0 + 0.9 × 1 = 0.9; new Q = 0.5 + 0.1 × (0.9 − 0.5) = **0.54**.
> - **SARSA** uses the move it *will* take, Up, worth 0: target = 0 + 0.9 × 0 = 0; new Q = 0.5 + 0.1 × (0 − 0.5) = **0.45**.
>
> Q-learning is optimistic ("I will play perfectly next"). SARSA is realistic ("I know I sometimes explore badly").

> **Going deeper (optional): SARSA in symbols**
>
> Q(s, a) ← Q(s, a) + α [ r + γ Q(s′, a′) − Q(s, a) ], where a′ is the action the agent actually chooses in s′.

## 15.2 The cliff walk: where the difference matters

![The cliff walk: the shortest path runs along the cliff edge; a safer path goes further away.](modules/behavioural-ai/figures/cliff-walk.png)

*Figure 10. The cliff walk. Falling off the cliff gives a big penalty and sends the agent back to the start.*

A grid has a cliff along the bottom. The shortest path hugs the edge; a safer path stays further away.

- **Q-learning** learns the edge path, because its target assumes perfect play from now on. That is best *if exploring stops* when the robot is used for real.
- **SARSA** learns the safer path, because its target includes the occasional random step that could fall off the edge.

In everyday terms: Q-learning happily walks right along the edge of a cliff path because it is the shortest route "if I never slip"; SARSA keeps a step away from the edge because it knows it sometimes stumbles.

> **Check Q15.1. In the cliff walk, which algorithm would a safety engineer prefer if the robot keeps exploring while in use?**
>
> **Answer.** SARSA. Its on-policy updates include the random steps the robot really takes, so it learns a path that is safe even with continued exploring.

## 15.3 Deep Q-Networks (DQN)

A Q-table needs one row for every state. A video-game screen has millions of pixels, so there are far too many possible screens to list. A **Deep Q-Network (DQN)** replaces the table with a **neural network**: a function made of layers of simple adjustable units. You give it the screen, and it gives back one score for each move.

Think of it like this: you have never walked down most streets in the world, but you can still guess whether a new street looks safe, because it looks like streets you know. In the same way, the network gives similar screens similar scores, so it can score screens it has never seen before.

Two tricks keep DQN stable:

- **Experience replay:** keep a memory of past steps and learn from small random handfuls of them (**minibatches**). Learning only from the last few steps is like revising only yesterday's lesson: they are all too similar.
- **Target network:** work out the targets with a second copy of the network that is updated only now and then. Otherwise the target moves every time the network learns, like trying to hit a goal that keeps sliding away.

DQN learned to play many Atari games from the screen alone (Mnih et al., 2015).

> **Activity 15.1 — DQN vs Q-table**
>
> Why can a DQN be used where a Q-table cannot? Give one example.

> **Answer**
>
> A Q-table needs one entry per state–move pair, which is impossible for states such as raw screen pixels. A DQN uses a neural network that gives similar scores to similar states, so it does not need a row for each one. Example: Atari games played from the screen.

> **Activity 15.2 — Choose a method**
>
> A robot's state is 512 continuous sensor readings. Is a Q-table or a DQN feasible? Why?

> **Answer**
>
> A DQN. With 512 continuous numbers there are infinitely many states, so a table is impossible. The network approximates the scores and generalises between similar readings, at the cost of being harder to train and debug.

> **Remember**
>
> SARSA = on-policy, uses the move it really takes, safer. DQN = Q-learning with a neural network instead of a table.

---

# 16. Learning the Plan Directly: REINFORCE

> **The big idea**
>
> Instead of scoring moves, adjust the plan itself: after each game, make the moves you took more likely if the game went well and less likely if it went badly.

## 16.1 Why learn the plan directly?

- When actions are amounts, not a short list. A steering wheel can turn to any angle, so there is no small table of moves to score.
- When the best plan is to be unpredictable. In rock–paper–scissors, always playing the same move loses.
- When we want behaviour to change gradually as learning goes on, not jump suddenly.

## 16.2 The idea in words

Think of the plan as a set of dials, one setting how likely each move is. **REINFORCE** plays a whole game, works out the return after each move, and then turns the dials so that each move it took becomes more likely, more so when the return after it was big. Moves followed by big returns are pushed up strongly; moves followed by poor returns are pushed up only a little (or pushed down, with a baseline, Section 16.3).

Everyday version: a basketball player who scores tends to repeat that shot more often; a shot that misses badly gets used less.

Because it uses whole-game returns, REINFORCE is a **Monte Carlo** method (Section 13.3) and is **on-policy**.

> **Worked example — the returns REINFORCE uses**
>
> A game has three moves with rewards 0, 0, then 1, and γ = 0.9. Work backwards from the end:
>
> - Return after the last move = 1
> - Return after the middle move = 0 + 0.9 × 1 = 0.9
> - Return after the first move = 0 + 0.9 × 0.9 = 0.81
>
> All three moves are made more likely, the last one most strongly because it was closest to the reward. Notice that every move gets some credit, even if one of them was actually a poor move.

> **Going deeper (optional): the policy gradient formula**
>
> With the plan written π<sub>θ</sub>(a | s) (θ = its adjustable numbers), REINFORCE updates θ ← θ + α G<sub>t</sub> ∇<sub>θ</sub> ln π<sub>θ</sub>(A<sub>t</sub> | S<sub>t</sub>) for each step t. ∇<sub>θ</sub> ln π<sub>θ</sub> points in the direction that makes the chosen action more likely, and G<sub>t</sub> scales the push by how good the result was. This comes from the policy gradient theorem, ∇<sub>θ</sub>J(θ) = E[ G<sub>t</sub> ∇<sub>θ</sub> ln π<sub>θ</sub>(A<sub>t</sub> | S<sub>t</sub>) ], where J(θ) is the expected return. (Some books include an extra factor γ<sup>t</sup>; practical code usually leaves it out.)

## 16.3 The noise problem and the fix

The return from one game can vary a lot just by luck, so REINFORCE's pushes are **noisy** (statisticians say it has *high variance*): correct on average, but jumpy from game to game, which makes learning slow.

The standard fix is a **baseline**: instead of the return, use "return minus what we normally expect here". A move then only gets pushed up if it did *better than usual*, and down if it did worse. The quantity "better than usual" is called the **advantage**. Actor–critic (Section 17) learns that baseline automatically.

> **Check Q16.1. In the worked example, why does the first move get less credit than the last one?**
>
> **Answer.** The reward is further away from the first move, so it is discounted more (0.81 versus 1).

> **Activity 16.1 — Compute returns**
>
> Rewards after moves 1 to 4 are 0, 2, 0, 1 and γ = 0.5. Find the return after each move (work backwards).

> **Answer**
>
> After move 4: 1. After move 3: 0 + 0.5 × 1 = 0.5. After move 2: 2 + 0.5 × 0.5 = 2.25. After move 1: 0 + 0.5 × 2.25 = **1.125**.

> **Activity 16.2 — Predict what happens**
>
> A learner uses a fixed baseline of 100 when returns are usually between 0 and 10. Predict what happens.

> **Answer**
>
> On average the direction of learning is unchanged, but every "return − 100" is about −90 to −100, so every move taken is pushed down hard each game. The updates are huge and jumpy, so learning becomes unstable. Fix: learn the baseline so that it tracks the returns you normally get.

> **Remember**
>
> REINFORCE: after each game, make the moves you took more likely, in proportion to how well things went. Noisy; a baseline helps.

---

# 17. Actor–Critic

> **The big idea**
>
> Two parts learn together: the **actor** chooses moves (the plan) and the **critic** judges them after every step ("better or worse than I expected?"). The actor listens to the critic.

## 17.1 How it works

![The actor–critic loop: the actor picks an action; the critic's TD error tells the actor how good it was.](modules/behavioural-ai/figures/actor-critic-loop.png)

*Figure 11. The actor–critic loop.*

- The **actor** is a plan, like REINFORCE's.
- The **critic** keeps a value V(s) for each state, learned by TD (Section 13.4).

After every step, the critic works out its surprise:

**Formula in words:** δ = reward + γ × V(next) − V(here)

- If δ > 0, things went **better** than expected, so the actor makes that move **more** likely.
- If δ < 0, things went **worse** than expected, so the actor makes that move **less** likely.
- The critic also moves V(here) towards its target, so its predictions improve.

This δ is the same TD error as in Section 13.4, and it plays the role of the "better than usual" advantage from Section 16.3.

> **Worked example — one actor–critic step**
>
> V(here) = 0.5, reward = 1, V(next) = 0.4, γ = 0.9.
>
> δ = 1 + 0.9 × 0.4 − 0.5 = 1 + 0.36 − 0.5 = **0.86**.
>
> δ is positive, so the actor makes this move more likely. The critic moves V(here) towards its target, 1 + 0.36 = 1.36.

> **Going deeper (optional): the two update rules**
>
> Advantage: A<sub>π</sub>(s, a) = Q<sub>π</sub>(s, a) − V<sub>π</sub>(s), estimated by δ = r + γV<sub>w</sub>(s′) − V<sub>w</sub>(s). Actor: θ ← θ + α δ ∇<sub>θ</sub> ln π<sub>θ</sub>(a | s). Critic: w ← w + β δ ∇<sub>w</sub> V<sub>w</sub>(s), where w are the critic's numbers and β its learning rate.

## 17.2 Why it learns faster than REINFORCE

REINFORCE waits until the end of a game and then uses one noisy total. Actor–critic gets a judgement after **every** step, and each one-step surprise is much less noisy than a whole-game total. More, steadier feedback means faster learning. Modern methods such as A2C and PPO, which have been used to train game-playing and robot agents, are actor–critic methods.

> **Check Q17.1. If δ = −0.3, what should the actor do to the probability of the move it took? Why?**
>
> **Answer.** Lower it: the result was worse than the critic expected.

> **Activity 17.1 — Compute a surprise**
>
> V(here) = 2.0, reward = 1, V(next) = 1.5, γ = 0.9. Find δ. Should the actor make the move more or less likely?

> **Answer**
>
> δ = 1 + 0.9 × 1.5 − 2.0 = 1 + 1.35 − 2.0 = **0.35**. Positive, so more likely.

> **Activity 17.2 — Explain in your own words**
>
> Explain why actor–critic usually learns faster than REINFORCE. If you use the word "variance", explain what it means.

> **Answer**
>
> REINFORCE updates once per game, using the game's total reward. Actor–critic updates after every step, using the critic's surprise, so it gets many more learning signals from the same play. "Variance" means how much a number jumps around from one try to the next: a whole game's total jumps around a lot, while a one-step surprise is steadier, so actor–critic's updates are less noisy.

> **Remember**
>
> Actor = plan, critic = judge. The critic's surprise δ after each step tells the actor what to do more or less often.

---

# 18. Real-World Applications and Reward Design

> **The big idea**
>
> RL is used wherever a system must make a sequence of decisions. In every case, the reward decides what behaviour is learned, so choosing the reward is a design decision with real consequences.

## 18.1 Where RL is used

For each example, ask two questions: **what is learned?** and **what reward is it chasing?**

| Area | Example | What is learned | Reward |
|---|---|---|---|
| Games | Agents for Atari, Go and chess | A plan and/or a value function | Game score, or win/loss |
| Recommendations | A video platform choosing what to show next | A ranking plan | Clicks, watch time |
| Robotics | A robot arm learning to grasp or pour, trained in simulation first | A control plan from sensors to motors | Task success, minus penalties for drops or collisions |
| Healthcare | A rehabilitation robot adjusting exercise difficulty | A personalisation plan | Measured patient progress |
| Energy | A building's heating learning when to pre-heat | A control plan | Minus energy cost, minus a discomfort penalty |
| Traffic | Traffic lights learning their timing | A signalling plan | Minus the average waiting time |

## 18.2 Reward design: "you get what you reward"

An RL agent will find **any** way to collect reward, including ways nobody intended. This is called **reward hacking**.

- In a real example, a boat-racing game agent rewarded for hitting targets learned to drive in circles hitting the same targets again and again, and never finished the race (Clark & Amodei, 2016).
- A recommender rewarded only for watch time may push extreme or repetitive videos that keep people watching but leave them feeling worse.
- A robot rewarded only for speed may learn unsafe shortcuts.

> **Why this matters**
>
> The reward is chosen by people, and it shapes the behaviour of the agent and, often, of the people using it. Before you trust an RL system, ask: **"What is the reward, who chose it, and whose behaviour does it shape?"**

> **Check Q18.1. In the heating example, why is a discomfort penalty needed?**
>
> **Answer.** Without it, the cheapest plan is to switch the heating off completely: "optimal" for the reward but unacceptable for the people in the building.

> **Activity 18.1 — Design a reward, predict the behaviour**
>
> A delivery drone is trained with RL. Propose a reward, predict one behaviour it will learn, then name one behaviour you did *not* intend.

> **Answer**
>
> Reward: +10 for an on-time delivery, −20 for a crash, −1 per minute late, −0.1 per unit of battery used. Intended: quick, efficient routes. Unintended: flying very close to buildings or trees to save time, because near-misses are not penalised. Fix: add a penalty for coming too close to obstacles, and test in simulation first.

> **Activity 18.2 — Find the error**
>
> A cleaning robot gets +10 for cleaning a dirty patch, −5 for bumping furniture and +1 per minute of running. It learns to circle and "clean" the same patch again and again. Find the flaw and fix it.

> **Answer**
>
> The +1 per minute rewards simply staying switched on, and the +10 can be earned repeatedly if the same patch is detected as dirty again. Fix: remove the per-minute bonus (or make it −1 per minute), mark patches as cleaned so they cannot pay twice, and add a bonus for finishing the whole room. Any part of a reward that can be exploited will be.

> **Remember**
>
> The agent learns whatever the reward pays for. Design it carefully and check for loopholes.

---

# 19. Mind Map and Summary

![Mind map of the Behavioural AI module.](modules/behavioural-ai/figures/mind-map.png)

*Figure 12. Mind map of the module.*

| Idea | One line to remember |
|---|---|
| Reinforcement learning | Learn from rewards by trial and error; no right answers given |
| MDP | States, actions, transitions, rewards, discount; the present state is enough (Markov) |
| Discount γ | Later rewards count less: 0.9, 0.81, 0.729, … |
| Value | Points you expect from here if you follow the plan |
| Bellman | Value here = reward now + γ × value next |
| Dynamic programming | Have the map: measure the plan, improve it, or do both at once (value iteration) |
| Update rule | new = old + α × (target − old) |
| Monte Carlo | Target = real total at the end of the game |
| TD | Target = reward + γ × next guess, after every step |
| Q-learning | Off-policy; target uses the best next move |
| SARSA | On-policy; target uses the move really taken next; safer |
| DQN | Q-learning with a neural network instead of a table |
| REINFORCE | Make taken moves more likely in proportion to the return; noisy |
| Actor–critic | Actor = plan; critic's surprise δ trains it every step |
| Reward design | You get what you reward; check for loopholes |

---

# 20. Case Studies

> **Case study 1 — The video recommender**
>
> A streaming service trains an RL recommender whose reward is total watch time. After launch, people watch more hours but report feeling worse and complain about repetitive, extreme content.
>
> **Tasks:** (a) name the agent, environment, action, state and reward; (b) explain what the agent learned that nobody intended; (c) propose a better reward and one safeguard; (d) who chose the reward, and whose behaviour does it shape?

> **Answer**
>
> (a) Agent = the recommendation plan; environment = the users and the video catalogue; action = which video to show; state = the user's history and context; reward = watch time. (b) It learned whatever keeps people watching, such as autoplay chains and sensational or repetitive content, whether or not it is good for them. (c) Combine watch time with satisfaction signals (surveys, "not interested" clicks, variety of content) and cap daily exposure; test changes on a small group first and monitor for harmful drift. (d) The company chose the reward; it shapes the behaviour of every user, so the company carries an ethical responsibility.

> **Case study 2 — The cliff-side delivery robot**
>
> A delivery robot crosses a campus where the shortest path runs beside a steep drop. It is trained in simulation with ε-greedy exploring and keeps exploring (ε = 0.1) after it starts work, so that it can adapt to new routes.
>
> **Tasks:** (a) would you choose Q-learning or SARSA, and why? (b) what would the other algorithm learn? (c) name two more safeguards.

> **Answer**
>
> (a) SARSA: it is on-policy, so it learns the value of what it really does, including the occasional random step, and therefore keeps away from the edge. (b) Q-learning would learn the shortest path right along the edge, which is only safe if exploring stops; with ε = 0.1 the robot would sometimes step off. (c) Explore only in simulation or switch exploring off near danger; add a large penalty for being near the edge; add a physical barrier or speed limit that does not depend on the learning at all.

> **Case study 3 — The smart classroom thermostat**
>
> A school wants an RL controller for one classroom's heating. Every 10 minutes it can set the heater to Off, Low or High. Sensors give the room temperature, the outside temperature, the time and whether the room is occupied.
>
> **Tasks:** (a) write the states, actions and reward; (b) would you use a model-based or a model-free method, and why? (c) which algorithm family suits three discrete actions? (d) name one behaviour your reward might cause that you did not intend.

> **Answer**
>
> (a) State = (room temperature, outside temperature, time of day, occupied?). Actions = Off, Low, High. Reward each step = −(energy used) − (a penalty for being outside 19–22 °C while the room is occupied). (b) Model-free is simpler if no accurate model of the building exists, but training should happen in a simulator because real-world trial and error is slow and uncomfortable; a model-based method is a good choice if a reliable physical model is available. (c) Value-based, for example DQN, because the temperature readings are continuous but there are only three actions. (d) If the comfort penalty only applies when the room is occupied, the heater may switch off overnight and leave the room cold when the first class arrives; add a penalty for the temperature at arrival time, or a pre-heating reward.

---

# 21. Mixed Practice

Try each question before you read the answer.

**P1.** A game gives rewards 1, 0, 3 and γ = 0.5. What is the return from the start?

> **Answer:** 1 + 0.5 × 0 + 0.25 × 3 = **1.75**.

**P2.** In one state, action A gives reward 0 and leads to a state worth 4; action B gives reward 2 and leads to a state worth 3. With γ = 0.9, which is better, and what is the best value?

> **Answer:** A: 0 + 0.9 × 4 = 3.6. B: 2 + 0.9 × 3 = 4.7. B is better; best value = **4.7**.

**P3.** An action succeeds with chance 0.8 (reward 10) and fails with chance 0.2 (reward 0); both end the game. What is its Q-value?

> **Answer:** Q = 0.8 × 10 + 0.2 × 0 = **8** (the average reward).

**P4.** Q(s, a) = 4, reward = 2, γ = 0.9, best next score = 5, α = 0.5. What is the new Q with Q-learning?

> **Answer:** Target = 2 + 0.9 × 5 = 6.5; surprise = 6.5 − 4 = 2.5; new Q = 4 + 0.5 × 2.5 = **5.25**.

**P5.** Same numbers, but the move actually taken next has a score of 2. What is the new Q with SARSA?

> **Answer:** Target = 2 + 0.9 × 2 = 3.8; surprise = 3.8 − 4 = −0.2; new Q = 4 + 0.5 × (−0.2) = **3.9**.

**P6.** On-policy or off-policy? (a) Learning the best plan from a log of another robot's moves; (b) REINFORCE; (c) SARSA.

> **Answer:** (a) Off-policy. (b) On-policy. (c) On-policy.

**P7.** Why is the goal (terminal) square always worth 0?

> **Answer:** The game is over, so no more reward can be collected; the reward for reaching the goal is counted in the square before it.

**P8.** Give one reason to use γ less than 1, and one problem with γ = 1.

> **Answer:** γ < 1 prefers sooner rewards and keeps totals finite. With γ = 1, a game that never ends can have an endless (infinite) total.

**P9.** V(s) = 0.6, reward = 0, V(next) = 1, γ = 0.9, α = 0.5. Do one TD update.

> **Answer:** Target = 0 + 0.9 × 1 = 0.9; δ = 0.9 − 0.6 = 0.3; new V = 0.6 + 0.5 × 0.3 = **0.75**.

---

# 22. End-of-Module Test

Total: 55 marks. Suggested time: 55 minutes. Answer without notes, then mark yourself with the scheme below.

## Questions

1. Define reinforcement learning and say how it differs from supervised learning. [3]
2. A thermostat learns to control heating. Identify the agent, the environment and one reward. [3]
3. Rewards in a game are 0, 0, 4 and γ = 0.5. Compute the return from the start. [2]
4. State the Markov property and give one example of a state that does not satisfy it. [3]
5. Corridor of cells 1, 2, 3 (+1 for entering 3, the goal), γ = 0.8, plan "always Right". Compute V(1) and V(2). [3]
6. Explain the difference between model-based and model-free learning. [2]
7. Write the Bellman optimality equation in words and say what γ does in it. [3]
8. Action A: reward 1, next best value 2. Action B: reward 0, next best value 3. γ = 0.9. Find the best value and the best action. [3]
9. Why does dynamic programming need the model? [2]
10. Give two differences between value iteration and policy iteration. [2]
11. Define behaviour policy and target policy. [2]
12. Why is Q-learning off-policy? [2]
13. Q(s, a) = 2, reward = 1, γ = 0.9, best next score = 3, α = 0.2. Compute the new Q with Q-learning. [3]
14. Same numbers, but SARSA, where the move actually taken next has score 1. Compute the new Q. [3]
15. In the cliff walk, which algorithm learns the safer path, and why? [2]
16. Name the two stabilising ideas in DQN and say what each does. [2]
17. Why are REINFORCE's updates noisy? Give one remedy. [2]
18. V(here) = 1.2, reward = 0.5, V(next) = 1, γ = 0.9. Compute δ and say what the actor does. [3]
19. Explain the roles of the actor and the critic. [3]
20. A recommender is rewarded for watch time. Describe two possible unintended behaviours and one ethical consequence. [4]
21. V(s) = 0.5, reward = 1, the next state is the goal, γ = 0.9, α = 0.2. Do one TD update and say why TD can learn before the game ends but Monte Carlo cannot. [3]

## Mark scheme

| Q | Answer (marks) |
|---|---|
| 1 | An agent learns to act by interacting with an environment and receiving rewards (1); trial and error, no correct answers given (1); supervised learning is given the correct output for each input, RL only a reward saying how good the result was (1). |
| 2 | Agent: the heating controller (1); environment: the room and the weather (1); reward, e.g. −energy used minus a penalty for being too cold (1). |
| 3 | 0 + 0.5 × 0 + 0.25 × 4 (1) = 1 (1). |
| 4 | The current state contains everything needed to predict what happens next; the history adds nothing (2); example: only the cards in your hand, or one camera image that cannot show what is behind a robot (1). |
| 5 | V(2) = 1 + 0.8 × 0 = 1 (1); V(1) = 0 + 0.8 × 1 = 0.8 (2). |
| 6 | Model-based uses or learns the map (transitions and rewards) and plans with it (1); model-free learns values or a plan directly from experience (1). |
| 7 | The best value of a state is the best action's reward now plus the discounted value of the next state (2); γ makes future value count less than immediate reward (1). |
| 8 | A: 1 + 0.9 × 2 = 2.8; B: 0 + 0.9 × 3 = 2.7 (2); best value 2.8, action A (1). |
| 9 | Its update adds up over every possible next state using the transition chances and rewards, so these must be known (2). |
| 10 | Any two: value iteration merges measuring and improving, policy iteration alternates them; value iteration stops when values settle, policy iteration when the plan stops changing; value iteration sweeps are cheap, policy iteration rounds are expensive (1 each). |
| 11 | Behaviour policy: the plan used to choose actions while learning (1). Target policy: the plan being learned (1). |
| 12 | Its target uses the best next move (1), whatever the agent actually does next, so it learns the best plan while exploring (1). |
| 13 | Target = 1 + 0.9 × 3 = 3.7; surprise = 1.7 (1); new Q = 2 + 0.2 × 1.7 (1) = 2.34 (1). |
| 14 | Target = 1 + 0.9 × 1 = 1.9; surprise = −0.1 (1); new Q = 2 + 0.2 × (−0.1) (1) = 1.98 (1). |
| 15 | SARSA (1): its on-policy target includes the exploring steps that could fall off the cliff (1). |
| 16 | Experience replay: learning from random handfuls of stored steps breaks the link between similar consecutive steps (1). Target network: a copy updated only now and then keeps the target steady (1). |
| 17 | One game's return varies a lot by luck (1); remedy: subtract a baseline, or use a critic (actor–critic) (1). |
| 18 | δ = 0.5 + 0.9 × 1 − 1.2 (1) = 0.2 (1); positive, so the actor makes the move more likely (1). |
| 19 | Actor: the plan that chooses moves (1). Critic: a value function that judges them (1) and supplies the TD error used to update the actor and itself (1). |
| 20 | Any two unintended behaviours, e.g. promoting sensational or addictive content, ignoring wellbeing, showing repetitive content (1 each); ethical consequence, e.g. it shapes users' behaviour for the platform's benefit, so its designers are responsible for the reward chosen (2). |
| 21 | Target = 1 + 0.9 × 0 = 1; δ = 1 − 0.5 = 0.5; new V = 0.5 + 0.2 × 0.5 = 0.6 (2); TD's target uses the next state's current guess, available after one step, whereas MC needs the full return, known only at the end (1). |

---

# 23. Learning Material List

Titles are given so that you can find them; check availability before relying on a link.

| Resource | Type | Use it for |
|---|---|---|
| Sutton & Barto, *Reinforcement Learning: An Introduction* (2nd ed.), free online from the authors | Textbook | The standard reference; chapters 1–6 match Sections 1–14 |
| David Silver, *Introduction to Reinforcement Learning* lectures (UCL / DeepMind, YouTube) | Video lectures | Lectures 1–7 match Sections 4–17 |
| Hugging Face, *Deep Reinforcement Learning Course* | Free online course | Hands-on Q-learning and DQN with exercises |
| OpenAI, *Spinning Up in Deep RL* | Web tutorial | Policy gradients and actor–critic (Sections 16–17) |
| Gymnasium (Python library) | Software | Try FrozenLake and CliffWalking (Sections 14–15) |
| Stable-Baselines3 (Python library) | Software | Ready-made DQN, A2C and PPO |
| Mnih et al. (2015), *Human-level control through deep reinforcement learning* | Paper | The original DQN paper (Section 15.3) |

## Suggested path

1. Sections 1–7 with Sutton & Barto chapters 1–3.
2. Sections 8–11 with Silver lectures 2–3.
3. Sections 12–15: run Q-learning on CliffWalking in Gymnasium and compare it with SARSA.
4. Sections 16–17 with Spinning Up.

---

# 24. Glossary

| Term | Meaning |
|---|---|
| **Action (a)** | A choice available to the agent. |
| **Actor–critic** | A method with a plan (actor) and a value function (critic) that learn together. |
| **Advantage** | How much better a move did than usual; estimated by the TD error δ. |
| **Agent** | The learner and decision-maker. |
| **Baseline** | "What we normally expect", subtracted from the return to make REINFORCE less noisy. |
| **Behaviour policy** | The plan the agent actually follows while learning. |
| **Bellman equation** | Value here = reward now + γ × value of the next state. |
| **Bootstrapping** | Updating a guess using another guess (DP and TD do this; Monte Carlo does not). |
| **Contraction** | (Optional) An update that always brings two guesses closer together; why value iteration settles. |
| **Credit assignment** | Working out which earlier actions deserve credit for a later reward. |
| **Discount (γ)** | How much a reward one step later is worth now (between 0 and 1). |
| **DQN** | Deep Q-Network: Q-learning with a neural network instead of a table. |
| **Dynamic programming** | Solving an MDP with the map, by sweeping the Bellman equation over all states. |
| **Environment** | Everything the agent interacts with. |
| **Episode** | One complete run from start to finish (one game). |
| **ε-greedy** | With chance ε do a random action; otherwise the best-known action. |
| **Experience replay** | Learning from random handfuls of stored past steps. |
| **Exploration / exploitation** | Trying something new / using what currently looks best. |
| **First-visit / every-visit MC** | Monte Carlo using only the first visit to a state in a game / every visit. |
| **Fixed point** | (Optional) A set of values that no longer changes when updated. |
| **Greedy** | Always choosing the action with the highest current score. |
| **Learning rate (α)** | How much of the gap between the old estimate and the target each update closes. |
| **Markov property** | The current state is enough to predict what happens next. |
| **MDP** | Markov Decision Process: states, actions, transitions, rewards, discount. |
| **Minibatch** | A small random handful of stored steps. |
| **Model** | The agent's map of the world: where each move leads and what it earns. |
| **Model-based / model-free** | Planning with a map / learning directly from experience without one. |
| **Monte Carlo (MC)** | Learning values by averaging the actual returns of complete games. |
| **Neural network** | A function made of layers of simple adjustable units; used in DQN. |
| **On-policy / off-policy** | Learns about the plan it follows / learns about a different (usually the best) plan. |
| **Policy (π)** | The agent's plan: which action to take in each state. |
| **Policy evaluation** | Working out the value of every state for a fixed plan. |
| **Policy gradient** | (Optional) Adjusting a plan's numbers in the direction that increases expected return. |
| **Policy improvement** | Switching, in every state, to the action with the best "reward + γ × next value". |
| **Policy iteration** | Repeating: evaluate the plan, then improve it, until it stops changing. |
| **Prediction / control** | Scoring a fixed plan / improving the plan. |
| **Q-learning** | Off-policy method that learns move scores using the best next move. |
| **Q-value Q(s, a)** | Expected return from taking action a in state s, then following the plan. |
| **REINFORCE** | Policy method that, after each game, makes the moves taken more likely in proportion to the return. |
| **Return** | The total of the rewards from now on, each discounted by how far away it is. |
| **Reward (r)** | The points given after an action. |
| **Reward hacking** | The agent exploiting a loophole in the reward instead of doing the intended task. |
| **SARSA** | On-policy method that learns move scores using the move actually taken next. |
| **State (s)** | A description of the current situation. |
| **Target** | The better guess an update moves towards. |
| **Target network** | A copy of the DQN network, updated only occasionally, used to compute steady targets. |
| **Target policy** | The plan the agent is trying to learn. |
| **TD error (δ)** | The surprise: target minus current estimate. |
| **TD learning** | Updating values after every step using reward + γ × the next state's current guess. |
| **Transition** | Where a move leads (and, if uncertain, with what chance). |
| **Value V(s)** | The return the agent expects from state s if it follows its plan. |
| **Value iteration** | Sweeping "keep the biggest reward + γ × next value" over all states until it settles. |
| **Variance** | How much a number jumps around from one try to the next ("noisiness"). |

---

# 25. References and Revision Notes

## 25.1 References

1. Sutton, R. S., & Barto, A. G. (2018). *Reinforcement Learning: An Introduction* (2nd ed.). MIT Press.
2. Bellman, R. (1957). *Dynamic Programming*. Princeton University Press.
3. Watkins, C. J. C. H., & Dayan, P. (1992). Q-learning. *Machine Learning*, 8, 279–292.
4. Rummery, G. A., & Niranjan, M. (1994). *On-line Q-learning using connectionist systems* (Technical Report CUED/F-INFENG/TR 166). Cambridge University Engineering Department.
5. Williams, R. J. (1992). Simple statistical gradient-following algorithms for connectionist reinforcement learning. *Machine Learning*, 8, 229–256.
6. Konda, V. R., & Tsitsiklis, J. N. (2000). Actor-critic algorithms. *Advances in Neural Information Processing Systems*, 12.
7. Mnih, V., et al. (2015). Human-level control through deep reinforcement learning. *Nature*, 518, 529–533.
8. Puterman, M. L. (1994). *Markov Decision Processes*. Wiley.
9. Skinner, B. F. (1938). *The Behavior of Organisms*. Appleton-Century.
10. Clark, J., & Amodei, D. (2016). Faulty reward functions in the wild. *OpenAI Blog*.

**Attribution.** The grid world, corridor and cliff-walk examples follow the standard teaching examples in Sutton & Barto (2018); all numbers in them were recalculated for this module.

## 25.2 Revision notes

| Version | Change | Where |
|---|---|---|
| 3.0 | Rewritten for beginners: every section now opens with **The big idea** and closes with **Remember**; plain-words explanation before every formula, with a **Formula in words** line | All sections |
| 3.0 | Symbols cut from 16 to the 8 needed for the core path; the rest moved into clearly labelled **Going deeper (optional)** boxes | Notation; Sections 2, 4, 5, 7–10, 13–17 |
| 3.0 | Added everyday analogies (a mouse learning a maze, a restaurant, a learner driver, a bus journey) alongside the 2×2 grid used for all calculations | Running examples; Sections 1–3, 5–7, 12, 13, 15, 18 |
| 3.0 | Added two figures: value spreading back from the goal, and an update as a step towards a target | Sections 8 and 13 |
| 3.0 | Merged the add-on Monte Carlo and TD material into Section 13, with a shared learning-rate explanation (13.2) used by Sections 14–17 | Section 13 |
| 3.0 | Added a Q-table illustration, a reward-hacking subsection, Mixed Practice P9, and test Q21 (TD learning); test total now 55 marks | 14.1, 18.2, 21, 22 |
| 3.0 | Mark scheme now shows how each mark is earned | 22 |
| 3.0 | Merged the glossary and its supplement into one alphabetical list in plain language | 24 |
| 3.0 | Removed edition labels (NEW badges, "What's new" page) from the learning path; duplicated activity titles fixed | Throughout |
| 2.1 | Added Monte Carlo and TD learning between dynamic programming and Q-learning | 13 |
| 2.0 | Corrected the policy-iteration and Q-learning vs SARSA examples; defined the return before first use; added figures, case studies, practice, test and learning material list | 5, 11, 15, 19–23 |

## 25.3 Optional extensions (beyond this module)

These are not part of the completed module and are not tested: exploration methods beyond ε-greedy (softmax, UCB), multi-step TD and eligibility traces, PPO and TRPO in detail, offline RL and multi-agent RL.
