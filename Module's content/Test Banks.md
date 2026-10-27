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
# Networks — Test Bank

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Source:** Networks.md (Stage 1 snapshot, reviewed by Rysen)

---

## Part 1 — Quick Reviews and Reviews (with answers)

### Quick Review 1 (Section 3)
**Question:** What is the definition of a computer network and its key components?

**Answer:** A computer network is two or more devices connected together so they can share information and resources. Its key components are:
- **Nodes (devices):** any device connected to the network, such as phones, laptops, or printers.
- **Links (connections):** the wired or wireless pathways that allow devices to communicate.
- **Routers:** devices that connect different networks and forward data between them.
- **Switches:** devices that direct data to the intended device within a local area network (LAN).

---

### Review 1 (Section 5.3)
**Question:** What are the three parts of a packet and what does each do?

**Answer:**
- **Header:** Stores control information including source address, destination address, and sequence number. It helps the packet reach the right device and be reassembled in order.
- **Payload:** Carries the actual data being transmitted.
- **Trailer:** Marks the end of the packet and contains error detection bits.

---

### Quick Review 2 (Section 6.1)
**Question:** What is the definition of computer networks and its key components?

**Answer:** A computer network is two or more devices connected together so they can share information and resources. Its key components are:
- **Nodes (devices):** any device connected to the network, such as phones, laptops, or printers.
- **Links (connections):** the wired or wireless pathways that allow devices to communicate.
- **Routers:** devices that connect different networks and forward data between them.
- **Switches:** devices that direct data to the intended device within a local area network (LAN).

*(Note: This duplicates Quick Review 1; you may remove it from the test bank.)*

---

### Quick Review 3 (Section 6.2.2)
**Question:** What is an IP address and what are the two main versions in use?

**Answer:** An IP address is a software-assigned numerical label given to a device whenever it connects to a network. The two main versions are:
- **IPv4:** 32-bit address written in denary, e.g., `93.184.216.34`.
- **IPv6:** 128-bit address written in hexadecimal, e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`.

---

### Quick Review 4 (Section 6.2.2)
**Question:** What is a MAC address and how does it differ from an IP address?

**Answer:** A MAC address is a unique 48-bit physical identifier hardcoded into a Network Interface Card (NIC) by the manufacturer. An IP address is a software-assigned numerical label given to a device when it connects to a network. The key differences are:
- A MAC address is **physical and permanent** (burned into the hardware); an IP address is **logical and can change** each time a device connects to a different network.
- A MAC address identifies the **hardware interface** on a local network; an IP address identifies the **device's location** on a network so data can be routed across the internet.

---

### Review 2 (Section 6.3)
**Question:** How does the Domain Name System (DNS) work?

**Answer:** DNS translates human-readable domain names (such as `google.com`) into machine-readable IP addresses. When you type a domain name into a browser, DNS looks up the corresponding IP address so your device can locate and connect to the correct web server.

---

### Review 3 (Section 7.9)
**Question:** What is network topology and what are the common types?

**Answer:** Network topology is the physical or logical arrangement of nodes and links in a network. Common types include **bus, point-to-point, star, mesh, ring, hybrid, and tree**, each with different trade-offs in cost, complexity, fault tolerance, and scalability.

---

### Review 4 (Section 8.3)
**Question:** What are the three types of data flow?

**Answer:**
- **Simplex:** Data travels in one direction only (e.g., TV broadcast, keyboard input).
- **Half-duplex:** Data travels in both directions but not at the same time (e.g., walkie-talkies).
- **Full-duplex:** Data travels in both directions at the same time (e.g., telephone conversation).

---

### Review 5 (Section 8.3)
**Question:** What is the difference between serial and parallel transmission?

**Answer:** Serial transmission sends data one bit at a time along a single channel, making it slower but suitable for longer distances with less cabling. Parallel transmission sends many bits at the same time along multiple channels, making it faster but only suitable for short distances.

---

### Review 6 (Section 8.3)
**Question:** What is the difference between synchronous and asynchronous transmission?

**Answer:** Synchronous transmission requires both devices to be synchronized in time. The client sends a request and waits for a response before continuing (blocking). Asynchronous transmission does not require the client to wait — it can continue other work after sending a request (non-blocking). Synchronous works in real time; asynchronous works in bursts with irregular time gaps.

---

### Review 7 (Section 9.2.2)
**Question:** What is the difference between a LAN and a WAN?

**Answer:** A LAN (Local Area Network) connects devices in a single, limited area such as a home or office. It typically uses star topology and is cheaper and simpler to maintain. A WAN (Wide Area Network) connects computers and smaller networks over large geographical areas such as cities, countries, or continents. It typically uses mesh or hybrid topology, requires more complex infrastructure, and is more expensive to maintain.

---

### Review 8 (Section 9.2.2)
**Question:** What is the difference between the client-server model and the peer-to-peer model?

**Answer:** In the client-server model, roles are fixed: a dedicated server stores data and processes requests, while clients request and consume services. It is centralized. In the peer-to-peer model, every participant has equal status and acts as both client and server at the same time. It is decentralized and does not need a central authority.

---

### Review 9 (Section 10.9)
**Question:** Name three types of malware and one countermeasure for each.

**Answer:**
- **Virus:** Attaches to host files and replicates. Countermeasure: Antivirus and anti-malware.
- **Worm:** Self-replicates and spreads across networks. Countermeasure: Firewall and antivirus.
- **Ransomware:** Encrypts files and demands payment. Countermeasure: Regular backups and antivirus.
- (Also acceptable: Trojan Horse, Spyware, Adware with appropriate countermeasures.)

---

### Review 10 (Section 10.9)
**Question:** Name two cyberattacks and one defence for each.

**Answer:**
- **Brute-force attack:** Defence — Authentication with multi-factor authentication (MFA) and account lockout policies.
- **Data interception (packet sniffing):** Defence — Encryption (HTTPS) and VPN.
- (Also acceptable: DDoS with IDS/IPS; phishing with user awareness and authentication.)

---

### Review 11 (Section 10.9)
**Question:** Name all three network types with the topology each commonly uses and why.

**Answer:**
- **LAN (Local Area Network):** Uses star topology because if one cable or device fails, only that device goes down; the rest of the network keeps working. It is also easy to add or remove devices.
- **WAN (Wide Area Network):** Uses mesh or hybrid topology because it connects distinct cities or countries using multiple redundant paths. If one cable is cut, traffic automatically reroutes.
- **MAN (Metropolitan Area Network):** Uses tree topology because it allows a central "root" (such as a city government) to branch down to individual departments, schools, and police stations across a city.

---

## Part 2 — Worked Examples (demonstrations)

### Worked Example 1: Tracing a Packet Through a Network

**Scenario:** You send a message from your laptop to a web server. The message is 1 MB, which the network splits into 100 packets.

| Step | What happens | Key concept |
|------|--------------|-------------|
| 1 | The message is divided into 100 packets. Each packet gets a header with source IP, destination IP, and sequence number (1–100). | Packetisation |
| 2 | A trailer is added to each packet for error checking. | Error detection |
| 3 | Your laptop sends the packets to your router. The router examines the destination IP in each header and forwards the packet toward the internet. | Routing |
| 4 | The packets travel through multiple routers. Some packets take faster routes and arrive out of order. | Packet switching |
| 5 | The web server receives the packets. Using the sequence numbers, it reassembles them in the correct order (1, 2, 3, …). | Reassembly |
| 6 | If a packet is lost, TCP detects the gap and requests retransmission. | Reliability |

---

### Worked Example 2: Choosing a Network Topology

**Scenario:** A small business has 10 employees and a limited budget. They need a reliable network where one broken cable does not stop everyone from working.

| Consideration | Analysis | Decision |
|---------------|----------|----------|
| Budget | Limited | Star topology uses more cable than bus but is affordable for 10 devices. |
| Reliability | One broken cable should not affect everyone | Star isolates failures to individual devices. |
| Scalability | May add more employees later | Star makes it easy to add devices. |
| **Recommendation** | **Star topology** | Best balance of cost, reliability, and scalability for this scenario. |

---

### Worked Example 3: Breaking Down a URL

**URL:** `https://www.bbc.co.uk/news`

| Part | Value | Explanation |
|------|-------|-------------|
| Protocol | `https` | Secure web protocol. |
| Subdomain | `www` | World Wide Web. |
| Domain name | `bbc` | The organization's name. |
| Second-level domain | `co` | Indicates commercial organization. |
| Top-level domain (country code) | `uk` | United Kingdom. |
| Path | `/news` | The specific page on the website. |

---

## Part 3 — Structured Learner Activities (with expected outcomes)

### Activity 1: Label the Parts of a Packet

**Instructions:** Draw or describe a packet with three parts. Label each part and write one sentence explaining its purpose.

**Expected outcome:**
- **Header:** Contains source address, destination address, and sequence number. It helps the packet reach the right device and be reassembled in order.
- **Payload:** Contains the actual data being transmitted.
- **Trailer:** Marks the end of the packet and contains error detection bits.

---

### Activity 2: Choose a Topology

**Scenario:** A university is building a new campus network connecting five buildings across a city. The network must be reliable, and if one building's connection fails, the others should keep working.

**Question:** Which topology would you recommend and why?

**Expected answer:** **Mesh or hybrid topology.** A mesh topology provides multiple redundant paths, so if one link fails, data can reroute through another path. A hybrid topology could combine a star topology within each building (connecting devices to a local switch) with a mesh topology between buildings for redundancy. A bus or ring topology would be unsuitable because a single failure could affect the entire network.

---

### Activity 3: Match the Threat to the Countermeasure

**Instructions:** Draw lines to match each threat on the left to an appropriate countermeasure on the right.

| Threat | Countermeasure |
|--------|----------------|
| Virus | Antivirus and anti-malware |
| Brute-force attack | Multi-factor authentication (MFA) |
| Packet sniffing | Encryption (HTTPS/VPN) |
| DDoS | Intrusion Detection and Prevention Systems (IDS/IPS) |

**Expected outcome:** Each threat is matched to a countermeasure that directly addresses it, as shown in the Threat–Countermeasure Mapping table in Section 10.8 of Networks.md.

---

### Activity 4: Break Down a URL

**Instructions:** For the URL `https://store.example.co.uk/product/123`, identify each part.

**Expected answer:**

| Part | Value |
|------|-------|
| Protocol | `https` |
| Subdomain | `store` |
| Domain name | `example` |
| Second-level domain | `co` |
| Top-level domain (country code) | `uk` |
| Path | `/product/123` |

---

### Activity 5: Classify the Data Flow

**Instructions:** For each scenario below, state whether it uses simplex, half-duplex, or full-duplex communication.

1. A TV broadcast
2. A telephone conversation
3. A walkie-talkie conversation
4. A keyboard sending input to a computer
5. Two people chatting over a video call

**Expected answers:**
1. **Simplex** — data travels in one direction only.
2. **Full-duplex** — both directions at the same time.
3. **Half-duplex** — both directions but not at the same time.
4. **Simplex** — one direction only.
5. **Full-duplex** — both directions at the same time.

---

### Activity 6: Choose the Right Transmission Method

**Instructions:** For each scenario, state whether serial or parallel transmission would be more appropriate and explain why.

1. Connecting a keyboard to a computer over a 2-metre cable
2. Sending data between two buildings 500 metres apart
3. Connecting a printer to a computer using an older 25-pin cable

**Expected answers:**
1. **Serial** — modern keyboards use USB, which is serial. Serial works well over short distances with less cabling.
2. **Serial** — parallel is unreliable over long distances due to skew and crosstalk.
3. **Parallel** — older printer cables used parallel transmission for short distances.

---

## Part 4 — Review Questions with Answers (20 questions)

### Question 1
**Q:** What is the difference between TCP and IP?

**A:** TCP is a connection-oriented protocol that ensures reliable, in-order delivery. IP is a connectionless protocol that handles addressing and routing. TCP is layered on top of IP to provide reliability that IP lacks.

---

### Question 2
**Q:** What is the difference between a router and a switch?

**A:** A router connects different networks and forwards data between them by examining destination IP addresses. A switch connects multiple devices within a LAN and directs data to the intended device using MAC addresses.

---

### Question 3
**Q:** What is the difference between a virus and a worm?

**A:** A virus attaches itself to a host file and requires user action to spread. A worm is a standalone program that self-replicates and spreads across networks without needing a host file or user action.

---

### Question 4
**Q:** What is the difference between phishing and pharming?

**A:** Phishing sends fraudulent messages that trick users into revealing information. Pharming redirects users from legitimate websites to fake replica sites using DNS manipulation. Phishing relies on user action; pharming redirects automatically.

---

### Question 5
**Q:** Which topology would you recommend for a school computer lab and why?

**A:** **Star topology.** Each computer connects independently to a central switch. If one cable or computer fails, only that node goes down. It is also easy to add or remove computers.

---

### Question 6
**Q:** Why is packet switching efficient?

**A:** Packet switching breaks data into small packets that can travel through available routes. Many devices can send data at the same time. If a router or link fails, packets reroute around the problem.

---

### Question 7
**Q:** What is the difference between symmetric and asymmetric encryption?

**A:** Symmetric encryption uses the same key to encrypt and decrypt data. Asymmetric encryption uses two different keys: a public key to encrypt and a private key to decrypt. HTTPS uses asymmetric encryption to exchange a symmetric session key, then uses the faster symmetric encryption for the actual data.

---

### Question 8
**Q:** What is the difference between a LAN and a WAN?

**A:** A LAN connects devices in a single, limited area such as a home or office. A WAN connects networks over large geographical areas such as cities or countries.

---

### Question 9
**Q:** What is the difference between the client-server model and the peer-to-peer model?

**A:** In the client-server model, roles are fixed: a server provides resources and clients consume them. In the peer-to-peer model, every node has equal status and acts as both client and server.

---

### Question 10
**Q:** Name all three network types (LAN, WAN, MAN) with the topology each commonly uses and why.

**A:**
- **LAN:** Star topology — isolates failures and is easy to expand.
- **WAN:** Mesh or hybrid topology — provides redundant paths across large distances.
- **MAN:** Tree topology — hierarchical structure suits city-wide or campus networks.

---

### Question 11
**Q:** What are the three parts of a packet and what does each do?

**A:**
- **Header:** Stores control information including source address, destination address, and sequence number. It helps the packet reach the right device and be reassembled in order.
- **Payload:** Carries the actual data being transmitted.
- **Trailer:** Marks the end of the packet and contains error detection bits.

---

### Question 12
**Q:** What is the difference between a MAC address and an IP address?

**A:** A MAC address is a unique 48-bit physical identifier hardcoded into a NIC by the manufacturer. An IP address is a software-assigned logical address given to a device when it connects to a network. A MAC address is permanent; an IP address can change.

---

### Question 13
**Q:** What is a URL and what are its main parts?

**A:** A URL is the address of a source on the internet. Its main parts are:
- **Protocol:** Determines how data is transferred (e.g., HTTP or HTTPS).
- **Subdomain:** Identifies each area of the website (e.g., www).
- **Domain name:** The unique, human-readable name of a specific website.
- **Top-level domain:** Categorizes the website by purpose, industry, or location (e.g., .com, .org, .edu, .uk).

---

### Question 14
**Q:** What are the three types of data flow?

**A:**
- **Simplex:** Data travels in one direction only (e.g., TV broadcast, keyboard input).
- **Half-duplex:** Data travels in both directions but not at the same time (e.g., walkie-talkies).
- **Full-duplex:** Data travels in both directions at the same time (e.g., telephone conversation).

---

### Question 15
**Q:** What is the difference between serial and parallel transmission?

**A:** Serial transmission sends data one bit at a time along a single channel, making it slower but suitable for longer distances with less cabling. Parallel transmission sends many bits at the same time along multiple channels, making it faster but only suitable for short distances.

---

### Question 16
**Q:** What is the difference between synchronous and asynchronous transmission?

**A:** Synchronous transmission requires both devices to be synchronized in time. The client sends a request and waits for a response before continuing (blocking). Asynchronous transmission does not require the client to wait — it can continue other work after sending a request (non-blocking). Synchronous works in real time; asynchronous works in bursts with irregular time gaps.

---

### Question 17
**Q:** What is a DDoS attack and how can it be defended against?

**A:** A Distributed Denial of Service (DDoS) attack overwhelms a server or network with a massive flood of data requests from a botnet of multiple infected computers, causing it to crash or become unavailable. It can be defended against using Intrusion Detection and Prevention Systems (IDS/IPS), which monitor traffic patterns, identify abnormal flood requests, and automatically filter or rate-limit malicious traffic.

---

### Question 18
**Q:** What is social engineering?

**A:** Social engineering is the manipulation of human psychology (trust, fear, curiosity, or authority) to persuade individuals to break security procedures or reveal confidential information. It targets people rather than technical systems.

---

### Question 19
**Q:** Why is encryption important for network security?

**A:** Encryption converts readable information into an encoded form so that unauthorized people cannot easily understand it. It protects data in transit — for example, HTTPS encrypts web communication, and a VPN encrypts data travelling across an untrusted network. Even if an eavesdropper captures the packets, they only see unreadable ciphertext.

---

### Question 20
**Q:** Name three network topologies and state one advantage and one disadvantage of each.

**A:**
- **Star:** Advantage — isolated failures (one broken cable only affects one device). Disadvantage — the central hub is a single point of failure.
- **Bus:** Advantage — cost-effective (least cabling required). Disadvantage — a break in the backbone cable brings down the entire network.
- **Mesh:** Advantage — high fault tolerance (no single point of failure). Disadvantage — high cabling cost and complex setup.

---

## Appendix — Image Manifest (optional for test bank)

The structured `Networks.md` uses placeholder alt text and local paths such as `assets/diagrams/packet-routing.png`. The table below maps each figure to the original image URL from the raw draft so you can download and save them locally. You can remove this appendix if the test bank does not require images.

| Figure | Description | Suggested local filename | Source URL |
|--------|-------------|--------------------------|------------|
| Fig 1 | Packet structure | `packet-structure.png` | https://github.com/user-attachments/assets/06815940-666a-479b-b6ba-5bd465a1e12d |
| Fig 2 | Packet routing | `packet-routing.png` | https://github.com/user-attachments/assets/cd4b78e7-9c64-459c-b848-25866e2cfe69 |
| Fig 3 | URL structure | `url-structure.png` | https://github.com/user-attachments/assets/9e4d2275-3699-430f-9aa2-427a474ec29c |
| Fig 4 | Bus topology | `topology-bus.png` | https://github.com/user-attachments/assets/0e5488f7-ad58-41a1-9c59-784db3c6ead3 |
| Fig 5 | Point-to-point topology | `topology-point-to-point.png` | https://github.com/user-attachments/assets/49e98028-962f-4e68-a197-e26e9b3bbc94 |
| Fig 6 | Star topology | `topology-star.png` | https://github.com/user-attachments/assets/6ca71f98-f097-4e52-9443-f8fac7ec1ef4 |
| Fig 7 | Mesh topology | `topology-mesh.png` | https://github.com/user-attachments/assets/44a193b5-a518-40f6-943d-8c119de1a099 |
| Fig 8 | Ring topology | `topology-ring.png` | https://github.com/user-attachments/assets/d9f40110-446f-46d9-9a1b-978836aedc24 |
| Fig 9 | Hybrid topology | `topology-hybrid.png` | https://github.com/user-attachments/assets/fc597be3-0501-4658-91c2-05ac0470382f |
| Fig 10 | Tree topology | `topology-tree.png` | https://github.com/user-attachments/assets/e35bc84e-4279-489a-818f-df85d0bfb347 |
| Fig 11 | Simplex data flow | `dataflow-simplex.png` | https://github.com/user-attachments/assets/a6d2268c-d2b5-49b4-8342-00c5042b2584 |
| Fig 12 | Full-duplex data flow | `dataflow-full-duplex.png` | https://github.com/user-attachments/assets/75772075-200d-4701-a97a-dadc764392f9 |
| Fig 13 | Half-duplex data flow | `dataflow-half-duplex.png` | https://github.com/user-attachments/assets/09115fb2-014b-4257-ae1a-73a62f031afc |
| Fig 14 | Serial transmission | `transmission-serial.png` | https://github.com/user-attachments/assets/447bd65c-bfc0-4c3d-8389-ae817c81a22a |
| Fig 15 | Parallel transmission | `transmission-parallel.png` | https://github.com/user-attachments/assets/a9ab9e0b-133b-4e4e-87f2-b81eef3c4e38 |
| Fig 16 | Client-server model | `model-client-server.png` | https://github.com/user-attachments/assets/a573d1bf-cc3c-44d5-833a-1d7e0c85123b |
| Fig 17 | Peer-to-peer model | `model-peer-to-peer.png` | https://github.com/user-attachments/assets/3ed8da96-00b7-4642-894a-454fa8ca88d0 |

#### **Behavioral AI Study Guide**
# Behaviourist AI — Test Bank

**Module:** Hardware, Networks and Behaviourist AI  
**Team:** Max Medium  
**Scope:** Behaviourist AI (PDF Section 3) — reactive robotics content only  
**Purpose:** Question bank for quizzes, tests and revision  
**Note:** No behavioural-analytics questions are included. All questions test Brooks-style Behaviourist AI, subsumption, APF, FSM, Q-learning and the edge robotics integration example.

---

## Section A — Multiple Choice (with answer key)

| No. | Question | Options | Answer |
|---|---|---|---|
| A1 | What is the central idea of Behaviourist AI? | A) Build a detailed internal world map before acting  B) Couple sensory inputs directly to motor actions without complex internal models  C) Use formal logical deliberation before every action  D) Train a generative model of the environment | **B** |
| A2 | Which phrase best summarises Brooks' view of the environment? | A) The map is the territory  B) The world is its own best model  C) The model is the world  D) The mind is a computer | **B** |
| A3 | What does SMPA stand for? | A) Sense–Model–Plan–Act  B) Sense–Motor–Plan–Act  C) Signal–Model–Process–Act  D) Sense–Map–Predict–Act | **A** |
| A4 | Why is the SMPA loop described as a latency bottleneck? | A) It uses too little memory  B) It spends too long updating maps and planning, so robots freeze when environments change  C) It cannot use sensors  D) It requires a GPU | **B** |
| A5 | The frame problem is best described as: | A) The difficulty of drawing frames around objects  B) The impossibility of efficiently updating a central world model with every non-change in a dynamic environment  C) The problem of grounding symbols  D) The delay in the SMPA loop | **B** |
| A6 | The symbol grounding problem means: | A) Symbols are too large for memory  B) Abstract symbols have no natural link to real physical sensor signals unless grounded in physical interaction  C) Symbols cannot be stored in binary  D) Symbols need a GPU to process | **B** |
| A7 | Which of these is NOT one of Brooks' four core axioms? | A) The world is its own best model  B) Embodied and situated cognition  C) Tight sensorimotor coupling  D) Full internal world modelling | **D** |
| A8 | "Emergent behaviour" means: | A) Behaviour is explicitly programmed line by line  B) Complex behaviour arises from simple reactive rules interacting with an unpredictable environment  C) Behaviour emerges only after planning  D) Behaviour is random | **B** |
| A9 | Subsumption architecture is built from: | A) Neural networks  B) Augmented Finite State Machines (AFSMs) in parallel layers  C) Single large planners  D) Genetic algorithms | **B** |
| A10 | In subsumption, **suppression** means: | A) A higher layer blocks a lower layer's output  B) A higher layer intercepts and replaces the input signal flowing into a lower layer  C) A lower layer overrides a higher layer  D) All layers run in sequence | **B** |
| A11 | In subsumption, **inhibition** means: | A) A higher layer blocks or silences the output command of a lower layer  B) A higher layer replaces a lower layer's input  C) A layer is deleted  D) Two layers merge | **A** |
| A12 | In the robotic vacuum example, Layer 0 (basic survival) does what? | A) Drives forward in a straight line  B) Detects dirt and spirals outward  C) Stops, reverses and rotates 45° when the bumper/proximity sensor triggers  D) Builds a full room map | **C** |
| A13 | In the robotic vacuum, which layer detects dirt and switches to an outward spiral? | A) Layer 0  B) Layer 1  C) Layer 2  D) Layer 3 | **C** |
| A14 | In Motor Schema Architecture, the net motion vector is: | A) Only the attractive force  B) Only the repulsive force  C) The sum of attractive and repulsive force vectors  D) A random vector | **C** |
| A15 | The **local minima trap** occurs when: | A) The robot reaches the goal  B) Attractive and repulsive vectors cancel out before the goal, so the robot gets stuck  C) The robot has too much memory  D) The network is down | **B** |
| A16 | A common reactive fix for the local minima trap is: | A) Build a full global map  B) Inject random noise vectors (random walk) or switch to wall-following  C) Stop permanently  D) Ask the server for a new plan | **B** |
| A17 | A finite state machine (FSM): | A) Runs many states at once  B) Restricts the agent to one active state at a time, switching on environmental triggers  C) Learns from rewards  D) Uses potential fields | **B** |
| A18 | Model-free Q-learning learns: | A) A world map  B) An optimal policy matrix Q(s,a) from environmental rewards  C) Only attractive forces  D) A neural network from scratch | **B** |
| A19 | In Q-learning, the **discount factor γ** controls: | A) How fast the robot moves  B) How much future rewards are valued relative to immediate rewards  C) The memory size  D) The network bandwidth | **B** |
| A20 | Which is a recognised limitation of Behaviourist AI? | A) Too much internal state  B) Lack of internal state representation and difficulty with generalisation and partial observability  C) Cannot use sensors  D) Cannot run on hardware | **B** |
| A21 | Which is a recognised ethical concern for modern Behaviourist AI (e.g., camera-equipped delivery robots)? | A) Colour of the robot  B) Privacy and consent when recording pedestrians  C) Robot battery life  D) Robot weight | **B** |
| A22 | In the autonomous edge robotics pod, why is **UDP** used for telemetry? | A) It is reliable and ordered  B) It is connectionless and fast, suitable for streaming live location data  C) It encrypts data  D) It builds a map | **B** |
| A23 | In the edge robotics pod, why is **TCP** used for server commands? | A) It is fast but unreliable  B) It is connection-oriented and reliable, so target coordinates arrive correctly  C) It is used only for video  D) It avoids encryption | **B** |
| A24 | In the edge robotics pod, Layer 0 Subsumption overrides remote commands so that: | A) The pod follows the server exactly  B) The pod can instantly halt if a pedestrian steps in front, regardless of network delay  C) The pod ignores all sensors  D) The pod reboots | **B** |
| A25 | Which pairing correctly matches an AI paradigm to its approach? | A) Deliberative AI → sense→act directly; Behaviourist AI → SMPA loop  B) Deliberative AI → SMPA loop; Behaviourist AI → sense→act directly  C) Both use only SMPA  D) Both use only sense→act | **B** |

---

## Section B — True / False (with answers)

| No. | Statement | Answer |
|---|---|---|
| B1 | Behaviourist AI relies on a complete internal world model before acting. | **False** |
| B2 | "The world is its own best model" means the robot should query the real environment with sensors instead of trusting an internal map. | **True** |
| B3 | The SMPA loop is faster than a direct sense→act loop. | **False** |
| B4 | The frame problem is about updating a world model with every non-change. | **True** |
| B5 | Symbol grounding means abstract symbols must be connected to real sensor signals through physical interaction. | **True** |
| B6 | In subsumption, lower layers always override higher layers. | **False** |
| B7 | Suppression acts on a lower layer's input; inhibition acts on a lower layer's output. | **True** |
| B8 | In the robotic vacuum, Layer 1 drives forward in a straight line. | **True** |
| B9 | Artificial potential fields combine attraction to a goal and repulsion from obstacles. | **True** |
| B10 | A local minimum means the robot has reached the goal. | **False** |
| B11 | A finite state machine can have many active states at the same time. | **False** |
| B12 | Q-learning is model-free and learns from rewards. | **True** |
| B13 | Behaviourist AI struggles with partially observable and dynamic environments. | **True** |
| B14 | Privacy is irrelevant to modern edge robotics. | **False** |
| B15 | In the edge robotics pod, UDP is used for reliable target coordinates. | **False** (TCP is used for commands; UDP for telemetry) |

---

## Section C — Short Answer (with model answers)

| No. | Question | Model answer |
|---|---|---|
| C1 | Define Behaviourist AI in one or two sentences. | Behaviourist AI (also called Reactive AI) builds autonomous systems that couple sensory inputs directly to motor actions without relying on complex internal world models or formal logical deliberation. |
| C2 | State the four core axioms of Brooks' Behaviourist AI. | (1) The world is its own best model; (2) embodied and situated cognition; (3) tight sensorimotor coupling; (4) emergent behaviour. |
| C3 | What is embodied and situated cognition? | Intelligence cannot exist as an abstract program; it must be embodied in a physical body interacting directly with a physical environment. |
| C4 | What is tight sensorimotor coupling? | Connecting sensor readings directly to motor actuators through fast, parallel channels (Sense → Act). |
| C5 | Explain the SMPA latency bottleneck. | The deliberative Sense–Model–Plan–Act loop spends too long updating maps and calculating routes, so physical robots freeze or crash when the environment changes mid-calculation. |
| C6 | Explain the frame problem in your own words. | It is the impossibility of efficiently updating a central world model with every non-change occurring in a dynamic environment. |
| C7 | Explain the symbol grounding problem. | Abstract symbols inside a program (e.g., "WALL", "DANGER") have no natural link to real physical sensor signals unless grounded in direct physical interaction. |
| C8 | Describe the subsumption architecture. | It organises control into parallel, task-achieving layers built from Augmented Finite State Machines; higher-level behaviours run concurrently above lower survival behaviours and can intervene via suppression or inhibition. |
| C9 | Distinguish suppression and inhibition in subsumption. | Suppression: a higher layer intercepts and replaces the input signal flowing into a lower layer. Inhibition: a higher layer blocks or silences the output command of a lower layer. |
| C10 | Describe the three layers in the robotic vacuum example. | Layer 0 (collision avoidance): bumper triggers → stop, reverse, rotate 45°. Layer 1 (coverage walk): drive forward in a straight line. Layer 2 (dirt detection): dirt sensor triggers → outward spiral until clean. |
| C11 | What is a motor schema / artificial potential field? | A reactive control method using continuous vector fields: an attractive force pulls the agent toward the goal and repulsive forces push it away from obstacles; the net motion vector is their sum. |
| C12 | What is the local minima trap, and how can a reactive system escape it? | It occurs when attractive and repulsive vectors cancel out before the goal (e.g., inside a U-shaped obstacle). Reactive fixes: inject random noise vectors (random walk) or switch to temporary wall-following until the gradient clears. |
| C13 | What is a finite state machine, and give an example from the PDF. | An FSM restricts the agent to one active state at a time and switches on environmental triggers. Example: PATROL → (player spotted) → CHASE → (health < 20%) → FLEE. |
| C14 | Explain Q-learning conceptually. | Model-free reinforcement learning that learns an optimal policy matrix Q(s,a) directly from environmental rewards, using a learning rate α and discount factor γ. |
| C15 | State two limitations of Behaviourist AI. | (1) Lack of internal state representation; (2) difficulty with generalisation, dynamic environments and partial observability. |
| C16 | State one ethical concern for modern Behaviourist AI. | Privacy and consent when camera-equipped robots record pedestrians or collect telemetry; unintended consequences of autonomous action. |
| C17 | Why does the edge robotics pod use UDP for telemetry and TCP for commands? | UDP is connectionless and fast, suitable for streaming live location telemetry; TCP is connection-oriented and reliable, so target coordinates from the server arrive correctly and in order. |
| C18 | Why does Layer 0 Subsumption override remote commands in the pod? | To guarantee safety: if a pedestrian steps in front, Layer 0 instantly halts the motors in milliseconds, regardless of network delays or server connectivity. |

---

## Section D — Matching (with answer key)

Match each term to its correct description.

| Term | Description |
|---|---|
| 1. SMPA | A. Higher layer replaces a lower layer's input |
| 2. Frame problem | B. Impossibility of updating a world model with every non-change |
| 3. Symbol grounding | C. Linking abstract symbols to real sensor signals |
| 4. Suppression | D. Sense–Model–Plan–Act loop |
| 5. Inhibition | E. Higher layer blocks a lower layer's output |
| 6. AFSM | F. Building block of subsumption layers |
| 7. APF | G. Attraction + repulsion vector fields |
| 8. Local minimum | H. Forces cancel before the goal |
| 9. FSM | I. One active state at a time |
| 10. Q-learning | J. Learns policy from rewards |

**Answer key:** 1-D, 2-B, 3-C, 4-A, 5-E, 6-F, 7-G, 8-H, 9-I, 10-J.

---

## Section E — Scenario / Application Questions (with model answers)

| No. | Scenario | Question | Model answer |
|---|---|---|---|
| E1 | A robot using SMPA freezes when a person walks into its planned path. | Why does this happen, and how would a Behaviourist AI approach differ? | The SMPA loop is too slow: it is still updating its map/plan when the environment changes. A Behaviourist AI would couple sensors directly to actuators (sense→act), reacting in milliseconds without replanning. |
| E2 | A delivery robot must avoid a pedestrian even if the network is down. | Which subsumption mechanism ensures safety, and why? | Layer 0 (basic survival / collision avoidance) overrides remote commands via suppression/inhibition, halting the robot in milliseconds regardless of network delay. |
| E3 | A robot gets stuck inside a U-shaped obstacle. | Name the problem and two reactive solutions. | Local minima trap. Solutions: inject random noise (random walk) or switch to wall-following until the force gradient clears. |
| E4 | A game enemy patrols, chases the player when spotted, and flees when health < 20%. | Which reactive control method models this, and what are the states and transitions? | A finite state machine. States: PATROL, CHASE, FLEE. Transitions: PATROL → CHASE (player spotted); CHASE → FLEE (health < 20%). |
| E5 | A warehouse pod must stream live location and receive reliable target coordinates. | Which protocols should it use, and why? | UDP for telemetry (fast, connectionless, tolerates loss); TCP for commands (reliable, ordered delivery of target coordinates). |
| E6 | A camera-equipped delivery robot records pedestrians. | Identify one ethical concern and one safeguard. | Privacy/consent concern: recording pedestrians without consent. Safeguards: blur faces on-device, store minimal data, obtain consent where required, define retention limits. |
| E7 | A student says "Behaviourist AI is the same as rule-based software." | Correct the statement. | Rule-based software follows fixed hand-coded rules. Behaviourist AI couples sensors directly to actuators and lets complex behaviour emerge from simple reactive layers interacting with an unpredictable environment. |
| E8 | A robot with APF navigation is pulled toward its goal but pushed away from a wall. | Describe how the net motion vector is computed. | The net vector is the sum of the attractive force (toward the goal) and the repulsive force (from the obstacle, active only within influence distance Q*). |

---

## Section F — Extended Response (with marking guidance)

| No. | Question | Marking guidance |
|---|---|---|
| F1 | Compare classical deliberative AI with Behaviourist AI. | Award marks for: SMPA loop vs sense→act; internal world model vs no model; latency bottleneck vs real-time reaction; frame and symbol grounding problems vs grounding through physical interaction; one example each (e.g., planner robot vs Roomba). |
| F2 | Explain Brooks' four core axioms and give one robot example for each. | Marks for: world as its own best model (sensor query, not map); embodied/situated cognition (physical body); tight sensorimotor coupling (sense→act); emergent behaviour (simple rules → complex navigation). Examples accepted if correctly matched. |
| F3 | Describe the subsumption architecture, including suppression and inhibition, using the robotic vacuum. | Marks for: parallel layers; AFSMs; priority; suppression (input) vs inhibition (output); Layer 0 collision avoidance; Layer 1 coverage walk; Layer 2 dirt detection; correct interaction (higher overrides lower). |
| F4 | Explain artificial potential fields and the local minima problem, with one solution. | Marks for: attractive force to goal; repulsive force from obstacles within Q*; net vector sum; local minimum when vectors cancel; solution: random walk or wall-following. |
| F5 | Explain how hardware, networking and Behaviourist AI connect in the autonomous edge robotics pod. | Marks for: hardware (SoC with CPU/GPU/TPU, LiDAR, sensors, motors on system buses); networking (5G, UDP telemetry, TCP commands); Behaviourist AI (Subsumption/APF, Layer 0 override); integrated lifecycle (hardware processing → networking telemetry → behaviourist navigation). |
| F6 | Discuss two limitations and two ethical concerns of Behaviourist AI. | Limitations: no internal state; poor generalisation; dynamic/partially observable environments. Ethical: privacy/consent in camera robots; unintended consequences; lack of ethical reasoning. Award marks for balanced, specific discussion. |

---

## Section G — Quick Recall Drill (one-line answers)

| No. | Prompt | Answer |
|---|---|---|
| G1 | Who pioneered Behaviourist AI? | Rodney Brooks (late 1980s). |
| G2 | What does the phrase "Intelligence Without Representation" refer to? | Brooks' paper/idea that intelligence can arise without internal world models. |
| G3 | What does AFSM stand for? | Augmented Finite State Machine. |
| G4 | What does APF stand for? | Artificial Potential Field. |
| G5 | What is the opposite of reactive AI in this module? | Deliberative (cognitivist) AI. |
| G6 | Name the robotic vacuum example used in the PDF. | Roomba-style robotic vacuum. |
| G7 | Which layer in the vacuum handles dirt detection? | Layer 2. |
| G8 | Which layer in the vacuum handles collision avoidance? | Layer 0. |
| G9 | What Greek letter represents the Q-learning learning rate? | α (alpha). |
| G10 | What Greek letter represents the Q-learning discount factor? | γ (gamma). |
| G11 | What does the pod use for telemetry? | UDP. |
| G12 | What does the pod use for server commands? | TCP. |
| G13 | What is the net motion vector formula in words? | Attractive force + sum of repulsive forces. |
| G14 | Name one way to escape a local minimum. | Random walk / random noise vector, or wall-following. |
| G15 | What are the three states in the FSM example? | PATROL, CHASE, FLEE. |

---
