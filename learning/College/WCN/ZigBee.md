- is a personal area network technology
- based on IEEE 802.15.4
- ZigBee is an open, global, packet-based protocol designed to provide an easy-to-use architecture for secure, reliable, low power wireless networks.
- IEEE 802.15.4 supports star and peer-to-peer topologies(mesh and cluster tree).
### Types of ZigBee Devices:  

- **Zigbee Coordinator Device:** It communicates with routers. This device is used for connecting the devices.
- **Zigbee Router:** It is used for passing the data between devices.
- **Zigbee End Device:** It is the device that is going to be controlled.![[Pasted image 20241210184258.png]]


### **ZigBee Architecture**

![[Pasted image 20241210184429.png]]

- **Physical layer:**  The Physical layer is closest to the hardware and directly controls and communicates with the Zigbee radio. The physical layer translates the data packets in the over-the-air bits for transmission and vice-versa during the reception.
-  **Medium Access Control layer (MAC layer):** The layer is responsible for the interface between the physical and network layer. 
- **Network layer:** This layer acts as an interface between the MAC layer and the application layer. It is responsible for mesh networking.
- **Application layer:** The application layer in the Zigbee stack is the highest protocol layer and it consists of the application support sub-layer and Zigbee device object. It contains manufacturer-defined applications.


### **Features of ZigBee**
- Low power consumption
- Low data rate
- Mesh networking
- Short-range communication.
- **Topologies**
    - **Star topology**: One central device (coordinator) communicates with all other devices (end devices).
    - **Mesh topology**: Devices communicate with each other and can relay data over multiple hops, improving range and robustness.
    - **Tree topology**: Similar to mesh, but with a more hierarchical structure for routing data.


### **ZigBee Frequency Band**

- **2.4 GHz ISM Band**: Most widely used (globally), providing a data rate of up to **250 Kbps**.
- **868 MHz Band**: Used primarily in Europe, with a maximum data rate of **20 Kbps**.
- **915 MHz Band**: Used in North America and some other regions, providing a data rate of **40 Kbps**.


### **IEEE Standard for ZigBee**

Zigbee is defined by the **IEEE 802.15** standards family, specifically **IEEE 802.15.4** and **Zigbee Alliance** specifications.

- **IEEE 802.15.4**: This standard defines the **Physical Layer** (PHY) and **Medium Access Control (MAC)** layer for low-power wireless communication. Zigbee is built on top of this standard and adds higher layers for network and application management.
- **Zigbee Alliance Specifications**: Zigbee provides detailed application profiles and networking specifications, ensuring that devices and networks conform to the required functionality and interoperability standards.


|**Feature**|**Zigbee**|
|---|---|
|**Frequency Band**|2.4 GHz (global), 868 MHz (Europe), 915 MHz (North America)|
|**Data Rate**|Up to 250 Kbps|
|**Range**|10-100 meters (depending on environment and mesh setup)|
|**Power Consumption**|Low, supports sleep modes|
|**Network Size**|Up to 65,000 devices|
|**Topology**|Star, Mesh, and Tree topologies|
|**Security**|AES-128 encryption, device authentication|
|**Standard**|IEEE 802.15.4, Zigbee Alliance specifications|
|**Applications**|Home automation, industrial control, smart energy, IoT|
|**Mesh Networking**|Yes, enhances range and reliability|
