# Networking


## OSI 7 Layer Model

![alt text](https://cdn2.hubspot.net/hubfs/2954816/The%207%20Layers%20of%20OSI.png)

## Layer 1 - Physical Layer

Layer 1 specifications defines the transmission and reception of raw but streams between a device and a shared physical medium. It defines things like voltage levels,timings,rates,distances,modulations and connectors.

Physical medium can be copper(electical), Fibre(light), or wifi(radio frequency).

**Physical Hub** - is a basic hardware device that connects multiple computers or devices in a local area network (LAN) so they can communicate.

Anything receivied on any port, is transmitted on every other port, including errors and collissions.

If multiple devices trasnmit at once, a collission occurs, which corrupts any transmission on the shared medium.

### Limitations of Layer 1 

There is no device addressing, all data is processed by all devices. Its a broadcast medium like shouting in a room of 3 other people and not using names.

Layer 1 has no media access control (MAC) and no collission detection.

No method for device to device communication, everything is broadcast.

All devices part of the same layer 1 network need to be using the same layer 1 medium and device standards. A certain type of network card and medium, e.g. wifi cards with antennas and frequency.


## Layer 2 - Data Link Layer


Layer 2 requires a functional layer 1 to work, higher ayers build on lower layers adding features and capabilities. Devices at L2 have a unique hardware MAC address, its a 12 digit hexadecimal number.


### Data Encapsulation

Layer 2 provides frames, it used to transmit data across a physical network and can be addressed to a destination or broadcasted. 

At Layer 2 (the Data Link Layer), data encapsulation wraps a Layer 3 packet inside a frame by adding a specific Layer 2 header and a trailer.

**The Payload:** Is the data the frame carries from source to destination. its generally provided by Layer 3 and the ethertype attribute defines which Layer 3 protocol is used.


**Layer 2 Header:** Added to the front of the packet. It includes the source MAC address and the destination MAC address to ensure the data moves correctly across the local network segment.


**Layer 2 Trailer:** Added to the end of the frame. This typically contains a Frame Check Sequence (FCS) for error detection, allowing the receiving device to check if the frame was corrupted during transmission. 



### CSMA/CD

**Carrier Sense Multiple Access with Collision Detection**

At Layer 1 there is no media access control and when two devices send transmission at once, it causes a collission and corrupts the data, this is solved at layer 2.

MAC manages the device interaction, responsible for addressing frames and also controls physical media access.

When transmitting layer 2 checks for carriers, if no carriers are detected,then layer 1 takes frame data converts it to raw bits and transmit. If a carrier is detected, it waits therefore no collission occurs.

However, if both devices check for a carrier that doesn't exist and transmit at the same time. Then a **Jam Signal** is sent by all devies. The devices then use a "backoff algorithm" to wait for a randomised amount if time before attempting to retransmit.

### Switches

Switches understand frames and MAC address. They mainatain a MAC address table, which starts off empty. As the switch receivies frames on its ports, it learns which devices are connected and populates the MAC address table.
If a frame is transmitted to a specific port, it will be forwarded if the destination MAC address is on the table. If not on the table it forwarded to all ports. Any frames with "All F's" will be forwarded to all ports.
Switched store and forward, they dont repeat blindly like hubs. It means only valid frames are forwarded, and collisions are isolated on the port they occurred.


### Layer 2 Features

- Identifable devices 
- Media access control
- Collision detection
- Unicast 1:1 communication
- Broadcast 1:All communication 
- Switches

## Layer 3 - Network Layer

Layer 3 requires a minimum of one or more operational Layer 2 networks, the purpose is to send and receive data from one location to another.

If there are two isolated local are networks, using only layer 2, only those networks joined by a direct point to point link using the same layer 2 protocol could communicate. **Ethernet** is a layer 2 protocol used generally for local networks. Long distance point to point links will use other more suitable protocols such as **MPLS (Multiprotocol Label Switching) and ATM(synchronous Transfer Mode)**.

Internet protocol is layer 3 protocol which adds cross-network IP addressing and routing to move data between local are networks without a direct point to point link. IP packets are moved step by step from source to destination via intermediate networks. Encapsulated in different frames along the way. Routes(L3) devices, remove frame encapsulation and add a new frame encapsulation at every step.

### IP Packet Structure 

**IPV4**
- Source IP address
- Destination IP address
- Protocol e.g. ICMP, TCP, UDP
- Data
- Time to live(TTL) - maximum number of hops before discarded.

**IPV6**
- Source IP address - bigger larger addresses
- Destination IP address
- Data
- Hop Limit - similar to TTL

### IP Addressing

An IP address is a unique label assigned to every device connected to a computer network. It acts like a digiital street address, allowing devices(phones, routers, laptop) to identify each other and route internet traffic back and forth. All IP addresses have a netwrok part and a host part. if the network part of two IP addresses match, it means they're on the same IP network. 


### Subnet Mask

Its the subnet mask which allows a host to determine if an IP address it needs to communicate with is local or remote - which influences if it needs to use a gateway or can communicate locally.


### Route Tables and Routes

A routing table is a set of rules, often viewed in table format, that is used to determine where data packets traveling over an IP network will be directed. Route tables can be statically populated or there are protocols such as BGP (boarder gateway protocol), which allows all routers to communicate with each other to exchange which netwroks they know about. 

### Address Resolution Protocol (ARP)

ARP -  maps IP addresses to MAC addresses within a local network.

If on the same network, one device can be sent a layer 2 All F's broadcast who has a certain IP address. ARP software sees the broadcast and says " I'm that IP address", sends the corresponding MAC address. Therefore, the firstndevice now knows the second devices MAC address and use it as a destination address.

### IP Routing

Subnet mask and destination IP address confirm if two devices are on the same network or not. In this scenario ARP (Address resolution protocol) is used to find the mac address of the default gateway(router). The payload with a destination of the remote device is encapsulated in a frame with a destination of the router's MAC address. The router removes the frame around the payload and reviews the packets destination IP. The router has a route for the network of the final destination and creates a new frame with a second router mac address as its next destination. The frame is sent to the next routers mac address and removes the frame around the payload. The second router confirms the destination IP address is in the same network, uses ARP to get the mac address of the device. A new frame with the final devices as its mac address is created and encapsulated the payload is sent to the device. 

### Layer 3 Summary

- IP address(IPv4/IPv6) - cross network addressing.
- ARP - Maps the MAC address to the corresponding IP address. 
- Route - Where to forward the packet.
- Route Table - shows multiple routes.
- Router - moves packets from source to destination, encapsulating in frames along the way. 
- Allowing for device to device communication over the internet.

### Limitations 

- No method for channels of communications, only source IP and destination IP. It cannot distinguish between different applications running on the same device.

- Packets can be delivered out of order. Individual packets move across the internet through intermediate networks, depending on network conditions, theres no guarantee the packet will take the same route from source to destination. Its possible they arrive in different order.

- IP has no flow control, if the source transmit faster than the destination can receive it, it can saturate the destination causing loss of packets and loss of data.

## Layer 4

Layer 4 is responsible for provding reliable, efficient and ordered end to end communication between applications on different hosts.

### TCP and UDP

**TCP** - Transmission Control Protocol

**UDP** - User Datagram Protocol