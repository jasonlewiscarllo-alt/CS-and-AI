
# Computer Hardware & Microarchitecture

**Module 1**

Aligned with Cambridge IGCSE Computer Science 0478 / O Level 2210 and AS & A Level 9618

Integrated with D. Watson & H. Williams, Cambridge IGCSE and O Level Computer Science and Cambridge International AS & A Level Computer Science

Part of: Hardware, Networks and Behaviourist AI

------------------------------------------------------------------------

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

# Module overview and learning outcomes

This module introduces the physical components of a computer and the microarchitectural principles that let those components execute instructions. It starts with the parts you can touch, establishes the binary number system (the language all hardware speaks), and builds upward through logic gates, the Von Neumann model, the fetch–decode–execute cycle, the memory hierarchy, input/output devices, networks, embedded systems, monitoring and control, and processor specialisation.

**Prerequisite knowledge:** none beyond everyday familiarity with a computer. Binary is taught in Section 1.2 before any section that uses it, and every new term is defined before it is used.

> **By the end of this module you should be able to:**
>
> 1.  Identify the major internal components of a computer and state the role of each.
> 2.  Convert between binary, denary and hexadecimal, and explain why hexadecimal is used.
> 3.  State and use the units of data: bit, nibble, byte, KB, MB, GB, TB.
> 4.  Explain how transistors form logic gates and how gates form combinational and sequential circuits.
> 5.  Identify the registers and buses of the Von Neumann architecture and explain the role of each.
> 6.  Trace the fetch–decode–execute (FDE) cycle stage by stage, naming the registers and buses active at each step.
> 7.  Explain how interrupts and the interrupt service routine (ISR) work, and how pipelining speeds up instruction throughput.
> 8.  Explain why the memory hierarchy exists and compare DRAM and SRAM.
> 9.  Distinguish PROM, EPROM and EEPROM, and state appropriate uses for each.
> 10. Explain what buffers and virtual memory are, and why they exist.
> 11. Describe the principles of operation of common input and output devices, including sensors and actuators, and compare HDMI and VGA.
> 12. Compare local storage with cloud storage, and describe the network hardware that makes cloud storage possible.
> 13. Describe embedded systems, real-time constraints, and monitoring/control systems.
> 14. Compare CPU, GPU and TPU architectures in terms of latency and throughput.

## How to study this module

Every section follows the same rhythm, so you always know what to do next:

1.  **Read the objectives** (blue box) so you know the target.
2.  **Read the explanation** and study each figure. Redraw the figure from memory when you finish the section.
3.  **Follow the worked example** (purple box) line by line with a pencil.
4.  **Do the activity** (orange box) *before* reading the checked answer (green box).
5.  **Answer the exam-style question** (red box) in full sentences, then compare with the mark scheme.

> **Suggested study plan (about 6 weeks, 3 sessions per week)**
>
> | Week | Sections         | Focus                                               | Self-check                                               |
> |------|------------------|-----------------------------------------------------|----------------------------------------------------------|
> | 1    | 1.1, 1.2         | Components; binary, denary, hex conversions         | Convert 10 numbers each way without a calculator         |
> | 2    | 1.3, 1.4         | Logic gates, truth tables; registers and buses      | Draw the Von Neumann diagram from memory                 |
> | 3    | 1.5, 1.6         | FDE trace, interrupts, pipelining; memory hierarchy | Trace an ADD instruction register by register            |
> | 4    | 1.7, 1.8, 1.9    | RAM/ROM types; buffers, virtual memory; I/O devices | Make a one-page comparison table for DRAM/SRAM/ROM types |
> | 5    | 1.10, 1.11, 1.12 | Networks, cloud, embedded systems, CPU/GPU/TPU      | Explain a washing machine as a control system            |
> | 6    | 1.13 – 1.16      | Mind map, case studies, mixed practice, test        | Sit the end-of-module test under timed conditions        |
>
> **Learning suggestions:** (1) Use *retrieval practice*: close the book and write down everything you remember, then check. (2) Use *spaced repetition*: re-do the activities after 1 day, 1 week and 1 month. (3) Explain each concept aloud to someone else — if you cannot, you have found a gap. (4) Always show working in conversions; marks are usually awarded for method. (5) Pair each new term with a one-line everyday analogy (for example: a register is a sticky note on your desk, RAM is the desk, storage is the filing cabinet).

# Section 1.1 — Physical Parts of a Computer

> **Learning objectives**
>
> By the end of this section you should be able to name the main physical components inside a computer, state the purpose of each, and explain the difference between hardware, firmware, software and data.

## 1.1.1 What hardware actually means

**Hardware** is the set of physical parts of a computer that you can see, touch and (usually) move. It is contrasted with **software**, the instructions and data the hardware carries out and stores. Software has no physical form of its own; it exists as patterns stored in hardware.

| Term     | Meaning                                                                     | Example                              |
|----------|-----------------------------------------------------------------------------|--------------------------------------|
| Hardware | The physical parts                                                          | The CPU chip                         |
| Software | Programs and data stored as patterns in hardware                            | A web browser                        |
| Firmware | Software permanently stored in hardware, usually in ROM, and rarely changed | The BIOS/UEFI that starts a computer |
| Data     | Raw facts that programs process                                             | The numbers in a spreadsheet         |

A computer works only when all four cooperate. The hardware provides the physical capability, the firmware starts the machine, the software tells the hardware what to do, and the data is what gets processed.

## 1.1.2 The motherboard

The **motherboard** is the large circuit board that everything else plugs into. Its purpose is not to *do* computing itself but to *connect* the parts that do, and to supply them with power and communication pathways. It holds the CPU socket, the RAM slots, expansion slots for add-on cards, the **chipset** (support chips managing communication), storage connectors, input/output connectors, and the firmware chip holding the BIOS/UEFI.

Connections between components are made by **traces**: thin copper pathways printed into the board. Traces carry both electrical power and electrical signals. When a diagram shows a line between the CPU and RAM, that line represents a set of traces forming a **bus**, explained in Section 1.4.

> **Why this matters**
>
> A fast CPU connected by a slow or narrow pathway cannot perform at its full speed. The motherboard and its traces are part of the performance story.

![alt](./Assests/Screenshot%202026-11-02%20190346.png)

*Figure 1 — Motherboard block diagram. Traces carry both electricity and signals between components.*

## 1.1.3 The CPU

The **Central Processing Unit (CPU)** fetches instructions, decodes them and executes them. Inside are the Control Unit (CU), the Arithmetic Logic Unit (ALU), registers, and cache memory.

## 1.1.4 RAM: the workspace

**Random Access Memory (RAM)** is the short-term workspace. Programs and data currently in use are loaded into RAM for fast access. RAM is **volatile**: its contents are lost when power is removed.

> **Why RAM exists**
>
> SSDs and hard drives are much slower than the CPU. Without RAM, the CPU would spend most of its time waiting. RAM is the intermediate workspace fast enough to keep the CPU busy. Section 1.6 explains this speed gap.

## 1.1.5 ROM: permanent start-up instructions

**Read-Only Memory (ROM)** is **non-volatile**: it keeps its contents when power is switched off. ROM stores firmware, such as the BIOS/UEFI that starts the computer and checks the hardware before loading the operating system.

## 1.1.6 Secondary storage

- **HDD (hard disk drive)**: magnetic spinning platters; large capacity, relatively cheap, slower, sensitive to movement.
- **SSD (solid-state drive)**: flash memory chips, no moving parts; faster, quieter, more shock-resistant, more expensive per gigabyte.
- **USB flash drives and memory cards**: portable flash storage.

## 1.1.7 GPU and TPU

A **GPU (Graphics Processing Unit)** contains hundreds or thousands of small arithmetic units that operate concurrently, making it effective for graphics rendering and parallel numerical work. A **TPU (Tensor Processing Unit)** is an ASIC (application-specific integrated circuit) designed to accelerate machine-learning matrix operations. Its core is a **systolic array**: a grid of processing elements through which data flows in a regular rhythm.

## 1.1.8 The system clock

The **system clock** produces timing signals measured in hertz (Hz); 1 GHz is one billion ticks per second. Clock speed is one of three IGCSE performance factors, alongside cache size and number of cores.

## 1.1.9 Other common components

- **PSU**: converts mains electricity into DC voltages.
- **Cooling system**: fans, heat sinks or liquid cooling remove heat.
- **Expansion cards**: add graphics, Wi-Fi, sound, etc.
- **Case**: protects components and supports airflow.

> **Activity 1.1 — Identify the component**
>
> | Job                                     | Component |
> |-----------------------------------------|-----------|
> | Holds the program currently running     | ?         |
> | Starts the computer before the OS loads | ?         |
> | Performs arithmetic                     | ?         |
> | Connects all components                 | ?         |
> | Keeps files when power is off           | ?         |

> **Checked answers**
>
> | Job                                     | Component         |
> |-----------------------------------------|-------------------|
> | Holds the program currently running     | RAM               |
> | Starts the computer before the OS loads | ROM / firmware    |
> | Performs arithmetic                     | ALU               |
> | Connects all components                 | Motherboard       |
> | Keeps files when power is off           | Secondary storage |

> **Exam-style practice**
>
> **Question (2 marks).** Explain why RAM is described as volatile.
>
> **Checked answer.** RAM loses its contents when power is removed **(1)**, because it relies on electrical charge that is not maintained without power **(1)**.

## 1.1.10 Motherboard form factors

A **form factor** is a standard that defines a motherboard's physical dimensions, mounting-hole positions, and the layout of expansion slots and connectors. Form factors exist so that cases, power supplies and add-on cards from different manufacturers fit together. Without a recognised form factor, every case and PSU would have to be custom-made.

| Form factor         | Typical size  | Expansion slots | Typical use                                   |
|---------------------|---------------|-----------------|-----------------------------------------------|
| EATX (Extended ATX) | ~305 x 330 mm | Up to 7         | Workstations, servers, multi-GPU builds       |
| ATX (standard)      | ~305 x 244 mm | Up to 7         | Desktop PCs, gaming builds                    |
| Micro-ATX (mATX)    | ~244 x 244 mm | Up to 4         | Smaller desktops, budget builds               |
| Mini-ITX            | ~170 x 170 mm | 1–2             | Small-form-factor PCs, home theatre, embedded |

![Figure 2 — Relative sizes of the four main motherboard form factors.](figures/hardware/fig-02.svg)

*Figure 2 — Relative sizes of the four main motherboard form factors.*

> **Worked example — choosing a form factor**
>
> A user needs a gaming PC with two graphics cards, four RAM modules and a large air cooler. EATX or full ATX is best: more expansion slots, more RAM slots, and enough clearance for cooling. A user building a small home-theatre PC should choose Mini-ITX: it fits a compact case but limits slots and cooling options.

> **Activity 1.1.10 — Match the form factor**
>
> | Scenario                        | Best form factor | Reason |
> |---------------------------------|------------------|--------|
> | Dual-GPU scientific workstation | ?                | ?      |
> | Standard office desktop         | ?                | ?      |
> | Small home-theatre PC           | ?                | ?      |
> | Budget family PC                | ?                | ?      |

> **Checked answers**
>
> | Scenario                        | Best form factor | Reason                                                    |
> |---------------------------------|------------------|-----------------------------------------------------------|
> | Dual-GPU scientific workstation | EATX or ATX      | Most expansion slots; room for cooling and power delivery |
> | Standard office desktop         | ATX              | Standard, widely available, enough slots                  |
> | Small home-theatre PC           | Mini-ITX         | Smallest footprint, fits compact cases                    |
> | Budget family PC                | Micro-ATX        | Cheaper, smaller, enough slots for basic use              |

> **Exam-style practice**
>
> **Question (2 marks).** Explain why motherboard form factors are standardised.
>
> **Checked answer.** Standardisation ensures cases, power supplies and expansion cards fit together across manufacturers **(1)**, reducing cost and allowing upgrades **(1)**.

## 1.1.11 Power supply unit: internal mechanics

The **power supply unit (PSU)** converts the high-voltage alternating current (AC) from a wall socket into the low-voltage direct current (DC) that the computer's components need. The conversion happens in four stages.

![Figure 3 — The four stages of AC-to-DC conversion inside a PSU.](figures/hardware/fig-03.svg)

*Figure 3 — The four stages of AC-to-DC conversion inside a PSU.*

> **Worked example — why smoothing matters**
>
> After rectification the DC output still pulses: the diodes only allow current one way, but the voltage drops to zero between peaks. A smoothing capacitor charges during the peaks and discharges between them, filling the gaps. Without smoothing, sensitive components would receive a rippled supply and could malfunction.

> **Activity 1.1.11 — Order the stages**
>
> | Stage               | Position (1–4) | What it does |
> |---------------------|----------------|--------------|
> | Voltage regulator   | ?              | ?            |
> | Transformer         | ?              | ?            |
> | Smoothing capacitor | ?              | ?            |
> | Rectifier           | ?              | ?            |

> **Checked answers**
>
> | Stage               | Position | What it does                |
> |---------------------|----------|-----------------------------|
> | Transformer         | 1        | Steps AC voltage down       |
> | Rectifier           | 2        | Converts AC to pulsating DC |
> | Smoothing capacitor | 3        | Removes ripple              |
> | Voltage regulator   | 4        | Holds stable DC output      |

> **Exam-style practice**
>
> **Question (3 marks).** Describe how a PSU converts AC to DC.
>
> **Checked answer.** Transformer steps voltage down **(1)**; rectifier converts AC to DC using diodes **(1)**; smoothing capacitors remove ripple and a regulator holds a steady output **(1)**.

## 1.1.12 PSU internal components

Opening a PSU (only safely, with the unit unplugged and discharged) reveals a circuit board with several distinct components. Each plays a role in conversion, filtering or protection.

| Component           | Function                                                                    |
|---------------------|-----------------------------------------------------------------------------|
| Transformer         | Steps the AC voltage down using magnetic induction between coils.           |
| Rectifier diodes    | Allow current to flow in one direction only, converting AC to pulsating DC. |
| Capacitors          | Store charge and smooth out voltage ripple; also filter noise.              |
| Resistors           | Limit current and divide voltage; used in sensing circuits.                 |
| Rotary switch       | On some older PSUs, selects the input voltage (110 V or 230 V).             |
| Heatsinks           | Dissipate heat from power transistors and diodes.                           |
| Fan                 | Moves air through the unit to keep components within safe temperatures.     |
| Protection circuits | Shut down the PSU on over-voltage, over-current or short-circuit.           |

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

| Part                                   | Function                                                                                                  |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------|
| 1\. GPU chip                           | The processor itself; contains thousands of shader cores that execute rendering and parallel computation. |
| 2\. VRAM                               | Dedicated video memory that stores textures, framebuffers and working data for the GPU.                   |
| 3\. PCIe interface                     | The edge connector that plugs into the motherboard and carries data between CPU and GPU.                  |
| 4\. Heatsink + fan                     | Removes heat generated by the GPU chip and VRAM.                                                          |
| 5\. 6/8-pin auxiliary power connectors | Supply extra power beyond what the PCIe slot provides; needed for high-end GPUs.                          |
| 6\. Monitor outputs                    | HDMI, DisplayPort, DVI and other connectors that send video to displays.                                  |
| 7\. Video BIOS                         | Firmware that initialises the card at start-up and controls clock speeds and voltages.                    |

![Figure 4 — The seven main parts of a graphics card.](figures/hardware/fig-04.svg)

*Figure 4 — The seven main parts of a graphics card.*

> **Worked example — why auxiliary power matters**
>
> A high-end GPU can draw 250 W or more, but the PCIe slot provides only 75 W. Without the 6-pin and 8-pin auxiliary connectors, the card would not receive enough power and would throttle or fail to start. The PSU's PCIe power cables plug into these connectors.

> **Activity 1.1.13 — Match the GPU part**
>
> | Function                             | Part |
> |--------------------------------------|------|
> | Stores textures and framebuffers     | ?    |
> | Connects the card to the motherboard | ?    |
> | Supplies extra power beyond the slot | ?    |
> | Initialises the card at start-up     | ?    |
> | Removes heat from the GPU            | ?    |

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

| Unit          | Size           | Example use         |
|---------------|----------------|---------------------|
| bit           | 1 binary digit | one flag            |
| nibble        | 4 bits         | one hex digit       |
| byte          | 8 bits         | one ASCII character |
| KB (kilobyte) | 1024 bytes     | short text file     |
| MB            | 1024 KB        | photo               |
| GB            | 1024 MB        | video / RAM         |
| TB            | 1024 GB        | SSD / HDD           |

> **Convention note**
>
> In this module 1 KB = 1024 bytes because 1024 = 2<sup>10</sup>. This is the convention used in Cambridge papers. Storage manufacturers sometimes use 1000 bytes per KB. The IEC names the power-of-two units kibibyte (KiB), mebibyte (MiB) and so on. Use 1024 in exams unless told otherwise.

## 1.2.3 Binary place values

Each bit position has a value that is double the one to its right. To convert binary to denary, add the place values wherever there is a 1.

![Figure 5 — Binary place-value chart: 10110101 = 181.](figures/hardware/fig-05.svg)

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

![Figure 6 — Binary to hex grouping: 1101 0110 = D6.](figures/hardware/fig-06.svg)

*Figure 6 — Binary to hex grouping: 1101 0110 = D6.*

## 1.2.5 Conversion practice

| Task                        | Answer                                 |
|-----------------------------|----------------------------------------|
| 10110<sub>2</sub> to denary | 16 + 4 + 2 = 22<sub>10</sub>           |
| 45<sub>10</sub> to binary   | 101101<sub>2</sub>                     |
| 11101101<sub>2</sub> to hex | 1110 = E, 1101 = D, so ED<sub>16</sub> |
| B7<sub>16</sub> to denary   | 183<sub>10</sub>                       |
| 2C<sub>16</sub> to binary   | 0010 1100 = 00101100<sub>2</sub>       |
| 3 bytes = ? bits / nibbles  | 24 bits, 6 nibbles                     |

> **Activity 1.2 — Try it yourself**
>
> Convert: (a) 11001<sub>2</sub> to denary; (b) 100<sub>10</sub> to binary; (c) 3F<sub>16</sub> to denary; (d) 10101111<sub>2</sub> to hex.

> **Checked answers**
>
> \(a\) 16 + 8 + 1 = 25. (b) 64 + 32 + 4 = 01100100<sub>2</sub>. (c) 3 × 16 + 15 = 63. (d) 1010 = A, 1111 = F, so AF<sub>16</sub>.

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

![Figure 7 — Standard logic gate symbols.](figures/hardware/fig-07.svg)

*Figure 7 — Standard logic gate symbols.*

| A   | B   | AND | OR  | XOR | NAND | NOR | XNOR |
|-----|-----|-----|-----|-----|------|-----|------|
| 0   | 0   | 0   | 0   | 0   | 1    | 1   | 1    |
| 0   | 1   | 0   | 1   | 1   | 1    | 0   | 0    |
| 1   | 0   | 0   | 1   | 1   | 1    | 0   | 0    |
| 1   | 1   | 1   | 1   | 0   | 0    | 0   | 1    |

**Memory aids:** AND outputs 1 only if *both* inputs are 1. OR outputs 1 if *at least one* input is 1. XOR outputs 1 if the inputs are *different*. NOT inverts a single input. NAND, NOR and XNOR are AND, OR and XOR followed by NOT.

## 1.3.2 Combinational and sequential circuits

**Combinational circuits** depend only on the current inputs (adders, multiplexers, decoders). **Sequential circuits** depend on the current inputs *and* stored state, updated on clock ticks (flip-flops, latches). Flip-flops are the physical basis of registers and memory cells.

## 1.3.3 The half-adder

A half-adder adds two single bits, producing a **Sum** and a **Carry**.

![Figure 8 — Half-adder: XOR gives the Sum, AND gives the Carry.](figures/hardware/fig-08.svg)

*Figure 8 — Half-adder: XOR gives the Sum, AND gives the Carry.*

| A   | B   | Sum (XOR) | Carry (AND) |
|-----|-----|-----------|-------------|
| 0   | 0   | 0         | 0           |
| 0   | 1   | 1         | 0           |
| 1   | 0   | 1         | 0           |
| 1   | 1   | 0         | 1           |

This matches binary addition: 1 + 1 = 10<sub>2</sub> (sum 0, carry 1). A **full adder** adds three bits (A, B and a carry-in) and chaining full adders forms the adder inside the ALU.

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

# Section 1.4 — System Architecture and the Von Neumann Engine

> **Learning objectives**
>
> Explain the stored-program concept, identify the main parts of the Von Neumann architecture, explain each register, and explain the three system buses.

## 1.4.1 The stored-program concept

The **Von Neumann architecture** stores both instructions and data in the same memory. This is the **stored-program concept**, proposed in the 1940s. It made general-purpose computing possible: to change what a computer does you change the program in memory rather than rewire the machine.

> **The Von Neumann bottleneck**
>
> Because instructions and data share the same memory and buses, the CPU cannot fetch an instruction and a data value at exactly the same instant. Cache memory (Section 1.6) reduces its impact.

![Figure 9 — Von Neumann architecture. Main memory is the Immediate Access Store (IAS).](figures/hardware/fig-09.svg)

*Figure 9 — Von Neumann architecture. Main memory is the Immediate Access Store (IAS).*

## 1.4.2 Core subcomponents

- **Control Unit (CU)**: fetches and decodes instructions and emits control signals that coordinate the other parts.
- **ALU**: performs arithmetic and bitwise logical operations.
- **Registers and cache**: very small, very fast storage inside the CPU.
- **Immediate Access Store (IAS)**: the Cambridge term for **main memory (RAM)**, the memory the CPU can access directly. It holds the running program and its data.
- **System clock**: timing signals sent on the control bus.

## 1.4.3 Registers

| Register                           | Purpose                                                                    |
|------------------------------------|----------------------------------------------------------------------------|
| PC (Program Counter)               | Address of the next instruction                                            |
| MAR (Memory Address Register)      | Address currently being read or written                                    |
| MDR (Memory Data Register)         | Data or instruction just retrieved from (or about to be written to) memory |
| CIR (Current Instruction Register) | Instruction currently being decoded and executed                           |
| ACC (Accumulator)                  | Intermediate ALU results                                                   |
| SR (Status Register)               | Status flags: Carry, Overflow, Zero, Negative                              |

## 1.4.4 Status flags

- **Carry** = 1 if a carry out of the most significant bit (MSB) occurred.
- **Overflow** = 1 if the signed result cannot be represented.
- **Zero** = 1 if the result is zero.
- **Negative** = 1 if the result is negative (MSB = 1 in two's complement).

Flags let the CPU make decisions such as “jump if zero”.

## 1.4.5 System buses

| Bus         | Direction               | Function                                                                             |
|-------------|-------------------------|--------------------------------------------------------------------------------------|
| Address bus | CPU to memory (one-way) | Carries the memory address; its width determines the maximum addressable memory.     |
| Data bus    | Two-way                 | Carries data and instructions; its width determines the number of bits per transfer. |
| Control bus | Two-way                 | Carries clock ticks and commands (READ, WRITE, INTERRUPT).                           |

> **Worked example — address bus width**
>
> With *n* address lines the bus can carry 2<sup>*n*</sup> different addresses. An 8-bit address bus addresses 2<sup>8</sup> = 256 locations. A 32-bit bus addresses 2<sup>32</sup> = 4 294 967 296 locations, which is 4 GiB if each location holds one byte.

> **Activity 1.4 — Match the register**
>
> | Job                                       | Register |
> |-------------------------------------------|----------|
> | Holds the address of the next instruction | ?        |
> | Holds the instruction being decoded       | ?        |
> | Holds data read from memory               | ?        |
> | Holds the address being read              | ?        |
> | Holds ALU results                         | ?        |
> | Holds Zero/Carry flags                    | ?        |

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

![Figure 10 — The FDE cycle. Writeback is shown as a separate stage; some syllabi merge it into Execute.](figures/hardware/fig-10.svg)

*Figure 10 — The FDE cycle. Writeback is shown as a separate stage; some syllabi merge it into Execute.*

## 1.5.1 Step by step

### Fetch

1.  PC → MAR via the address bus.
2.  READ signal on the control bus.
3.  Memory → MDR via the data bus.
4.  MDR → CIR.
5.  PC incremented.

### Decode

The CU decodes the opcode in the CIR and generates control signals.

### Execute

The ALU performs the operation and the SR flags are updated.

### Writeback

The result is stored in the ACC or written to memory.

## 1.5.2 Worked trace — ADD

| Step | Action                                      | Registers / buses    |
|------|---------------------------------------------|----------------------|
| 1    | Copy address 200 from PC to MAR             | PC, MAR, address bus |
| 2    | Send READ                                   | Control bus          |
| 3    | Memory contents to MDR                      | Data bus, MDR        |
| 4    | MDR to CIR; PC incremented                  | CIR, PC              |
| 5    | CU decodes ADD                              | CU, CIR              |
| 6    | Fetch the operand into MDR (address in MAR) | MAR, MDR, buses      |
| 7    | ALU adds the operand to ACC                 | ALU, ACC             |
| 8    | Update flags                                | SR                   |

## 1.5.3 Interrupts

An **interrupt** is a signal that causes the processor to suspend its current task and service an event. Causes: a timing signal, I/O completion, a user action, a hardware fault or a software error. At the end of each FDE cycle the processor checks for interrupts. The **Interrupt Service Routine (ISR)** services the highest-priority interrupt: the processor saves its state, runs the ISR, restores the state and continues. An interrupt does **not** restart the computer.

![Figure 11 — Interrupt handling.](figures/hardware/fig-11.svg)

*Figure 11 — Interrupt handling.*

## 1.5.4 Instruction format, assembly and pipelining

An **instruction** has two parts: an **opcode** (which operation to perform) and an **operand** (the data or the address of the data). The set of all instructions a CPU understands is its **instruction set architecture (ISA)**. **Machine code** is instructions in binary; **assembly language** uses short mnemonics (LDA, ADD, STO, JMP) that an **assembler** translates to machine code, one assembly instruction to one machine instruction.

| Addressing mode | Operand meaning                                 | Example                                              |
|-----------------|-------------------------------------------------|------------------------------------------------------|
| Immediate       | The operand is the value itself                 | ADD \#5 adds the number 5                            |
| Direct          | The operand is the address of the value         | ADD 200 adds the contents of address 200             |
| Indirect        | The operand is the address of an address        | ADD (200): address 200 holds the address of the data |
| Indexed         | Operand address + contents of an index register | Used for arrays                                      |

**Pipelining** overlaps the stages of consecutive instructions so that, while one instruction is being executed, the next is being decoded and the one after is being fetched. It raises *throughput* (instructions completed per unit time) but does not shorten the time for a single instruction. Branches can disrupt a pipeline because the CPU may have fetched the wrong instructions.

![Figure 12 — Pipelining five instructions through a three-stage pipeline.](figures/hardware/fig-12.svg)

*Figure 12 — Pipelining five instructions through a three-stage pipeline.*

> **Worked example — pipeline speed-up**
>
> Five instructions, three stages, one clock cycle per stage. Without pipelining: 5 × 3 = 15 cycles. With pipelining: the first instruction finishes after 3 cycles, then one more completes every cycle, so the total is 3 + (5 − 1) = 7 cycles. Speed-up = 15 / 7 ≈ 2.1.

> **Activity 1.5 — Order the FDE stages**
>
> | Scrambled step                   | Position |
> |----------------------------------|----------|
> | Instruction decoded and executed | ?        |
> | Address copied PC → MAR          | ?        |
> | PC incremented                   | ?        |
> | Memory → MDR                     | ?        |
> | MDR → CIR                        | ?        |

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

# Section 1.6 — Memory Hierarchy and Cache

> **Learning objectives**
>
> Explain why a hierarchy exists, compare registers, cache, RAM and storage, explain locality, and explain how cache works.

Fast memory is expensive and small; large memory is cheap and slow. Computers therefore combine several kinds of memory in layers, keeping the most-needed data in the fastest layer. This is the **memory hierarchy**.

![Figure 13 — Memory hierarchy pyramid.](figures/hardware/fig-13.svg)

*Figure 13 — Memory hierarchy pyramid.*

| Tier | Type      | Technology | Capacity       | Latency    |
|------|-----------|------------|----------------|------------|
| 1    | Registers | Flip-flops | ~1–2 KB        | \< 0.5 ns  |
| 2    | Cache     | SRAM       | 32 KB – 128 MB | 1–15 ns    |
| 3    | RAM       | DRAM       | 8–128 GB       | 50–100 ns  |
| 4    | Storage   | Flash SSD  | 512 GB – 4 TB  | ~50 000 ns |

## 1.6.1 Locality

**Temporal locality:** recently used data is likely to be reused soon. **Spatial locality:** data near recently used data is likely to be used soon. Cache exploits both by keeping recent data and by fetching neighbouring data together. A **cache hit** means the data is in cache; a **cache miss** means it must be fetched from a slower tier.

> **Worked example — cache benefit**
>
> If 90% of accesses hit cache (1 ns) and 10% miss and go to RAM (80 ns):  
> Average = 0.9 × 1 + 0.1 × 80 = 0.9 + 8 = **8.9 ns**.  
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
> **Checked answer.** Cache is faster and holds frequently used data close to the CPU **(1)**, reducing the average wait time **(1)**.

# Section 1.7 — RAM, ROM and Storage Technologies

> **Learning objectives**
>
> Compare DRAM and SRAM, explain their uses, distinguish PROM, EPROM and EEPROM, and explain flash memory.

## 1.7.1 DRAM vs SRAM

**DRAM** (dynamic RAM) uses one transistor and one capacitor per bit. The capacitor leaks charge, so each cell must be **refreshed** periodically. DRAM is dense and cheap, so it is used for main memory. **SRAM** (static RAM) uses several transistors (commonly six) per bit; it needs no refresh while powered. It is fast but expensive and bulky, so it is used for cache and registers.

![Figure 14 — DRAM versus SRAM cells (simplified).](figures/hardware/fig-14.svg)

*Figure 14 — DRAM versus SRAM cells (simplified).*

| Feature      | DRAM                       | SRAM                   |
|--------------|----------------------------|------------------------|
| Storage      | 1 transistor + 1 capacitor | Multi-transistor latch |
| Refresh      | Yes                        | No (while powered)     |
| Speed        | Slower                     | Faster                 |
| Cost per bit | Lower                      | Higher                 |
| Density      | High                       | Lower                  |
| Typical use  | Main memory                | Cache                  |

## 1.7.2 ROM types

| Type       | Programmed        | Erased                                  | Typical use                                   |
|------------|-------------------|-----------------------------------------|-----------------------------------------------|
| ROM (mask) | At the factory    | Never                                   | Fixed firmware in mass-produced devices       |
| PROM       | Once, by the user | Cannot be erased                        | Small production runs                         |
| EPROM      | By the user       | Ultraviolet light; chip usually removed | Prototyping                                   |
| EEPROM     | By the user       | Electrically, often in-circuit          | Firmware updated in place, e.g. BIOS settings |

**Flash memory** is EEPROM-related, erased and written in blocks. It is used in SSDs, USB drives and memory cards.

> **Activity 1.7 — Choose the memory**
>
> | Situation                   | Best choice | Reason |
> |-----------------------------|-------------|--------|
> | Main memory                 | ?           | ?      |
> | L3 cache                    | ?           | ?      |
> | Firmware updated in-circuit | ?           | ?      |
> | USB drive                   | ?           | ?      |

> **Checked answers**
>
> | Situation                   | Best choice | Reason                              |
> |-----------------------------|-------------|-------------------------------------|
> | Main memory                 | DRAM        | Dense and cheap per bit             |
> | L3 cache                    | SRAM        | Fast, no refresh                    |
> | Firmware updated in-circuit | EEPROM      | Electrically erasable in place      |
> | USB drive                   | Flash       | Non-volatile, block erase, portable |

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

![Figure 15 — A buffer smoothing speed differences.](figures/hardware/fig-15.svg)

*Figure 15 — A buffer smoothing speed differences.*

> **Buffer vs cache**
>
> A **cache** speeds up *repeated* access to the same data. A **buffer** smooths a *speed mismatch* during a transfer; the data is usually read once, in order.

## 1.8.2 Virtual memory

**Virtual memory** uses secondary storage as extra RAM. The operating system divides memory into fixed-size **pages** and moves them between RAM and a **swap file** (page file). A **page fault** occurs when a required page is not in RAM. **Thrashing** is excessive swapping, where the system spends more time moving pages than running programs.

![Figure 16 — Virtual memory: pages swapped between RAM and the swap file.](figures/hardware/fig-16.svg)

*Figure 16 — Virtual memory: pages swapped between RAM and the swap file.*

**How it works:** the OS checks whether a page is in RAM; if not, a page fault occurs, an unneeded page is written to the swap file, and the required page is read into RAM. This is much slower than RAM but allows programs larger than RAM to run. Adding more RAM reduces page faults.

> **Activity 1.8 — Buffer or cache?**
>
> | Scenario                       | Buffer or cache? | Why |
> |--------------------------------|------------------|-----|
> | Keyboard holds key presses     | ?                | ?   |
> | CPU holds recently used data   | ?                | ?   |
> | Video player stores data ahead | ?                | ?   |
> | L1 holds loop instructions     | ?                | ?   |

> **Checked answers**
>
> | Scenario                       | Answer | Why                                   |
> |--------------------------------|--------|---------------------------------------|
> | Keyboard holds key presses     | Buffer | Speed mismatch with the CPU           |
> | CPU holds recently used data   | Cache  | Temporal locality                     |
> | Video player stores data ahead | Buffer | Smooths network variation             |
> | L1 holds loop instructions     | Cache  | Repeated use of the same instructions |

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

| Device          | Principle of operation                                                                                           | Typical use                      |
|-----------------|------------------------------------------------------------------------------------------------------------------|----------------------------------|
| Keyboard        | Key presses close circuits, generating a unique code (e.g. ASCII).                                               | Text and number entry            |
| Mouse           | Movement is detected by a sensor and translated into cursor movement; buttons register clicks.                   | Pointing and selection           |
| Microphone      | Converts sound waves into electrical signals, then into digital data via an ADC (analogue-to-digital converter). | Voice input, audio recording     |
| Barcode scanner | Shines light on a barcode; the reflected light pattern is converted into a digital code.                         | Retail, inventory                |
| QR code scanner | A camera captures the QR pattern; software decodes the data.                                                     | Mobile payments, advertising     |
| Digital camera  | A lens focuses light onto a sensor (CCD/CMOS) that converts it into digital pixels.                              | Photography, video               |
| 2D / 3D scanner | 2D scans documents; 3D scans objects using lasers or structured light.                                           | Document archiving, 3D modelling |
| Touchscreen     | Detects touch via capacitive or resistive layers; position is calculated by a microprocessor.                    | Smartphones, kiosks              |
| Sensors         | Measure physical quantities (light, temperature, pressure, moisture) and output a signal.                        | Monitoring and control systems   |

## 1.9.2 Output devices

An **output device** presents processed results.

| Device                | Principle of operation                                                           | Typical use                |
|-----------------------|----------------------------------------------------------------------------------|----------------------------|
| Inkjet printer        | Sprays tiny droplets of ink onto paper.                                          | Home/office printing       |
| Laser printer         | A laser charges a drum; toner adheres to the charge and is fused onto paper.     | High-volume printing       |
| 3D printer            | Builds objects layer by layer from plastic, resin or metal.                      | Prototyping, manufacturing |
| 2D / 3D cutter        | 2D cuts flat material; 3D cuts or sculpts objects.                               | Sign-making, fabrication   |
| Speakers / headphones | Convert electrical signals into sound waves.                                     | Audio output               |
| Actuators             | Electromechanical devices (motors, valves, relays) that produce physical action. | Control systems            |
| LCD / LED display     | LCD uses liquid crystals; LED uses light-emitting diodes as backlight or pixels. | Monitors, TVs, phones      |
| LCD / DLP projector   | Projects an image onto a screen using LCD panels or DLP micromirrors.            | Presentations, cinema      |

## 1.9.3 HDMI vs VGA

| Feature     | HDMI                    | VGA                           |
|-------------|-------------------------|-------------------------------|
| Signal      | Digital                 | Analogue                      |
| Audio       | Yes (when supported)    | No                            |
| Connector   | Compact, flat           | 15-pin D-sub                  |
| Typical use | Modern displays and TVs | Older displays and projectors |

## 1.9.4 Worked example — a mouse click

> **Mouse click**
>
> Mouse → I/O controller → device driver → CPU executes → display controller updates the monitor. The CPU does not “see” the mouse directly; the device driver translates between the hardware and the operating system.

> **Activity 1.9 — Match the device**
>
> | Task                                | Most suitable device | Reason |
> |-------------------------------------|----------------------|--------|
> | Enter text into a word processor    | ?                    | ?      |
> | Read a product barcode at checkout  | ?                    | ?      |
> | Print a high-volume office document | ?                    | ?      |
> | Produce a physical prototype        | ?                    | ?      |

> **Checked answers**
>
> Keyboard (text entry); barcode scanner (fast, accurate); laser printer (high volume, low cost per page); 3D printer (layered construction).

> **Exam-style practice**
>
> **Question (2 marks).** Compare HDMI and VGA in signal type and audio support.
>
> **Checked answer.** HDMI is digital and carries audio **(1)**; VGA is analogue and does not carry audio **(1)**.

# Section 1.10 — Network Hardware and Cloud Storage

> **Learning objectives**
>
> Define LAN and WAN, identify common network hardware, explain packets, and compare local and cloud storage.

## 1.10.1 Networks

A **LAN (Local Area Network)** covers a small area such as a home, school or office. A **WAN (Wide Area Network)** covers a large area such as cities or countries; the Internet is the best-known WAN. Networks allow resource sharing, communication and central management. The *Networks* module in this series covers them in depth.

## 1.10.2 Network hardware

| Device                       | Role                                                                                           |
|------------------------------|------------------------------------------------------------------------------------------------|
| NIC (network interface card) | Connects a device to a network; converts data into signals. Each NIC has a unique MAC address. |
| Switch                       | Forwards data within a LAN to the intended device only.                                        |
| Router                       | Connects different networks and forwards packets between them.                                 |
| WAP (wireless access point)  | Provides wireless access to a wired network.                                                   |
| Modem                        | Converts signals between the service provider's line and the local network.                    |
| Firewall                     | Monitors and controls traffic for security.                                                    |

Data is broken into **packets**: small units with addressing information. Packets let many devices share a network efficiently.

## 1.10.3 Cloud storage

**Cloud storage** stores data on provider servers accessed over a network. The user's device sends data to a data centre; the provider stores it and makes it available to authorised devices.

| Feature   | Local storage         | Cloud storage                     |
|-----------|-----------------------|-----------------------------------|
| Location  | User device           | Provider servers                  |
| Access    | Direct                | Requires a network                |
| Capacity  | Limited by the device | Often scalable                    |
| Sharing   | Manual                | Easy via links                    |
| Main risk | Device loss or damage | Account security, provider outage |
| Cost      | One-off hardware      | Subscription or usage-based       |

**Advantages of cloud:** access from multiple devices, easy backup, scalable capacity, collaboration. **Disadvantages:** depends on a network, ongoing cost, privacy and security concerns, provider lock-in.

> **Activity 1.10 — Local or cloud?**
>
> | Scenario                         | Better choice | Reason |
> |----------------------------------|---------------|--------|
> | Editing a video while travelling | ?             | ?      |
> | Sharing a group project          | ?             | ?      |
> | Backing up important photos      | ?             | ?      |
> | Storing an OS for fast boot      | ?             | ?      |

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

| System type | Job                     | Example                       |
|-------------|-------------------------|-------------------------------|
| Monitoring  | Observe and report      | Temperature display           |
| Control     | Observe and act         | Thermostat switching a heater |
| Combined    | Observe, report and act | Smart thermostat              |

## 1.11.4 Worked example — greenhouse

Temperature sensor → microcontroller compares with the target → heater actuator switched on if too cold → vent/fan switched on if too warm → repeat (feedback). Note that the sensor produces an analogue signal, so an ADC converts it to digital before the microcontroller can use it.

![Figure 17 — A monitoring-and-control feedback loop.](figures/hardware/fig-17.svg)

*Figure 17 — A monitoring-and-control feedback loop.*

> **Activity 1.11 — Identify sensors and actuators**
>
> | System           | Sensor | Actuator |
> |------------------|--------|----------|
> | Washing machine  | ?      | ?        |
> | Greenhouse       | ?      | ?        |
> | Anti-lock brakes | ?      | ?        |
> | Smart speaker    | ?      | ?        |

> **Checked answers**
>
> | System           | Sensor                    | Actuator                 |
> |------------------|---------------------------|--------------------------|
> | Washing machine  | Water level / temperature | Motor / valve            |
> | Greenhouse       | Temperature               | Heater / vent            |
> | Anti-lock brakes | Wheel speed               | Brake-pressure modulator |
> | Smart speaker    | Microphone                | Speaker                  |

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

**Latency** is the delay before a result is available; **throughput** is the amount of work completed per unit time. A processor can be designed to favour one or the other.

| Processor       | Design goal                           | Best at                                                                        | Limitation                      |
|-----------------|---------------------------------------|--------------------------------------------------------------------------------|---------------------------------|
| CPU             | Low latency                           | Sequential, branchy code (operating system, general programs)                  | Lower parallel throughput       |
| GPU             | High throughput                       | Graphics, parallel numerical work (SIMT: single instruction, multiple threads) | Weak on branchy sequential code |
| TPU             | Very high throughput for tensor maths | Matrix multiplication for machine learning                                     | Narrow specialisation           |
| Microcontroller | Predictable, low power                | Dedicated control tasks with hard real-time deadlines                          | Small memory, limited speed     |

## 1.12.2 P-cores and E-cores

**P-cores** (performance cores) prioritise speed on demanding tasks. **E-cores** (efficiency cores) prioritise power efficiency on background tasks. More cores help only if the workload can be split to use them.

> **Activity 1.12 — Choose the processor**
>
> For each scenario choose from: CPU, GPU, TPU, microcontroller.
>
> | Scenario                  | Best choice | Reason |
> |---------------------------|-------------|--------|
> | Running a word processor  | ?           | ?      |
> | Rendering 3D game frames  | ?           | ?      |
> | Training a neural network | ?           | ?      |
> | Anti-lock braking control | ?           | ?      |

> **Checked answers**
>
> CPU (sequential, general purpose); GPU (parallel pixels); TPU (matrix maths); microcontroller (hard real-time, dedicated control).

> **Exam-style practice**
>
> **Question (4 marks).** Compare CPU, GPU and TPU for running an OS, rendering graphics and training a neural network.
>
> **Checked answer.** CPU for the OS (sequential) **(1)**; GPU for graphics (parallel pixels) **(1)**; TPU for training (matrix multiplication) **(1)**; each balances latency and throughput differently **(1)**.

# Section 1.13 — Module Summary and Mind Map

![Figure 18 — Mind map of Module 1: Computer Hardware and Microarchitecture.](figures/hardware/fig-18.svg)

*Figure 18 — Mind map of Module 1: Computer Hardware and Microarchitecture.*

| Topic                        | Core comparison                                            |
|------------------------------|------------------------------------------------------------|
| 1.2 Binary / denary / hex    | Base and bit grouping; units bit to TB                     |
| 1.3 Logic                    | Gates, truth tables, half-adder                            |
| 1.4 Von Neumann              | Registers and three buses; IAS = main memory               |
| 1.5 FDE                      | Stage order; interrupts/ISR; pipelining                    |
| 1.6 Memory hierarchy         | Speed vs capacity vs cost; locality                        |
| 1.7 RAM/ROM                  | DRAM vs SRAM; PROM/EPROM/EEPROM; flash                     |
| 1.8 Buffers / virtual memory | Transfer storage; RAM + secondary storage                  |
| 1.9 I/O devices              | Input principles; output principles; HDMI vs VGA           |
| 1.10 Networks / cloud        | Network hardware; local vs cloud                           |
| 1.11 Embedded / control      | Specific function; real-time; sensors, actuators, feedback |
| 1.12 Processors              | Latency vs throughput; P-core vs E-core                    |

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
> Sensors: temperature and soil-moisture. Actuators: heater, vent/fan motor, water valve. It is a **control system** (it acts as well as observes) built on an **embedded** microcontroller using a **feedback** loop; because it can also display and log readings it is a combined system. Deadlines are **soft** real-time: a few seconds' delay does not cause failure. An ADC converts the analogue sensor signals to digital.

> **Case study 3 — specifying a video-editing PC**
>
> A student wants a PC for 4K video editing with two monitors and room to upgrade later.
>
> **Task:** recommend a motherboard form factor, memory, storage and processing hardware, and justify each choice.

> **Model answer**
>
> **ATX** motherboard: enough expansion slots and RAM slots for upgrades. **32 GB+ DRAM**: large video files live in RAM while editing. **NVMe SSD** for the project (low latency) plus a large HDD or cloud storage for archive. A **GPU** with plenty of VRAM accelerates rendering and effects through parallel processing, and needs auxiliary power connectors, so the **PSU** must have enough wattage and the right PCIe power cables. A multi-core CPU with several **P-cores** for encoding. Good cooling because sustained load generates heat.

# Section 1.15 — Exam-Style Mixed Practice with Full Answers

| \#  | Marks | Question                                                                  | Mark-scheme answer                                                                                          |
|-----|-------|---------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| 1   | 2     | Explain why hexadecimal is used for memory addresses.                     | Each hex digit = 4 bits; compact and less error-prone.                                                      |
| 2   | 4     | Describe the fetch stage of the FDE cycle.                                | PC→MAR via address bus; READ on control bus; memory→MDR via data bus; MDR→CIR; PC incremented.              |
| 3   | 3     | Explain what happens when an interrupt is received.                       | Save state; service the highest-priority interrupt with its ISR; restore state and continue.                |
| 4   | 2     | Explain why cache sits between the CPU and main memory.                   | Faster; holds frequently used data close to the CPU; reduces wait time.                                     |
| 5   | 3     | Explain how virtual memory allows a larger program to run.                | Pages moved to secondary storage and swapped back when needed.                                              |
| 6   | 2     | State one advantage and one disadvantage of cloud storage.                | Access from multiple devices; depends on network / security risk.                                           |
| 7   | 3     | Describe three components of an embedded washing-machine system.          | Microcontroller executes the program; sensor monitors water/temperature; actuator drives motor/valve.       |
| 8   | 2     | Compare HDMI and VGA in signal type and audio support.                    | HDMI digital + audio; VGA analogue, no audio.                                                               |
| 9   | 4     | Compare CPU, GPU and TPU for an OS, graphics and neural-network training. | CPU (sequential OS), GPU (parallel graphics), TPU (matrix training); different latency/throughput balances. |
| 10  | 2     | State the difference between a P-core and an E-core.                      | P-core: high performance; E-core: lower power for background work.                                          |

# Section 1.16 — End-of-Module Test

Total: 50 marks. Suggested time: 50 minutes. Attempt without notes, then mark yourself with the answers below.

## Questions

1.  Convert 11010110<sub>2</sub> to denary and to hexadecimal. \[2\]
2.  Convert 4B<sub>16</sub> to binary. \[1\]
3.  A file is 3 MB. How many bytes is this (use 1024)? \[2\]
4.  State the output of NAND when A = 1 and B = 1, and of XOR when A = 1 and B = 1. \[2\]
5.  Complete the half-adder outputs for A = 1, B = 0. \[2\]
6.  State what the MAR and MDR hold. \[2\]
7.  A computer has a 20-bit address bus. How many locations can it address? \[2\]
8.  Which bus is one-way, and in which direction? \[2\]
9.  Six instructions run through a three-stage pipeline. How many cycles are needed? \[2\]
10. Calculate average access time: 95% cache hits at 2 ns, 5% misses at 100 ns. \[2\]
11. Give two differences between DRAM and SRAM. \[2\]
12. State which ROM type allows in-circuit electrical reprogramming. \[1\]
13. Distinguish a buffer from a cache. \[2\]
14. Describe thrashing. \[2\]
15. Name two input devices and their principle of operation. \[4\]
16. Explain the role of the rectifier in a PSU. \[2\]
17. Give two reasons a GPU needs auxiliary power connectors. \[2\]
18. Distinguish hard and soft real-time with an example of each. \[4\]
19. Explain why the Von Neumann bottleneck occurs and one way to reduce it. \[3\]
20. Explain the difference between latency and throughput. \[2\]

## Mark scheme

| \#  | Answer                                                                                                                      |
|-----|-----------------------------------------------------------------------------------------------------------------------------|
| 1   | 214; D6.                                                                                                                    |
| 2   | 0100 1011.                                                                                                                  |
| 3   | 3 × 1024 × 1024 = 3 145 728 bytes.                                                                                          |
| 4   | NAND = 0; XOR = 0.                                                                                                          |
| 5   | Sum = 1; Carry = 0.                                                                                                         |
| 6   | MAR: address being accessed; MDR: data/instruction transferred to or from memory.                                           |
| 7   | 2<sup>20</sup> = 1 048 576.                                                                                                 |
| 8   | Address bus, CPU to memory.                                                                                                 |
| 9   | 3 + (6 − 1) = 8 cycles.                                                                                                     |
| 10  | 0.95 × 2 + 0.05 × 100 = 1.9 + 5 = 6.9 ns.                                                                                   |
| 11  | DRAM needs refresh, slower, cheaper, main memory; SRAM no refresh, faster, dearer, cache.                                   |
| 12  | EEPROM.                                                                                                                     |
| 13  | Buffer smooths speed mismatch during transfer; cache speeds repeated access to frequently used data.                        |
| 14  | Excessive swapping of pages between RAM and storage; performance collapses as time is spent swapping.                       |
| 15  | e.g. Keyboard: key press closes a circuit, generating a code. Barcode scanner: reflected light pattern converted to a code. |
| 16  | Diodes let current flow one way, converting AC to pulsating DC.                                                             |
| 17  | Draws more than the 75 W the PCIe slot supplies; extra current delivered from the PSU.                                      |
| 18  | Hard: missing the deadline is failure, e.g. airbag. Soft: missing degrades quality, e.g. video streaming.                   |
| 19  | Instructions and data share one memory and bus so they cannot be fetched at the same instant; cache reduces the impact.     |
| 20  | Latency: delay for one result; throughput: work completed per unit time.                                                    |

Scoring: 45–50 outstanding; 40–44 excellent; 32–39 good; 25–31 fair; below 25 revisit the sections above.

# Section 1.17 — Learning Material List

Suggested resources for further study. Titles are given so you can search for them; check that each is current before relying on it.

| Resource                                                                            | Type     | Use it for                                                                   |
|-------------------------------------------------------------------------------------|----------|------------------------------------------------------------------------------|
| Watson & Williams, *Cambridge IGCSE and O Level Computer Science* (Hodder)          | Textbook | Core reading for Sections 1.1–1.12 at IGCSE level                            |
| Watson & Williams, *Cambridge International AS & A Level Computer Science* (Hodder) | Textbook | Processor fundamentals, pipelining and system software at A Level            |
| Cambridge syllabuses 0478 / 2210 / 9618                                             | Syllabus | Checking exactly what may be asked                                           |
| Crash Course Computer Science (YouTube series)                                      | Video    | Short animated explanations of logic gates, the CPU, memory and instructions |
| Ben Eater, 8-bit computer series (YouTube)                                          | Video    | Seeing registers, buses and the FDE cycle built from simple parts            |
| Nand2Tetris (nand2tetris.org)                                                       | Course   | Building a computer from NAND gates upward                                   |
| Khan Academy, Computer Science and Computing                                        | Course   | Binary, logic and how computers work, with practice questions                |
| Computerphile (YouTube)                                                             | Video    | Short talks on memory, caches and processors                                 |

# Section 1.18 — Glossary

| Term                  | Definition                                                        |
|-----------------------|-------------------------------------------------------------------|
| **Actuator**          | Output device producing physical action.                          |
| **Address bus**       | One-way bus carrying memory addresses.                            |
| **ALU**               | Arithmetic Logic Unit; performs arithmetic and logic.             |
| **ASIC**              | Application-specific integrated circuit.                          |
| **Bit**               | A single binary digit.                                            |
| **Buffer**            | Temporary storage during data transfer.                           |
| **Bus**               | Set of parallel wires carrying signals.                           |
| **Cache**             | Small fast memory holding frequently used data.                   |
| **Cloud storage**     | Data stored on remote servers accessed over a network.            |
| **Control bus**       | Bus carrying timing and command signals.                          |
| **Control system**    | System that observes and acts automatically.                      |
| **CPU**               | Central Processing Unit.                                          |
| **CU**                | Control Unit.                                                     |
| **Data bus**          | Two-way bus carrying data and instructions.                       |
| **Denary**            | Base-10 number system.                                            |
| **DRAM**              | Dynamic RAM; needs refresh.                                       |
| **EEPROM**            | Electrically erasable programmable ROM.                           |
| **Embedded system**   | Computer dedicated to a specific function.                        |
| **EPROM**             | Erasable programmable ROM (UV light).                             |
| **Feedback**          | Using a measured output to adjust action.                         |
| **Firmware**          | Software stored permanently in hardware.                          |
| **Flash memory**      | Non-volatile memory erased in blocks.                             |
| **FDE cycle**         | Fetch–Decode–Execute cycle.                                       |
| **GPU**               | Graphics Processing Unit.                                         |
| **HDMI**              | Digital video and audio connection.                               |
| **Hexadecimal**       | Base-16 number system.                                            |
| **IAS**               | Immediate Access Store: main memory (RAM).                        |
| **ISA**               | Instruction set architecture: the instructions a CPU understands. |
| **Interrupt**         | Signal causing the processor to suspend its current task.         |
| **ISR**               | Interrupt Service Routine.                                        |
| **LAN**               | Local Area Network.                                               |
| **Latency**           | Delay before data is available.                                   |
| **Logic gate**        | Circuit implementing a logical operation.                         |
| **MAR**               | Memory Address Register.                                          |
| **MDR**               | Memory Data Register.                                             |
| **Monitoring system** | System that observes and reports.                                 |
| **Motherboard**       | Main circuit board connecting components.                         |
| **Nibble**            | 4 bits.                                                           |
| **NIC**               | Network Interface Card.                                           |
| **Opcode**            | Part of an instruction specifying the operation.                  |
| **Operand**           | Data, or the address of data, used by an instruction.             |
| **Packet**            | Small unit of network data.                                       |
| **Page**              | Fixed-size block moved between RAM and storage.                   |
| **Pipelining**        | Overlapping the stages of consecutive instructions.               |
| **PC**                | Program Counter.                                                  |
| **P-core / E-core**   | Performance core / efficiency core.                               |
| **PROM**              | Programmable ROM (usually once).                                  |
| **RAM**               | Volatile working memory.                                          |
| **Register**          | Fast storage inside the CPU.                                      |
| **ROM**               | Non-volatile memory for firmware.                                 |
| **Router**            | Connects different networks.                                      |
| **SIMT**              | Single Instruction, Multiple Threads.                             |
| **SRAM**              | Static RAM; no refresh while powered.                             |
| **Status Register**   | Holds condition flags.                                            |
| **Swap file**         | Storage area used for virtual memory.                             |
| **Switch**            | Connects devices in a LAN.                                        |
| **Systolic array**    | Grid of processing elements for matrix operations.                |
| **Thrashing**         | Excessive swapping.                                               |
| **Throughput**        | Tasks completed per unit time.                                    |
| **TPU**               | Tensor Processing Unit.                                           |
| **Transistor**        | Tiny electronic switch.                                           |
| **Virtual memory**    | Using secondary storage as extra RAM.                             |
| **VGA**               | Older analogue video connection.                                  |
| **Volatile**          | Loses contents when power is removed.                             |
| **WAN**               | Wide Area Network.                                                |

## Section 1.19 — References and attribution

1.  Watson, D. and Williams, H. *Cambridge IGCSE and O Level Computer Science*. Hodder Education. Chapters on binary systems, logic gates, computer architecture, input/output devices, and memory and data storage.
2.  Watson, D. and Williams, H. *Cambridge International AS & A Level Computer Science*. Hodder Education. Chapters on hardware, processor fundamentals and system software.
3.  Cambridge IGCSE Computer Science 0478 / O Level Computer Science 2210 syllabus.
4.  Cambridge International AS & A Level Computer Science 9618 syllabus.

Revision notes (v3.0): corrected the definition of the IAS (main memory, not registers and cache); added pipelining, instruction format and addressing modes; made figure numbering sequential; replaced unrendered LaTeX with plain notation; replaced the Activity 1.12 option set so every answer is available; fixed table widths; removed a dangling reference to a conversion helper; added learning suggestions, mind map, case studies, end-of-module test and learning material list. All conversion calculations, truth tables and latency figures were recomputed.
