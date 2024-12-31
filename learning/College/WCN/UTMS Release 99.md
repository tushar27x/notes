![[Pasted image 20241210021122.png]]
#### **1. User Equipment (UE)**

- **Mobile Device**: The user's device used to access UMTS services.
- **USIM (Universal Subscriber Identity Module)**: Stores user-specific information like IMSI (International Mobile Subscriber Identity), security keys, and service profiles.
#### **2. UMTS Terrestrial Radio Access Network (UTRAN)**

UTRAN handles all radio-related functions.

- **Node B**:
    - Equivalent to a base station.
    - Facilitates the physical layer, including modulation and demodulation.
    - Handles radio transmission and reception with the UE.
- **Radio Network Controller (RNC)**:
    - Controls multiple Node Bs.
    - Manages radio resources, handovers, and packet scheduling.
    - Acts as the interface between the UTRAN and the Core Network.
    
#### **3. Core Network (CN)**

The core network is split into two domains for handling different types of traffic:

**A. Circuit-Switched Domain**  
Used for voice services and other real-time applications.
- **Mobile Switching Center (MSC)**:
    - Performs call control and mobility management for circuit-switched calls.
- **Gateway MSC (GMSC)**:
    - Connects the UMTS network to external telecommunication networks like PSTN/ISDN.

**B. Packet-Switched Domain**  
Used for data services like internet access.

- **Serving GPRS Support Node (SGSN)**:
    - Handles data packet delivery, mobility management, and session management.
- **Gateway GPRS Support Node (GGSN)**:
    - Provides access to external packet data networks (e.g., the Internet).

#### **4. Interfaces**

Key interfaces between components ensure smooth communication:

- `Uu`: Between UE and Node B (air interface).
- `Iub`: Between Node B and RNC.
- `Iu`: Between RNC and the Core Network (with variants `Iu-CS` for circuit-switched and `Iu-PS` for packet-switched domains).
- `Gn/Gp`: Between GGSN and SGSN (internal/external packet-switched domains).

#### **5. External Networks**

- **PSTN/ISDN**: For voice and traditional telecommunication services.
- **Internet**: For IP-based services.