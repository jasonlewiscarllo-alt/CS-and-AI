# ***<h1 align="center">Networks</h1>***
##### ***<h1 align="center">Source:AI and computer science textbook second edition IGCSE&O level second edition and computer science textbook AS&A level(Both textbooks by David Watson and Helen Williams)</h1>***

### ***Network definition***
#### **A network is like a group of friends sharing ideas. A computer network is simply two or more devices—such as phones, laptops, or printers—connected together so they can share information and resources.Devices talk to each other using physical cables or wireless signals like Wi-Fi. Networks can be small, like the setup in your home, or huge, connecting devices across different countries. Every time you send a message, share a photo, or browse the web, you are using a network.In the end, networks make communicating and working together much faster. They also save time and resources by letting multiple devices share the same internet connection, printer, or files with ease.**

### ***Components of the network***
 - #### ***1)Nodes(devices)***
 - - #### *Node are any device connected to a network capable of sending, receiving, or processing data (e.g., laptops, phones, printers, servers).*
 - - #### *Key Function: Enables devices to exchange information and share resources over a network.*
 - - #### *Example: In a home Wi-Fi setup, your phone, laptop, and printer are all individual nodes interacting with one another.*

 - #### ***2)Nodes(devices)***
 - - #### *Links are the connections that allow devices in a network to communicate with one another. These connections can be wired or wireless, depending on the type of network and the devices being used.*
 - - #### *Types of links:*
 - - - #### *Wired links use physical cables, such as Ethernet cables, to transfer data between devices.*
 - - - #### *Wireless links use signals, such as Wi-Fi or Bluetooth, to send information without needing a physical cable.*
  - - #### *Key Function: It provides the physical or wireless pathway that allows devices to exchange information. Without links, network communication is impossible, and your devices would be completely isolated on separate islands.*
 - - #### *Example: when you connect your laptop to a router using an Ethernet cable, the cable acts as a link. When you connect your phone to the same router through Wi-Fi, the wireless connection acts as a link. Without links, devices would not be able to exchange information.*

 - #### ***3)Routers***
 - - #### *Routers are networking devices that connect different networks and forward data between them, they examine information in data packets.They are commonly used in homes, schools, offices, and large organizations.*
 - - #### *Key Function: Examines information inside data packets, such as destination IP addresses, to determine where the data should go next and selects an appropriate path across the network.*
 - - #### *Example: When you open a website on your phone, your home router forwards your request from your home network toward the internet. When the website sends information back, the router helps deliver the data to your device.*

 - #### ***4)Switches***
 - - #### *Switches are networking devices that connect multiple devices within a local area network (LAN)[This will be further explained later at the bottom]. They are commonly used in offices, schools, and other places where many devices need to communicate within the same local network.
 - - #### *Key Function: Directs data specifically to the intended device rather than sending it unnecessarily to every connected device. It uses MAC addresses[It wil explained at the bottom as well] to identify devices on a local network, checking the destination MAC address and forwarding the data through the appropriate port.
 - - #### *Example: In a school computer lab, when one computer sends a document to a network printer connected to the same switch, the switch forwards the data directly toward the printer.

### ***Packets***
<img width="738" height="237" alt="image-1" src="https://github.com/user-attachments/assets/06815940-666a-479b-b6ba-5bd465a1e12d" />

#### *In networks, a packet is a small part of a larger piece of information that is sent over the internet. Each packet contains the a header, payload, and a trailer, which includes important details about the data, The header stores where it needs to go and who sent it. The header also helps the receiving device understand how to rearrange the packet back together. The payload is the place where the actual infromation is stored within the packet.This is to tell that all packets have been sent.When we send information over the internet, such as a photo, video, or message, the data is divided into smaller packets. These packets travel through network devices like routers and switches until they reach their destination. Once they arrive, the receiving device puts the packets back together so the information can be viewed or used. This process is similar to building a puzzle, where each piece is sent separately and then joined together to complete the picture.Sending data in packets also makes the internet more efficient because many devices can send and receive information at the same time. This method is called packet switching. Instead of one connection taking up the whole network, packets can travel through available routes, allowing many people to use the internet simultaneously.*

<img width="666" height="395" alt="image-3" src="https://github.com/user-attachments/assets/cd4b78e7-9c64-459c-b848-25866e2cfe69" />

#### *This picture shows the available paths where the packets will go and they will seperate to different routes since if a router or link fails, packets can automatically reroute around the problem so that the packets won't get lost and never received*


### ***Identification of Devices***

 - #### ***1)MAC Address(Media Access Control)***
 - - #### *MAC Address is a unique, hardcoded **48-bit** physical identifier burned into a Network Interface Card (NIC) by the hardware manufacturer.*
 - - #### *Key Function: Identifies a specific hardware interface so that devices connected to the same local network segment can send data directly to each other.*
 - - #### *Example: 00:1A:2B:3C:4D:5E(A MAC address is decided by the network hardware manufacturer during production or by a network administrator using software settings)*
 - #### ***2)IP Address (Internet Protocol Address)***
 - - #### *IP Address A software-assigned numerical label given to a device whenever it connects to a network*
 - - #### *Types of IP address:*
  - - - #### *IPv4(Internet Protocol version 4):It is the original and widely used version of the Internet Protocol and it has a **Address Length of 32 bits e.g. 93.184.216.34  written in denary***
  - - - #### *IPv6(Internet Protocol version 6):The newer version of the Internet Protocol designed to permanently replace IPv4 and it has a **Address Length of 128 bits e.g. 2001:0db8:85a3:0000:0000:8a2e:0370:7334 written in hexadecimal***
 - - #### *Key Function: Enables data to be routed across multiple interconnected networks, guiding packets from a source device across the global internet to a destination device.*


## Table of Contents
* [1.Pros](#benefits)
* [2.Cons](#losses)

