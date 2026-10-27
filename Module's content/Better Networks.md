# Networks

**Module:** Hardware, Networks and Behavioural AI  
**Team:** Max Medium  
**Status:** Drafted — ready for peer review  
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
14. [References](#14-references)

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

<img width="738" height="237" alt="Packet structure diagram" src="https://github.com/user-attachments/assets/06815940-666a-479b-b6ba-5bd465a1e12d" />

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
