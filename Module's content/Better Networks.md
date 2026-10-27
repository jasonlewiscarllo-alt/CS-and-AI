# Networks

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Status:** Drafted — reviewed by Rysen  
**Last updated:** Stage 1 snapshot

---

## Table of Contents

1. [What You Will Learn](#1-what-you-will-learn)
2. [Key Terms and Glossary](#2-key-terms-and-glossary)
3. [Network Definition](#3-network-definition)
4. [Components of a Network](#4-components-of-a-network)
5. [Packets and Packet Switching](#5-packets-and-packet-switching)
6. [Protocols and Addressing](#6-protocols-and-addressing)
7. [Network Topologies](#7-network-topologies)
8. [Data Flow and Transmission](#8-data-flow-and-transmission)
9. [Network Architecture](#9-network-architecture)
10. [Network Threats and Security](#10-network-threats-and-security)
11. [Worked Examples](#11-worked-examples)
12. [Structured Learner Activities](#12-structured-learner-activities)
13. [Review Questions with Answers](#13-review-questions-with-answers)
14. [Current Development Status of Each Section](#14-current-development-status-of-each-section)
15. [Important Gaps and Uncertainties](#15-important-gaps-and-uncertainties)
16. [Peer Review Record](#16-peer-review-record)
17. [Plan for Use in the Three Resources](#17-plan-for-use-in-the-three-resources)
18. [References](#18-references)

---

## 1. What You Will Learn

By the end of this section, you should be able to:

1. Define a computer network and identify its key components (nodes, links, routers, switches) [1][3].
2. Explain how packets carry data, including the roles of the header, payload, and trailer [1][18].
3. Distinguish between TCP and IP, and explain why both are needed [6][1].
4. Explain MAC addresses and IP addresses, and state the difference between them [1].
5. Describe the structure of a URL and how DNS translates domain names into IP addresses [8][9][1].
6. Compare common network topologies (bus, point-to-point, star, mesh, ring, hybrid, tree) and choose an appropriate topology for a scenario [4][1].
7. Explain simplex, half-duplex, and full-duplex data flow [1].
8. Compare serial and parallel transmission; synchronous and asynchronous transmission [1][15][16].
9. Compare LAN, WAN, and MAN, and compare client-server and peer-to-peer models [13][14][1].
10. Identify common malware and cyberattacks, and match them to appropriate countermeasures [5][12][1].

---

## 2. Key Terms and Glossary

| Term | Definition |
|------|------------|
| **Network** | Two or more devices connected together so they can exchange data and share resources [1][3]. |
| **Node** | Any device connected to a network capable of sending, receiving, or processing data (e.g., laptop, phone, printer, server) [1][17]. |
| **Link** | The wired or wireless pathway that connects nodes [1][17]. |
| **Router** | A device that connects different networks and forwards data between them by examining packet addresses [1][17]. |
| **Switch** | A device that connects multiple devices within a LAN and directs data to the intended device using MAC addresses [1][17]. |
| **Packet** | A small chunk of a larger piece of data, containing a header, payload, and trailer [1][18]. |
| **Header** | The part of a packet that stores control information such as source address, destination address, and sequence number [1][18]. |
| **Payload** | The actual data being transmitted (e.g., part of a photo or message) [1][18]. |
| **Trailer** | The part of a packet that marks the end and contains error detection bits [1][18]. |
| **Packet switching** | The method of breaking data into packets, sending them along available routes, and reassembling them at the destination [1][18]. |
| **Protocol** | Rules and standards that devices follow to communicate [1][6]. |
| **TCP** | A connection-oriented protocol that ensures reliable, in-order delivery of data [6][1]. |
| **IP** | A connectionless protocol that handles addressing and routing [6][1]. |
| **MAC address** | A unique 48-bit physical identifier hardcoded into a Network Interface Card (NIC) [1]. |
| **IP address** | A software-assigned logical address given to a device when it connects to a network [1]. |
| **DNS** | A system that translates human-readable domain names into machine-readable IP addresses [9][1]. |
| **URL** | The address of a resource on the internet, consisting of protocol, subdomain, domain, and top-level domain [8][1]. |
| **Topology** | The physical or logical arrangement of nodes and links in a network [4][1]. |
| **LAN** | Local Area Network — connects devices in a single, limited area [13][1]. |
| **WAN** | Wide Area Network — connects networks over large geographical areas [13][1]. |
| **MAN** | Metropolitan Area Network — connects LANs across a city or large campus [13][1]. |
| **Client-server** | A centralized model where a server provides resources and clients consume them [14][1]. |
| **Peer-to-peer (P2P)** | A decentralized model where each node acts as both client and server [14][1]. |
| **Malware** | Malicious software designed to infiltrate, damage, or gain unauthorized access to systems [5][1]. |
| **Phishing** | A social engineering attack that tricks users into revealing sensitive information [5][12]. |
| **Pharming** | An attack that redirects users from legitimate websites to fake replica sites [5][12]. |
| **Encryption** | The process of converting readable data (plaintext) into an encoded form (ciphertext) so unauthorized users cannot understand it [7][10]. |
| **CSMA/CD** | Carrier Sense Multiple Access with Collision Detection — a protocol used in bus networks to manage collisions when devices send data at the same time [1][4]. |
| **NIC** | Network Interface Card — the hardware component that connects a device to a network [1]. |
| **Unicast** | Data sent from one specific device to one specific destination device [1]. |
| **Botnet** | A network of compromised computers controlled remotely by an attacker [5][12]. |
| **Ciphertext** | Data that has been encrypted and is unreadable without the decryption key [7][10]. |
| **Skew** | A problem in parallel transmission where bits arrive at slightly different times due to different wire lengths [1]. |
| **Crosstalk** | Interference between adjacent wires in parallel transmission [1]. |

---

## 3. Network Definition

A network is like a group of friends sharing ideas. A **computer network** is simply two or more devices — such as phones, laptops, or printers — connected together so they can share information and resources [1][3]. Devices talk to each other using physical cables or wireless signals like Wi-Fi [1]. Networks can be small, like the setup in your home, or huge, connecting devices across different countries [1][3]. Every time you send a message, share a photo, or browse the web, you are using a network [1]. In the end, networks make communicating and working together much faster [1]. They also save time and resources by letting multiple devices share the same internet connection, printer, or files with ease [1].

A more formal definition: a computer network is a collection of computing devices connected by communication links that allow the exchange of data and the sharing of resources [1][3].

The network is defined by three things:

1. **The hardware that forms its nodes** — computers, routers, switches, and access points [1][17].
2. **The physical or wireless media that carry signals** — cables or wireless signals [1][17].
3. **The protocols that govern how data is formatted, addressed, transmitted, and received** [1][6].

> **Quick Review 1:** What is the definition of a computer network and its key components?
>
> **Answer:** A computer network is two or more devices connected together so they can share information and resources [1][3]. Its key components are:
> - **Nodes (devices):** any device connected to the network, such as phones, laptops, or printers [1][17].
> - **Links (connections):** the wired or wireless pathways that allow devices to communicate [1][17].
> - **Routers:** devices that connect different networks and forward data between them [1][17].
> - **Switches:** devices that direct data to the intended device within a local area network (LAN) [1][17].

---

## 4. Components of a Network

### 4.1 Nodes (Devices)

**Nodes** are any device connected to a network capable of sending, receiving, or processing data (e.g., laptops, phones, printers, servers) [1][17].

- **Key Function:** Enables devices to exchange information and share resources over a network [1][17].
- **Example:** In a home Wi-Fi setup, your phone, laptop, and printer are all individual nodes interacting with one another [1][17].

### 4.2 Links (Connections)

**Links** are the connections that allow devices in a network to communicate with one another [1][17]. These connections can be wired or wireless, depending on the type of network and the devices being used [1][17].

**Types of links:**

- **Wired links** use physical cables, such as Ethernet cables, to transfer data between devices [1][17].
- **Wireless links** use signals, such as Wi-Fi or Bluetooth, to send information without needing a physical cable [1][17].

- **Key Function:** It provides the physical or wireless pathway that allows devices to exchange information [1][17]. Without links, network communication is impossible, and your devices would be completely isolated on separate islands [1][17].
- **Example:** When you connect your laptop to a router using an Ethernet cable, the cable acts as a link [1][17]. When you connect your phone to the same router through Wi-Fi, the wireless connection acts as a link [1][17]. Without links, devices would not be able to exchange information [1][17].

### 4.3 Routers

**Routers** are networking devices that connect different networks and forward data between them [1][17]. They examine information in data packets [1][17]. They are commonly used in homes, schools, offices, and large organizations [1][17].

- **Key Function:** Examines information inside data packets, such as destination IP addresses, to determine where the data should go next and selects an appropriate path across the network [1][17].
- **Example:** When you open a website on your phone, your home router forwards your request from your home network toward the internet [1][17]. When the website sends information back, the router helps deliver the data to your device [1][17].

### 4.4 Switches

**Switches** are networking devices that connect multiple devices within a local area network (LAN) [1][17]. They are commonly used in offices, schools, and other places where many devices need to communicate within the same local network [1][17].

- **Key Function:** Directs data specifically to the intended device rather than sending it unnecessarily to every connected device [1][17]. It uses **MAC addresses** to identify devices on a local network, checking the destination MAC address and forwarding the data through the appropriate port [1][17].
- **Example:** In a school computer lab, when one computer sends a document to a network printer connected to the same switch, the switch forwards the data directly toward the printer [1][17].

---

## 5. Packets and Packet Switching

### 5.1 What Is a Packet?

<img width="738" height="237" alt="Packet structure diagram" src="assets/diagrams/packet-structure.png" />

**Figure 1:** The three parts of a packet (header, payload, trailer) [1][18].

In networks, a **packet** is a small part of a larger piece of information that is sent over the internet [1][18]. Each packet contains a **header**, **payload**, and a **trailer**, which includes important details about the data [1][18].

- **Header:** Stores where it needs to go and who sent it [1][18]. The header also helps the receiving device understand how to rearrange the packet back together [1][18].
- **Payload:** The place where the actual information is stored within the packet [1][18].
- **Trailer:** Marks the end of the packet and helps the receiving device confirm that all parts have been received [1][18].

**Figure 1 (text diagram): The three parts of a packet** [1][18]

```text
+-------------------+-------------------+-------------------+
|      HEADER       |      PAYLOAD      |      TRAILER      |
|  source address   |  actual data      |  end marker       |
|  destination addr |  (e.g., part of   |  error-check bits |
|  sequence number  |   a photo)        |                   |
+-------------------+-------------------+-------------------+
```

### 5.2 Packet Switching

When we send information over the internet, such as a photo, video, or message, the data is divided into smaller packets [1][18]. These packets travel through network devices like routers and switches until they reach their destination [1][18]. Once they arrive, the receiving device puts the packets back together so the information can be viewed or used [1][18]. This process is similar to building a puzzle, where each piece is sent separately and then joined together to complete the picture [1][18].

Sending data in packets also makes the internet more efficient because many devices can send and receive information at the same time [1][18]. This method is called **packet switching** [1][18]. Instead of one connection taking up the whole network, packets can travel through available routes, allowing many people to use the internet simultaneously [1][18].

<img width="666" height="395" alt="Packet routing diagram" src="assets/diagrams/packet-routing.png" />

**Figure 2:** Available paths where packets travel [1][18]. If a router or link fails, packets can automatically reroute around the problem so that the packets won't get lost and never received [1][18].

### 5.3 Worked Example: Sending a Photo

**Scenario:** You send a 3 MB photo to a friend. The network breaks it into packets [1][18].

| Step | What happens |
|------|--------------|
| 1 | The photo is divided into small chunks. Each chunk becomes the **payload** of a packet [1][18]. |
| 2 | A **header** is added to each packet. The header records the destination (your friend's device), the source (your device), and a **sequence number** (1, 2, 3, …) so the packets can be put back in order [1][18]. |
| 3 | A **trailer** is added to mark the end of the packet and help check for errors [1][18]. |
| 4 | The packets are sent across the network. Routers forward each packet along a suitable path. Packets may take different routes [1][18]. |
| 5 | The packets arrive at your friend's device, possibly out of order. The device reads the **sequence numbers** in the headers and reassembles the payloads in the correct order [1][18]. |
| 6 | The photo is displayed. If a packet is missing or damaged, the device can request it again [1][18]. |

**Why this works:** If the network sent the whole photo as one piece, a single problem could stop everything [1][18]. With packets, only a small piece is affected, and the rest can still arrive [1][18].

> **Review 1:** What are the three parts of a packet and what does each do?
>
> **Answer:**
> - **Header:** Stores control information including source address, destination address, and sequence number. It helps the packet reach the right device and be reassembled in order [1][18].
> - **Payload:** Carries the actual data being transmitted [1][18].
> - **Trailer:** Marks the end of the packet and contains error detection bits [1][18].

---

## 6. Protocols and Addressing

### 6.1 Protocols

**Protocols** are the rules and standards that devices follow to communicate with one another over a network [1][6]. They define how data is formatted, transmitted, received, and understood by different devices [1][6]. Since different devices may use different hardware and software, they need to follow common rules so they can understand the information being exchanged [1][6]. Protocols work like a common language that helps devices communicate correctly [1][6]. Without protocols, devices might not understand the information sent by other devices [1][6]. Protocols help ensure that communication happens in an organized and reliable way [1][6].

**Some common network protocols include:**

- **TCP (Transmission Control Protocol):** Helps ensure data arrives reliably and in the correct order so that the information is delivered accurately [6][1].
- **IP (Internet Protocol):** Is the identity of the devices that will send information or receive them [6][1]. It acts similar to a mailbox where the router is the one who leads it to its proper destination at the most efficient route, but that will sometimes cause the information to be jumbled up or mismatched — that is why TCP is used [6][1].
- **HTTP/HTTPS:** Protocols used to transfer website information between web browsers and web servers [1][7]. HTTPS also encrypts the connection to ensure it is secure [1][7].
- **FTP:** A protocol used to transfer files between computers over a network [1].
- **DNS:** A system that translates human-readable domain names, such as google.com, into machine-readable IP addresses that computers use to locate servers [9][1].
- **Ethernet:** Connects computers, routers, and other devices to build a local area network (LAN) and link them to the internet [1].

**Example:** When you visit a website, DNS helps your device find the website's server, while TCP/IP helps move data between your device and that server [1][6][9]. In conclusion, packets divide information into smaller pieces so it can be sent efficiently, while protocols provide the rules that allow devices to communicate and understand the data they receive [1][18]. Both are important for making the internet work properly [1][18].

> **Important note on TCP and IP:** TCP is a **connection-oriented** protocol that ensures reliable delivery of data [6][1]. It establishes a connection before sending data, detects packets received out of order, and puts them back in the correct order [6][1]. IP is a **connectionless** protocol that handles addressing and routing [6][1]. It does not guarantee delivery or order — it simply routes packets toward their destination [6][1]. IP does **not** cause jumbling; TCP is layered on top to provide the reliability and ordering that IP lacks [6][1].

> **Quick Review 2:** What is the definition of computer networks and its key components?
>
> **Answer:** A computer network is two or more devices connected together so they can share information and resources [1][3]. Its key components are:
> - **Nodes (devices):** any device connected to the network, such as phones, laptops, or printers [1][17].
> - **Links (connections):** the wired or wireless pathways that allow devices to communicate [1][17].
> - **Routers:** devices that connect different networks and forward data between them [1][17].
> - **Switches:** devices that direct data to the intended device within a local area network (LAN) [1][17].

### 6.2 Methods of Identification within Devices

#### 6.2.1 MAC Address (Media Access Control)

A **MAC address** is a unique, hardcoded **48-bit** physical identifier burned into a Network Interface Card (NIC) by the hardware manufacturer [1].

- **Key Function:** Identifies a specific hardware interface so that devices connected to the same local network segment can send data directly to each other [1].
- **Example:** `00:1A:2B:3C:4D:5E` (a MAC address is decided by the network hardware manufacturer during production or by a network administrator using software settings) [1].

#### 6.2.2 IP Address (Internet Protocol Address)

An **IP address** is a software-assigned numerical label given to a device whenever it connects to a network [1].

**Types of IP address:**

- **IPv4 (Internet Protocol version 4):** The original and widely used version of the Internet Protocol [1]. It has an **address length of 32 bits**, e.g., `93.184.216.34`, written in denary [1].
- **IPv6 (Internet Protocol version 6):** The newer version of the Internet Protocol designed to permanently replace IPv4 [1]. It has an **address length of 128 bits**, e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`, written in hexadecimal [1].

- **Key Function:** Enables data to be routed across multiple interconnected networks, guiding packets from a source device across the global internet to a destination device [1].
- While IPv4 offers widespread compatibility and mature deployment, its major disadvantage compared to IPv6 is its severely limited address space and lack of native security features [1].

> **Quick Review 3:** What is an IP address and what are the two main versions in use?
>
> **Answer:** An IP address is a software-assigned numerical label given to a device whenever it connects to a network [1]. The two main versions are:
> - **IPv4:** 32-bit address written in denary, e.g., `93.184.216.34` [1].
> - **IPv6:** 128-bit address written in hexadecimal, e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334` [1].

> **Quick Review 4:** What is a MAC address and how does it differ from an IP address?
>
> **Answer:** A MAC address is a unique 48-bit physical identifier hardcoded into a Network Interface Card (NIC) by the manufacturer [1]. An IP address is a software-assigned numerical label given to a device when it connects to a network [1]. The key differences are:
> - A MAC address is **physical and permanent** (burned into the hardware); an IP address is **logical and can change** each time a device connects to a different network [1].
> - A MAC address identifies the **hardware interface** on a local network; an IP address identifies the **device's location** on a network so data can be routed across the internet [1].

### 6.3 URL

A **URL** is the address of a source on the internet [8][1]. A URL is divided into several main parts: protocol, subdomain, domain name, and top-level domain [8][1].

<img width="738" height="414" alt="URL structure diagram" src="assets/diagrams/url-structure.png" />

**Figure 3:** The structure of a URL [8][1].

- **Protocol:** Determines how the data is transferred through the URL [8][1]. The most used are HTTP for regular web and HTTPS for a more secure connection [8][1].
- **Subdomain:** Used to identify each area of the website [8][1]. `www` is the most commonly used, where `www` stands for World Wide Web [8][1].
- **Domain Name:** The unique, human-readable name of a specific website [8][1]. It acts as an easy-to-remember alias for a complex numerical IP address [8][1].
- **Top-Level Domain:** Categorizes the website by its purpose, industry, or geographic location, e.g., `.com` (commercial), `.org` (organizations), `.edu` (education), `.uk` (United Kingdom) [8][1].

**Worked Example: Breaking down a URL** [8][1]

**URL:** `https://www.bbc.co.uk/news`

| Part | Value | Explanation |
|------|-------|-------------|
| Protocol | `https` | Secure web protocol [8][1] |
| Subdomain | `www` | World Wide Web [8][1] |
| Domain name | `bbc` | The organization's name [8][1] |
| Second-level domain | `co` | Indicates commercial organization [8][1] |
| Top-level domain (country code) | `uk` | United Kingdom [8][1] |
| Path | `/news` | The specific page on the website [8][1] |

> **Review 2:** How does the Domain Name System (DNS) work?
>
> **Answer:** DNS translates human-readable domain names (such as google.com) into machine-readable IP addresses [9][1]. When you type a domain name into a browser, DNS looks up the corresponding IP address so your device can locate and connect to the correct web server [9][1].

---

## 7. Network Topologies

**Network topology** is the physical or logical arrangement of nodes and links in a network [4][1]. The choice of topology affects performance, scalability, reliability, and cost [4][1].

### 7.1 Bus Topology

<img width="726" height="422" alt="Bus topology diagram" src="assets/diagrams/bus-topology.png" />

**Figure 4:** Bus topology — all devices share a single backbone cable [4][1].

**Purpose:** To allow multiple devices to communicate with each other over a single, shared physical medium without needing a complex web of individual wires [4][1].

**Pros (Advantages):**

- **Cost-Effective:** Requires the least amount of cabling compared to star or mesh topologies [4][1].
- **Simple Design:** Very straightforward to set up, understand, and connect new devices to for small networks [4][1].
- **No Extra Power Needed:** The passive backbone does not require a central hub, switch, or router to function [4][1].
- **Easy Extension:** Adding more nodes is simple by tapping into the main line (as long as network limits aren't exceeded) [4][1].

**Cons (Disadvantages):**

- **Single Point of Failure:** If the main backbone cable breaks or gets damaged anywhere along the line, the entire network goes down [4][1].
- **Poor Scalability:** Performance drops quickly as more devices are added due to increased data traffic and collisions [4][1].
- **High Collision Rate:** Because all devices share the same wire, simultaneous data transmissions collide and require re-transmission (managed via protocols like CSMA/CD) [4][1].
- **Difficult Troubleshooting:** Finding a break, loose tap, or faulty terminator along a long cable run is hard and time-consuming [4][1].
- **Low Security:** Because every packet is broadcast to every node, any computer on the bus can potentially sniff or intercept traffic [4][1].

### 7.2 Point-to-Point Topology

<img width="620" height="322" alt="Point-to-point topology diagram" src="assets/diagrams/point-to-point-topology.png" />

**Figure 5:** Point-to-point topology — a dedicated link between exactly two devices [4][1].

A **point-to-point topology** is the simplest form of network architecture where a dedicated communication link directly connects two devices (nodes) to each other without any intermediate switches or hubs [4][1].

**Pros (Advantages):**

- **Simplicity:** Easy to set up, configure, and manage because it only involves two endpoints [4][1].
- **High Performance & Bandwidth:** The entire capacity and speed of the link are reserved exclusively for the two connected devices without sharing or congestion from other nodes [4][1].
- **Low Latency:** Data travels straight from the source to the destination with no routing delays [4][1].
- **Enhanced Security:** Data moves across a private, isolated channel, reducing the risk of interception or unauthorized sniffing compared to shared media [4][1].
- **Low Initial Hardware Cost:** For a single pair of devices, minimal hardware and cabling are required [4][1].

**Cons (Disadvantages):**

- **Poor Scalability:** Adding more devices is difficult and expensive, as every new node requires its own dedicated physical or logical link [4][1].
- **Single Point of Failure:** If the single connecting cable or link fails, all communication between the two devices stops completely [4][1].
- **High Cost at Scale:** Connecting multiple locations or devices requires a separate dedicated line (such as a leased line) for each pair, which becomes very costly [4][1].
- **Limited Flexibility:** The architecture is strictly locked to two endpoints, making it unsuited for multi-user local area networks (LANs) [4][1].
- **Higher Maintenance Overhead:** Managing multiple independent point-to-point connections across a larger environment increases administrative and troubleshooting complexity [4][1].

### 7.3 Star Topology

<img width="554" height="554" alt="Star topology diagram" src="assets/diagrams/star-topology.png" />

**Figure 6:** Star topology — every device connects to a central hub, switch, or router [4][1].

A **star topology** is a computer network setup where every node (device) connects independently to a central device, such as a hub, switch, or router [4][1].

**Pros (Advantages):**

- **Isolated Failures:** If one cable or device breaks, only that specific node goes down while the rest of the network keeps working normally [4][1].
- **Easy Scalability:** You can add or remove devices easily just by plugging them into or unplugging them from the central switch [4][1].
- **Simple Troubleshooting:** Finding a broken connection is straightforward because every device has its own dedicated line leading back to the center [4][1].
- **Better Performance:** Using a modern switch allows unicast data flow, reducing data collisions and keeping speeds high compared to older shared-media layouts like bus topologies [4][1].
- **Centralized Management:** Network administrators can easily monitor traffic, spot issues, and manage devices from the central hub [4][1].

**Cons (Disadvantages):**

- **Single Point of Failure:** If the central hub, switch, or router stops working, the entire network goes down [4][1].
- **Higher Cabling Cost:** Running a separate cable from every single device to a central location requires more wire and installation effort than a linear bus layout [4][1].
- **Hub/Switch Bottlenecks:** Heavy network traffic passing through the central device can cause slowdowns if the hardware lacks the capacity to handle it [4][1].
- **Hardware Dependency:** The overall performance and maximum capacity of the network are completely limited by the specs and reliability of the central device [4][1].

### 7.4 Mesh Topology

<img width="554" height="554" alt="Mesh topology diagram" src="assets/diagrams/mesh-topology.png" />

**Figure 7:** Mesh topology — devices connect directly to multiple other devices [4][1].

**Mesh topology** is a network design where devices, called nodes, connect directly to multiple other nodes without relying on a single central hub [4][1].

**Pros (Advantages):**

- **High Fault Tolerance:** If a single node or cable fails, data automatically reroutes through alternative paths without bringing down the network [4][1].
- **No Single Point of Failure:** The lack of a central hub means a localized breakdown does not compromise the entire system [4][1].
- **High Traffic Handling:** Dedicated and simultaneous data paths reduce congestion and support heavy data loads [4][1].
- **Scalability:** You can add new devices or nodes to the network without disrupting existing communication [4][1].
- **Improved Security and Privacy:** Direct point-to-point or encrypted multi-path links make data harder to intercept or compromise [4][1].

**Cons (Disadvantages):**

- **High Cost:** A full mesh requires an extensive number of cables, ports, and hardware components (N(N-1)/2 connections for N nodes), making it expensive to build [4][1].
- **Complex Setup and Installation:** Designing, configuring, and wiring a full mesh network takes a massive amount of planning and physical labor [4][1].
- **Difficult Maintenance:** Troubleshooting broken links or isolated nodes is time-consuming due to the sheer volume of interconnections [4][1].
- **High Power Consumption:** In a wired or always-on setup, keeping all nodes and redundant paths active demands more power [4][1].

### 7.5 Ring Topology

<img width="300" height="259" alt="Ring topology diagram" src="assets/diagrams/ring-topology.png" />

**Figure 8:** Ring topology — each device connects to two others, forming a closed loop [4][1].

A **ring topology** is a network setup where each device (node) connects to two other devices, forming a closed, circular loop [4][1].

**Pros (Advantages):**

- **No Data Collisions:** Data travels in an orderly sequence using a token-passing method, which prevents packet crashes [4][1].
- **Equal Resource Access:** Every device on the ring gets an identical opportunity to transmit and receive data [4][1].
- **Predictable Performance:** The network maintains steady data speeds and handles heavy traffic much better than a bus topology [4][1].
- **No Central Server Needed:** Devices manage communication independently without relying on a main server [4][1].
- **Lower Cabling Costs:** It requires less physical cable than a star topology because each node only connects to its two immediate neighbors [4][1].

**Cons (Disadvantages):**

- **Single Point of Failure:** In a standard single-ring setup, a broken wire or failed node can bring down the entire network [4][1].
- **Difficult Troubleshooting:** Locating a fault or break requires checking multiple nodes around the circle [4][1].
- **Higher Latency:** Data must pass sequentially through every intermediate device between the sender and the receiver [4][1].
- **Disruption During Changes:** Adding or removing a device traditionally requires stopping the entire network [4][1].

### 7.6 Hybrid Topology

<img width="678" height="452" alt="Hybrid topology diagram" src="assets/diagrams/hybrid-topology.png" />

**Figure 9:** Hybrid topology — combines two or more basic topologies [4][1].

A **hybrid topology** is a computer network structure that combines two or more different basic network topologies — such as star, ring, bus, or mesh — into a single unified system [4][1]. This topology is also the most commonly used topology due to the fact that it combines different topologies' strengths [4][1].

**Pros (Advantages):**

- **High Flexibility & Customization:** You can tailor different sections of the network to match specific department workflows, traffic loads, and physical environments [4][1].
- **Effective Fault Isolation:** Problems or failures in one segment are usually contained to that specific section without crashing the entire network [4][1].
- **Enhanced Reliability & Uptime:** By merging structures, you can build redundancy where it matters most, keeping critical operations running if a sub-network drops [4][1].
- **Scalability:** You can easily add new nodes, devices, or entire network segments (like a new star or ring cluster) without disrupting existing operations [4][1].
- **Optimized Performance:** Traffic can be routed efficiently through pathways best suited for heavy data loads [4][1].

**Cons (Disadvantages):**

- **High Cost:** Hardware components — such as intelligent hubs, multi-protocol routers, and specialized connectors — are expensive [4][1].
- **Complex Design and Setup:** Planning, configuring, and installing a multi-layered hybrid architecture requires advanced network engineering skills [4][1].
- **Heavy Cabling and Infrastructure Requirements:** Merging diverse layouts often demands extensive physical cabling, cooling systems, and specialized infrastructure [4][1].
- **Difficult Maintenance and Troubleshooting:** Because multiple structures work together, diagnosing the root cause of an issue can span across different protocols and physical layouts [4][1].

### 7.7 Tree Topology

<img width="738" height="411" alt="Tree topology diagram" src="assets/diagrams/tree-topology.png" />

**Figure 10:** Tree topology — hierarchical structure with root, branch, and leaf nodes [4][1].

**Tree topology** is a hierarchical network structure that combines elements of star and bus topologies, resembling a tree with a central root node, branches, and leaf nodes [4][1]. Root nodes are located at the very top, branch nodes are located in the middle, and leaf nodes are located at the very bottom [4][1].

**Pros (Advantages):**

- **High Scalability:** You can easily add new secondary branches and sub-networks without disrupting the rest of the existing network [4][1].
- **Effective Fault Isolation:** Problems or damages in one lower-level branch are contained locally and do not automatically crash other branches [4][1].
- **Structured Organization:** The hierarchical layout mimics corporate or departmental structures, making management and monitoring much clearer for IT teams [4][1].
- **Point-to-Point Connections:** Individual devices and segments use dedicated wiring, which reduces data collisions and simplifies targeted troubleshooting [4][1].
- **Good Resource Sharing:** Centralized servers and storage devices can be shared efficiently across various segments [4][1].

**Cons (Disadvantages):**

- **Single Point of Failure:** If the main root node or a critical upper-level backbone cable fails, large portions or the entire network goes down [4][1].
- **High Installation Costs:** Requiring extensive cabling, backbone components, and multiple hubs makes initial setup expensive [4][1].
- **Complex Maintenance:** As the hierarchy grows larger and more branches are added, cable management and troubleshooting upstream become difficult [4][1].
- **Performance Bottlenecks:** Heavy traffic flowing from lower branches must pass through higher-level nodes, leading to potential slowdowns during peak usage [4][1].

### 7.8 Topology Comparison Table

| Topology | How it works | Advantages | Disadvantages | Cost | Reliability | Scalability |
|----------|--------------|------------|---------------|------|-------------|-------------|
| **Bus** | All devices share a single backbone cable [4][1] | Cost-effective; easy to install [4][1] | Backbone failure affects entire network; poor scalability [4][1] | Low [4] | Low [4] | Low [4] |
| **Point-to-Point** | Dedicated link between exactly two devices [4][1] | Simple; high performance; low latency; secure [4][1] | Poor scalability; single point of failure; high cost at scale [4][1] | Low (for two devices) [4] | Low [4] | Low [4] |
| **Star** | Every device connects to a central hub, switch, or router [4][1] | Isolated failures; easy to add/remove devices [4][1] | Central hub is a single point of failure [4][1] | Medium [4] | High [4] | High [4] |
| **Ring** | Each device connects to two others, forming a loop [4][1] | No data collisions; equal access [4][1] | A single break can bring down the network [4][1] | Medium [4] | Medium [4] | Medium [4] |
| **Mesh** | Devices connect directly to multiple other devices [4][1] | High fault tolerance; no single point of failure [4][1] | High cabling cost; complex setup [4][1] | High [4] | Very High [4] | Medium [4] |
| **Tree** | Hierarchical structure with root, branch, and leaf nodes [4][1] | Structured organization; good resource sharing [4][1] | Root failure affects entire network [4][1] | Medium [4] | High [4] | High [4] |
| **Hybrid** | Combines two or more basic topologies [4][1] | Flexible; fault isolation; high reliability [4][1] | Complex design; expensive [4][1] | High [4] | Very High [4] | Very High [4] |

### 7.9 Choosing a Topology

**Scenario:** A school is building a new computer lab with 30 computers [4][1].

**Recommended topology:** **Star topology** [4][1].

**Reason:** Each computer connects independently to a central switch [4][1]. If one cable or computer fails, only that specific node goes down while the rest of the network keeps working [4][1]. It is also easy to add or remove computers by plugging them into or unplugging them from the central switch [4][1].

> **Review 3:** What is network topology and what are the common types?
>
> **Answer:** Network topology is the physical or logical arrangement of nodes and links in a network [4][1]. Common types include bus, point-to-point, star, mesh, ring, hybrid, and tree, each with different trade-offs in cost, complexity, fault tolerance, and scalability [4][1].

---

## 8. Data Flow and Transmission

### 8.1 Types of Data Flow

#### 8.1.1 Simplex (One Way)

<img width="515" height="388" alt="Simplex data flow diagram" src="assets/diagrams/simplex-data-flow.png" />

**Figure 11:** Simplex data flow — one direction only [1].

- Data travels in only one direction [1].
- The sender can send data, but the receiver cannot send data back through that communication channel [1].
- **Example:** Traditional TV broadcasting and a computer keyboard sending input to a computer [1].

#### 8.1.2 Full-Duplex (Two Way Simultaneous)

<img width="359" height="136" alt="Full-duplex data flow diagram" src="assets/diagrams/full-duplex-data-flow.png" />

**Figure 12:** Full-duplex data flow — both directions at the same time [1].

- Data travels in both directions at the same time [1].
- Both devices can send and receive data simultaneously [1].
- **Example:** A telephone conversation [1].

#### 8.1.3 Half-Duplex (Two Way Alternating)

<img width="359" height="109" alt="Half-duplex data flow diagram" src="assets/diagrams/half-duplex-data-flow.png" />

**Figure 13:** Half-duplex data flow — both directions but not at the same time [1].

- Data can travel in both directions, but not at the same time [1].
- One device sends data while the other receives it. Then they can switch roles [1].
- **Example:** Walkie-talkies [1].

### 8.2 Methods of Data Transmission

#### 8.2.1 Serial Transmission

<img width="660" height="330" alt="Serial transmission diagram" src="assets/diagrams/serial-transmission.png" />

**Figure 14:** Serial transmission — bits sent one at a time along a single channel [1].

- Serial transmission sends data one bit at a time along a single communication channel [1].
- It is slower than parallel transmission but works well over longer distances and requires less cabling [1].
- **Example:** USB connections and most modern network cables [1].

#### 8.2.2 Parallel Transmission

<img width="660" height="330" alt="Parallel transmission diagram" src="assets/diagrams/parallel-transmission.png" />

**Figure 15:** Parallel transmission — multiple bits sent simultaneously along multiple channels [1].

- Parallel transmission sends many bits of data at the same time from one computer to another [1]. It is faster than serial and works well for short distances [1]. It fits well with how computers are built inside, as they use parallel systems [1]. Computers and other devices can easily use parallel transmission [1].
- It is easy to set up and fix problems with parallel transmission [1]. It uses one cable with a 25-pin port [1]. This port has 17 signal lines and 8 ground lines [1]. The 17 lines are split into 4 lines to start the data transfer, 5 lines to talk and report errors, and 8 lines to move the data [1].

**Why parallel is not used for long distances:** Parallel transmission suffers from **skew** (bits arriving at slightly different times) and **crosstalk** (interference between wires), making it unreliable over long distances [1].

### 8.3 Methods of Data Synchronization

#### 8.3.1 Synchronous Transmission

- Synchronous processing is the traditional way of processing in client-server communication [15][16]. A client sends a request to a server and waits for the server to complete the job and send a response before the client can continue doing any other work [15][16]. This process is often referred to as **blocking** (i.e., the client is blocked from doing any other work until a response is received) [15][16].
- Both you and the other person must be on the line at the exact same time for the communication to work [15][16].
- **Why it fits:**
  - You are perfectly synchronized in time [15][16].
  - When you speak, the other person hears it instantly [15][16].
  - If one person drops off or lags, the entire flow of the conversation stops or breaks up [15][16].

#### 8.3.2 Asynchronous Transmission

- Asynchronous processing is the opposite of synchronous processing, as the client does not have to wait for a response after a request is made, and can continue other forms of processing [15][16]. This process is referred to as **non-blocking** because the execution thread of the client is not blocked after the request is made [15][16]. This allows systems to scale better as more work can be done in a given amount of time [15][16].
- **Example:** You send a message, and the other person opens it whenever they are ready [15][16]. There is no real-time link or shared schedule between you [15][16].
- **Why it fits:**
  - The conversation happens in bursts [15][16].
  - You might send a text at 2:00 PM, and they reply at 2:05 PM [15][16].
  - The time gaps between messages are completely random and irregular [15][16].

> **Review 4:** What are the three types of data flow?
>
> **Answer:**
> - **Simplex:** Data travels in one direction only (e.g., TV broadcast, keyboard input) [1].
> - **Half-duplex:** Data travels in both directions but not at the same time (e.g., walkie-talkies) [1].
> - **Full-duplex:** Data travels in both directions at the same time (e.g., telephone conversation) [1].

> **Review 5:** What is the difference between serial and parallel transmission?
>
> **Answer:** Serial transmission sends data one bit at a time along a single channel, making it slower but suitable for longer distances with less cabling [1]. Parallel transmission sends many bits at the same time along multiple channels, making it faster but only suitable for short distances [1].

> **Review 6:** What is the difference between synchronous and asynchronous transmission?
>
> **Answer:** Synchronous transmission requires both devices to be synchronized in time [15][16]. The client sends a request and waits for a response before continuing (blocking) [15][16]. Asynchronous transmission does not require the client to wait — it can continue other work after sending a request (non-blocking) [15][16]. Synchronous works in real time; asynchronous works in bursts with irregular time gaps [15][16].

---

## 9. Network Architecture

### 9.1 Types of Networks

#### 9.1.1 LAN (Local Area Network)

- A **LAN** is a collection of connected devices in one physical location, such as a home or an office [13][1]. It uses the **star topology** since if a single Ethernet cable fails or a computer crashes, only that individual machine loses connection [13][1]. The rest of the office keeps working perfectly [13][1]. When adding new employees, you simply plug a new cable into the central switch [13][1]. You don't have to take the network offline to expand it [13][1]. A LAN can be small or large, ranging from a home network with one user to a large enterprise network with thousands of users and devices [13][1]. A LAN may include both wired and wireless devices [13][1].
- Regardless of size, a LAN's particular characteristic is that it connects devices that are in a single, limited area [13][1].

#### 9.1.2 WAN (Wide Area Network)

- A **WAN** connects computers and smaller networks over large geographical areas, such as different cities, countries, or continents [13][1]. It allows people and organizations in different locations to communicate and share information [13][1]. It uses either **mesh or hybrid topology** since it connects distinct cities or countries using multiple redundant paths [13][1]. If an undersea fiber-optic cable is cut, traffic automatically reroutes through another country [13][1].
- **Example:** A company may have offices in Tokyo, Singapore, and London [13][1]. A WAN can connect the networks in these offices so employees can access company files and systems from different locations [13][1].
- The internet is the most well-known example of a WAN because it connects millions of networks around the world [13][1]. WANs often rely on telecommunications companies and internet service providers (ISPs) to carry data over long distances [13][1]. Compared with a LAN, a WAN usually requires more complex infrastructure and can be more expensive to maintain [13][1].

#### 9.1.3 MAN (Metropolitan Area Network)

- A **MAN** connects multiple LANs across a city, town, or large campus [13][1]. It is larger than a typical LAN but generally covers a smaller geographical area than a WAN [13][1]. It uses **tree topology** as a tree topology allows a city government to act as the "root," branching down to individual municipal departments, schools, and police stations [13][1].
- **Example:** A university with several buildings across a city may use a MAN to connect the computer networks in its library, laboratories, administration offices, and other facilities [13][1]. This allows students and staff to access shared resources across different locations [13][1].
- A MAN may use fibre-optic cables or other high-speed communication links to transfer data between locations [13][1]. It is useful for universities, government offices, hospitals, and businesses that need to connect several buildings within the same metropolitan area [13][1].

### 9.2 Network Service Models

#### 9.2.1 Client-Server Model

<img width="499" height="300" alt="Client-server model diagram" src="assets/diagrams/client-server-model.png" />

**Figure 16:** Client-server model — a centralized server provides resources to clients [14][1].

- The **client-server model** is a centralized network architecture where a dedicated computer system (the server) stores data, manages resources, and processes requests, while other devices (the clients) request and consume those services [14][1]. Client and server roles are fixed [14][1].
- **Examples:** Websites and web browsers (such as looking up pages hosted on Apache or Nginx servers via HTTP/HTTPS), email services (such as Gmail or Outlook connecting to mail servers), streaming services (such as Netflix serving video streams to user devices), cloud storage (such as Google Drive or Dropbox) [14][1].
- **What it is used for:** Managing heavy user traffic, enforcing centralized security and firewalls, running enterprise databases, and handling regular backups from a single location [14][1].

#### 9.2.2 Peer-to-Peer Model

<img width="430" height="465" alt="Peer-to-peer model diagram" src="assets/diagrams/peer-to-peer-model.png" />

**Figure 17:** Peer-to-peer model — every node acts as both client and server [14][1].

- A **peer-to-peer (P2P)** network is a decentralized network where every participant (called a "peer") has equal status and acts as both a client and a server at the same time [14][1]. Peers share resources directly with each other without needing a central authority [14][1].
- **Examples:** File sharing (BitTorrent): When downloading a popular software update or media file via torrent, you are not downloading it from a single company's computer [14][1]. You are pulling fragments of the file from hundreds of other everyday internet users who already have it, while simultaneously uploading fragments to new users [14][1]. Home Wi-Fi networks: In a simple home setup, two laptops can connect directly over the local network to transfer a photo or print a document without needing an external corporate server to process the request [14][1].
- **What it is used for:** Sharing files directly between users, distributed file sharing, and simple home network connections without a dedicated server [14][1].

> **Review 7:** What is the difference between a LAN and a WAN?
>
> **Answer:** A LAN (Local Area Network) connects devices in a single, limited area such as a home or office [13][1]. It typically uses star topology and is cheaper and simpler to maintain [13][1]. A WAN (Wide Area Network) connects computers and smaller networks over large geographical areas such as cities, countries, or continents [13][1]. It typically uses mesh or hybrid topology, requires more complex infrastructure, and is more expensive to maintain [13][1].

> **Review 8:** What is the difference between the client-server model and the peer-to-peer model?
>
> **Answer:** In the client-server model, roles are fixed: a dedicated server stores data and processes requests, while clients request and consume services [14][1]. It is centralized [14][1]. In the peer-to-peer model, every participant has equal status and acts as both client and server at the same time [14][1]. It is decentralized and does not need a central authority [14][1].

---

## 10. Network Threats and Security

### 10.1 Malware

- **Virus:** A program that attaches itself to a host file or program, replicates by copying itself, and corrupts, modifies, or deletes data [5][1].
- **Worm:** A standalone program that self-replicates and spreads across networks without needing a host file or human interaction [5][1].
- **Trojan Horse:** Malicious code disguised as or bundled inside a legitimate, useful piece of software; once installed, it creates backdoors for attackers [5][1].
- **Spyware:** Secretive software that monitors user activity (such as keystrokes, screen captures, and browsing history) and transmits the data back to a third party [5][1].
- **Adware:** Software that automatically displays unwanted, intrusive pop-up advertisements and may redirect browser traffic [5][1].
- **Ransomware:** Software that encrypts a victim's files or locks the hard drive, demanding a financial ransom (often in cryptocurrency) in exchange for the decryption key [5][1].

**How each malware type spreads:** [5][1]

| Malware type | How it spreads |
|--------------|----------------|
| Virus | Requires user action (opening the infected file) [5][1] |
| Worm | Exploits network vulnerabilities; no user action needed [5][1] |
| Trojan Horse | User is tricked into installing it [5][1] |
| Ransomware | Often delivered via phishing emails or malicious downloads [5][1] |
| Spyware | Bundled with other software or downloaded from malicious sites [5][1] |
| Adware | Bundled with free software [5][1] |

### 10.2 Cyberattacks

- **Brute-Force & Dictionary Attacks:** Trying every possible combination of a password or PIN (or using a list of common words) until the correct credentials are found [12][1].
- **Data Interception (Packet Sniffing):** Eavesdropping on data as it travels across a wired or wireless network using software or hardware "packet sniffers" [12][1].
- **Denial of Service (DoS) & Distributed Denial of Service (DDoS):** Overwhelming a server or network with a massive flood of data requests from a single source (DoS) or a botnet of multiple infected computers (DDoS) so it crashes or becomes unavailable [12][1].
- **Hacking / Unauthorized Access:** Gaining illegal entry into a computer system or network to view, delete, or alter data [12][1].
- **Phishing:** Sending fraudulent emails, SMS (smishing), or phone calls (vishing) that mimic legitimate organizations to trick users into revealing sensitive data or passwords [12][1].
- **Pharming:** Using malicious code or DNS/browser manipulation to silently redirect a user from a legitimate website to a fake replica site designed to steal credentials [12][1].
- **Social Engineering:** Manipulating human psychology (trust, fear, curiosity, or authority) to persuade individuals to break security procedures or reveal confidential information [12][1].

### 10.3 System and Network Vulnerabilities

- **Weak or Default Passwords:** Using easily guessed, short, or factory-default passwords (e.g., 123456, admin) [12][1].
- **Unpatched / Outdated Software:** Running operating systems or applications missing critical security patches, leaving known vulnerabilities open to exploit [12][1].
- **Misconfigured Access Rights:** Setting file permissions or server roles too loosely (e.g., giving standard users administrative privileges) [12][1].
- **Removable Media:** Using infected USB flash drives, CDs, or external hard drives that bypass network firewalls when plugged into a system [12][1].

### 10.4 Common Types of Network Security

1. **Firewall:** A security system that monitors and controls incoming and outgoing network traffic based on defined rules [1][5]. It helps block unwanted or unauthorized connections [1][5].
2. **Encryption:** Converts readable information into an encoded form so that unauthorized people cannot easily understand it [7][10]. HTTPS is an example of technology that uses encryption to protect web communication [7][10].
3. **Antivirus and Anti-malware:** Security software that detects, blocks, and removes malicious programs that could damage devices or steal information [5][1].
4. **Authentication:** Verifies a user's identity before allowing access to a system or network [12][1]. Examples include passwords, fingerprint scans, and multi-factor authentication (MFA) [12][1].
5. **VPN (Virtual Private Network):** Creates an encrypted connection between a device and a VPN endpoint, helping protect data while it travels across an untrusted network [7][10].
6. **Intrusion Detection and Prevention Systems (IDS/IPS):** Monitor network traffic for suspicious activity [5][12]. An IDS detects and reports potential threats, while an IPS can also block certain malicious traffic [5][12].

### 10.5 Countermeasures to Malware

- **Firewall:** Blocks unauthorized outbound communication, preventing spyware and trojans from leaking stolen data or downloading payload updates from command-and-control servers [5][1].
- **Antivirus and Anti-malware:** Continuously scans files and memory to detect, quarantine, and remove viruses, worms, trojans, and spyware based on signature databases and heuristic analysis [5][1].

### 10.6 Countermeasures Against Cyberattacks

- **Authentication:** Defeats brute-force and dictionary attacks and hacking [12][1]. Even if an attacker guesses a password, MFA requires a second verification step (like an authenticator app or hardware token) [12][1]. Account lockout policies also stop rapid password-guessing scripts [12][1].
- **Encryption and VPN:** Defeats data interception (packet sniffing) [7][10]. By scrambling data in transit (e.g., using HTTPS or a VPN tunnel), eavesdroppers only see unreadable ciphertext even if they capture the packets [7][10].
- **Intrusion Detection and Prevention Systems (IDS/IPS):** Defeats DoS and DDoS attacks by monitoring traffic patterns, identifying abnormal flood requests, and automatically filtering or rate-limiting malicious traffic [5][12].

### 10.7 Countermeasures Against System and Network Vulnerabilities

- **Robust Password Policies and Password Managers:** Address weak or default passwords [12][1]. Enforcing minimum length, complexity, and prohibiting factory-default credentials [12][1].
- **Automated Patch Management:** Addresses unpatched or outdated software [12][1]. Regularly updating operating systems, firmware, and applications ensures that newly discovered security flaws are quickly patched before attackers can exploit them [12][1].

### 10.8 Threat–Countermeasure Mapping Table

| Threat | Countermeasure | How it works |
|--------|----------------|--------------|
| Virus, worm, Trojan, spyware | **Antivirus and anti-malware** [5][1] | Scans files and memory to detect, quarantine, and remove malicious software [5][1] |
| Ransomware | **Regular backups** [5][1] | Allows recovery of encrypted files without paying the ransom [5][1] |
| Brute-force attack | **Multi-factor authentication (MFA)** and **account lockout policies** [12][1] | Requires a second verification step; locks accounts after repeated failed attempts [12][1] |
| Data interception (packet sniffing) | **Encryption (HTTPS)** and **VPN** [7][10] | Scrambles data so eavesdroppers only see unreadable ciphertext [7][10] |
| DoS / DDoS | **Intrusion Detection and Prevention Systems (IDS/IPS)** [5][12] | Monitors traffic patterns and filters or rate-limits malicious traffic [5][12] |
| Phishing / pharming | **User awareness training** and **authentication** [12][1] | Teaches users to recognize fraudulent messages; verifies identities [12][1] |
| Weak or default passwords | **Robust password policies** [12][1] | Enforces minimum length, complexity, and prohibits factory-default credentials [12][1] |
| Unpatched software | **Automated patch management** [12][1] | Regularly updates operating systems and applications to fix known vulnerabilities [12][1] |

### 10.9 How Encryption Works (Symmetric vs Asymmetric)

**Symmetric encryption** uses the **same key** to encrypt and decrypt data [7][10]. It is fast but requires the sender and receiver to share the key securely [7][10].

**Asymmetric encryption** uses **two different keys**: a public key to encrypt and a private key to decrypt [7][10]. It solves the key-exchange problem but is slower than symmetric encryption [7][10].

**How HTTPS uses both:** When you connect to an HTTPS website, the browser and server use asymmetric encryption to securely exchange a **symmetric session key** [7][10]. Once the session key is established, they switch to symmetric encryption for the actual data transfer because it is faster [7][10].

> **Review 9:** Name three types of malware and one countermeasure for each.
>
> **Answer:**
> - **Virus:** Attaches to host files and replicates. Countermeasure: Antivirus and anti-malware [5][1].
> - **Worm:** Self-replicates and spreads across networks. Countermeasure: Firewall and antivirus [5][1].
> - **Ransomware:** Encrypts files and demands payment. Countermeasure: Regular backups and antivirus [5][1].
> - (Also acceptable: Trojan Horse, Spyware, Adware with appropriate countermeasures) [5][1].

> **Review 10:** Name two cyberattacks and one defence for each.
>
> **Answer:**
> - **Brute-force attack:** Defence — Authentication with multi-factor authentication (MFA) and account lockout policies [12][1].
> - **Data interception (packet sniffing):** Defence — Encryption (HTTPS) and VPN [7][10].
> - (Also acceptable: DDoS with IDS/IPS; phishing with user awareness and authentication) [12][1].

> **Review 11:** Name all three network types with the topology each commonly uses and why.
>
> **Answer:**
> - **LAN (Local Area Network):** Uses star topology because if one cable or device fails, only that device goes down; the rest of the network keeps working [13][1]. It is also easy to add or remove devices [13][1].
> - **WAN (Wide Area Network):** Uses mesh or hybrid topology because it connects distinct cities or countries using multiple redundant paths [13][1]. If one cable is cut, traffic automatically reroutes [13][1].
> - **MAN (Metropolitan Area Network):** Uses tree topology because it allows a central "root" (such as a city government) to branch down to individual departments, schools, and police stations across a city [13][1].

---

## 11. Worked Examples

### Worked Example 1: Tracing a Packet Through a Network

**Scenario:** You send a message from your laptop to a web server. The message is 1 MB, which the network splits into 100 packets [1][18].

| Step | What happens | Key concept |
|------|--------------|-------------|
| 1 | The message is divided into 100 packets. Each packet gets a **header** with source IP, destination IP, and sequence number (1–100) [1][18]. | Packetisation [1][18] |
| 2 | A **trailer** is added to each packet for error checking [1][18]. | Error detection [1][18] |
| 3 | Your laptop sends the packets to your **router**. The router examines the destination IP in each header and forwards the packet toward the internet [1][17]. | Routing [1][17] |
| 4 | The packets travel through multiple routers. Some packets take faster routes and arrive out of order [1][18]. | Packet switching [1][18] |
| 5 | The web server receives the packets. Using the **sequence numbers**, it reassembles them in the correct order (1, 2, 3, …) [1][18]. | Reassembly [1][18] |
| 6 | If a packet is lost, **TCP** detects the gap and requests retransmission [6][1]. | Reliability [6][1] |

### Worked Example 2: Choosing a Network Topology

**Scenario:** A small business has 10 employees and a limited budget. They need a reliable network where one broken cable does not stop everyone from working [4][1].

| Consideration | Analysis | Decision |
|---------------|----------|----------|
| Budget | Limited | Star topology uses more cable than bus but is affordable for 10 devices [4][1] |
| Reliability | One broken cable should not affect everyone | Star isolates failures to individual devices [4][1] |
| Scalability | May add more employees later | Star makes it easy to add devices [4][1] |
| **Recommendation** | **Star topology** | Best balance of cost, reliability, and scalability for this scenario [4][1] |

### Worked Example 3: Breaking Down a URL

**URL:** `https://www.bbc.co.uk/news` [8][1]

| Part | Value | Explanation |
|------|-------|-------------|
| Protocol | `https` | Secure web protocol [8][1] |
| Subdomain | `www` | World Wide Web [8][1] |
| Domain name | `bbc` | The organization's name [8][1] |
| Second-level domain | `co` | Indicates commercial organization [8][1] |
| Top-level domain (country code) | `uk` | United Kingdom [8][1] |
| Path | `/news` | The specific page on the website [8][1] |

---

## 12. Structured Learner Activities

### Activity 1: Label the Parts of a Packet

**Instructions:** Draw or describe a packet with three parts. Label each part and write one sentence explaining its purpose [1][18].

**Expected outcome:**

- **Header:** Contains source address, destination address, and sequence number. It helps the packet reach the right device and be reassembled in order [1][18].
- **Payload:** Contains the actual data being transmitted [1][18].
- **Trailer:** Marks the end of the packet and contains error detection bits [1][18].

### Activity 2: Choose a Topology

**Scenario:** A university is building a new campus network connecting five buildings across a city. The network must be reliable, and if one building's connection fails, the others should keep working [4][1].

**Question:** Which topology would you recommend and why?

**Expected answer:** **Mesh or hybrid topology** [4][1]. A mesh topology provides multiple redundant paths, so if one link fails, data can reroute through another path [4][1]. A hybrid topology could combine a star topology within each building (connecting devices to a local switch) with a mesh topology between buildings for redundancy [4][1]. A bus or ring topology would be unsuitable because a single failure could affect the entire network [4][1].

### Activity 3: Match the Threat to the Countermeasure

**Instructions:** Draw lines to match each threat on the left to an appropriate countermeasure on the right [5][12].

| Threat | Countermeasure |
|--------|----------------|
| Virus [5][1] | Antivirus and anti-malware [5][1] |
| Brute-force attack [12][1] | Multi-factor authentication (MFA) [12][1] |
| Packet sniffing [12][1] | Encryption (HTTPS/VPN) [7][10] |
| DDoS [12][1] | Intrusion Detection and Prevention Systems (IDS/IPS) [5][12] |

**Expected outcome:** Each threat is matched to a countermeasure that directly addresses it, as shown in the Threat–Countermeasure Mapping table in Section 10.8 [5][12].

### Activity 4: Break Down a URL

**Instructions:** For the URL `https://store.example.co.uk/product/123`, identify each part [8][1].

**Expected answer:**

| Part | Value |
|------|-------|
| Protocol | `https` [8][1] |
| Subdomain | `store` [8][1] |
| Domain name | `example` [8][1] |
| Second-level domain | `co` [8][1] |
| Top-level domain (country code) | `uk` [8][1] |
| Path | `/product/123` [8][1] |

### Activity 5: Classify the Data Flow

**Instructions:** For each scenario below, state whether it uses simplex, half-duplex, or full-duplex communication [1].

1. A TV broadcast
2. A telephone conversation
3. A walkie-talkie conversation
4. A keyboard sending input to a computer
5. Two people chatting over a video call

**Expected answers:**

1. Simplex — data travels in one direction only [1].
2. Full-duplex — both directions at the same time [1].
3. Half-duplex — both directions but not at the same time [1].
4. Simplex — one direction only [1].
5. Full-duplex — both directions at the same time [1].

### Activity 6: Choose the Right Transmission Method

**Instructions:** For each scenario, state whether serial or parallel transmission would be more appropriate and explain why [1].

1. Connecting a keyboard to a computer over a 2-metre cable
2. Sending data between two buildings 500 metres apart
3. Connecting a printer to a computer using an older 25-pin cable

**Expected answers:**

1. Serial — modern keyboards use USB, which is serial. Serial works well over short distances with less cabling [1].
2. Serial — parallel is unreliable over long distances due to skew and crosstalk [1].
3. Parallel — older printer cables used parallel transmission for short distances [1].

---

## 13. Review Questions with Answers

> **Question 1:** What is the difference between TCP and IP?
>
> **Answer:** TCP is a connection-oriented protocol that ensures reliable, in-order delivery [6][1]. IP is a connectionless protocol that handles addressing and routing [6][1]. TCP is layered on top of IP to provide reliability that IP lacks [6][1].

> **Question 2:** What is the difference between a router and a switch?
>
> **Answer:** A router connects different networks and forwards data between them by examining destination IP addresses [1][17]. A switch connects multiple devices within a LAN and directs data to the intended device using MAC addresses [1][17].

> **Question 3:** What is the difference between a virus and a worm?
>
> **Answer:** A virus attaches itself to a host file and requires user action to spread [5][1]. A worm is a standalone program that self-replicates and spreads across networks without needing a host file or user action [5][1].

> **Question 4:** What is the difference between phishing and pharming?
>
> **Answer:** Phishing sends fraudulent messages that trick users into revealing information [12][1]. Pharming redirects users from legitimate websites to fake replica sites using DNS manipulation [12][1]. Phishing relies on user action; pharming redirects automatically [12][1].

> **Question 5:** Which topology would you recommend for a school computer lab and why?
>
> **Answer:** **Star topology** [4][1]. Each computer connects independently to a central switch [4][1]. If one cable or computer fails, only that node goes down [4][1]. It is also easy to add or remove computers [4][1].

> **Question 6:** Why is packet switching efficient?
>
> **Answer:** Packet switching breaks data into small packets that can travel through available routes [1][18]. Many devices can send data at the same time [1][18]. If a router or link fails, packets reroute around the problem [1][18].

> **Question 7:** What is the difference between symmetric and asymmetric encryption?
>
> **Answer:** Symmetric encryption uses the same key to encrypt and decrypt data [7][10]. Asymmetric encryption uses two different keys: a public key to encrypt and a private key to decrypt [7][10]. HTTPS uses asymmetric encryption to exchange a symmetric session key, then uses the faster symmetric encryption for the actual data [7][10].

> **Question 8:** What is the difference between a LAN and a WAN?
>
> **Answer:** A LAN connects devices in a single, limited area such as a home or office [13][1]. A WAN connects networks over large geographical areas such as cities or countries [13][1].

> **Question 9:** What is the difference between the client-server model and the peer-to-peer model?
>
> **Answer:** In the client-server model, roles are fixed: a server provides resources and clients consume them [14][1]. In the peer-to-peer model, every node has equal status and acts as both client and server [14][1].

> **Question 10:** Name all three network types (LAN, WAN, MAN) with the topology each commonly uses and why.
>
> **Answer:**
> - **LAN:** Star topology — isolates failures and is easy to expand [13][1].
> - **WAN:** Mesh or hybrid topology — provides redundant paths across large distances [13][1].
> - **MAN:** Tree topology — hierarchical structure suits city-wide or campus networks [13][1].

> **Question 11:** What are the three parts of a packet and what does each do?
>
> **Answer:**
> - **Header:** Stores control information including source address, destination address, and sequence number. It helps the packet reach the right device and be reassembled in order [1][18].
> - **Payload:** Carries the actual data being transmitted [1][18].
> - **Trailer:** Marks the end of the packet and contains error detection bits [1][18].

> **Question 12:** What is the difference between a MAC address and an IP address?
>
> **Answer:** A MAC address is a unique 48-bit physical identifier hardcoded into a NIC by the manufacturer [1]. An IP address is a software-assigned logical address given to a device when it connects to a network [1]. A MAC address is permanent; an IP address can change [1].

> **Question 13:** What is a URL and what are its main parts?
>
> **Answer:** A URL is the address of a source on the internet [8][1]. Its main parts are:
> - **Protocol:** Determines how data is transferred (e.g., HTTP or HTTPS) [8][1].
> - **Subdomain:** Identifies each area of the website (e.g., www) [8][1].
> - **Domain name:** The unique, human-readable name of a specific website [8][1].
> - **Top-level domain:** Categorizes the website by purpose, industry, or location (e.g., .com, .org, .edu, .uk) [8][1].

> **Question 14:** What are the three types of data flow?
>
> **Answer:**
> - **Simplex:** Data travels in one direction only (e.g., TV broadcast, keyboard input) [1].
> - **Half-duplex:** Data travels in both directions but not at the same time (e.g., walkie-talkies) [1].
> - **Full-duplex:** Data travels in both directions at the same time (e.g., telephone conversation) [1].

> **Question 15:** What is the difference between serial and parallel transmission?
>
> **Answer:** Serial transmission sends data one bit at a time along a single channel, making it slower but suitable for longer distances with less cabling [1]. Parallel transmission sends many bits at the same time along multiple channels, making it faster but only suitable for short distances [1].

> **Question 16:** What is the difference between synchronous and asynchronous transmission?
>
> **Answer:** Synchronous transmission requires both devices to be synchronized in time [15][16]. The client sends a request and waits for a response before continuing (blocking) [15][16]. Asynchronous transmission does not require the client to wait — it can continue other work after sending a request (non-blocking) [15][16]. Synchronous works in real time; asynchronous works in bursts with irregular time gaps [15][16].

> **Question 17:** What is a DDoS attack and how can it be defended against?
>
> **Answer:** A Distributed Denial of Service (DDoS) attack overwhelms a server or network with a massive flood of data requests from a botnet of multiple infected computers, causing it to crash or become unavailable [12][1]. It can be defended against using Intrusion Detection and Prevention Systems (IDS/IPS), which monitor traffic patterns, identify abnormal flood requests, and automatically filter or rate-limit malicious traffic [5][12].

> **Question 18:** What is social engineering?
>
> **Answer:** Social engineering is the manipulation of human psychology (trust, fear, curiosity, or authority) to persuade individuals to break security procedures or reveal confidential information [12][1]. It targets people rather than technical systems [12][1].

> **Question 19:** Why is encryption important for network security?
>
> **Answer:** Encryption converts readable information into an encoded form so that unauthorized people cannot easily understand it [7][10]. It protects data in transit — for example, HTTPS encrypts web communication, and a VPN encrypts data travelling across an untrusted network [7][10]. Even if an eavesdropper captures the packets, they only see unreadable ciphertext [7][10].

> **Question 20:** Name three network topologies and state one advantage and one disadvantage of each.
>
> **Answer:**
> - **Star:** Advantage — isolated failures (one broken cable only affects one device) [4][1]. Disadvantage — the central hub is a single point of failure [4][1].
> - **Bus:** Advantage — cost-effective (least cabling required) [4][1]. Disadvantage — a break in the backbone cable brings down the entire network [4][1].
> - **Mesh:** Advantage — high fault tolerance (no single point of failure) [4][1]. Disadvantage — high cabling cost and complex setup [4][1].

---

## 14. Current Development Status of Each Section

This table shows the current development status of every section, using the status labels required by the assignment (`Outline only`, `Drafted`, `Needs revision`, `Checked`).

| Section | Title | Status | Notes |
|---------|-------|--------|-------|
| 1 | What You Will Learn | `Drafted` | Learning outcomes cover the full Networks scope. |
| 2 | Key Terms and Glossary | `Drafted` | Glossary added. Needs cross-check that all body terms appear in the glossary. |
| 3 | Network Definition | `Checked` | Definition, formal definition, and three-part breakdown reviewed. |
| 4 | Components of a Network | `Checked` | Nodes, links, routers, switches all explained with examples. |
| 5 | Packets and Packet Switching | `Checked` | Includes text diagram, worked example, and review question with answer. |
| 6 | Protocols and Addressing | `Checked` | TCP/IP distinction clarified; MAC and IP addresses compared; URL anatomy with worked example. |
| 7 | Network Topologies | `Checked` | Seven topologies compared; comparison table added; topology selection scenario included. |
| 8 | Data Flow and Transmission | `Checked` | Simplex / half-duplex / full-duplex labels corrected; serial vs parallel clarified; sync vs async explained. |
| 9 | Network Architecture | `Checked` | LAN / WAN / MAN and client-server vs P2P compared with examples. |
| 10 | Network Threats and Security | `Checked` | Malware labels corrected; threat–countermeasure mapping table added; encryption explained. |
| 11 | Worked Examples | `Checked` | Three worked examples: packet trace, topology choice, URL breakdown. |
| 12 | Structured Learner Activities | `Checked` | Six activities with expected outcomes. |
| 13 | Review Questions with Answers | `Checked` | Twenty questions with answers. |
| 14 | Current Development Status | `Drafted` | This table. |
| 15 | Important Gaps and Uncertainties | `Drafted` | See below. |
| 16 | Peer Review Record | `Drafted` | See below (reviewed by Rysen). |
| 17 | Plan for Use in the Three Resources | `Drafted` | See below. |

**Overall status:** `Drafted and peer-reviewed by Rysen`. Ready for integration into the wider module content.

---

## 15. Important Gaps and Uncertainties

The following gaps and uncertainties remain and are acknowledged honestly:

1. **External images must be moved to the local `assets/` folder.** The Markdown file now references local paths (`assets/diagrams/...`), but the actual image files must still be downloaded from the previous GitHub attachment URLs and saved into `assets/diagrams/` before submission. If the files are not placed there, the images will not display.

2. **Reference [1] and [2] publisher details are incomplete.** Watson & Williams (2016a, 2016b) are cited, but the publisher name and place of publication still say "[Publisher details to be confirmed]". These must be filled in before final submission.

3. **Terminology coverage is uneven.** Some terms (e.g., CSMA/CD, NIC, unicast, botnet, ciphertext) appear in the glossary but are also used in the body without an inline definition at first use. This should be reviewed to ensure every technical term is defined in context the first time it is used.

4. **Synchronous vs asynchronous definition is slightly imprecise.** The current explanation is framed around client-server blocking/non-blocking behaviour. This is accurate for processing but is not the same as synchronous/asynchronous *transmission* synchronisation (clock signals, start/stop bits). A short additional paragraph should clarify the transmission-level meaning.

5. **The Hardware and Behavioural AI sections are not included in this file.** This file covers only Networks. The whole-module outline (`Content_Outline.md`) must cover all three parts and reference this file as the Networks content.

6. **No contribution evidence exists yet.** This file does not identify which team members wrote which section. A contribution table with author names and relevant sections must be added to `evidence/Repository_Evidence.md`.

7. **No commit history is recorded here.** GitHub commit history (authors, dates, commit messages) must be captured separately as evidence.

8. **No AI-use record is included here.** All significant AI assistance must be recorded in the project log and each member's personal log, following Section 6 of the Shared Assignment Rules.

---

## 16. Peer Review Record

**Reviewer:** Rysen  
**Date reviewed:** Stage 1 snapshot review  
**Scope of review:** Sections 1–13 of this file (the learning content and questions).

### What was checked

Rysen reviewed the following:

- All definitions in the glossary (Section 2).
- All factual claims in Sections 3–10 against the cited sources.
- The three worked examples in Section 11 (packet trace, topology choice, URL breakdown).
- The six structured activities in Section 12 and their expected outcomes.
- The twenty review questions and answers in Section 13.
- The correctness of the earlier corrections (full-duplex and half-duplex labels, serial transmission, malware labels, P2P wording, packet trailer).

### What was found

Rysen reported the following findings:

1. **Accurate:** The corrections to the full-duplex and half-duplex labels were confirmed to be correct.
2. **Accurate:** The corrected serial transmission definition (one bit at a time along a single channel) was confirmed.
3. **Accurate:** The malware labels (Virus, Worm, Trojan Horse, Spyware, Adware, Ransomware) were confirmed correct.
4. **Accurate:** The TCP / IP distinction was confirmed — TCP is connection-oriented and reliable; IP is connectionless and does not guarantee order.
5. **Accurate:** All three worked examples were checked step by step and confirmed to be logically consistent.
6. **Accurate:** All twenty review questions and answers in Section 13 were checked and confirmed.
7. **Needs improvement:** The synchronous vs asynchronous section frames the concept mainly through client-server blocking behaviour. Rysen noted that this should be supplemented with a brief note on transmission-level synchronisation (clock signals, start/stop bits).
8. **Needs improvement:** Several body terms (e.g., CSMA/CD, NIC, unicast, ciphertext) are in the glossary but are used in the body without an inline definition at first use.
9. **Needs improvement:** Image URLs were originally external GitHub attachment URLs. Rysen recommended replacing them with local relative paths (`assets/diagrams/...`). This has since been done in this version.
10. **Confirmed:** The Threat–Countermeasure Mapping table in Section 10.8 was checked and confirmed correct.

### What was corrected or confirmed

- **Confirmed accurate:** The earlier corrections (labels, malware names, transmission definitions, P2P wording, packet trailer) were confirmed correct by Rysen.
- **Corrected in this version:** Image URLs replaced with local relative paths (`assets/diagrams/...`) as recommended by Rysen.
- **Corrected in this version:** Development status labels and gaps/uncertainties added (Sections 14–15) in response to Rysen's feedback that the document lacked a status overview.
- **Outstanding:** The synchronous vs asynchronous explanation and the inline terminology definitions have been noted as gaps in Section 15 and will be addressed in the next revision.

### Confirmation

Rysen confirmed that, once the outstanding gaps in Section 15 are addressed, the content of this file is suitable to form the Networks component of the Study Guide, PPT Slides, and Video Tutorials.

---

## 17. Plan for Use in the Three Resources

This section explains how this Markdown content will be used to produce the three connected learning resources.

### Study Guide

This file forms the **Networks chapter** of the Study Guide. It already contains:

- A "What You Will Learn" introduction (Section 1).
- A glossary (Section 2).
- Full explanations with examples (Sections 3–10).
- Worked examples (Section 11).
- Structured activities (Section 12).
- Review questions with answers (Section 13).

The Study Guide will reproduce these sections in the same order, with images from `assets/diagrams/` embedded directly.

### PPT Slides

The PPT Slides will visualise the key ideas using selected material from this file:

- **Slide 1:** What is a network? (from Section 3) — uses the "group of friends sharing ideas" analogy.
- **Slide 2:** Network components (from Section 4) — nodes, links, routers, switches shown as a labelled diagram.
- **Slide 3:** What is a packet? (from Section 5) — the header/payload/trailer text diagram, animated to show the three parts.
- **Slide 4:** Packet switching (from Section 5.2) — the routing diagram from `assets/diagrams/packet-routing.png`.
- **Slide 5:** TCP vs IP (from Section 6.2) — a side-by-side comparison table.
- **Slide 6:** Topologies (from Section 7.8) — a single comparison table with mini-diagrams.
- **Slide 7:** Data flow types (from Section 8.1) — the three data flow diagrams side by side.
- **Slide 8:** Threats and countermeasures (from Section 10.8) — the mapping table.
- **Slide 9:** Worked example (from Section 11) — tracing a packet step by step.
- **Slide 10:** Activity (from Section 12) — one activity for the audience.

Each slide will cite the section number in the footer so students can return to the Study Guide for full detail.

### Video Tutorials

Two short video tutorials will be produced from this file:

- **Video 1: "How Packets Travel Across a Network"** (3–5 minutes). Walks through Section 5 and Section 11 (Worked Example 1) with the routing diagram narrated. Pauses at the end with Activity 1 (label the parts of a packet) for the viewer to attempt.
- **Video 2: "Choosing the Right Network Topology"** (3–5 minutes). Walks through Section 7.8 (comparison table) and Section 11 (Worked Example 2), with a screen recording of the table and mini-diagrams. Pauses at the end with Activity 2 (choose a topology for a university campus).

The video tutorials will use the same citations and images as the Study Guide so that all three resources are consistent.

### How the three resources support one another

- The **Study Guide** provides the full reference text for self-study and revision.
- The **PPT Slides** provide a visual summary for classroom teaching and review.
- The **Video Tutorials** provide narrated walkthroughs of the hardest concepts, with activities built in.

All three resources are derived from this single Markdown file, so corrections to this file automatically affect the other two. Any future correction (e.g., the outstanding gaps in Section 15) must be applied here first, then propagated to the slides and videos.

---

## 18. References

1. Watson, D., & Williams, H. (2016a). *AI and Computer Science Textbook, IGCSE & O Level* (2nd ed.). [Publisher details to be confirmed].
2. Watson, D., & Williams, H. (2016b). *Computer Science Textbook, AS & A Level*. [Publisher details to be confirmed].
3. IEEE Technology Navigator. (n.d.). *Computer Networks*. Retrieved from https://technav.ieee.org/area/computer-networks/
4. Splunk. (2024, April 10). *Network Topology: The Complete Guide*. Retrieved from https://www.splunk.com/en_us/blog/learn/network-topology.html
5. CERT UCC. (2024, August 19). *Malware: Insights and Protection*. Retrieved from https://ug-cert.ug/malware-insights-and-protection/
6. Cisco Learning Network. (2015, June 10). *TCP connection oriented and IP connectionless*. Retrieved from https://learningnetwork.cisco.com/s/question/0D53i00000KsyLQCAZ/tcp-connection-oriented-and-ip-connectionless
7. MIT Computer Science and Artificial Intelligence Laboratory. (2014). *SSL/TLS and HTTPS*. Retrieved from https://people.csail.mit.edu/alinush/6.858-fall-2014/l14-forcehttps.html
8. auDA. (2022, September 13). *Key terms explained: website URLs*. Retrieved from https://www.auda.org.au/
9. Microsoft Learn. (2009, October 8). *How DNS query works: Domain Name System (DNS)*. Retrieved from https://learn.microsoft.com/
10. Google Patents. (2002). *Efficient packet encryption method* (US7006628). Retrieved from https://patents.google.com/patent/US7006628
11. Google Patents. (2001). *Network system with dual routers* (US20010056499A1). Retrieved from https://patentimages.storage.googleapis.com/
12. NTNU Open. (n.d.). *Authentication Failures and Cyberattacks*. Retrieved from https://ntnuopen.ntnu.no/
13. NIELIT Gorakhpur. (n.d.). *LAN, MAN, and WAN*. Retrieved from https://nielit.gov.in/
14. Zenodo. (n.d.). *Client-server vs peer-to-peer*. Retrieved from https://www.zenodo.org/
15. ScienceDirect. (n.d.). *Synchronous and asynchronous communication services*. Retrieved from https://www.sciencedirect.com/
16. Computer.org. (2023, January 10). *Synchronous And Asynchronous Data Transmission*. Retrieved from https://www.computer.org/
17. Max Medium. (2026). *Module Outline.md*. Team planning document.
18. Max Medium. (2026). *Networks.md*. Team draft.

---
