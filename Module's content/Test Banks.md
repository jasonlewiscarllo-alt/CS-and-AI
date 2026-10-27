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
