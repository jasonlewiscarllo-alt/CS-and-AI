
# Networks

**Module 2**

Part of: Hardware, Networks and Behaviourist AI

Aligned with Cambridge IGCSE / O Level / AS & A Level Computer Science networking content

------------------------------------------------------------------------

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

# Module overview and learning outcomes

Almost everything you do on a computer or phone involves a network. This module explains what networks are made of, how data is cut into packets and delivered, the rules (protocols) and addresses that make delivery possible, how devices can be arranged, how data flows over a link, how networks are classified, and how they are attacked and defended.

> **By the end of this module you should be able to:**
>
> 1.  Define a computer network and identify its key components (nodes, links, routers, switches).
> 2.  Explain how packets carry data, including the roles of the header, payload and trailer.
> 3.  Distinguish between TCP and IP, and explain why both are needed.
> 4.  Explain MAC addresses and IP addresses, and state the difference between them.
> 5.  Describe the structure of a URL and how DNS translates domain names into IP addresses.
> 6.  Compare common network topologies (bus, point-to-point, star, mesh, ring, hybrid, tree) and choose an appropriate topology for a scenario.
> 7.  Explain simplex, half-duplex and full-duplex data flow.
> 8.  Compare serial and parallel transmission, and synchronous and asynchronous transmission and communication.
> 9.  Compare LAN, WAN and MAN, and compare client–server and peer-to-peer models.
> 10. Identify common malware and cyberattacks, and match them to appropriate countermeasures.

## How to study this module

1.  Read the learning objectives, then the explanation, studying each diagram.
2.  Cover the answer in each **Quick review** and write your own first.
3.  Do every worked example with pencil and paper.
4.  Finish with the activities, case studies and the end-of-module test.

> **Suggested study plan (about 4 weeks)**
>
> | Week | Sections | Focus                                                      |
> |------|----------|------------------------------------------------------------|
> | 1    | 1–3      | Network basics, components, packets                        |
> | 2    | 4–5      | Protocols, addressing, topologies                          |
> | 3    | 6–7      | Data flow, transmission, LAN/WAN/MAN, client–server vs P2P |
> | 4    | 8–14     | Security, activities, case studies, test                   |
>
> **Learning suggestions:** (1) Draw each topology from memory and list one advantage and one disadvantage. (2) Use an analogy for every protocol (post office, phone book, language). (3) Use a real tool: on your own computer, run `ping` and `tracert`/`traceroute` to see packets cross routers. (4) Teach the packet-switching puzzle analogy to a friend. (5) Revisit the threat–countermeasure table until you can reproduce it.

# 1. What a Network Is

A network is like a group of friends sharing ideas. A **computer network** is two or more devices, such as phones, laptops or printers, connected so they can share information and resources. Devices talk over physical cables or wireless signals such as Wi-Fi. Networks can be small, like the one in your home, or huge, connecting devices across countries. Every time you send a message, share a photo or browse the web you are using a network. Networks save time and resources by letting devices share one internet connection, a printer or files.

A more formal definition: a computer network is a collection of computing devices connected by communication links that allow the exchange of data and the sharing of resources. A network is defined by three things:

1.  The **hardware** that forms its nodes: computers, routers, switches and access points.
2.  The **physical or wireless media** that carry signals: cables or radio.
3.  The **protocols** that govern how data is formatted, addressed, transmitted and received.

> **Quick review 1 — What is a computer network and what are its key components?**
>
> A computer network is two or more devices connected so they can share information and resources. Key components: **nodes** (devices), **links** (wired or wireless pathways), **routers** (connect different networks and forward data between them) and **switches** (direct data to the intended device within a LAN).

# 2. Components of a Network

![Figure 1 — Components of a small network. Links join nodes to a switch; the router connects the LAN to other networks.](figures/networks/fig-01.svg)

*Figure 1 — Components of a small network. Links join nodes to a switch; the router connects the LAN to other networks.*

## 2.1 Nodes (devices)

A **node** is any device connected to a network that can send, receive or process data (laptops, phones, printers, servers). *Example:* in a home Wi-Fi setup the phone, laptop and printer are all nodes.

## 2.2 Links (connections)

Links connect devices so they can communicate. **Wired links** use physical cables such as Ethernet (copper) or fibre-optic cable. **Wireless links** use radio signals such as Wi-Fi or Bluetooth. Without links, devices would be isolated. *Example:* a laptop plugged into a router by Ethernet uses a wired link; a phone on the same router over Wi-Fi uses a wireless link.

## 2.3 Routers

A **router** connects different networks and forwards data between them. It examines the destination **IP address** in each packet to decide where to send it next and selects an appropriate path. *Example:* when you open a website your home router forwards your request toward the internet and delivers the reply back to your device.

## 2.4 Switches

A **switch** connects multiple devices within a local area network (LAN). It learns which **MAC address** is on which port and sends data only to the intended device, instead of to every device as an older hub does. *Example:* in a school computer lab a document sent to a network printer on the same switch is forwarded directly to the printer.

| Device                | Works with               | Connects                            | Sends data to                       |
|-----------------------|--------------------------|-------------------------------------|-------------------------------------|
| Hub (older)           | Nothing: repeats signals | Devices in one LAN                  | Every port                          |
| Switch                | MAC addresses            | Devices in one LAN                  | Only the intended port              |
| Router                | IP addresses             | Different networks                  | The next hop toward the destination |
| Wireless access point | Radio signals            | Wireless devices to a wired network | Wireless clients                    |

> **Quick review 2 — Router or switch?**
>
> \(a\) A device sending your request from your home to the internet is a **router**. (b) A device that sends a file only to one printer in the same lab is a **switch**. The difference: a switch uses MAC addresses inside one LAN; a router uses IP addresses between networks.

# 3. Packets and Packet Switching

## 3.1 What is a packet?

A **packet** is a small part of a larger piece of data sent over a network. Each packet has a **header**, a **payload** and a **trailer**.

![Figure 2 — The three parts of a packet.](figures/networks/fig-02.svg)

*Figure 2 — The three parts of a packet.*

- **Header:** stores where the packet must go and who sent it, plus a sequence number that helps the receiver reassemble the data.
- **Payload:** the actual data being carried.
- **Trailer:** marks the end of the packet and holds error-detection bits so the receiver can check that it arrived intact.

> **A note on real protocols**
>
> The header/payload/trailer model is the standard teaching model. In real protocols the layout varies: an IPv4 packet has a header but no trailer (its error check, the checksum, is inside the header), while an Ethernet frame has a header and a trailer (the frame check sequence). The model is still correct as a general description of how data is wrapped for transmission.

## 3.2 Packet switching

When a photo, video or message is sent, the data is divided into packets. They travel through routers until they reach the destination, where the receiving device puts them back together, like building a puzzle whose pieces were posted separately. Because many devices can send packets at the same time over shared links, the network is used efficiently: one connection does not hog the whole network. This method is called **packet switching**.

![Figure 3 — Packets can take different routes. If a router or link fails, packets are rerouted around the problem.](figures/networks/fig-03.svg)

*Figure 3 — Packets can take different routes. If a router or link fails, packets are rerouted around the problem.*

## 3.3 Worked example — sending a photo

**Scenario:** you send a 3 MB photo to a friend.

| Step | What happens                                                                                                                        |
|------|-------------------------------------------------------------------------------------------------------------------------------------|
| 1    | The photo is divided into small chunks. Each chunk becomes the payload of a packet.                                                 |
| 2    | A header is added to each packet: destination, source and a sequence number (1, 2, 3, ...) so the packets can be put back in order. |
| 3    | A trailer is added to mark the end and help check for errors.                                                                       |
| 4    | The packets are sent. Routers forward each packet along a suitable path; packets may take different routes.                         |
| 5    | The packets arrive, possibly out of order. The receiver reads the sequence numbers and reassembles the payloads in order.           |
| 6    | The photo is displayed. If a packet is missing or damaged, the receiver asks for it to be sent again.                               |

**Why this works:** if the network sent the whole photo as one piece, a single problem could stop everything. With packets, only a small piece is affected and the rest still arrive.

> **Quick review 3 — What are the three parts of a packet and what does each do?**
>
> **Header:** source address, destination address and sequence number. **Payload:** the data being carried. **Trailer:** end marker and error-detection bits.

# 4. Protocols, Layers and Addressing

## 4.1 Protocols

**Protocols** are the rules and standards that devices follow to communicate over a network. They define how data is formatted, transmitted, received and understood. Because devices use different hardware and software, they need common rules: protocols work like a shared language.

| Protocol                            | Purpose                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------|
| TCP (Transmission Control Protocol) | Reliable, ordered delivery of data between two programs.                               |
| UDP (User Datagram Protocol)        | Fast, connectionless delivery with no guarantee; used for live video, voice and games. |
| IP (Internet Protocol)              | Addressing and routing of packets across networks.                                     |
| HTTP / HTTPS                        | Transfer web pages between browsers and servers; HTTPS adds encryption.                |
| FTP                                 | Transfer files between computers.                                                      |
| SMTP, POP3, IMAP                    | Send (SMTP) and receive (POP3, IMAP) email.                                            |
| DHCP                                | Automatically gives a device an IP address when it joins a network.                    |
| DNS                                 | Translates domain names into IP addresses.                                             |
| Ethernet / Wi-Fi                    | Deliver frames between devices on a local network.                                     |

## 4.2 TCP and IP: why both?

> **The difference**
>
> **IP** is *connectionless*: it addresses each packet and routers send it toward its destination, like a postal address on a letter. It does not guarantee delivery or order, so packets can be lost, duplicated or arrive in a different order. **TCP** is *connection-oriented*: it sets up a connection before sending data, numbers the data, detects missing or out-of-order packets, asks for retransmission and puts the data back in order. TCP is layered on top of IP to provide the reliability IP lacks. IP does not cause the jumbling; it simply does not prevent it.

## 4.3 The layered model

Network software is organised in layers, each doing one job and using the layer below. When you send data, each layer adds its own header (the model in Section 3); the receiver removes them in reverse order.

![Figure 4 — The TCP/IP model. A switch works mainly at the link layer; a router at the internet layer.](figures/networks/fig-04.svg)

*Figure 4 — The TCP/IP model. A switch works mainly at the link layer; a router at the internet layer.*

> **Quick review 4 — Why do we need both TCP and IP?**
>
> IP gets packets across networks using addresses but makes no promises. TCP adds reliable, ordered delivery on top. Without IP packets would not find their destination; without TCP the data might arrive incomplete or jumbled.

## 4.4 Identification of devices

### MAC address (Media Access Control)

A **MAC address** is a 48-bit physical identifier assigned by the manufacturer to a Network Interface Card (NIC) and normally fixed for the life of the card (it can be overridden in software). It is usually written as six hexadecimal pairs, for example `00:1A:2B:3C:4D:5E`. It identifies a specific hardware interface so devices on the *same local network* can send data directly to each other.

### IP address (Internet Protocol address)

An **IP address** is a logical address given to a device when it joins a network; it can change when the device joins a different network. It lets data be routed across many interconnected networks.

| Version | Length   | Written as                                                   | Example                                   | Notes                                                 |
|---------|----------|--------------------------------------------------------------|-------------------------------------------|-------------------------------------------------------|
| IPv4    | 32 bits  | Four denary numbers 0–255 separated by dots (dotted decimal) | `93.184.216.34`                           | About 4.3 billion addresses: running out              |
| IPv6    | 128 bits | Eight groups of four hexadecimal digits                      | `2001:0db8:85a3:0000:0000:8a2e:0370:7334` | Vastly larger address space; replacing IPv4 gradually |

|             | MAC address               | IP address                        |
|-------------|---------------------------|-----------------------------------|
| Assigned by | Manufacturer (hardware)   | Network / software (e.g. DHCP)    |
| Size        | 48 bits                   | 32 bits (IPv4) or 128 bits (IPv6) |
| Permanence  | Normally fixed to the NIC | Can change with the network       |
| Used by     | Switches, within one LAN  | Routers, between networks         |
| Analogy     | Your name                 | Your current postal address       |

> **Quick review 5 — MAC vs IP address**
>
> A MAC address is a 48-bit hardware identifier set by the manufacturer and used within a LAN. An IP address is a logical address given to a device by the network and used for routing between networks; it can change when the device moves.

### 4.5 URL and DNS

A **URL (Uniform Resource Locator)** is the address of a resource on the internet. It is divided into: **protocol** (how data is transferred, e.g. HTTP or HTTPS), **subdomain** (an area of a site, `www` being the most common), **domain name** (the human-readable name of the site), **top-level domain** (purpose or country, e.g. .com, .org, .edu, .uk) and optionally a **path** to a page.

![Figure 5 — Anatomy of the URL https://www.bbc.co.uk/news.](figures/networks/fig-05.svg)

*Figure 5 — Anatomy of the URL https://www.bbc.co.uk/news.*

| Part                            | Value | Explanation                             |
|---------------------------------|-------|-----------------------------------------|
| Protocol                        | https | Secure web protocol                     |
| Subdomain                       | www   | World Wide Web                          |
| Domain name                     | bbc   | The organisation                        |
| Second-level domain             | co    | Commercial organisation (UK convention) |
| Top-level domain (country code) | uk    | United Kingdom                          |
| Path                            | /news | The page on the site                    |

Computers route by IP address, not by name, so the **Domain Name System (DNS)** acts as a phone book: your device asks a DNS server for the IP address of the domain, then connects to that address.

> **How DNS works, step by step**
>
> 1\. You type `www.example.com`. 2. Your device checks its own cache; if it has no answer it asks the DNS resolver (usually run by your ISP). 3. The resolver asks other DNS servers until it finds the address. 4. The resolver returns the IP address, e.g. `93.184.216.34`. 5. Your browser opens a connection to that IP address and requests the page.

> **Quick review 6 — How does DNS work?**
>
> DNS translates human-readable domain names into IP addresses. When you type a domain name, a DNS server looks up the matching IP address so your device can contact the right web server.

# 5. Network Topologies

**Network topology** is the physical or logical arrangement of nodes and links in a network. The choice affects performance, scalability, reliability and cost. *Physical* topology is how cables are laid out; *logical* topology is how data actually flows.

![Figure 6 — Six basic topologies (a hybrid is a combination of these).](figures/networks/fig-06.svg)

*Figure 6 — Six basic topologies (a hybrid is a combination of these).*

## 5.1 Bus topology

All devices share a single backbone cable. Collisions are managed by protocols such as **CSMA/CD** (Carrier Sense Multiple Access with Collision Detection): a device listens first, and if two devices transmit together they detect the collision, stop, and retry after a random delay.

> **Advantages**
>
> - Cheapest: least cabling
> - Simple to set up and extend for small networks
> - No central hub or switch needed

> **Disadvantages**
>
> - Backbone break takes the whole network down
> - Performance falls as devices are added (collisions)
> - Hard to locate faults
> - Low security: every device can see all traffic

## 5.2 Point-to-point topology

A dedicated link connects exactly two devices, with no intermediate switches.

> **Advantages**
>
> - Simple to set up and manage
> - All the link's capacity is reserved for the two devices
> - Low latency; private channel, harder to intercept

> **Disadvantages**
>
> - Poor scalability: each extra device needs its own link
> - Single point of failure
> - Cost grows quickly when many sites must be linked

## 5.3 Star topology

Every device connects independently to a central hub, switch or router. This is the most common wired LAN layout today.

> **Advantages**
>
> - A failed cable affects only one device
> - Easy to add or remove devices
> - Easy troubleshooting and central management
> - A switch sends data only to the intended device

> **Disadvantages**
>
> - The central device is a single point of failure
> - More cable than a bus
> - The central device can become a bottleneck

## 5.4 Mesh topology

Each device connects directly to several others. In a **full mesh** of *N* nodes there are N(N−1)/2 links; a **partial mesh** connects only some pairs.

> **Advantages**
>
> - Very fault tolerant: traffic reroutes around a failure
> - No single point of failure
> - High capacity; hard to intercept

> **Disadvantages**
>
> - Expensive: many cables and ports (10 nodes need 45 links)
> - Complex to set up and maintain
> - High power use

## 5.5 Ring topology

Each device connects to exactly two others, forming a closed loop. Data travels one way round, often controlled by a **token** that gives the holder permission to transmit.

> **Advantages**
>
> - No collisions with token passing
> - Every device gets a fair turn
> - Predictable performance; less cable than a star

> **Disadvantages**
>
> - A single break or failed node can stop the ring (unless it is dual-ring)
> - Harder troubleshooting
> - Higher latency as data passes through every node
> - Adding a device can disrupt the network

## 5.6 Hybrid topology

Combines two or more basic topologies, such as stars joined in a ring or a mesh. Most large real networks are hybrids.

> **Advantages**
>
> - Flexible and customisable
> - Faults contained to one segment
> - Redundancy where it matters most
> - Scales by adding segments

> **Disadvantages**
>
> - Expensive hardware
> - Complex design and setup
> - Hard to diagnose across different layouts

![Figure 7 — A hybrid topology.](figures/networks/fig-07.svg)

*Figure 7 — A hybrid topology.*

## 5.7 Tree topology

A hierarchy of root, branch and leaf nodes combining star and bus ideas, like a company or school structure.

> **Advantages**
>
> - Scales by adding branches
> - Faults in one branch stay local
> - Structured and easy to manage in groups

> **Disadvantages**
>
> - Root or top-level failure affects large parts
> - Expensive backbone cabling
> - Higher levels can become bottlenecks

## 5.8 Topology comparison table

| Topology       | Cost            | Reliability       | Scalability              | Key weakness                 |
|----------------|-----------------|-------------------|--------------------------|------------------------------|
| Bus            | Low             | Low               | Low                      | Backbone failure; collisions |
| Point-to-point | Low (2 devices) | Low               | Low                      | Only two devices             |
| Star           | Medium          | High (per device) | High                     | Central device               |
| Ring           | Medium          | Medium            | Medium                   | One break can stop the ring  |
| Mesh           | High            | Very high         | Medium (links grow fast) | Cost and complexity          |
| Tree           | Medium          | Medium            | High                     | Root failure                 |
| Hybrid         | High            | Very high         | Very high                | Complexity                   |

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

![Diagram](figures/networks/fig-13.svg)

Data travels in one direction only. *Examples:* traditional TV broadcast; a keyboard sending input to a computer.

### Half-duplex

![Diagram](figures/networks/fig-14.svg)

Both directions, but not at the same time; the devices take turns. *Example:* walkie-talkies.

### Full-duplex

![Diagram](figures/networks/fig-15.svg)

Both directions at the same time. *Examples:* a telephone conversation; a video call; a switched Ethernet link.

## 6.2 Methods of data transmission

![Figure 8 — Serial and parallel transmission.](figures/networks/fig-08.svg)

*Figure 8 — Serial and parallel transmission.*

**Serial transmission** sends data one bit at a time along a single channel. It is slower per channel but works well over longer distances and needs less cabling. *Examples:* USB, SATA, Ethernet and most modern cables. **Parallel transmission** sends many bits at the same time along multiple channels. It is faster over short distances and matches how computers work inside. An old printer port used a 25-pin connector: 8 data lines, 4 control lines, 5 status lines and 8 grounds.

**Why parallel is not used for long distances:** **skew** (bits arriving at slightly different times because wires differ in length) and **crosstalk** (interference between adjacent wires) make it unreliable. This is why modern fast links are serial.

## 6.3 Synchronous and asynchronous: two related meanings

The words *synchronous* and *asynchronous* are used at two levels. Do not mix them up.

### (a) At the transmission level: how sender and receiver agree on timing

|                  | Synchronous transmission                                                                               | Asynchronous transmission                                                 |
|------------------|--------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| Timing           | Sender and receiver share a **clock signal** (or the clock is recovered from the data)                 | No shared clock                                                           |
| How data is sent | A continuous stream in **blocks / frames**, with synchronisation characters at the start of each block | One **byte at a time**, each framed by a **start bit** and a **stop bit** |
| Gaps             | None within a block                                                                                    | Random gaps between bytes are allowed                                     |
| Overhead         | Low                                                                                                    | Higher (2 extra bits per byte)                                            |
| Speed            | Fast                                                                                                   | Slower                                                                    |
| Typical use      | High-speed links, large transfers                                                                      | Keyboards, serial ports, simple devices                                   |

![Figure 9 — An asynchronous frame carrying one byte.](figures/networks/fig-09.svg)

*Figure 9 — An asynchronous frame carrying one byte.*

### (b) At the communication / processing level: whether the caller waits

In **synchronous communication** (blocking), a client sends a request to a server and waits for the response before continuing; both sides must be active at the same time, like a phone call. In **asynchronous communication** (non-blocking), the client sends the request and carries on with other work; the reply is dealt with when it arrives, like sending a text message that the other person answers whenever they are ready. Asynchronous designs scale better because more work can be done in the same time.

> **Quick review 8 — Synchronous or asynchronous?**
>
> \(a\) Sending a byte with start and stop bits: asynchronous transmission. (b) Two devices sharing a clock and sending a block of data: synchronous transmission. (c) Placing an online order and carrying on browsing while it is processed: asynchronous communication. (d) A phone call where both people must be on the line: synchronous communication.

## 6.4 Bandwidth and latency

**Bandwidth** is the maximum amount of data a link can carry per second (e.g. 100 Mbit/s). **Latency** is the delay for data to travel from sender to receiver (e.g. 20 ms). A link can have high bandwidth but high latency, like a wide road that is very long. Video streaming needs bandwidth; online gaming needs low latency.

> **Worked example — download time**
>
> A 600 MB file is downloaded over a 100 Mbit/s link. 600 MB = 600 × 8 = 4800 Mbit. Time = 4800 / 100 = 48 seconds (ignoring overheads and latency).

> **Quick review 9 — Serial vs parallel; the three types of flow**
>
> **Serial** sends one bit at a time on a single channel, suiting longer distances with less cabling; **parallel** sends many bits at once on multiple channels, faster over short distances only. Flow types: **simplex** (one way), **half-duplex** (both ways, alternating), **full-duplex** (both ways at once).

# 7. Network Architecture

## 7.1 Types of network by size

![Figure 10 — Networks classified by the area they cover.](figures/networks/fig-10.svg)

*Figure 10 — Networks classified by the area they cover.*

### LAN (Local Area Network)

A collection of connected devices in one physical location such as a home or office, covering a single, limited area. A LAN can range from one user at home to thousands of users and devices in an enterprise, and can include wired and wireless devices. Modern wired LANs are **most often built as a star** around a switch, because a failed cable or computer affects only that device and new devices are simply plugged in without taking the network offline.

### WAN (Wide Area Network)

Connects computers and smaller networks over large geographical areas such as different cities, countries or continents. WANs usually rely on telecommunications companies and ISPs to carry data over long distances. Because they need **redundant paths**, WAN backbones are typically a **partial mesh or hybrid**: if an undersea cable is cut, traffic reroutes another way. *Example:* a company with offices in Tokyo, Singapore and London joins them with a WAN. The internet is the best-known WAN, a “network of networks”. Compared with a LAN a WAN usually has more complex infrastructure and is more expensive to maintain.

### MAN (Metropolitan Area Network)

Connects multiple LANs across a city, town or large campus; larger than a LAN but smaller than a WAN. It often uses high-speed fibre-optic links and is commonly laid out as a **fibre ring or a tree** (a central root branching to departments, schools or stations). *Example:* a university with several buildings across a city linking the networks of its library, laboratories and administration.

> **Be careful with “uses”**
>
> The topologies above are what each network type *commonly* uses, not rules. Large networks are almost always hybrids of several topologies. In exams, give the reason with the topology (for example “WAN: mesh, because redundant paths let traffic reroute”).

|                     | LAN                        | MAN                            | WAN                           |
|---------------------|----------------------------|--------------------------------|-------------------------------|
| Area                | Single site                | City or campus                 | Cities, countries, continents |
| Typical owner       | Individual or organisation | Organisation or city authority | Telecoms companies, ISPs      |
| Common topology     | Star                       | Ring / tree                    | Partial mesh / hybrid         |
| Speed               | Very high                  | High                           | Lower, varies                 |
| Cost and complexity | Low                        | Medium                         | High                          |

## 7.2 Network service models

![Figure 11 — Client–server and peer-to-peer models.](figures/networks/fig-11.svg)

*Figure 11 — Client–server and peer-to-peer models.*

### Client–server

A centralised architecture in which a dedicated computer (the **server**) stores data, manages resources and processes requests, while other devices (the **clients**) request and use those services. Roles are fixed. *Examples:* websites (web browser to a web server over HTTP/HTTPS), email (Gmail or Outlook to mail servers), streaming (Netflix to user devices), cloud storage. *Used for:* managing heavy traffic, centralised security and backups, enterprise databases.

### Peer-to-peer (P2P)

A decentralised architecture in which every participant (a **peer**) has equal status and acts as both client and server. Peers share resources directly with each other without a central authority. *Examples:* BitTorrent file sharing, where you download fragments from many other users while uploading fragments to others; two laptops on a home network sharing a file directly.

|                     | Client–server                   | Peer-to-peer                     |
|---------------------|---------------------------------|----------------------------------|
| Control             | Centralised                     | Decentralised                    |
| Roles               | Fixed: client or server         | Every peer is both               |
| Security and backup | Easy to manage centrally        | Harder: each peer is responsible |
| Cost                | Server hardware and admin       | Low                              |
| Failure             | Server failure affects everyone | No single point of failure       |
| Scales with users   | Needs server capacity           | More peers can add capacity      |

> **Quick review 10 — LAN vs WAN; client–server vs P2P**
>
> A LAN covers a single limited area (often a star, cheaper and simpler); a WAN covers large areas (often mesh or hybrid, more complex and costly). In client–server, roles are fixed and a server provides services to clients; in P2P every node is both client and server and no central authority is needed.

# 8. Network Threats and Security

## 8.1 Malware

**Malware** is malicious software designed to infiltrate, damage or gain unauthorised access to systems.

| Malware      | What it is                                                                                   | How it spreads                                          | Countermeasure                                      |
|--------------|----------------------------------------------------------------------------------------------|---------------------------------------------------------|-----------------------------------------------------|
| Virus        | Attaches itself to a host file or program and replicates; corrupts, modifies or deletes data | Needs user action (opening the infected file)           | Antivirus / anti-malware; do not open unknown files |
| Worm         | Standalone program that self-replicates across networks without a host file                  | Exploits network vulnerabilities; no user action needed | Firewall, patches, antivirus                        |
| Trojan horse | Malicious code disguised as useful software; creates backdoors                               | User is tricked into installing it                      | Antivirus, install only trusted software            |
| Spyware      | Secretly monitors activity (keystrokes, screenshots, browsing) and reports it                | Bundled with other software or from malicious sites     | Anti-malware, firewall                              |
| Adware       | Shows unwanted pop-up adverts and may redirect the browser                                   | Bundled with free software                              | Anti-malware, careful installation                  |
| Ransomware   | Encrypts files or locks the drive and demands a ransom for the key                           | Phishing e-mails, malicious downloads                   | Regular offline backups, antivirus, patching        |

## 8.2 Cyberattacks

| Attack                              | Description                                                                                                                             | Defence                                                              |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| Brute-force / dictionary            | Trying every possible password or a list of common words until one works                                                                | Strong passwords, multi-factor authentication (MFA), account lockout |
| Data interception (packet sniffing) | Eavesdropping on data as it travels, using sniffers                                                                                     | Encryption (HTTPS, VPN)                                              |
| DoS / DDoS                          | Flooding a server with requests from one source (DoS) or from a **botnet** of infected computers (DDoS) so it crashes or is unavailable | IDS/IPS, firewalls and rate-limiting, traffic filtering              |
| Hacking / unauthorised access       | Gaining illegal entry to view, delete or change data                                                                                    | Authentication, firewalls, access rights, patching                   |
| Phishing                            | Fraudulent e-mails, SMS (smishing) or calls (vishing) that mimic real organisations to steal data                                       | User awareness training, spam filters, MFA                           |
| Pharming                            | Malicious code or DNS manipulation silently redirects users from a real site to a fake copy                                             | Anti-malware, checking the HTTPS padlock and URL, secure DNS         |
| Social engineering                  | Manipulating trust, fear, curiosity or authority so people break procedures or reveal secrets                                           | Training, verification procedures                                    |

## 8.3 System and network vulnerabilities

| Vulnerability                 | Why it is dangerous                     | Countermeasure                                |
|-------------------------------|-----------------------------------------|-----------------------------------------------|
| Weak or default passwords     | Easily guessed (e.g. 123456, admin)     | Robust password policy, password manager, MFA |
| Unpatched / outdated software | Known flaws remain open                 | Automated patch management                    |
| Misconfigured access rights   | Users have more privilege than needed   | Least-privilege access, regular audits        |
| Removable media               | Infected USB drives bypass the firewall | Disable auto-run, scan media, restrict ports  |

## 8.4 Common types of network security

1.  **Firewall:** monitors and controls incoming and outgoing traffic against rules; blocks unauthorised connections. It also blocks malware from sending data out.
2.  **Encryption:** converts readable *plaintext* into *ciphertext* so unauthorised people cannot understand it; HTTPS uses it to protect web traffic.
3.  **Antivirus / anti-malware:** detects, quarantines and removes malicious programs using signatures and behaviour analysis.
4.  **Authentication:** verifies identity before granting access: passwords, fingerprints, multi-factor authentication.
5.  **VPN (Virtual Private Network):** an encrypted tunnel between a device and a VPN endpoint, protecting data across untrusted networks.
6.  **IDS / IPS:** an intrusion detection system detects and reports suspicious traffic; an intrusion prevention system can also block it.

## 8.5 How encryption works

**Symmetric encryption** uses the same key to encrypt and decrypt: it is fast but the key must be shared securely. **Asymmetric encryption** uses a pair of keys: a **public key** (shared openly) encrypts and the matching **private key** (kept secret) decrypts; it solves the key-sharing problem but is slower. **HTTPS** uses both: the browser and server use asymmetric encryption to agree a symmetric *session key*, then switch to the faster symmetric encryption for the data (this is part of the TLS protocol).

> **Worked example — a Caesar cipher (symmetric)**
>
> Key = shift by 3. Plaintext `NETWORK` becomes ciphertext `QHWZRUN` (N→Q, E→H, T→W, W→Z, O→R, R→U, K→N). The same key (3) is used backwards to decrypt. Real encryption such as AES works the same way in principle but is vastly stronger.

## 8.6 Threat–countermeasure mapping

| Threat                       | Countermeasure                             | How it works                                                               |
|------------------------------|--------------------------------------------|----------------------------------------------------------------------------|
| Virus, worm, Trojan, spyware | Antivirus / anti-malware                   | Scans files and memory to detect, quarantine and remove malicious software |
| Ransomware                   | Regular backups (and antivirus)            | Allows recovery of encrypted files without paying                          |
| Brute-force attack           | MFA and account lockout                    | Requires a second check; locks the account after repeated failures         |
| Data interception            | Encryption (HTTPS) and VPN                 | Eavesdroppers see only unreadable ciphertext                               |
| DoS / DDoS                   | IDS/IPS and firewall rate-limiting         | Detects abnormal floods and filters or limits them                         |
| Phishing / pharming          | User awareness training and authentication | Teaches users to recognise fakes; verifies identity                        |
| Weak or default passwords    | Robust password policy                     | Minimum length, complexity, no factory defaults                            |
| Unpatched software           | Automated patch management                 | Updates fix known vulnerabilities before attackers exploit them            |

> **Quick review 11 — Malware and attacks**
>
> Three malware types with a countermeasure: virus (antivirus), worm (firewall and antivirus), ransomware (backups and antivirus). Two attacks with a defence: brute force (MFA and lockout), packet sniffing (encryption, VPN). Also: DDoS (IDS/IPS), phishing (awareness training and authentication).

# 9. Worked Examples

> **Worked example 1 — tracing a packet**
>
> **Scenario:** a 1 MB message is sent from your laptop to a web server and the network splits it into 100 packets.
>
> | Step | What happens                                                                                                                   | Key concept       |
> |------|--------------------------------------------------------------------------------------------------------------------------------|-------------------|
> | 1    | The message is divided into 100 packets; each header holds source IP, destination IP and sequence number (1–100)               | Packetisation     |
> | 2    | A trailer is added to each packet for error checking                                                                           | Error detection   |
> | 3    | The laptop sends the packets to your router, which reads the destination IP in each header and forwards it toward the internet | Routing           |
> | 4    | Packets cross several routers; some take faster routes and arrive out of order                                                 | Packet switching  |
> | 5    | The server uses the sequence numbers to reassemble the data in order                                                           | Reassembly        |
> | 6    | If a packet is lost, TCP detects the gap and requests retransmission                                                           | Reliability (TCP) |

> **Worked example 2 — choosing a topology**
>
> **Scenario:** a small business with 10 employees and a limited budget needs a network where one broken cable does not stop everyone working.
>
> | Consideration  | Analysis                                  | Decision                                                       |
> |----------------|-------------------------------------------|----------------------------------------------------------------|
> | Budget         | Limited                                   | Star uses more cable than bus but is affordable for 10 devices |
> | Reliability    | One broken cable must not affect everyone | Star isolates failures to individual devices                   |
> | Scalability    | More staff may join                       | Star makes it easy to add devices                              |
> | Recommendation | Star topology                             | Best balance of cost, reliability and scalability              |

> **Worked example 3 — breaking down a URL**
>
> URL: `https://www.bbc.co.uk/news`. Protocol: https. Subdomain: www. Domain name: bbc. Second-level domain: co. Top-level (country) domain: uk. Path: /news.

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
> A university is building a campus network connecting five buildings across a city. If one building's connection fails, the others must keep working. Which topology would you recommend and why?

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
> \(1\) Simplex. (2) Full-duplex. (3) Half-duplex. (4) Simplex. (5) Full-duplex.

> **Activity 6 — Choose the transmission method**
>
> State serial or parallel and why: (1) a keyboard on a 2 m USB cable, (2) data between two buildings 500 m apart, (3) an older printer on a 25-pin cable.

> **Expected outcome**
>
> \(1\) Serial: USB is serial and works well with fewer wires. (2) Serial: parallel suffers skew and crosstalk over long distances. (3) Parallel: older printer cables used parallel over short distances.

> **Activity 7 — Synchronous or asynchronous?**
>
> Decide the type and give a reason: (1) a keyboard sending a byte with a start and stop bit, (2) a high-speed link sending a block of data with a shared clock, (3) a web page that loads comments in the background while you keep reading.

> **Expected outcome**
>
> \(1\) Asynchronous transmission: start and stop bits, no shared clock. (2) Synchronous transmission: shared clock, block of data. (3) Asynchronous communication: the browser does not wait (non-blocking).

> **Activity 8 — Spot the errors**
>
> A student writes: “IP guarantees that packets arrive in order. A switch sends data using IP addresses. A MAC address changes every time you join Wi-Fi.” Correct all three statements.

> **Expected outcome**
>
> IP does not guarantee order; TCP provides ordered, reliable delivery. A switch uses MAC addresses; a router uses IP addresses. A MAC address is normally fixed to the NIC; the IP address changes when you join a network.

# 11. Mind Map and Summary

![Figure 12 — Mind map of the Networks module.](figures/networks/fig-12.svg)

*Figure 12 — Mind map of the Networks module.*

| Section         | Key idea to remember                                                     |
|-----------------|--------------------------------------------------------------------------|
| Network         | Devices + links + protocols that exchange data and share resources       |
| Packet          | Header (who, where, order) + payload (data) + trailer (end, error check) |
| TCP / IP        | IP routes packets; TCP makes delivery reliable and ordered               |
| MAC / IP        | MAC = hardware, used in a LAN; IP = logical, used between networks       |
| Topology        | Arrangement of nodes and links; star is the default for LANs             |
| Data flow       | Simplex, half-duplex, full-duplex                                        |
| Transmission    | Serial vs parallel; synchronous vs asynchronous                          |
| LAN / MAN / WAN | Area covered: single site, city, wide area                               |
| Security        | Know each threat and its matching countermeasure                         |

# 12. Case Studies

> **Case study 1 — “The school Wi-Fi is down”**
>
> A school has a star network: 40 classroom computers connect to a switch in each of four corridors; the four switches connect to one central switch, which connects to a router and the internet. On Monday the whole of corridor B loses access, but the other corridors work.
>
> **Tasks:** (a) name the topology of the whole school network, (b) say where the fault probably lies, (c) say what would happen if the central switch failed, and (d) suggest an improvement.

> **Model answer**
>
> \(a\) A **tree/hybrid** of stars (star within each corridor, stars joined to a central switch). (b) Corridor B's switch, or its link to the central switch, because only that branch is affected. (c) Everything would lose connection to each other and to the internet: the central switch is a single point of failure. (d) Add a second link or a second central switch (redundancy), moving toward a partial mesh between the switches.

> **Case study 2 — a phishing e-mail**
>
> An employee receives an e-mail that appears to come from the company's bank, asking her to click a link and confirm her password. The link text shows the real bank name, but hovering shows `http://secure-bank-login.example-site.com`.
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
> Both matter, but streaming needs enough **bandwidth** for the video bitrate and low, steady latency for liveness. **UDP** is often used for live video because a slightly late packet is better dropped than waiting for TCP retransmission, though many services use TCP-based protocols with buffering. The stream is **client–server**: a few servers (often many copies spread around the world) serve thousands of clients. A DDoS attack would be a serious risk, so IDS/IPS and traffic filtering are important.

# 13. Review Questions with Answers

Question 1. What is the difference between TCP and IP?

> **Answer:** TCP is a connection-oriented protocol that ensures reliable, in-order delivery. IP is a connectionless protocol that handles addressing and routing. TCP is layered on top of IP to provide the reliability IP lacks.

Question 2. What is the difference between a router and a switch?

> **Answer:** A router connects different networks and forwards data between them using destination IP addresses. A switch connects devices within a LAN and forwards data to the intended device using MAC addresses.

Question 3. What is the difference between a virus and a worm?

> **Answer:** A virus attaches to a host file and needs user action to spread. A worm is standalone, self-replicates and spreads across networks without a host file or user action.

Question 4. What is the difference between phishing and pharming?

> **Answer:** Phishing sends fraudulent messages that trick users into revealing information; it relies on user action. Pharming silently redirects users from legitimate websites to fake copies, for example by manipulating DNS.

Question 5. Which topology would you recommend for a school computer lab, and why?

> **Answer:** Star: each computer connects to a central switch, so one failed cable or computer only affects that node, and computers are easy to add or remove.

Question 6. Why is packet switching efficient?

> **Answer:** Data is split into small packets that can use any available route; many devices can send at the same time; if a router or link fails, packets reroute.

Question 7. What is the difference between symmetric and asymmetric encryption?

> **Answer:** Symmetric uses one shared key for encryption and decryption (fast). Asymmetric uses a public key to encrypt and a private key to decrypt (solves key sharing but slower). HTTPS uses asymmetric encryption to exchange a symmetric session key, then symmetric encryption for the data.

Question 8. What is the difference between a LAN and a WAN?

> **Answer:** A LAN connects devices in a single limited area such as a home or office. A WAN connects networks over large geographical areas such as cities or countries.

Question 9. What is the difference between client–server and peer-to-peer?

> **Answer:** In client–server, a server provides resources and clients use them (fixed roles, centralised). In P2P every node has equal status and acts as both client and server (decentralised).

Question 10. Name the three network types and the topology each commonly uses, with a reason.

> **Answer:** LAN: star (isolates failures, easy to expand). WAN: mesh or hybrid (redundant paths so traffic reroutes). MAN: ring or tree (a fibre ring or a hierarchy from a central root to departments across a city).

Question 11. What are the three parts of a packet?

> **Answer:** Header (source, destination, sequence number), payload (the data), trailer (end marker and error-check bits).

Question 12. What is the difference between a MAC address and an IP address?

> **Answer:** A MAC address is a 48-bit hardware identifier assigned by the manufacturer, normally fixed. An IP address is a logical address given by the network that can change.

Question 13. What is a URL and what are its main parts?

> **Answer:** The address of a resource on the internet: protocol, subdomain, domain name, top-level domain and path.

Question 14. What are the three types of data flow?

> **Answer:** Simplex (one direction), half-duplex (both directions, alternating), full-duplex (both directions at once).

Question 15. What is the difference between serial and parallel transmission?

> **Answer:** Serial: one bit at a time on one channel; suits long distances and needs less cabling. Parallel: many bits at once on many channels; faster but only for short distances because of skew and crosstalk.

Question 16. Distinguish synchronous and asynchronous transmission.

> **Answer:** Synchronous: sender and receiver share a clock and data is sent in continuous blocks. Asynchronous: no shared clock; each byte is framed by a start bit and a stop bit, with gaps allowed.

Question 17. What is a DDoS attack and how can it be defended against?

> **Answer:** A flood of requests from a botnet of infected computers overwhelms a server so it crashes or becomes unavailable. Defence: IDS/IPS and firewalls that identify abnormal floods and filter or rate-limit them.

Question 18. What is social engineering?

> **Answer:** Manipulating human psychology (trust, fear, curiosity, authority) to persuade people to break security procedures or reveal confidential information. It targets people, not technical systems.

Question 19. Why is encryption important for network security?

> **Answer:** It converts readable data into ciphertext so eavesdroppers who capture packets see only unreadable data; HTTPS and VPNs use it to protect data in transit.

Question 20. Name three topologies with one advantage and one disadvantage of each.

> **Answer:** Star: isolated failures / central device is a single point of failure. Bus: cheap, least cabling / backbone break stops everything. Mesh: fault tolerant / expensive and complex.

# 14. End-of-Module Test

Total: 49 marks. Suggested time: 45 minutes. Attempt without notes, then mark yourself against the answers.

## Questions

1.  Define a computer network and name its three defining elements. \[3\]
2.  State the function of a switch and the address it uses. \[2\]
3.  A 2.4 MB file is split into packets carrying 1200 bytes of payload each. Using 1 MB = 1 000 000 bytes, how many packets are needed? \[2\]
4.  State two items stored in a packet header. \[2\]
5.  Explain why TCP is used on top of IP. \[2\]
6.  Give the number of bits in a MAC address, an IPv4 address and an IPv6 address. \[3\]
7.  Explain the role of DNS. \[2\]
8.  Identify the protocol, domain name and path in `https://learn.example.edu/course/net`. \[3\]
9.  A full mesh connects 12 nodes. How many links does it need? \[2\]
10. Give one advantage and one disadvantage of a bus topology. \[2\]
11. State the type of data flow for: (a) radio broadcast, (b) walkie-talkie, (c) video call. \[3\]
12. Why is parallel transmission unsuitable over long distances? \[2\]
13. An asynchronous system sends 8-bit characters with 1 start bit and 1 stop bit. Calculate the efficiency. \[2\]
14. Distinguish a LAN from a WAN. \[2\]
15. State two differences between client–server and peer-to-peer networks. \[2\]
16. Describe how ransomware works and one countermeasure. \[3\]
17. Explain how a firewall protects a network. \[2\]
18. Explain how HTTPS uses both symmetric and asymmetric encryption. \[3\]
19. Download time: a 450 MB file on a 90 Mbit/s link. Calculate in seconds. \[3\]
20. Recommend a topology for a hospital linking 6 critical buildings so that no single failure isolates a building. Justify. \[4\]

## Mark scheme

| \#  | Answer                                                                                                                                       |
|-----|----------------------------------------------------------------------------------------------------------------------------------------------|
| 1   | Two or more devices connected to share data and resources; hardware (nodes), media/links, protocols.                                         |
| 2   | Forwards data only to the intended device within a LAN; MAC address.                                                                         |
| 3   | 2 400 000 / 1200 = 2000 packets.                                                                                                             |
| 4   | Any two of source address, destination address, sequence number.                                                                             |
| 5   | IP gives no guarantee of delivery or order; TCP adds retransmission and reordering for reliable delivery.                                    |
| 6   | 48; 32; 128.                                                                                                                                 |
| 7   | Translates a domain name into the IP address of the server so a connection can be made.                                                      |
| 8   | https; example (with learn as subdomain, .edu TLD); /course/net.                                                                             |
| 9   | 12 × 11 / 2 = 66.                                                                                                                            |
| 10  | Advantage: cheap/least cabling. Disadvantage: one backbone break stops the network (or collisions).                                          |
| 11  | Simplex; half-duplex; full-duplex.                                                                                                           |
| 12  | Skew and crosstalk make bits arrive at different times and corrupt each other.                                                               |
| 13  | 8 / 10 = 80%.                                                                                                                                |
| 14  | LAN: single limited area such as a building; WAN: large geographical areas such as countries.                                                |
| 15  | Any two: centralised vs decentralised; fixed vs equal roles; server cost vs low cost; central security vs per-peer.                          |
| 16  | Encrypts or locks files and demands payment; countermeasure: regular offline backups (or antivirus).                                         |
| 17  | Monitors incoming and outgoing traffic against rules and blocks unauthorised connections.                                                    |
| 18  | Asymmetric encryption exchanges a session key securely; symmetric encryption with that key protects the data because it is faster.           |
| 19  | 450 × 8 = 3600 Mbit; 3600 / 90 = 40 s.                                                                                                       |
| 20  | Mesh (or partial mesh/hybrid): multiple paths mean traffic reroutes after a failure; no single point of failure (accept cost as a drawback). |

# 15. Learning Material List

Suggested resources. Titles are given so you can find them; check each is current before relying on it.

| Resource                                                                                      | Type         | Use it for                                                |
|-----------------------------------------------------------------------------------------------|--------------|-----------------------------------------------------------|
| Watson & Williams, *Cambridge IGCSE and O Level Computer Science* (Hodder Education)          | Textbook     | Core network content: protocols, topologies, security     |
| Watson & Williams, *Cambridge International AS & A Level Computer Science* (Hodder Education) | Textbook     | Protocols, packet switching, security at A Level          |
| Kurose & Ross, *Computer Networking: A Top-Down Approach*                                     | Textbook     | Deeper treatment of layers, TCP/IP, DNS (beyond syllabus) |
| Cloudflare Learning Center (cloudflare.com/learning)                                          | Web articles | Short explainers on DNS, DDoS, HTTPS, firewalls           |
| Cisco Networking Academy, *Networking Basics*                                                 | Course       | Hands-on introduction to LANs, switches and routers       |
| Computerphile (YouTube)                                                                       | Video        | Short talks on TCP, encryption and the internet           |
| Cisco Packet Tracer (free simulator)                                                          | Software     | Build and test a star or hybrid network without hardware  |
| Wireshark (free packet analyser)                                                              | Software     | See real packet headers; compare with the teaching model  |
| RFC 791 (IP), RFC 793 (TCP), RFC 1035 (DNS)                                                   | Standards    | Primary sources on the protocols                          |

# 16. Glossary

| Term                          | Definition                                                                                                         |
|-------------------------------|--------------------------------------------------------------------------------------------------------------------|
| **Asynchronous transmission** | Data sent one byte at a time, each framed by a start and stop bit, with no shared clock.                           |
| **Bandwidth**                 | Maximum data a link can carry per second.                                                                          |
| **Botnet**                    | A network of compromised computers controlled remotely by an attacker.                                             |
| **Ciphertext**                | Encrypted data, unreadable without the key.                                                                        |
| **Client–server**             | A centralised model where a server provides resources and clients use them.                                        |
| **Crosstalk**                 | Interference between adjacent wires in parallel transmission.                                                      |
| **CSMA/CD**                   | Carrier Sense Multiple Access with Collision Detection: a method used on bus/shared Ethernet to manage collisions. |
| **DHCP**                      | Protocol that automatically assigns IP addresses.                                                                  |
| **DNS**                       | System that translates domain names into IP addresses.                                                             |
| **Encryption**                | Converting plaintext into ciphertext so unauthorised users cannot understand it.                                   |
| **Header**                    | Part of a packet holding control information such as source, destination and sequence number.                      |
| **IP address**                | Logical address given to a device when it joins a network.                                                         |
| **Latency**                   | Delay for data to travel from sender to receiver.                                                                  |
| **LAN**                       | Local Area Network: devices in a single limited area.                                                              |
| **Link**                      | The wired or wireless pathway connecting nodes.                                                                    |
| **MAC address**               | Unique 48-bit hardware identifier of a NIC.                                                                        |
| **MAN**                       | Metropolitan Area Network: LANs across a city or large campus.                                                     |
| **Malware**                   | Malicious software designed to infiltrate, damage or gain unauthorised access.                                     |
| **NIC**                       | Network Interface Card: connects a device to a network.                                                            |
| **Node**                      | Any device connected to a network.                                                                                 |
| **Packet**                    | A small chunk of data with a header, payload and (in the teaching model) a trailer.                                |
| **Packet switching**          | Breaking data into packets, sending them along available routes and reassembling them.                             |
| **Payload**                   | The actual data carried by a packet.                                                                               |
| **Peer-to-peer**              | A decentralised model where each node is both client and server.                                                   |
| **Pharming**                  | Redirecting users from legitimate sites to fake copies.                                                            |
| **Phishing**                  | Social-engineering attack tricking users into revealing sensitive information.                                     |
| **Protocol**                  | Rules and standards that devices follow to communicate.                                                            |
| **Router**                    | Connects different networks and forwards data using IP addresses.                                                  |
| **Skew**                      | Bits arriving at different times in parallel transmission.                                                         |
| **Switch**                    | Connects devices within a LAN and forwards data using MAC addresses.                                               |
| **Synchronous transmission**  | Sender and receiver share a clock; data sent in continuous blocks.                                                 |
| **TCP**                       | Connection-oriented protocol giving reliable, in-order delivery.                                                   |
| **Topology**                  | Physical or logical arrangement of nodes and links.                                                                |
| **Trailer**                   | Part of a packet marking its end and carrying error-check bits. (IPv4 has no trailer; Ethernet frames do.)         |
| **UDP**                       | Connectionless, fast transport protocol with no delivery guarantee.                                                |
| **Unicast**                   | Data sent from one device to one specific destination device.                                                      |
| **URL**                       | The address of a resource on the internet.                                                                         |
| **WAN**                       | Wide Area Network: networks over large geographical areas.                                                         |

## 17. References

1.  Watson, D. and Williams, H. *Cambridge IGCSE and O Level Computer Science*. Hodder Education.
2.  Watson, D. and Williams, H. *Cambridge International AS & A Level Computer Science*. Hodder Education.
3.  Kurose, J. F. and Ross, K. W. *Computer Networking: A Top-Down Approach*. Pearson.
4.  Postel, J. (1981). RFC 791: Internet Protocol. IETF.
5.  Postel, J. (1981). RFC 793: Transmission Control Protocol. IETF.
6.  Mockapetris, P. (1987). RFC 1035: Domain Names – Implementation and Specification. IETF.
7.  Cloudflare Learning Center, articles on DNS, DDoS attacks and HTTPS. cloudflare.com/learning.
8.  Cisco Networking Academy, *Networking Basics* course materials.

Revision notes (v2.0): removed project-management sections and inline citation tags from the learner text; replaced missing diagrams with drawn figures; made every quick-review box distinct; corrected the glossary note on trailers; clarified TCP versus IP; described LAN/WAN/MAN topologies as “commonly” used; rewrote synchronous versus asynchronous at both the transmission and communication levels; added UDP, DHCP, the TCP/IP layers, bandwidth and latency; added mind map, case studies, end-of-module test and learning material list; replaced patent and generic-website references with textbooks and standards. Please check the reference list against your assignment's citation requirements before submission.
