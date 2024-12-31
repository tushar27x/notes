- The second generation of mobile networks came with a shift from analog to digital signals.
- It allowed for text messaging, better voice quality and increased capacity of data transfer.

## **Significant 2G Systems**
#### AMPS (Advanced Mobile  Phone System)

- **Type**: Analog
- **Introduction**: AMPS was initially developed in the U.S. and became one of the first widely adopted cellular standards.
- **Functionality**: Operated in the 800 MHz frequency band, using FDMA (Frequency Division Multiple Access) for multiple access.
- **Features and Limitations**: Although AMPS provided basic mobile telephony, it faced issues such as lack of security (due to analog transmission) and limited data capabilities.

#### ETACS (Extended Total Access Communication System)

- **Type**: Analog
- **Introduction**: ETACS was an extension of the TACS (Total Access Communication System), used primarily in Europe.
- **Functionality**: Similar to AMPS but operated in a different frequency range, typically 900 MHz in Europe.
- **Advantages over AMPS**: ETACS could accommodate more users due to slight improvements in spectrum efficiency, though it still suffered from analog limitations.


#### GSM (Global System for Mobile Communication)

- **Type**: Digital
- **Introduction**: Developed in Europe in the early 1990s, GSM became the dominant 2G technology globally.
- **Technology**: Operated using TDMA (Time Division Multiple Access) and used encryption for secure communication.

**GSM Architecture**
1. **Mobile Station (MS)**: The mobile device or phone that communicates with the base stations.    
    - Consists of the Mobile Equipment (ME) and the Subscriber Identity Module (SIM) card.
2. **Base Station Subsystem (BSS)**:
    - **Base Transceiver Station (BTS)**: Handles radio communications with the MS and is responsible for sending and receiving radio signals.
    - **Base Station Controller (BSC)**: Manages the radio resources and controls multiple BTS, handling tasks like frequency allocation and handovers.
3. **Network and Switching Subsystem (NSS)**:
    
    - **Mobile Switching Center (MSC)**: The core component responsible for call switching and routing.
    - **Home Location Register (HLR)**: A database containing information about the subscribers, including their location and services.
    - **Visitor Location Register (VLR)**: Temporarily stores subscriber information for users currently connected to the network.
    - **Authentication Center (AuC)** and **Equipment Identity Register (EIR)**: Handle authentication and device validation for secure communication.
4. **Operation and Support System (OSS)**: Responsible for network management, maintenance, and fault resolution.
--- 
#### Mobility Management in GSM

Mobility management is crucial in GSM to track users’ movements and provide seamless service:
1. **Location Updating**: As a user moves across different areas, the mobile device sends location updates to the VLR, allowing the network to know the device’s current location.
2. **Roaming**: When a user travels outside the home network, the HLR works with VLRs in foreign networks to ensure that calls and messages are delivered.
3. **Handover**: GSM supports both intra-BTS and inter-BTS handovers, allowing a call or data session to continue seamlessly as the user moves between different cells.

#### Network Signaling in GSM

Network signaling is essential for establishing calls, transferring data, and managing resources:
1. **Signaling System No. 7 (SS7)**: A global standard for telecommunication signaling, enabling call setup, routing, and disconnection.
2. **MAP (Mobile Application Part)**: A protocol in SS7 used in GSM networks for mobility management and SMS services.
3. **A-Interface Protocol**: Used between BSC and MSC to facilitate communication between different network components.

#### Mobile Management in GSM

Mobile management in GSM includes functions such as:

1. **Authentication**: Verifying the user’s identity to prevent unauthorized access.
2. **IMEI (International Mobile Equipment Identity)**: Unique identifier for each device, used to block stolen or unauthorized devices.
3. **Subscriber Verification**: Through the use of a SIM card and PIN codes to access the network securely.

#### Voice Signal Processing and Coding in GSM

1. **Speech Coding**: GSM compresses voice data using codecs like RPE-LTP (Regular Pulse Excitation Long Term Prediction) at a rate of 13 kbps to save bandwidth.
2. **Channel Coding**: Adds error correction to protect the data from transmission errors caused by noise or interference.
3. **Encryption**: Voice data is encrypted to ensure privacy.