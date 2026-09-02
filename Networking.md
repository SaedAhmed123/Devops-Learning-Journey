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
 