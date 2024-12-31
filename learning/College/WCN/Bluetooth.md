- wireless communication technology designed for short-range communication between devices
- It allows for the exchange of data between devices over short distances using **radio waves**.

### **Architecture of Bluetooth**

Bluetooth defines 2 types of networks:
1. **Piconet**
	- contains one primary node called **master node**  seven active secondary nodes called slave nodes.
	- total 8 active nodes present at a distance of 10m.
	- The communication between the primary and secondary nodes can be one-to-one or one-to-many.
	- Possible communication is only between the master and slave; Slave-slave communication is not possible.
	- It also has 255 parked nodes, these are secondary nodes and cannot take participation in communication unless it gets converted to the active state.![[Pasted image 20241210154457.png]]

2. **Scatternet**
	- Formed by using various piconets.
	- A slave present in one piconet can serve as master in another piconet.
	- This kind of node can receive messages from master of one piconet and deliver them to the slave in another piconet.
	- This type of node is called as a **bridge node**.![[Pasted image 20241210154734.png]]

### **Bluetooth Features**

Bluetooth offers several key features that make it popular for wireless communication:

**1. Short-Range Communication**

- Bluetooth operates effectively over **short distances**, typically up to **100 meters** (depending on the class of the device). The most common range is around **10 meters**.

**2. Low Power Consumption**

- Bluetooth is designed to be energy-efficient, which makes it ideal for mobile devices and applications where power consumption is a concern (e.g., wearables, health devices, IoT sensors).

**3. Frequency Hopping**

- Bluetooth uses **frequency hopping** to avoid interference from other devices. It rapidly switches frequencies within the **2.4 GHz ISM band**, which allows it to minimize interference and optimize performance.

**4. Secure Communication**

- Bluetooth supports strong encryption (AES-128) and authentication mechanisms to ensure that the communication between devices is secure.

**5. Peer-to-Peer and Multi-Point Communication**

- Bluetooth supports both **point-to-point** and **point-to-multipoint** communication. Multiple devices can connect and communicate with each other in a **piconet** (a small network of Bluetooth devices).

**6. Low Latency**

- Bluetooth is designed to support low-latency communication, which makes it ideal for applications like audio streaming and gaming.

**7. Interoperability**

- Bluetooth is widely adopted and standardized, ensuring interoperability between devices from different manufacturers.

### **IEEE Standard for Bluetooth**

Bluetooth is governed by the **IEEE 802.15** standards family, specifically **IEEE 802.15.1**.

- **IEEE 802.15.1**: Defines the physical layer and media access control (MAC) layer specifications for Bluetooth.

Bluetooth's evolution is also defined by the Bluetooth Special Interest Group (SIG), which sets specifications and standards for Bluetooth technology. Some of the major versions of Bluetooth are:

- **Bluetooth 1.0/1.1**: The initial Bluetooth standard, which was prone to many interoperability issues.
- **Bluetooth 2.0 + EDR (Enhanced Data Rate)**: Introduced improved data rates (up to 3 Mbps) and better power efficiency.
- **Bluetooth 3.0 + HS (High Speed)**: Added support for high-speed data transfer via Wi-Fi.
- **Bluetooth 4.0 (Bluetooth Low Energy - BLE)**: Aimed at low-power applications, supporting IoT devices and wearables.
- **Bluetooth 5.0**: Increased range, speed, and support for more IoT devices with improved data transfer rates and broadcast capabilities.
- **Bluetooth 5.1/5.2**: Further improvements in positioning, low-latency communication, and multi-device connectivity, with Bluetooth 5.2 introducing enhanced audio features like **LE Audio**.

| **Feature**           | **Bluetooth**                                                |
| --------------------- | ------------------------------------------------------------ |
| **Frequency Band**    | 2.4 GHz ISM Band (2.402 GHz to 2.480 GHz)                    |
| **Range**             | 10 m (Class 2) to 100 m (Class 1)                            |
| **Data Rate**         | Up to 3 Mbps (Bluetooth 2.0 + EDR), higher in newer versions |
| **Topology**          | Master-Slave (Piconet and Scatternet)                        |
| **Power Consumption** | Low (especially in BLE mode)                                 |
| **Security**          | AES-128 Encryption, Authentication                           |
| **IEEE Standard**     | IEEE 802.15.1                                                |
| **Key Versions**      | Bluetooth 1.0/1.1, 2.0, 3.0, 4.0 (BLE), 5.0, 5.1, 5.2        |
