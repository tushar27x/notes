IS-95, also known as `cdmaOne`, was the first CDMA-based mobile network standard, primarily used in North America. CDMA operates on a fundamentally different principle from GSM, as it uses **spread spectrum technology** to share the same frequency band among multiple users.

#### Spread Spectrum

In spread spectrum systems, the signal is spread over a wide bandwidth, allowing multiple users to transmit simultaneously on the same frequency band. CDMA achieves this through **pseudo-random codes** assigned to each user, ensuring that only the intended receiver can decode the signal.

#### Frequency and Channel Specifications

- **Frequency Bands**: CDMA IS-95 typically operates in the 800 MHz or 1900 MHz bands.
- **Channels**: Channels are divided into **forward (downlink)** and **reverse (uplink)** channels. The forward channel is used to send data from the base station to the mobile device, while the reverse channel handles data from the mobile device back to the base station.

#### Forward and Reverse CDMA Channels

- **Forward Link**: Each base station sends data over multiple code channels. The forward channel uses unique codes to separate users.
- **Reverse Link**: Each user transmits data back to the base station with a unique code, reducing interference among multiple users on the same frequency.

---
#### Near-Far Problem

The **near-far problem** in CDMA arises when signals from nearby mobile devices are much stronger than those from farther devices, potentially overpowering weaker signals. To mitigate this, CDMA systems use **power control**.

#### Power Control

Power control in CDMA adjusts the transmission power of each mobile device to maintain a balanced signal strength across users. This prevents stronger signals from dominating and interfering with weaker ones, improving overall system performance and capacity.

--- 
#### Spread Spectrum Systems and Cellular Code Division Access Systems

CDMA employs spread spectrum techniques to allow multiple users to transmit on the same frequency without significant interference. The primary aspects of CDMA spread spectrum systems include:

1. **Principle of Code Division**: CDMA assigns a unique spreading code to each user, which modulates the signal before transmission. The receiver can then use the code to demodulate the signal.
2. **Advantages of Spread Spectrum**: Spread spectrum provides resistance to interference and improves security by making the transmitted signal appear as noise unless the correct code is used.
--- 
#### Effects of Multipath Propagation on CDMA

Multipath propagation occurs when a signal reflects off surfaces, resulting in multiple delayed versions of the same signal arriving at the receiver. In CDMA, multipath propagation can affect signal quality in the following ways:

1. **Signal Fading**: The various paths interfere, causing rapid fluctuations in signal strength.
2. **Rake Receiver**: To combat multipath fading, CDMA systems use a rake receiver, which processes multiple signal paths separately, combining them to enhance signal quality.
3. **Power Control Requirements**: Multipath fading requires more precise power control to ensure a stable connection.