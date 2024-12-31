Wireless channels play a critical role in determining the quality and reliability of communication between mobile devices and base stations.

### **Wireless Channel modelling and fading**

- Signals in wireless networks are subject to *fading*, which is a variation in signal amplitude and phase over time and space.
- Fading occurs due to multipath propagation phenomenon where signals take different path to reach the receiver, causing interference and fluctuations in received signal strength.
- Types of Fading:
1. **Fast fading** -> Occurs when the signal's phase and amplitude fluctuate rapidly within a short period, often due to the relative movement of the transmitter or receiver. Fast fading affects signals in environments with a high rate of multipath effects, such as urban areas or moving vehicles.
2. **Slow fading** -> Caused by large obstacles (e.g., buildings, mountains) and changes slowly over time or distance. This type of fading is also known as **shadow fading**.

#### **Fast Fading Wireless Channel Models**

- *Rayleigh Fading*
	- **Description**: Rayleigh fading assumes that the magnitude of the received signal follows a Rayleigh distribution.
	- **Scenario**: Commonly used for modeling non-line-of-sight (NLOS) wireless channels.
	- **Application**: Rayleigh fading is prevalent in urban environments with multipath propagation
- *Ricean Fading Channel*
    -  **Description**: Rician fading accounts for both a dominant line-of-sight (LOS) component and scattered multipath components.
	- **Scenario**: Suitable for environments where there is a strong LOS path alongside weaker multipath components.
	- **Application**: Often used in scenarios like indoor wireless communication with reflective surfaces