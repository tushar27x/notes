**Modulation** is a process of encoding information into a carrier signal by varying its properties (e.g. amplitude, frequency or phase).

### **Types of Modulations Techniques**

- **Amplitude Modulation (AM)**:
    - Varies the amplitude of the carrier signal according to the data signal.
    - Simple but susceptible to noise and interference.
    - Used in older analog systems and broadcasting.
- **Frequency Modulation (FM)**:
    - Varies the frequency of the carrier signal based on the data signal.
    - Provides better noise immunity than AM.
    - Used in radio broadcasting and some analog communication systems.
- **Phase Modulation (PM)**:
    - Varies the phase of the carrier signal to encode data.
    - Used in digital systems, often in combination with other techniques.
- **Digital Modulation Techniques**:
    - **Binary Phase Shift Keying (BPSK)**:
        - Uses two phase states (0° and 180°) to represent binary 0 and 1.
        - Robust against noise, with lower BER in AWGN channels.
    - **Quadrature Phase Shift Keying (QPSK)**:
        - Uses four phase states (0°, 90°, 180°, and 270°) to encode two bits per symbol, doubling data rate compared to BPSK.
        - Balances spectral efficiency and resilience against noise.
    - **Quadrature Amplitude Modulation (QAM)**:
        - Combines amplitude and phase modulation, allowing multiple bits to be represented per symbol (e.g., 16-QAM, 64-QAM).
        - Provides high spectral efficiency, widely used in modern cellular and Wi-Fi systems.
    - **Frequency Shift Keying (FSK)**:
        - Encodes data by shifting between multiple frequencies.
	        - Used in low-data-rate applications, as it’s simple but less spectrally efficient than QAM or QPSK.