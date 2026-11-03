# Module 1 — Computer Hardware & Microarchitecture (V2.0)

## Contents

1. Module Overview and Learning Outcomes
2. Section 1.1 — Physical Parts of a Computer
3. Section 1.2 — Number Systems and Data Units
4. Section 1.3 — Binary Logic
5. Section 1.4 — System Architecture and the Von Neumann Engine
6. Section 1.5 — The Fetch-Decode-Execute Cycle and Interrupts
7. Section 1.6 — Memory Hierarchy and Cache
8. Section 1.7 — RAM, ROM and Storage Technologies
9. Section 1.8 — Buffers and Virtual Memory
10. Section 1.9 — Input and Output Devices
11. Section 1.10 — Network Hardware and Cloud Storage
12. Section 1.11 — Embedded Systems, Monitoring and Control
13. Section 1.12 — Processor Specialisation and CPU Core Types
14. Section 1.13 — Module Summary
15. Section 1.14 — Exam-Style Mixed Practice
16. Section 1.15 — Glossary
17. Section 1.16 — References and Attribution
18. Conversion Helper (for Workflow B)

---

## Module Overview and Learning Outcomes

This module introduces the physical components of a computer system and the microarchitectural principles that allow those components to execute instructions. It begins with the parts you can touch, then establishes the binary number system — the language all hardware speaks — and builds upward through logic gates, the Von Neumann model, the fetch-decode-execute cycle, the memory hierarchy, input/output devices, networks, embedded systems, and processor specialisation.

By the end of this module you should be able to:

1. Identify the major internal components of a computer and state the role of each.
2. Convert between binary, denary and hexadecimal, and explain why hexadecimal is used.
3. State and use the units of data: bit, nibble, byte, KB, MB, GB, TB.
4. Explain how transistors form logic gates and how gates form combinational and sequential circuits.
5. Identify the registers and buses of the Von Neumann architecture and explain the role of each.
6. Trace the FDE cycle stage by stage, naming the registers and buses active at each step.
7. Explain how interrupts and the interrupt service routine work.
8. Explain why the memory hierarchy exists and compare DRAM and SRAM.
9. Explain what buffers and virtual memory are, and why they exist.
10. Compare local storage with cloud storage, and describe the network hardware that makes cloud storage possible.
11. Compare CPU, GPU and TPU architectures in terms of latency and throughput.
12. Describe the principles of operation of common input and output devices, including sensors and actuators.
13. Describe embedded systems, real-time constraints, and monitoring/control systems.
14. Distinguish PROM, EPROM and EEPROM, and state appropriate uses for each.
15. Compare HDMI and VGA in terms of signal type, audio support and typical use.

**Prerequisite knowledge assumed:** none beyond everyday familiarity with a computer. Binary is taught in Section 1.2 before any section that uses it. Every new term is defined before it is used.

---

## Section 1.1 — Physical Parts of a Computer

### Learning Objectives

By the end of this section you should be able to name the main physical components inside a computer, state the purpose of each, and explain the difference between hardware, firmware, software and data.

### 1.1.1 What Hardware Actually Means

**Hardware** is the set of physical parts of a computer that you can see, touch and (usually) move. The word is used in contrast to **software**, which is the set of instructions and data that the hardware carries out and stores. Software has no physical form of its own; it exists as patterns stored in hardware.

Four ideas are often confused at the start:

- **Hardware** — the physical parts. Example: the CPU chip.
- **Software** — programs and data. Example: a web browser.
- **Firmware** — software permanently stored in hardware, usually in ROM, and rarely changed. Example: the BIOS/UEFI that starts a computer.
- **Data** — raw facts that programs process. Example: the numbers in a spreadsheet.

A computer works only when all four cooperate. The hardware provides the physical capability, the firmware starts the machine, the software tells the hardware what to do, and the data is what gets processed.

### 1.1.2 The Motherboard

The motherboard is the large circuit board that everything else plugs into. Its purpose is not to do computing itself but to connect the parts that do, and to supply them with power and communication pathways.

It holds the CPU socket, the RAM slots, expansion slots for add-on cards, the chipset (support chips managing communication), storage connectors, input/output connectors, and the firmware chip holding the BIOS/UEFI.

Connections between components are made by **traces** — thin copper pathways printed into the board. Traces carry both electrical power and electrical signals. When a diagram shows a line between the CPU and RAM, that line represents a set of traces forming a bus, explained in Section 1.4.

#### Why This Matters

A fast CPU connected by a slow or narrow pathway cannot perform at its full speed. The motherboard and its traces are part of the performance story.


![alt text](./Assets/<Screenshot 2026-11-02 190346.png>)


**Figure 1.1 — Motherboard block diagram. Traces carry both electricity and signals between components.**

```text
MOTHERBOARD
CPU (Control Unit, ALU, Registers + Cache) | RAM Slots | Expansion Slots (GPU, Wi-Fi card, etc.)
System bus — traces carrying power and signals
ROM / BIOS (Firmware, Boot instructions) | Chipset (Manages communication) | Storage (SSD / HDD / USB, Non-volatile)
All components connect via the motherboard and communicate over buses (traces).
```

### 1.1.3 The CPU

The **Central Processing Unit (CPU)** fetches instructions, decodes them and executes them. Inside are the **Control Unit (CU)**, the **Arithmetic Logic Unit (ALU)**, registers, and cache memory.

### 1.1.4 RAM: The Workspace

**Random Access Memory (RAM)** is the short-term workspace. Programs and data currently in use are loaded into RAM for fast access. RAM is **volatile**: its contents are lost when power is removed.

#### Why RAM Exists

SSDs and hard drives are much slower than the CPU. Without RAM, the CPU would spend most of its time waiting. RAM is the intermediate workspace fast enough to keep the CPU busy. Section 1.6 explains this speed gap.

### 1.1.5 ROM: Permanent Startup Instructions

**Read-Only Memory (ROM)** is **non-volatile**: it keeps its contents when power is switched off. ROM stores firmware — such as the BIOS/UEFI that starts the computer and checks the hardware before loading the operating system.

### 1.1.6 Secondary Storage

- **HDD (hard disk drive)** — magnetic spinning platters; large capacity, relatively cheap, slower, sensitive to movement.
- **SSD (solid-state drive)** — flash memory chips, no moving parts; faster, quieter, more shock-resistant, more expensive per gigabyte.
- **USB flash drives and memory cards** — portable flash storage.

### 1.1.7 GPU and TPU

A **GPU (Graphics Processing Unit)** contains hundreds or thousands of small arithmetic units that operate concurrently, making it effective for graphics rendering and parallel numerical work.

A **TPU (Tensor Processing Unit)** is an ASIC designed to accelerate machine-learning matrix operations. Its core is a **systolic array**: a grid of processing elements through which data flows in a regular rhythm.

### 1.1.8 The System Clock

The system clock produces timing signals measured in **hertz (Hz)**. Clock speed is one of three IGCSE performance factors, alongside cache size and number of cores.

### 1.1.9 Other Common Components

- **PSU** — converts mains electricity into DC voltages.
- **Cooling system** — fans, heat sinks or liquid cooling remove heat.
- **Expansion cards** — add graphics, Wi-Fi, sound, etc.
- **Case** — protects components and supports airflow.

### Activity 1.1 — Identify the Component

| Job | Component |
|---|---|
| Holds the program currently running? | |
| Starts the computer before the OS loads? | |
| Performs arithmetic? | |
| Connects all components? | |
| Keeps files when power is off? | |

#### Checked Answers

| Job | Component |
|---|---|
| Holds the program currently running | RAM |
| Starts the computer before the OS loads | ROM / firmware |
| Performs arithmetic | ALU |
| Connects all components | Motherboard |
| Keeps files when power is off | Secondary storage |

### Exam-Style Practice

**Question (2 marks).** Explain why RAM is described as volatile.

**Checked answer.** RAM loses its contents when power is removed (1), because it relies on electrical charge not maintained without power (1).

### 1.1.10 Motherboard Form Factors

A **form factor** is a standard that defines a motherboard's physical dimensions, mounting-hole positions, and the layout of expansion slots and connectors. Form factors exist so that cases, power supplies, and add-on cards from different manufacturers can fit together. If a motherboard did not follow a recognised form factor, every case and PSU would have to be custom-made.

| Form factor | Typical size | Expansion slots | Typical use |
|---|---|---|---|
| EATX (Extended ATX) | ~305 × 330 mm | Up to 7 | Workstations, servers, multi-GPU builds |
| ATX (Standard ATX) | ~305 × 244 mm | Up to 7 | Desktop PCs, gaming builds |
| Micro-ATX (mATX) | ~244 × 244 mm | Up to 4 | Smaller desktops, budget builds |
| Mini-ITX / Mini-ATX | ~170 × 170 mm or smaller | 1–2 slots | Small-form-factor PCs, home theatre, embedded |

![Figure 1.13 — Relative sizes of the four main motherboard form factors](figure-1.13-form-factors.png)

**Figure 1.13 — Relative sizes of the four main motherboard form factors.**

```text
EATX: ~305 × 330 mm, Up to 7 slots, Server / workstation
ATX: ~305 × 244 mm, Up to 7 slots, Standard desktop
Micro-ATX: ~244 × 244 mm, Up to 4 slots, Budget / compact
Mini-ITX: ~170 mm, 1–2 slots
```

### Worked Example — Choosing a Form Factor

A user needs a gaming PC with two graphics cards, four RAM modules, and a large air cooler. **EATX or full ATX** is best: more expansion slots, more RAM slots, and enough physical clearance for cooling. A user building a small home-theatre PC should choose **Mini-ITX**: it fits a compact case but limits slots and cooling options.

### Activity 1.1.10 — Match the Form Factor

| Scenario | Best form factor | Reason |
|---|---|---|
| Dual-GPU scientific workstation | ? | ? |
| Standard office desktop | ? | ? |
| Small home-theatre PC | ? | ? |
| Budget family PC | ? | ? |

#### Checked Answers

| Scenario | Best form factor | Reason |
|---|---|---|
| Dual-GPU scientific workstation | EATX or ATX | Most expansion slots; room for cooling and power delivery |
| Standard office desktop | ATX | Standard, widely available, enough slots |
| Small home-theatre PC | Mini-ITX | Smallest footprint, fits compact cases |
| Budget family PC | Micro-ATX | Cheaper, smaller, enough slots for basic use |

### Exam-Style Practice

**Question (2 marks).** Explain why motherboard form factors are standardised.

**Checked answer.** Standardisation ensures cases, power supplies and expansion cards fit together across manufacturers (1), reducing cost and allowing upgrades (1).

### 1.1.11 Power Supply Unit: Internal Mechanics

The power supply unit (PSU) converts the high-voltage alternating current (AC) from a wall socket into the low-voltage direct current (DC) that the computer's components need. The conversion happens in four stages.

![Figure 1.14 — The four stages of AC-to-DC conversion inside a PSU](figure-1.14-psu-conversion.png)

**Figure 1.14 — The four stages of AC-to-DC conversion inside a PSU.**

```text
AC INPUT (230 V / 120 V)
→ 1. Transformer: Steps voltage down (e.g. to 12 V AC)
→ 2. Rectifier: Diodes convert AC → pulsating DC
→ 3. Smoothing: Capacitors remove ripple
→ 4. Regulator: Holds stable output (3.3/5/12 V)
```

Each stage reduces noise and produces a cleaner DC output. Modern PSUs also include protection circuits: over-voltage, over-current and short-circuit protection.

### Worked Example — Why Smoothing Matters

After rectification, the DC output still pulses because the diodes only allow current one way, but the voltage drops to zero between peaks. A smoothing capacitor charges during peaks and discharges between them, filling the gaps. Without smoothing, sensitive components would receive a rippled supply and could malfunction.

### Activity 1.1.11 — Order the Stages

| Stage | Correct position (1–4) | What it does |
|---|---|---|
| Voltage regulator | ? | ? |
| Transformer | ? | ? |
| Smoothing capacitor | ? | ? |
| Rectifier | ? | ? |

#### Checked Answers

| Stage | Position | What it does |
|---|---|---|
| Transformer | 1 | Steps AC voltage down |
| Rectifier | 2 | Converts AC to pulsating DC |
| Smoothing capacitor | 3 | Removes ripple |
| Voltage regulator | 4 | Holds stable DC output |

### 1.1.12 PSU Internal Components

Opening a PSU (only safely, with the unit unplugged and discharged) reveals a circuit board with several distinct components. Each plays a role in conversion, filtering or protection.

| Component | Function |
|---|---|
| Transformer | Steps the AC voltage down using magnetic induction between coils. |
| Rectifier diodes | Allow current to flow in one direction only, converting AC to pulsating DC. |
| Capacitors | Store charge and smooth out voltage ripple; also used for filtering noise. |
| Resistors | Limit current and divide voltage; used in sensing circuits. |
| Rotary switch | On some older PSUs, selects the input voltage (110 V or 230 V). |
| Heatsinks | Dissipate heat from power transistors and diodes. |
| Fan | Moves air through the unit to keep components within safe temperatures. |
| Protection circuits | Shut down the PSU on over-voltage, over-current or short-circuit. |

![Figure 1.15 — Typical internal layout of a PSU](figure-1.15-psu-internal.png)

**Figure 1.15 — Typical internal layout of a PSU.**

```text
Transformer (Steps AC down) | Rectifier (Diodes, AC → DC) | Capacitors (Smoothing, ripple removal) | Resistors (Limit current)
Rotary Switch (110 V / 230 V input) | Heatsinks (Cool power transistors) | Fan + Vent (Airflow and cooling)
Protection circuits: over-voltage, over-current, short-circuit
```

### Activity 1.1.12 — Match the Component to Its Role

| Component | Role |
|---|---|
| Transformer | ? |
| Rectifier diodes | ? |
| Capacitors | ? |
| Resistors | ? |
| Rotary switch | ? |

#### Checked Answers

- **Transformer:** steps AC voltage down.
- **Rectifier diodes:** convert AC to pulsating DC.
- **Capacitors:** smooth ripple.
- **Resistors:** limit current and divide voltage.
- **Rotary switch:** selects input voltage on older PSUs.

### Exam-Style Practice

**Question (2 marks).** State the function of the rectifier diodes in a PSU.

**Checked answer.** They allow current to flow in one direction only (1), converting AC into pulsating DC (1).

### 1.1.13 Graphics Card (GPU) Components

A graphics card is an expansion card that contains a GPU and its supporting components. It handles graphics rendering and highly parallel numerical work. A modern graphics card has seven main parts.

| Part | Function |
|---|---|
| 1. GPU chip | The processor itself; contains thousands of shader cores that execute rendering and parallel computation. |
| 2. VRAM | Dedicated video memory that stores textures, framebuffers and working data for the GPU. |
| 3. PCIe interface | The edge connector that plugs into the motherboard and carries data between CPU and GPU. |
| 4. Heatsink + fan | Removes heat generated by the GPU chip and VRAM. |
| 5. 6/8-pin auxiliary power connectors | Supply extra power beyond what the PCIe slot provides, needed for high-end GPUs. |
| 6. Monitor outputs | HDMI, DisplayPort, DVI and other connectors that send video to displays. |
| 7. Video BIOS | Firmware that initialises the card at startup and controls clock speeds and voltages. |

![Figure 1.16 — The seven main parts of a graphics card](figure-1.16-graphics-card.png)

**Figure 1.16 — The seven main parts of a graphics card.**

```text
GPU Chip (Shader cores) | VRAM (Video memory) | Video BIOS (Firmware) | 6/8-pin (Power)
Heatsink + Fan
PCIe Interface (edge connector)
Monitor Outputs (HDMI, DP, DVI)
```

### Worked Example — Why Auxiliary Power Matters

A high-end GPU can draw 250 W or more. The PCIe slot provides only 75 W. Without the 6-pin and 8-pin auxiliary connectors, the card would not receive enough power and would either throttle or fail to start. The PSU's PCIe power cables plug into these connectors.

### Activity 1.1.13 — Match the GPU Part

| Job | Part |
|---|---|
| Stores textures and framebuffers | ? |
| Connects the card to the motherboard | ? |
| Supplies extra power beyond the slot | ? |
| Initialises the card at startup | ? |
| Removes heat from the GPU | ? |

#### Checked Answers

VRAM; PCIe interface; 6/8-pin connectors; Video BIOS; heatsink + fan.

### Exam-Style Practice

**Question (2 marks).** Explain why high-end GPUs need auxiliary power connectors.

**Checked answer.** They draw more power than the PCIe slot can supply (1); the 6- or 8-pin connectors deliver the extra current from the PSU (1).

---

## Section 1.2 — Number Systems and Data Units

### Learning Objectives

Explain what a bit is, convert between binary and denary, convert between binary and hexadecimal, and use the units bit, nibble, byte, KB, MB, GB, TB.

### 1.2.1 What Is a Bit?

A **bit** is a single binary digit: `0` or `1`. In hardware these are two voltage levels. A bit is an abstraction for a two-state circuit. Using only two widely separated voltage levels makes circuits reliable against noise, heat and manufacturing variation. **Binary** is the base-2 number system using only `0` and `1`.

### 1.2.2 Units of Data

| Unit | Size | Example use |
|---|---|---|
| bit | 1 binary digit | one flag |
| nibble | 4 bits | one hex digit |
| byte | 8 bits | one ASCII character |
| KB | 1024 bytes | short text file |
| MB | 1024 KB | photo |
| GB | 1024 MB | video / RAM |
| TB | 1024 GB | SSD / HDD |

#### Convention Note

In this module, `1 KB = 1024` bytes because `1024 = 2^10`. Storage manufacturers sometimes use `1000`. Use the power-of-two convention in exams unless told otherwise.

### 1.2.3 Binary Place Values

![Figure 1.2 — Binary place-value chart](figure-1.2-binary-place-values.png)

**Figure 1.2 — Binary place-value chart.**

```text
2^7  2^6  2^5  2^4  2^3  2^2  2^1  2^0
128   64   32   16    8    4    2    1
  1    0    1    1    0    1    0    1

10110101 = 128 + 32 + 16 + 4 + 1 = 181
```

**Worked example — `1011` to denary:**

```math
1011_2 = 1 \times 2^3 + 0 \times 2^2 + 1 \times 2^1 + 1 \times 2^0 = 8 + 0 + 2 + 1 = 11_{10}
```

**Worked example — `45` to binary:** `45 = 32 + 8 + 4 + 1`, so `45_{10} = 101101_2`.

### 1.2.4 Hexadecimal

**Hexadecimal** uses `0–9` and `A–F` (base 16). `A = 10`, …, `F = 15`.

```math
B7_{16} = 11 \times 16 + 7 = 176 + 7 = 183_{10}
```

Each hex digit represents four bits (one nibble). Hex is used for memory addresses, machine code and colour codes.

#### Binary ↔ Hexadecimal Grouping

![Figure 1.3 — Binary to hex grouping: 1101 0110 = D6](figure-1.3-binary-to-hex.png)

**Figure 1.3 — Binary to hex grouping: `1101 0110 = D6`.**

```text
Binary: 1101  0110
Hex:      D     6
Result: D6
1101 = D
0110 = 6
```

### 1.2.5 Conversion Practice

| Task | Answer |
|---|---|
| `10110` to denary | 22 |
| `45` to binary | `101101` |
| `211101101` to hex | `ED` |
| `B7` to denary | 183 |
| `2C` to binary | `00101100` |
| 3 bytes = ? bits / nibbles | 24 bits, 6 nibbles |

### Exam-Style Practice

**Question (2 marks).** Explain why hexadecimal is used for memory addresses.

**Checked answer.** Each hex digit represents four binary bits (1), so long binary addresses become short and less error-prone (1).

---

## Section 1.3 — Binary Logic

### Learning Objectives

Explain how transistors form logic gates, state the function of standard gates, complete truth tables, distinguish combinational from sequential circuits, and explain the half-adder.

### 1.3.1 From Transistors to Gates

A **transistor** is a tiny electronic switch. Combining transistors forms **logic gates** — circuits whose output depends on the logical combination of their inputs.

### 1.3.2 Combinational and Sequential Circuits

**Combinational circuits** depend only on current inputs (adders, multiplexers, decoders). **Sequential circuits** depend on current inputs and stored state, updated on clock ticks (flip-flops, latches). Flip-flops are the physical basis of registers and memory cells.

### 1.3.3 The Half-adder

![Figure 1.5 — Half-adder: XOR for Sum, AND for Carry](figure-1.5-half-adder.png)

**Figure 1.5 — Half-adder: XOR for Sum, AND for Carry.**

```text
Sum = A XOR B
Carry = A AND B
```

| A | B | Sum (XOR) | Carry (AND) |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |

This matches binary addition: `1 + 1 = 10`. A **full adder** adds three bits and is the basis of the ALU.

### Activity 1.3 — Build a Half-adder

Using AND and XOR gates, draw a half-adder and complete the output for `A = 1`, `B = 1`.

#### Checked Answer

```math
\text{Sum} = 1 \text{ XOR } 1 = 0; \quad \text{Carry} = 1 \text{ AND } 1 = 1.
```

---

## Section 1.4 — System Architecture and the Von Neumann Engine

### Learning Objectives

Explain the stored-program concept, identify the main parts of the Von Neumann architecture, explain each register, and explain the three system buses.

### 1.4.1 The Stored-Program Concept

The Von Neumann architecture stores both instructions and data in the same memory. This is the **stored program concept**, proposed in the 1940s. It made general-purpose computing possible.

#### The Von Neumann Bottleneck

Because instructions and data share the same memory and buses, the CPU cannot fetch an instruction and a data value at exactly the same instant. Cache memory (Section 1.6) reduces its impact.

![Figure 1.6 — Von Neumann architecture](figure-1.6-von-neumann.png)

**Figure 1.6 — Von Neumann architecture.**

```text
CPU
  Control Unit (CU)
  ALU (Arithmetic Logic Unit)
  Registers: PC · MAR · MDR · CIR · ACC · SR
ADDRESS BUS (uni-directional, CPU → memory)
DATA BUS (bi-directional)
CONTROL BUS (READ / WRITE / CLOCK / INTERRUPT)
MAIN MEMORY (RAM): instructions + data
INPUT            OUTPUT
```

### 1.4.2 Core Subcomponents

- **Control Unit (CU)** — fetches, decodes and emits control signals.
- **ALU** — performs arithmetic and bitwise logical operations.
- **Immediate Access Store (IAS)** — registers and cache.
- **System clock** — timing signals on the control bus.

### 1.4.3 Registers

| Register | Role |
|---|---|
| PC (Program Counter) | Holds the address of the next instruction. |
| MAR (Memory Address Register) | Holds the address currently being read from or written to. |
| MDR (Memory Data Register) | Holds data read from memory or data to be written. |
| CIR (Current Instruction Register) | Holds the instruction being decoded/executed. |
| ACC (Accumulator) | Holds ALU results. |
| SR (Status Register) | Holds condition flags. |

### 1.4.4 Status Flags

- **Carry** `= 1` if a carry out of the MSB occurred.
- **Overflow** `= 1` if the signed result cannot be represented.
- **Zero** `= 1` if the result is zero.
- **Negative** `= 1` if the result is negative (MSB `= 1` in two's complement).

Flags let the CPU make decisions such as “jump if zero”.

### 1.4.5 System Buses

| Bus | Direction | Function |
|---|---|---|
| Address bus | CPU → memory | Carries the memory address; width determines maximum addressable memory. |
| Data bus | Bi-directional | Carries data and instructions; width determines bits per transfer. |
| Control bus | Bi-directional | Carries clock ticks and commands (READ, WRITE, INTERRUPT). |

#### Address Bus Width

With `n` lines, the address bus carries `2^n` addresses. An 8-bit bus addresses 256 locations; a 32-bit bus addresses `2^32` locations (about 4 GB if each is one byte).

### Activity 1.4 — Match the Register

| Job | Register |
|---|---|
| Holds the address of the next instruction? | |
| Holds the instruction being decoded? | |
| Holds data read from memory? | |
| Holds the address being read? | |
| Holds ALU results? | |
| Holds Zero/Carry flags? | |

**Answers:** PC, CIR, MDR, MAR, ACC, SR.

### Exam-Style Practice

**Question (2 marks).** State the role of the Program Counter.

**Checked answer.** Holds the address of the next instruction (1); incremented after each fetch (1).

---

## Section 1.5 — The Fetch-Decode-Execute Cycle and Interrupts

### Learning Objectives

Describe each FDE stage, name the registers and buses used, explain interrupts and the ISR.

![Figure 1.7 — The FDE cycle](figure-1.7-fde-cycle.png)

**Figure 1.7 — The FDE cycle.**

```text
1. FETCH — PC → MAR, Memory → MDR → CIR
2. DECODE — CU reads opcode in CIR
3. EXECUTE — ALU operates, SR flags updated
4. WRITEBACK — Result → ACC or memory
Loop repeats for the next instruction
```

### 1.5.1 Step by Step

#### Fetch

1. `PC → MAR` via the address bus.
2. `READ` signal on the control bus.
3. `Memory → MDR` via the data bus.
4. `MDR → CIR`.
5. `PC` incremented.

#### Decode

CU decodes the opcode in the CIR and generates control signals.

#### Execute

ALU performs the operation; SR flags updated.

### 1.5.2 Worked Trace — ADD

| Step | Action | Registers / buses |
|---|---|---|
| 1 | Copy address 200 from PC to MAR | PC, MAR, address bus |
| 2 | Send READ | Control bus |
| 3 | Memory → MDR | Data bus, MDR |
| 4 | MDR → CIR; PC incremented | CIR, PC |
| 5 | CU decodes ADD | CU, CIR |
| 6 | Fetch operand into MDR | MAR, MDR |
| 7 | ALU adds operand to ACC | ALU, ACC |
| 8 | Update flags | SR |

### 1.5.3 Interrupts

An **interrupt** is a signal that causes the processor to suspend its current task and service an event. Causes: timing signal, I/O completion, user action, hardware fault, software error.

![Figure 1.8 — Interrupt handling](figure-1.8-interrupt-handling.png)

**Figure 1.8 — Interrupt handling.**

```text
Normal → INTERRUPT arrives → Save state → Run ISR
Restore state → resume where it left off
```

The **Interrupt Service Routine (ISR)** services the highest-priority interrupt. The processor saves state, runs the ISR, restores state and continues. An interrupt does not restart the computer.

### Activity 1.5 — Order the FDE Stages

| Scrambled stage | Position | Key register / bus |
|---|---|---|
| Instruction decoded and executed | ? | ? |
| Address copied PC → MAR | ? | ? |
| PC incremented | ? | ? |
| Memory → MDR | ? | ? |
| MDR → CIR | ? | ? |

**Answers:** `PC → MAR` (1), `Memory → MDR` (2), `MDR → CIR` (3), `PC incremented` (4), `decode/execute` (5).

### Exam-Style Practice

**Question (3 marks).** Explain what happens when an interrupt is received.

**Checked answer.** Save current state (1); service highest-priority interrupt via ISR (1); restore state and continue (1).

---

## Section 1.6 — Memory Hierarchy and Cache

### Learning Objectives

Explain why a hierarchy exists, compare registers, cache, RAM and storage, explain locality, and explain cache.

![Figure 1.9 — Memory hierarchy pyramid](figure-1.9-memory-hierarchy.png)

**Figure 1.9 — Memory hierarchy pyramid.**

```text
Registers — ~1–2 KB — <0.5 ns        ▲ Faster · Smaller · More expensive
L1 / L2 / L3 Cache (SRAM) — 32 KB – 128 MB — 1–15 ns
System RAM (DRAM) — 8 GB – 128 GB — 50–100 ns
Secondary Storage (SSD / HDD) — 512 GB – 4 TB — ~50,000 ns
                                    ▼ Slower · Larger · Cheaper
```

| Tier | Type | Technology | Capacity | Latency |
|---|---|---|---|---|
| 1 | Registers | Flip-flops | ~1–2 KB | <0.5 ns |
| 2 | Cache | SRAM | 32 KB – 128 MB | 1–15 ns |
| 3 | RAM | DRAM | 8–128 GB | 50–100 ns |
| 4 | Storage | Flash SSD | 512 GB – 4 TB | ~50,000 ns |

### 1.6.1 Locality

**Temporal locality:** recently used data is likely reused. **Spatial locality:** nearby data is likely used soon. A **cache hit** means data is in cache; a **cache miss** means it must be fetched from a slower tier.

### 1.6.2 Worked Example — Cache Benefit

If `90%` of accesses hit cache (`1 ns`) and `10%` miss to RAM (`80 ns`):

```math
\text{Average} = 0.9 \times 1 + 0.1 \times 80 = 8.9 \text{ ns}
```

This is far better than `80 ns` for every access.

### Activity 1.6 — Rank the Access

Rank register, L1 cache, RAM, SSD from fastest to slowest.

#### Checked Answer

register → L1 cache → RAM → SSD.

### Exam-Style Practice

**Question (2 marks).** Explain why cache sits between CPU and main memory.

**Checked answer.** Cache is faster and holds frequently used data close to the CPU (1), reducing average wait time (1).

---

## Section 1.7 — RAM, ROM and Storage Technologies

### Learning Objectives

Compare DRAM and SRAM, explain their uses, distinguish PROM, EPROM and EEPROM, and explain flash memory.

### 1.7.1 DRAM vs SRAM

**DRAM** uses one transistor and one capacitor per bit; the capacitor leaks charge, so it needs periodic refresh. It is dense and cheap, used for main memory.

**SRAM** uses multiple transistors (commonly six) per bit; it does not need refresh while powered. It is fast and expensive, used for cache.

![Figure 1.10 — DRAM vs SRAM cells](figure-1.10-dram-vs-sram.png)

**Figure 1.10 — DRAM vs SRAM cells.**

```text
DRAM cell: bit line, word line, T1 transistor, capacitor — Needs periodic refresh
SRAM cell: cross-coupled inverters — No refresh needed while powered
```

| Feature | DRAM | SRAM |
|---|---|---|
| Storage | 1 transistor + 1 capacitor | Multi-transistor latch |
| Refresh | Yes | No, while powered |
| Speed | Slower | Faster |
| Cost/bit | Lower | Higher |
| Use | Main memory | Cache |

### 1.7.2 ROM Types

- **PROM** — programmable once.
- **EPROM** — erasable by UV light; usually removed.
- **EEPROM** — erasable and reprogrammable electrically; often in-circuit.

**Flash memory** is EEPROM-related, erased and written in blocks; used in SSDs, USB drives and memory cards.

### Activity 1.7 — Choose the Memory

| Situation | Best choice | Reason |
|---|---|---|
| Main memory | ? | ? |
| L3 cache | ? | ? |
| Firmware updated in-circuit | ? | ? |

#### Checked Answers

DRAM, SRAM, EEPROM, flash.

### Exam-Style Practice

**Question (2 marks).** Firmware must be updated without removing the chip. State the ROM type and justify.

**Checked answer.** EEPROM (1), because it can be erased and reprogrammed electrically in-circuit (1).

---

## Section 1.8 — Buffers and Virtual Memory

### Learning Objectives

Define a buffer, distinguish buffers from cache, explain virtual memory, paging and swapping.

### 1.8.1 Buffers

A **buffer** is temporary storage during data transfer between devices with different speeds. Examples: keyboard buffer, printer buffer, video streaming buffer, double buffering.

![Figure 1.11 — Buffer smoothing speed differences](figure-1.11-buffer.png)

**Figure 1.11 — Buffer smoothing speed differences.**

```text
FAST DEVICE (e.g. CPU) → BUFFER (temporary storage, smooths speed mismatch) → SLOW DEVICE (e.g. printer)
```

Without the buffer, the fast device would wait or data would be lost.

### 1.8.2 Virtual Memory

**Virtual memory** uses secondary storage as extra RAM. The OS moves pages between RAM and a swap file. A **page fault** occurs when a required page is not in RAM. **Thrashing** is excessive swapping.

![Figure 1.12 — Virtual memory: pages swapped between RAM and swap file](figure-1.12-virtual-memory.png)

**Figure 1.12 — Virtual memory: pages swapped between RAM and swap file.**

```text
Physical RAM: Page A, Page B, Page C, Page D, Free, Free
Swap File (SSD): Page E, Page F, Page G, Page H
swap out →   swap in ←
A page fault occurs when a required page is not in RAM.
```

**How it works:** the OS checks whether a page is in RAM; if not, a page fault occurs, an unneeded page is written to the swap file, and the required page is read into RAM. This is much slower than RAM but allows larger programs to run.

### Activity 1.8 — Buffer or Cache?

| Scenario | Buffer or cache? | Why |
|---|---|---|
| Keyboard holds key presses | ? | ? |
| CPU holds recently used data | ? | ? |
| Video player stores ahead | ? | ? |
| L1 holds loop instructions | ? | ? |

#### Checked Answers

Buffer (speed mismatch), cache (locality), buffer (network variation), cache (temporal locality).

### Exam-Style Practice

**Question (3 marks).** Explain how virtual memory allows a program larger than RAM to run.

**Checked answer.** OS divides memory into pages (1); unused pages moved to secondary storage (1); needed pages swapped back into RAM (1).

---

## Section 1.9 — Input and Output Devices

### Learning Objectives

Describe the principles of operation of common input and output devices, including sensors, actuators, printers and displays, and compare HDMI and VGA.

### 1.9.1 Input Devices

An **input device** converts data into a digital signal the computer can process.

| Device | Principle of operation | Typical use |
|---|---|---|
| Keyboard | Key presses close circuits, generating a unique code (e.g. ASCII). | Text and number entry. |
| Mouse | Movement detected by a sensor and translated into cursor movement; buttons register clicks. | Pointing and selection. |
| Microphone | Converts sound waves into electrical signals, then into digital data via an ADC. | Voice input, audio recording. |
| Barcode scanner | Shines light on a barcode; reflected light pattern is converted into a digital code. | Retail, inventory. |
| QR code scanner | Camera captures the QR pattern; software decodes the data. | Mobile payments, advertising. |
| Digital camera | Lens focuses light onto a sensor (CCD/CMOS), which converts it into digital pixels. | Photography, video. |
| 2D/3D scanner | 2D scans documents; 3D scans objects using lasers or structured light. | Document archiving, 3D modelling. |
| Touchscreen | Detects touch via capacitive or resistive layers; position calculated by a microprocessor. | Smartphones, kiosks. |
| Sensors | Measure physical quantities (light, temperature, pressure, moisture) and output a signal. | Monitoring and control systems. |

### 1.9.2 Output Devices

An **output device** presents processed results.

| Device | Principle of operation | Typical use |
|---|---|---|
| Inkjet printer | Sprays tiny droplets of ink onto paper. | Home/office printing. |
| Laser printer | Uses a laser to charge a drum; toner adheres and is fused onto paper. | High-volume printing. |
| 3D printer | Builds objects layer by layer from plastic, resin or metal. | Prototyping, manufacturing. |
| 2D/3D cutter | 2D cuts flat material; 3D cuts or sculpts objects. | Sign-making, fabrication. |
| Speakers/headphones | Convert electrical signals into sound waves. | Audio output. |
| Actuators | Electromechanical devices (motors, valves, relays) producing physical action. | Control systems. |
| LCD/LED display | LCD uses liquid crystals; LED uses light-emitting diodes as backlight or pixels. | Monitors, TVs, phones. |
| LCD/DLP projector | Projects an image onto a screen using LCD panels or DLP micromirrors. | Presentations, cinema. |

### 1.9.3 HDMI vs VGA

| Feature | HDMI | VGA |
|---|---|---|
| Signal | Digital | Analog |
| Audio | Yes (when supported) | No |
| Connector | Compact/flat | 15-pin D-sub |
| Use | Modern displays | Older displays/projectors |

### 1.9.4 Worked Example — Mouse Click

Mouse → I/O controller → device driver → CPU executes → display controller updates monitor. The CPU does not “see” the mouse directly.

### Activity 1.9 — Match the Device

| Task | Most suitable device | Reason |
|---|---|---|
| Enter text into a word processor | ? | ? |
| Read a product barcode at checkout | ? | ? |
| Print a high-volume office document | ? | ? |
| Produce a physical prototype | ? | ? |

#### Checked Answers

Keyboard (text entry), barcode scanner (fast, accurate), laser printer (high volume, low cost per page), 3D printer (layered construction).

### Exam-Style Practice

**Question (2 marks).** Compare HDMI and VGA in signal type and audio support.

**Checked answer.** HDMI is digital and carries audio (when supported); VGA is analog and carries no audio.

---

## Section 1.10 — Network Hardware and Cloud Storage

### Learning Objectives

Define LAN and WAN, identify common network hardware, explain packets, and compare local and cloud storage.

### 1.10.1 Networks

A **LAN** covers a small area; a **WAN** covers a large area. Networks allow resource sharing, communication and central management.

### 1.10.2 Network Hardware

| Device | Role |
|---|---|
| NIC | Connects a device to a network; converts data into signals. |
| Switch | Forwards data within a LAN to the intended device. |
| Router | Connects different networks and forwards packets. |
| WAP | Provides wireless access. |
| Modem | Converts signals between provider and local network. |
| Firewall | Monitors and controls traffic for security. |

Data is broken into **packets** — small units with addressing information. Packets allow many devices to share a network efficiently.

### 1.10.3 Cloud Storage

**Cloud storage** stores data on provider servers accessed over a network. The user's device sends data to a data centre; the provider stores it and makes it available to authorised devices.

| Feature | Local storage | Cloud storage |
|---|---|---|
| Location | User device | Provider servers |
| Access | Direct | Requires network |
| Capacity | Device-limited | Often scalable |
| Sharing | Manual | Easy via links |
| Risk | Device loss/damage | Account security, provider outage |
| Cost | One-off hardware | Subscription/usage-based |

**Advantages:** access from multiple devices, easy backup, scalable capacity, collaboration.  
**Disadvantages:** depends on network, ongoing cost, privacy/security concerns, provider lock-in.

### Activity 1.10 — Local or Cloud?

| Scenario | Better choice | Reason |
|---|---|---|
| Editing a video while travelling | ? | ? |
| Sharing a group project | ? | ? |
| Backing up important photos | ? | ? |
| Storing an OS for fast boot | ? | ? |

#### Checked Answers

Local (no reliable network), cloud (easy sharing), cloud (off-site backup), local (low latency needed).

### Exam-Style Practice

**Question (2 marks).** State one advantage and one disadvantage of cloud storage.

**Checked answer.** Advantage: access from multiple devices or automatic backup (1). Disadvantage: depends on internet connection or raises security concerns (1).

---

## Section 1.11 — Embedded Systems, Monitoring and Control

### Learning Objectives

Define an embedded system, identify its components, explain real-time constraints, and distinguish monitoring from control systems.

### 1.11.1 Embedded Systems

An **embedded system** is a computer dedicated to a specific function inside a larger device. Components: microcontroller/processor, memory, sensors, actuators, I/O interfaces. Examples: washing machine, car control system, smart speaker, traffic light.

### 1.11.2 Real-Time Constraints

**Hard real-time:** missing the deadline is a failure (airbag).  
**Soft real-time:** missing the deadline degrades quality (video streaming).

### 1.11.3 Monitoring and Control

A **monitoring system** observes and reports. A **control system** observes and acts automatically. Sensors measure; actuators act; feedback adjusts future action.

| System type | Job | Example |
|---|---|---|
| Monitoring | Observe and report | Temperature display |
| Control | Observe and act | Thermostat switching heater |
| Combined | Observe, report, act | Smart thermostat |

### 1.11.4 Worked Example — Greenhouse

A greenhouse controller uses temperature and moisture sensors; it compares readings with target ranges and switches heaters, vents and water valves. This is a combined monitoring and control system with feedback.

### Activity 1.11 — Identify Sensors and Actuators

| System | Sensor | Actuator |
|---|---|---|
| Washing machine | ? | ? |
| Greenhouse | ? | ? |
| Anti-lock brakes | ? | ? |
| Smart speaker | ? | ? |

#### Checked Answers

Water level/temperature; motor/valve. Temperature; heater/vent. Wheel speed; brake pressure modulator. Microphone; speaker.

### Exam-Style Practice

**Question (3 marks).** Describe three components of an embedded washing-machine system and their roles.

**Checked answer.** Microcontroller executes the program (1); sensor monitors water level/temperature (1); actuator drives motor/valve (1).

---

## Section 1.12 — Processor Specialisation and CPU Core Types

### Learning Objectives

Compare CPU, GPU and TPU in latency and throughput, and distinguish P-cores from E-cores.

### 1.12.1 CPU, GPU, TPU

| Processor | Design goal | Best at | Limitation |
|---|---|---|---|
| CPU | Low latency | Sequential, branchy code | Lower parallel throughput |
| GPU | High throughput | Graphics, parallel numerics | Weak on branchy sequential code |
| TPU | Very high throughput for tensor maths | Matrix multiplication | Narrow specialisation |

### 1.12.2 P-cores and E-cores

**P-cores** prioritise performance on demanding tasks. **E-cores** prioritise power efficiency on background tasks. More cores help only if the workload can use them.

### Activity 1.12 — Choose the Processor

| Scenario | Best choice | Reason |
|---|---|---|
| Running a word processor | ? | ? |
| Rendering 3D game frames | ? | ? |
| Training a neural network | ? | ? |
| Anti-lock braking control | ? | ? |

#### Checked Answers

CPU (sequential), GPU (parallel pixels), TPU (matrix maths), microcontroller (hard real-time).

### Exam-Style Practice

**Question (4 marks).** Compare CPU, GPU and TPU for running an OS, rendering graphics and training a neural network.

**Checked answer.** CPU for OS (sequential) (1); GPU for graphics (parallel pixels) (1); TPU for training (matrix multiplication) (1); each balances latency and throughput differently (1).

---

## Section 1.13 — Module Summary: Key Comparisons

| Topic | Core comparison |
|---|---|
| §1.2 Binary/denary/hex | Base and bit grouping; units bit → TB |
| §1.3 Logic | Gates, truth tables, half-adder |
| §1.4 Von Neumann | Registers and three buses |
| §1.5 FDE | Stage order; interrupts/ISR |
| §1.6 Memory hierarchy | Speed vs capacity vs cost; locality |
| §1.7 RAM/ROM | DRAM vs SRAM; PROM/EPROM/EEPROM; flash |
| §1.8 Buffers/virtual memory | Transfer storage; RAM + secondary storage |
| §1.9 I/O devices | Input principles; output principles; HDMI vs VGA |
| §1.10 Networks/cloud | Network hardware; local vs cloud |
| §1.11 Embedded/control | Specific function; real-time; sensors/actuators/feedback |
| §1.12 Processors | Latency vs throughput; P-core vs E-core |

---

## Section 1.14 — Exam-Style Mixed Practice

1. **(2 marks)** Explain why hexadecimal is used for memory addresses.  
   **Answer:** Each hex digit = 4 bits; compact and less error-prone.

2. **(4 marks)** Describe the fetch stage of the FDE cycle.  
   **Answer:** `PC → MAR` via address bus; `READ` on control bus; memory → MDR via data bus; `MDR → CIR`; PC incremented.

3. **(3 marks)** Explain what happens when an interrupt is received.  
   **Answer:** Save state; service highest-priority ISR; restore state and continue.

4. **(2 marks)** Explain why cache sits between CPU and main memory.  
   **Answer:** Faster; holds frequently used data close to CPU; reduces wait time.

5. **(3 marks)** Explain how virtual memory allows a larger program to run.  
   **Answer:** Pages moved to secondary storage and swapped back when needed.

6. **(2 marks)** State one advantage and one disadvantage of cloud storage.  
   **Answer:** Access from multiple devices; depends on network/security risk.

7. **(3 marks)** Describe three components of an embedded washing-machine system.  
   **Answer:** Microcontroller executes program; sensor monitors water/temperature; actuator drives motor/valve.

8. **(2 marks)** Compare HDMI and VGA in signal type and audio support.  
   **Answer:** HDMI digital + audio; VGA analog, no audio.

9. **(4 marks)** Compare CPU, GPU and TPU for OS, graphics and neural-network training.  
   **Answer:** CPU (sequential OS), GPU (parallel graphics), TPU (matrix training); different latency/throughput balances.

10. **(2 marks)** State the difference between a P-core and an E-core.  
    **Answer:** P-core high performance; E-core lower power for background work.

---

## Section 1.15 — Glossary

| Term | Definition |
|---|---|
| Actuator | Output device producing physical action. |
| Address bus | Uni-directional bus carrying memory addresses. |
| ALU | Arithmetic Logic Unit; performs arithmetic and logic. |
| ASIC | Application-specific integrated circuit. |
| Bit | A single binary digit. |
| Buffer | Temporary storage during data transfer. |
| Bus | Set of parallel wires carrying signals. |
| Cache | Small fast memory holding frequently used data. |
| Cloud storage | Data stored on remote servers accessed over a network. |
| Control bus | Bus carrying timing and command signals. |
| Control system | System that observes and acts automatically. |
| CPU | Central Processing Unit. |
| CU | Control Unit. |
| Data bus | Bi-directional bus carrying data and instructions. |
| Denary | Base-10 number system. |
| DRAM | Dynamic RAM; needs refresh. |
| EEPROM | Electrically erasable programmable ROM. |
| Embedded system | Computer dedicated to a specific function. |
| EPROM | Erasable programmable ROM (UV light). |
| Feedback | Using measured output to adjust action. |
| Firmware | Software stored permanently in hardware. |
| Flash memory | Non-volatile memory erased in blocks. |
| FDE cycle | Fetch-Decode-Execute cycle. |
| GPU | Graphics Processing Unit. |
| HDMI | Digital video/audio connection. |
| Hexadecimal | Base-16 number system. |
| IAS | Immediate Access Store (registers + cache). |
| Interrupt | Signal causing processor to suspend current task. |
| ISR | Interrupt Service Routine. |
| LAN | Local Area Network. |
| Latency | Delay before data is available. |
| Logic gate | Circuit implementing a logical operation. |
| MAR | Memory Address Register. |
| MDR | Memory Data Register. |
| Monitoring system | System that observes and reports. |
| Motherboard | Main circuit board connecting components. |
| Nibble | 4 bits. |
| NIC | Network Interface Card. |
| Opcode | Part of an instruction specifying the operation. |
| Packet | Small unit of network data. |
| Page | Fixed-size block moved between RAM and storage. |
| PC | Program Counter. |
| P-core | Performance core. |
| E-core | Efficiency core. |
| PROM | Programmable ROM (usually once). |
| RAM | Volatile working memory. |
| Register | Fast storage inside the CPU. |
| ROM | Non-volatile memory for firmware. |
| Router | Connects different networks. |
| SIMT | Single Instruction, Multiple Threads. |
| SRAM | Static RAM; no refresh while powered. |
| Status Register | Holds condition flags. |
| Swap file | Storage area used for virtual memory. |
| Switch | Connects devices in a LAN. |
| Systolic array | Grid of processing elements for matrix operations. |
| Thrashing | Excessive swapping. |
| Throughput | Tasks completed per unit time. |
| TPU | Tensor Processing Unit. |
| Transistor | Tiny electronic switch. |
| Virtual memory | Using secondary storage as extra RAM. |
| VGA | Older analog video connection. |
| Volatile | Loses contents when power is removed. |
| WAN | Wide Area Network. |

---

## Section 1.16 — References and Attribution

- Watson, D. and Williams, H. *Cambridge IGCSE and O Level Computer Science*. Hodder Education. Chapters on binary systems, logic gates, computer architecture, input/output devices, and memory and data storage.
- Watson, D. and Williams, H. *Cambridge International AS & A Level Computer Science*. Hodder Education. Chapters on hardware, processor fundamentals, and system software.
- Cambridge IGCSE Computer Science 0478 / O Level 2210 syllabus.
- CIE AS & A Level 9618 syllabus.

All conversion calculations, truth tables, latency figures and comparison tables were recomputed and checked during review.

---

## Conversion Helper (for Workflow B)

This module is self-contained and does not depend on any other module. If you are converting it to another format or feeding it into an automated workflow, note:

- All diagrams are labelled `Figure 1.x` and can be replaced by their caption/text equivalent.
- All activities have “Checked Answers” immediately after; the checked answer is the authoritative answer.
- All exam-style practice questions have “Checked answer” lines; these are the mark-scheme equivalents.
- The glossary is the canonical definition source; terms are defined at first use in the body as well.

---

**End of Module 1 — Computer Hardware & Microarchitecture (V2.0)**
