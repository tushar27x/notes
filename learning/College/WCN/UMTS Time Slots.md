- **time slots** are used to organize and allocate radio resources over the air interface.
- Since UMTS uses WCDMA the concepts of time slots is different from traditional TDMA.
- Instead of fixed time slots WCDMA uses code division and a combination of time and frequency division multiple access techniques.

### **UTMS Frame Structure**

- the basic unit of data transmission in UTMS is a frame.
- A frame is further divided into slots.
- Each **time slot** can be allocated to a **physical channel**, depending on the traffic and control requirements for that particular time.
- Multiple users can share these slots through the use of **spreading codes** (in WCDMA, code-division is used, where each user is assigned a unique code).
#### **UMTS Radio Frame Structure**

- **Radio Frame Duration**: A radio frame in WCDMA lasts for **10 `ms`** (milliseconds).
- **Subframe**: The 10 `ms` frame is divided into **15 slots**, each of **666.7 microseconds** in duration.

Thus, the time structure looks like this:
- 1 frame (10 `ms`) = 15 slots
- 1 slot = 666.7 `µs`

### **Time Slot Allocation**

In UMTS, users are assigned time slots for data transmission based on the following conditions:

- **Dynamic Allocation**: The network dynamically allocates time slots based on the data rate requirements of the users. This means that not every user will necessarily have a time slot all the time; time slots are allocated based on demand and priority.

- **HSDPA/HSUPA**: With the introduction of **High-Speed Downlink Packet Access (HSDPA)** and **High-Speed Uplink Packet Access (HSUPA)**, the allocation of time slots became more efficient for high-speed data transmission. In these systems, multiple time slots can be bundled together to increase throughput.

- **Spreading Codes**: Since UMTS uses **Code Division** to share the spectrum, each user is assigned a unique **spreading code** that allows multiple users to share the same time slots without interference.