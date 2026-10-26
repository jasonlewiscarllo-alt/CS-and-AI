## ***<h1 align="center">Computer Science & Artificial Intelligence Study Guide</h1>***

### **Hardware Study Guide**
#### **1. Central Processing Unit Architecture**
#### *Question: What is the Central Processing Unit (CPU) and what are its primary components?*
#### *Answer: The CPU is the primary component that executes instructions in a computer. Its main components are the Control Unit (CU) which directs operations, the Arithmetic Logic Unit (ALU) which performs mathematical and logical operations, and Registers which store high-speed temporary data.*
#### **2. Memory Types: RAM vs. ROM**
#### *Question: What is the difference between RAM and ROM?*
#### *Answer: Random Access Memory (RAM) is volatile memory used for temporary storage of working data while the computer is powered on. Read-Only Memory (ROM) is non-volatile memory containing permanent instructions (like BIOS/UEFI firmware) required to boot the computer.*
#### **3. Storage Technologies**
#### *Question: How do Solid-State Drives (SSDs) differ from Hard Disk Drives (HDDs)?*
#### *Answer: HDDs use mechanical spinning magnetic disks and read/write heads to store data, making them slower and prone to mechanical wear. SSDs use flash memory (NAND chips) with no moving parts, resulting in significantly faster access speeds, durability, and lower power consumption.*
#### **4. Mainboard Integration**
#### *Question: What is the Motherboard and what is its main function?*
#### *Answer: The motherboard is the primary printed circuit board (PCB) in a computer that serves as the central communications hub, connecting all hardware components such as the CPU, RAM, storage, expansion cards, and peripheral ports.*
#### **5. Parallel Processing: GPUs**
#### *Question: What is a Graphics Processing Unit (GPU) and how does it differ from a CPU?*
#### *Answer: A CPU is designed with a few powerful cores optimized for sequential processing of general tasks. A GPU consists of thousands of smaller cores designed for parallel processing, making it ideal for graphics rendering, 3D simulation, and machine learning computations.*
#### **6. Power Infrastructure**
#### *Question: What is the purpose of Power Supply Units (PSU)?*
#### *Answer: The PSU converts high-voltage alternating current (AC) power from an electrical wall outlet into low-voltage direct current (DC) power required by internal computer hardware components.*
#### **7. Processor Caching Mechanisms**
#### *Question: What is cache memory and why is it important in processors?*
#### *Answer: Cache memory (L1, L2, L3) is small, extremely fast SRAM built directly onto or near the CPU die. It stores frequently accessed data and instructions to minimize latency by reducing CPU wait time when fetching data from main system RAM.*
#### **8. Data Volatility**
#### *Question: What is the difference between volatile and non-volatile memory?*
#### *Answer: Volatile memory requires continuous electrical power to retain stored data (e.g., RAM); data is lost when power is turned off. Non-volatile memory retains saved data permanently even when the power supply is disconnected (e.g., SSDs, HDDs, ROM).*
#### **9. Interconnect Architectures**
#### *Question: What is a Bus in computer architecture?*
#### *Answer: A bus is a high-speed communication pathway (a collection of wires or traces) that transfers data, signals, and power between different hardware components within a computer system (e.g., PCIe bus, Data bus, Address bus).*
#### **10. Peripheral Interface Control**
#### *Question: What is an Input/Output (I/O) Controller?*
#### *Answer: An I/O controller is a dedicated hardware chip that manages communication and data flow between the processor/RAM and external peripheral devices like #### *keyboards, mice, storage drives, and display monitors.*

#### *Computer Networks Study Guide*
#### **1. Network Fundamentals**
#### *Question: What is a Computer Network?and it's key components*
#### *Answer: A computer network is an interconnected group of autonomous computing devices that exchange data and share resources (such as files, internet access, and printers) using common communication protocols over physical or wireless media.They are nodes,links,routers and switch*

#### **2. Geographic Network Scopes**
#### *Question: What is the difference between a LAN and a WAN?*
#### *Answer: A Local Area Network (LAN) covers a small geographical area like a single home, office, or building with high data transfer speeds. A Wide Area Network (WAN) spans large geographical distances (connecting cities or countries), such as the internet.*
#### **3. Network Layer Addressing**
#### *Question: What is an IP address and what are the two main versions in use?*
#### *Answer: An IP (Internet Protocol) address is a unique numerical label assigned to every device on a network for identification and location addressing. The two main versions are IPv4 (32-bit address format) and IPv6 (128-bit address format).*
#### **4. Name Resolution**
#### *Question: How does the Domain Name System (DNS) work?*
#### *Answer: DNS acts as the "phonebook" of the internet. It translates human-readable domain names (like example.com) into machine-readable IP addresses (like 192.0.2.1) so web browsers can load internet resources.*
#### **7. Data Link Hardware Identification**
#### *Question: What is a MAC Address and how does it differ from an IP Address?*
#### *Answer: A MAC (Media Access Control) address is a permanent, hardware-embedded physical identifier assigned to a network interface card at manufacturing. An IP address is a logical network address assigned dynamically or statically by network configurations.*
#### **8. Network Topologies**
#### *Question: What is Network Topology and what is the most common type?*
#### *Answer: Network topology refers to the structural arrangement of nodes and links in a computer network. The most common topology is the Hybrid topology.*
#### **10. Secure Tunneling**
#### *Question: What is a Virtual Private Network (VPN)?*
#### *Answer: A VPN creates an encrypted tunnel across a public or untrusted network (like the internet), allowing devices to securely send and receive data as if they were directly connected to a private local network.*

#### **Behavioral AI Study Guide**
#### **1. Foundations of Behavioral AI**
#### *Question: What is Behavioral AI?*
#### *Answer: Behavioral AI refers to artificial intelligence systems designed to model, simulate, analyze, or predict human and autonomous agent behaviors by learning patterns from historical action data, decisions, and environment interactions.*
#### **2. Learning Through Environment Interaction**
#### *Question: How does Reinforcement Learning (RL) drive Behavioral AI?*
#### *Answer: RL trains AI agents to make sequential decisions by interacting with an environment, receiving positive rewards for desired actions and penalties for unwanted ones, enabling the agent to learn optimal behavioral strategies.*
#### **3. Discrete State Control**
#### *Question: What is a Finite State Machine (FSM) in behavioral game AI?*
#### *Answer: An FSM is a decision model where an AI agent can exist in one of a finite number of discrete states (e.g., Idle, Patrol, Chase, Attack) and transitions between them based on specific environmental inputs or triggers.*
#### **4. Modular Decision Architectures**
#### *Question: What are Behavior Trees and why are they widely used?*
#### *Answer: Behavior Trees are modular, tree-structured decision-making frameworks composed of composite, decorator, and leaf nodes. They are widely used because they offer better scalability, modularity, and maintainability than FSMs in complex AI behaviors.*
#### **5. Security Threat Detection**
#### *Question: How is Behavioral AI utilized in User and Entity Behavior Analytics (UEBA) for cybersecurity?*
#### *Answer: UEBA establishes a baseline of normal behavior for users and devices across a network. It continuously monitors activity to detect anomalous behavioral patterns that signal compromised accounts, data exfiltration, or insider threats.*
#### **6. Score-Based Action Selection**
#### *Question: What is Utility AI and how does it make choices?*
#### *Answer: Utility AI calculates a numerical score (utility) for multiple competing actions based on weighted environmental factors and internal needs, selecting the action that delivers the highest utility value at any given moment.*
#### **7. Multi-Agent Systems**
#### *Question: What is Agent-Based Modeling (ABM) in Behavioral AI?*
#### *Answer: ABM is a computational simulation technique where autonomous agents follow individual behavioral rules within a shared environment, allowing researchers to observe emergent macro-level system behaviors (e.g., crowd movement, market dynamics).*
#### **8. Adaptive Personalization**
#### *Question: How does Behavioral AI personalize User Experience (UX) in E-Commerce?*
#### *Answer: By evaluating real-time user clickstream data, search history, dwell time, and purchasing habits, Behavioral AI dynamically tailors product recommendations, search rankings, and personalized marketing messages.*
#### **9. Ethics and Governance**
#### *Question: What are the key ethical concerns associated with Behavioral AI?*
#### *Answer: Key concerns include consumer privacy violations through constant behavioral profiling, psychological manipulation (e.g., dark patterns or addictive features), algorithmic bias, and potential unauthorized surveillance.*
#### **10. Paradigm Shifts in AI Control**
#### *Question: How does Behavioral AI differ from traditional rule-based AI systems?*
#### *Answer: Traditional rule-based AI relies on static, hardcoded "if-then" logic created manually by programmers. Behavioral AI dynamically adapts, learns, and evolves its actions over time based on real-world interaction data and environmental feedback.*

Source : Gemini AI
