
- stands for Wireless Microwave Access.
- communication standard designed to provide high speed broadband access.
- based on IEEE 802.16

### **WiMAX Architecture**

The WiMAX architecture is designed to support point-to-multipoint communication, enabling efficient delivery of broadband services to fixed and mobile users.

#### **1. Key Components**

- **Base Station (BS)**:
    - Serves as the central point of communication.
    - Provides coverage and connectivity to subscriber stations.
- **Subscriber Station (SS)**:
    - Fixed or mobile devices that receive broadband services from the BS.
- **Access Service Network (ASN)**:
    - Handles subscriber access, mobility management, and resource allocation.
- **Connectivity Service Network (CSN)**:
    - Manages IP connectivity, authentication, billing, and QoS (Quality of Service).

#### **2. Network Topologies**

- **Point-to-Multipoint (PMP)**:
    - BS communicates with multiple SS devices.
- **Mesh Network**:
    - Devices can relay traffic for each other, extending the network's range and coverage.
- **Relay Network**:
    - Intermediate relay stations enhance signal coverage and reduce deployment costs.

### **WiMAX PHY Layer Overview**

The **Physical (PHY) Layer** in WiMAX is responsible for transmitting data over the air interface. WiMAX uses **Orthogonal Frequency Division Multiplexing (OFDM)** and **Orthogonal Frequency Division Multiple Access (OFDMA)** for efficient and robust communication.
#### **Key Features of PHY Layer**

1. **Modulation and Coding**:
    - Adaptive Modulation and Coding (AMC) to optimize throughput based on channel conditions.
    - Modulation schemes: BPSK, QPSK, 16-QAM, 64-QAM.
2. **Channel Bandwidth**:
    - Flexible bandwidth support: **1.25 MHz** to **20 MHz**.
3. **Subcarrier Allocation**:
    - Subcarriers are divided into:
        - **Data subcarriers** for payload.
        - **Pilot subcarriers** for channel estimation.
          
4. **Time-Division Duplexing (TDD) and Frequency-Division Duplexing (FDD)**:
    - TDD: Both uplink and downlink use the same frequency band but alternate in time.
    - FDD: Uplink and downlink use separate frequency bands.
    
5. **Multiple Antenna Techniques**:
    - Support for MIMO (Multiple Input Multiple Output) to enhance data rates and coverage.


### **WiMAX MAC Layer Overview**

The **MAC Layer** is responsible for managing access to the PHY layer and providing QoS support for different applications.

#### **Key Features of MAC Layer**

1. **Connection-Oriented**:
    - WiMAX uses connections rather than IP addresses for communication, improving QoS management.
2. **Scheduling**:
    - The MAC layer includes a centralized scheduler at the BS to allocate resources for uplink and downlink communication.
3. **QoS Management**:
    - The MAC layer ensures different levels of QoS for voice, video, and data services.
4. **Frame Structure**:
    - Divided into uplink and downlink subframes, containing control and data regions.

### **WiMAX Scheduling Services**

The MAC layer supports different scheduling services to meet the QoS requirements of various applications. The BS allocates resources based on the type of service.

#### **1. Unsolicited Grant Service (UGS)**:

- **Purpose**: Supports real-time applications with fixed data rates, such as VoIP.
- **Characteristics**:
    - Fixed-size periodic grants.
    - Low latency and guaranteed bandwidth.
    - Minimal signaling overhead.

#### **2. Real-Time Polling Service (rtPS)**:

- **Purpose**: Supports real-time applications with variable data rates, such as streaming video.
- **Characteristics**:
    - Periodic polling for resource requests.
    - Variable-size grants based on demand.
    - Higher latency than UGS but more efficient for variable traffic.

#### **3. Non-Real-Time Polling Service (nrtPS)**:

- **Purpose**: Supports non-real-time applications with variable data rates, such as FTP.
- **Characteristics**:
    - Polling-based resource allocation.
    - Less frequent polling than rtPS.
    - Suitable for delay-tolerant applications.

#### **4. Best Effort (BE)**:

- **Purpose**: Supports applications with no strict QoS requirements, such as web browsing and email.
- **Characteristics**:
    - Resources are allocated on a "best-effort" basis.
    - No guaranteed bandwidth or delay.
    - Lowest priority in resource allocation.