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
