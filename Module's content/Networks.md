# ***<h1 align="center">Networks</h1>***
##### ***<h1 align="center">Source:AI and computer science textbook second edition IGCSE&O level second edition and computer science textbook AS&A level(Both textbooks by David Watson and Helen Williams)</h1>***

### ***Network definition***
#### **A network is like a group of friends sharing ideas. A computer network is simply two or more devices—such as phones, laptops, or printers—connected together so they can share information and resources.Devices talk to each other using physical cables or wireless signals like Wi-Fi. Networks can be small, like the setup in your home, or huge, connecting devices across different countries. Every time you send a message, share a photo, or browse the web, you are using a network.In the end, networks make communicating and working together much faster. They also save time and resources by letting multiple devices share the same internet connection, printer, or files with ease.**

### ***Components of the network***
 - #### ***1) Nodes(devices)***
 - - #### *Node are any device connected to a network capable of sending, receiving, or processing data (e.g., laptops, phones, printers, servers).*
 - - #### *Key Function: Enables devices to exchange information and share resources over a network.*
 - - #### *Example: In a home Wi-Fi setup, your phone, laptop, and printer are all individual nodes interacting with one another.*

 - #### ***2) Links(Connections)***
 - - #### *Links are the connections that allow devices in a network to communicate with one another. These connections can be wired or wireless, depending on the type of network and the devices being used.*
 - - #### *Types of links:*
 - - - #### *Wired links use physical cables, such as Ethernet cables, to transfer data between devices.*
 - - - #### *Wireless links use signals, such as Wi-Fi or Bluetooth, to send information without needing a physical cable.*
  - - #### *Key Function: It provides the physical or wireless pathway that allows devices to exchange information. Without links, network communication is impossible, and your devices would be completely isolated on separate islands.*
 - - #### *Example: when you connect your laptop to a router using an Ethernet cable, the cable acts as a link. When you connect your phone to the same router through Wi-Fi, the wireless connection acts as a link. Without links, devices would not be able to exchange information.*

 - #### ***3) Routers***
 - - #### *Routers are networking devices that connect different networks and forward data between them, they examine information in data packets.They are commonly used in homes, schools, offices, and large organizations.*
 - - #### *Key Function: Examines information inside data packets, such as destination IP addresses, to determine where the data should go next and selects an appropriate path across the network.*
 - - #### *Example: When you open a website on your phone, your home router forwards your request from your home network toward the internet. When the website sends information back, the router helps deliver the data to your device.*

 - #### ***4) Switches***
 - - #### *Switches are networking devices that connect multiple devices within a local area network (LAN)[This will be further explained later at the bottom]. They are commonly used in offices, schools, and other places where many devices need to communicate within the same local network.*
 - - #### *Key Function: Directs data specifically to the intended device rather than sending it unnecessarily to every connected device. It uses MAC addresses[It wil explained at the bottom as well] to identify devices on a local network, checking the destination MAC address and forwarding the data through the appropriate port.*
 - - #### *Example: In a school computer lab, when one computer sends a document to a network printer connected to the same switch, the switch forwards the data directly toward the printer.*

### ***Packets***
<img width="738" height="237" alt="image-1" src="https://github.com/user-attachments/assets/06815940-666a-479b-b6ba-5bd465a1e12d" />

#### *In networks, a packet is a small part of a larger piece of information that is sent over the internet. Each packet contains the a header, payload, and a trailer, which includes important details about the data, The header stores where it needs to go and who sent it. The header also helps the receiving device understand how to rearrange the packet back together. The payload is the place where the actual infromation is stored within the packet.This is to tell that all packets have been sent.When we send information over the internet, such as a photo, video, or message, the data is divided into smaller packets. These packets travel through network devices like routers and switches until they reach their destination. Once they arrive, the receiving device puts the packets back together so the information can be viewed or used. This process is similar to building a puzzle, where each piece is sent separately and then joined together to complete the picture.Sending data in packets also makes the internet more efficient because many devices can send and receive information at the same time. This method is called packet switching. Instead of one connection taking up the whole network, packets can travel through available routes, allowing many people to use the internet simultaneously.*

<img width="666" height="395" alt="image-3" src="https://github.com/user-attachments/assets/cd4b78e7-9c64-459c-b848-25866e2cfe69" />

#### *This picture shows the available paths where the packets will go and they will seperate to different routes since if a router or link fails, packets can automatically reroute around the problem so that the packets won't get lost and never received*


### ***Protocol and Addressing***
 - #### ***Protocols***
 - - #### *Protocols are the rules and standards that devices follow to communicate with one another over a network. They define how data is formatted, transmitted, received, and understood by different devices.Since different devices may use different hardware and software, they need to follow common rules so they can understand the information being exchanged. Protocols work like a common language that helps devices communicate correctly.Without protocols, devices might not understand the information sent by other devices. Protocols help ensure that communication happens in an organized and reliable way.*
 - - #### **Some common network protocols include:**
 - - - #### *TCP(Transmission Control Protocol):It helps ensure data arrives reliably and in the correct order so that the information is delivered accurately*
 - - - #### *IP: is the identity of the devices that will send information or receive them it acts similar to a mailbox where the router is the one who leads it to its proper destination at the most efficient route but that will sometimes cause the information to be jumbled up or mismatched that is why TCP is used*
 - - - #### *HTTP/HTTPS: Protocols used to transfer website information between web browsers and web servers. HTTPS also encrypts the connection to ensure it is secure.*
 - - - #### *FTP: A protocol used to transfer files between computers over a network.*
 - - - #### *DNS: A system that translates domain names, such as google.com, into IP addresses that computers use to locate servers.*
 - - - #### *Ethernet:It connects computers, routers, and other devices to build a local area network (LAN) and link them to the internet.*
 - - #### *For example, when you visit a website, DNS helps your device find the website's server, while TCP/IP helps move data between your device and that server.In conclusion, packets divide information into smaller pieces so it can be sent efficiently, while protocols provide the rules that allow devices to communicate and understand the data they receive. Both are important for making the internet work properly.*

 - ### ***Method of Identification within devices***
 - #### ***1) MAC Address(Media Access Control)***
 - - #### *MAC Address is a unique, hardcoded **48-bit** physical identifier burned into a Network Interface Card (NIC) by the hardware manufacturer.*
 - - #### *Key Function: Identifies a specific hardware interface so that devices connected to the same local network segment can send data directly to each other.*
 - - #### *Example: 00:1A:2B:3C:4D:5E(A MAC address is decided by the network hardware manufacturer during production or by a network administrator using software settings)*
 - #### ***2) IP Address (Internet Protocol Address)***
 - - #### *IP Address A software-assigned numerical label given to a device whenever it connects to a network*
 - - #### *Types of IP address:*
  - - - #### *IPv4(Internet Protocol version 4):It is the original and widely used version of the Internet Protocol and it has a **Address Length of 32 bits e.g. 93.184.216.34  written in denary***
  - - - #### *IPv6(Internet Protocol version 6):The newer version of the Internet Protocol designed to permanently replace IPv4 and it has a **Address Length of 128 bits e.g. 2001:0db8:85a3:0000:0000:8a2e:0370:7334 written in hexadecimal***
 - - #### *Key Function: Enables data to be routed across multiple interconnected networks, guiding packets from a source device across the global internet to a destination device.*
 - - ##### *While IPv4 offers widespread compatibility and mature deployment, its major disadvantage compared to IPv6 is its severely limited address space and lack of native security features.*

 - ### ***URL***
 - - #### *URL is the address of a source on the internet. URL is divided into several main parts like protocols,subdomains, domain names and Top-Level Domain.*
<img width="738" height="414" alt="images" src="https://github.com/user-attachments/assets/9e4d2275-3699-430f-9aa2-427a474ec29c" />

 - - - #### *Protocol:It determines how the data is transferred through the URL and the most used are HTTP for regular web and HTTPS for a more secure connection*
 - - - #### *Subdomain:It is used to identify each area of the website and www is the most commonly used where www stands for world wide web*
 - - - #### *Domain Names:The unique, human-readable name of a specific website. It acts as an easy-to-remember alias for a complex numerical IP address*
 - - - #### *Top-Level Domain: It categorizes the website by its purpose, industry, or geographic location.e.g.: .com(commercial), .org(organizations) , .edu(education), .uk(united kingdom)*


### ***Network Topologies***
 - #### **1) Bus Topology**


 - - #### *To allow multiple devices to communicate with each other over a single, shared physical medium without needing a complex web of individual wires.* 
 - - #### *Pros (Advantages)*
 - - - #### *Cost-Effective: Requires the least amount of cabling compared to star or mesh topologies.*
 - - - #### *Simple Design: Very straightforward to set up, understand, and connect new devices to for small networks.*
 - - - #### *No Extra Power Needed: The passive backbone does not require a central hub, switch, or router to function.*
 - - - #### *Easy Extension:Adding more nodes is simple by tapping into the main line (as long as network limits aren't exceeded)*
 - - #### *Cons (Disadvantages)*
 - - - #### *Single Point of Failure: If the main backbone cable breaks or gets damaged anywhere along the line, the entire network goes down.*
 - - - #### *Poor Scalability: Performance drops quickly as more devices are added due to increased data traffic and collisions.*
 - - - #### *High Collision Rate: Because all devices share the same wire, simultaneous data transmissions collide and require re-transmission (managed via protocols like CSMA/CD).*
 - - - #### *Difficult Troubleshooting: Finding a break, loose tap, or faulty terminator along a long cable run is hard and time-consuming.*
 - - - #### *Low Security: Because every packet is broadcast to every node, any computer on the bus can potentially sniff or intercept traffic.*


 - #### **2) Point-To-Point**


  - - #### *A point-to-point topology is the simplest form of network architecture where a dedicated communication link directly connects two devices (nodes) to each other without any intermediate switches or hubs.* 
 - - #### *Pros (Advantages)*
 - - - #### *Simplicity: Easy to set up, configure, and manage because it only involves two endpoints.* 
 - - - #### *High Performance & Bandwidth: The entire capacity and speed of the link are reserved exclusively for the two connected devices without sharing or congestion from other nodes.* 
 - - - #### *Low Latency: Data travels straight from the source to the destination with no routing delays.* 
 - - - #### *Enhanced Security: Data moves across a private, isolated channel, reducing the risk of interception or unauthorized sniffing compared to shared media.* 
 - - - #### *Low Initial Hardware Cost: For a single pair of devices, minimal hardware and cabling are required.*
*
 - - #### *Cons (Disadvantages)*
 - - - #### *Poor Scalability: Adding more devices is difficult and expensive, as every new node requires its own dedicated physical or logical link.* 
 - - - #### *Single Point of Failure: If the single connecting cable or link fails, all communication between the two devices stops completely.* 
 - - - #### *High Cost at Scale: Connecting multiple locations or devices requires a separate dedicated line (such as a leased line) for each pair, which becomes very costly.* 
 - - - #### *Limited Flexibility: The architecture is strictly locked to two endpoints, making it unsuited for multi-user local area networks (LANs).* 
 - - - #### *Higher Maintenance Overhead: Managing multiple independent point-to-point connections across a larger environment increases administrative and troubleshooting complexity.*
*


  - #### **3) Star Topology**


  - - #### *A star topology is a computer network setup where every node (device) connects independently to a central device, such as a hub, switch, or router* 
 - - #### *Pros (Advantages)*
 - - - #### *Isolated failures: If one cable or device breaks, only that specific node goes down while the rest of the network keeps working normally.* 
 - - - #### *Easy scalability: You can add or remove devices easily just by plugging them into or unplugging them from the central switch.* 
 - - - #### *Simple troubleshooting: Finding a broken connection is straightforward because every device has its own dedicated line leading back to the center.* 
 - - - #### *Better performance: Using a modern switch allows unicast data flow, reducing data collisions and keeping speeds high compared to older shared-media layouts like bus topologies.*
 - - - #### *Centralized management: Network administrators can easily monitor traffic, spot issues, and manage devices from the central hub.*
 - - #### *Cons (Disadvantages)*
 - - - #### *Single point of failure: If the central hub, switch, or router stops working, the entire network goes down.* 
 - - - #### *Higher cabling cost: Running a separate cable from every single device to a central location requires more wire and installation effort than a linear bus layout.* 
 - - - #### *Hub/switch bottlenecks: Heavy network traffic passing through the central device can cause slowdowns if the hardware lacks the capacity to handle it.* 
 - - - #### *Hardware dependency: The overall performance and maximum capacity of the network are completely limited by the specs and reliability of the central device.* 



  - #### **4) Mesh Topology**


  - - #### *Mesh topology is a network design where devices, called nodes, connect directly to multiple other nodes without relying on a single central hub.* 
 - - #### *Pros (Advantages)*
 - - - #### *High Fault Tolerance: If a single node or cable fails, data automatically reroutes through alternative paths without bringing down the network.*
 - - - #### *No Single Point of Failure: The lack of a central hub means a localized breakdown does not compromise the entire system.*
 - - - #### *High Traffic Handling: Dedicated and simultaneous data paths reduce congestion and support heavy data loads.*
 - - - #### *Scalability: You can add new devices or nodes to the network without disrupting existing communication.*
 - - - #### *Improved Security and Privacy: Direct point-to-point or encrypted multi-path links make data harder to intercept or compromise.*
*
 - - #### *Cons (Disadvantages)*
 - - - #### *High Cost: A full mesh requires an extensive number of cables, ports, and hardware components (N(N-1)/2 connections for N nodes), making it expensive to build.* 
 - - - #### *Complex Setup and Installation: Designing, configuring, and wiring a full mesh network takes a massive amount of planning and physical labor.* 
 - - - #### *Difficult Maintenance: Troubleshooting broken links or isolated nodes is time-consuming due to the sheer volume of interconnections.* 
 - - - #### *High Power Consumption: In a wired or always-on setup, keeping all nodes and redundant paths active demands more power.*
*


  - #### **5) Ring Topology**


  - - #### *A ring topology is a network setup where each device (node) connects to two other devices, forming a closed, circular loop.* 
 - - #### *Pros (Advantages)*
 - - - #### *No data collisions: Data travels in an orderly sequence using a token-passing method, which prevents packet crashes.*
 - - - #### *Equal resource access: Every device on the ring gets an identical opportunity to transmit and receive data.*
 - - - #### *Predictable performance: The network maintains steady data speeds and handles heavy traffic much better than a bus topology.*
 - - - #### *No central server needed: Devices manage communication independently without relying on a main server.*
 - - - #### *Lower cabling costs: It requires less physical cable than a star topology because each node only connects to its two immediate neighbors.*
*
 - - #### *Cons (Disadvantages)*
 - - - #### *Single point of failure: In a standard single-ring setup, a broken wire or failed node can bring down the entire network.*
 - - - #### *Difficult troubleshooting: Locating a fault or break requires checking multiple nodes around the circle.*
 - - - #### *Higher latency: Data must pass sequentially through every intermediate device between the sender and the receiver.*
 - - - #### *Disruption during changes: Adding or removing a device traditionally requires stopping the entire network.*
*


  - #### **6) Hydbrid Topology**


  - - #### *A hybrid topology is a computer network structure that combines two or more different basic network topologies—such as star, ring, bus, or mesh—into a single unified system. This Topology is also the most used Topology due to the fact that it combines different topologies strength* 
 - - #### *Pros (Advantages)*
 - - - #### *High Flexibility & Customization: You can tailor different sections of the network to match specific department workflows, traffic loads, and physical environments.*
 - - - #### *Effective Fault Isolation: Problems or failures in one segment are usually contained to that specific section without crashing the entire network.*
 - - - #### *Enhanced Reliability & Uptime: By merging structures, you can build redundancy where it matters most, keeping critical operations running if a sub-network drops.*
 - - - #### *Scalability: You can easily add new nodes, devices, or entire network segments (like a new star or ring cluster) without disrupting existing operations.*
 - - - #### *Optimized Performance: Traffic can be routed efficiently through pathways best suited for heavy data loads.* 

 - - #### *Cons (Disadvantages)*
 - - - #### *High Cost: Hardware components—such as intelligent hubs, multi-protocol routers, and specialized connectors—are expensive.*
 - - - #### *Complex Design and Setup: Planning, configuring, and installing a multi-layered hybrid architecture requires advanced network engineering skills.*
 - - - #### *Heavy Cabling and Infrastructure Requirements: Merging diverse layouts often demands extensive physical cabling, cooling systems, and specialized infrastructure.*
 - - - #### *Difficult Maintenance and Troubleshooting: Because multiple structures work together, diagnosing the root cause of an issue can span across different protocols and physical layouts.*



  - #### **7) Tree Topology**


  - - #### *Tree topology is a hierarchical network structure that combines elements of star and bus topologies, resembling a tree with a central root node, branches, and leaf nodes*
 - - #### *Root nodes are located at the very top where branch nodes are located in the middle and the leaf node is located at the very bottom*
* 
 - - #### *Pros (Advantages)*
 - - - #### *High Scalability: You can easily add new secondary branches and sub-networks without disrupting the rest of the existing network.* 
 - - - #### *Effective Fault Isolation: Problems or damages in one lower-level branch are contained locally and do not automatically crash other branches.*
 - - - #### *Structured Organization: The hierarchical layout mimics corporate or departmental structures, making management and monitoring much clearer for IT teams.*
 - - - #### *Point-to-Point Connections: Individual devices and segments use dedicated wiring, which reduces data collisions and simplifies targeted troubleshooting.*
 - - - #### *Good Resource Sharing: Centralized servers and storage devices can be shared efficiently across various segments.*
*
 - - #### *Cons (Disadvantages)*
 - - - #### *Single Point of Failure: If the main root node or a critical upper-level backbone cable fails, large portions or the entire network goes down.*
 - - - #### *High Installation Costs: Requiring extensive cabling, backbone components, and multiple hubs makes initial setup expensive.*
 - - - #### *Complex Maintenance: As the hierarchy grows larger and more branches are added, cable management and troubleshooting upstream become difficult.*
 - - - #### *Performance Bottlenecks: Heavy traffic flowing from lower branches must pass through higher-level nodes, leading to potential slowdowns during peak usage*