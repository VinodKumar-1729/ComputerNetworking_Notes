**Transport Layer (Computer Networks)**

---

### Overview of the Transport Layer
The transport layer (Layer 4 of the OSI model) is crucial for controlling network traffic between hosts and end systems. It ensures the reliable and efficient flow of data by regulating the data volume, destination, and rate using protocols such as TCP, UDP, DCCP, and SCTP.

---

### Positioning in the OSI Model
- Located between the network layer (Layer 3) and the session layer (Layer 5).
- The network layer is responsible for routing data to the correct device, while the transport layer ensures correct sequencing, error detection, and delivery to the intended application.
- Works with the session layer to handle structured data for applications.

---

### Functions of the Transport Layer
1. **Segmentation and Reassembly**
   - Splits application data into smaller units called segments.
   - Adds sequence numbers to segments for reassembly at the destination.

2. **Connection Establishment and Termination**
   - Uses handshake protocols for connection-oriented services (e.g., TCP).
   - Ensures both systems are synchronized before data transfer and properly closes the connection afterward.

3. **Reliable Data Transmission**
   - Uses acknowledgments (ACKs) to ensure data is received correctly.
   - Retransmits lost or damaged segments.

4. **Flow Control**
   - Implements mechanisms like the sliding window protocol to prevent sender overload.
   - Receivers communicate acceptable data rates to senders.

5. **Error Control**
   - Detects and corrects errors end-to-end using techniques like checksums.
   - Retransmits erroneous segments when necessary.

6. **Multiplexing and Demultiplexing**
   - Allows multiple applications to use the network simultaneously by assigning unique port numbers.

---

### Characteristics of the Transport Layer
1. **Service-Point Addressing**
   - Uses port numbers to identify specific processes on a host.
   - Ensures data is delivered to the correct application.

2. **Segmentation and Reassembly**
   - Splits data into manageable segments.
   - Reassembles segments in the correct order at the destination.

3. **Connection Control**
   - Supports both connection-oriented (TCP) and connectionless (UDP) services.

4. **End-to-End Flow Control**
   - Prevents data overflow and ensures smooth transmission rates.

5. **End-to-End Error Control**
   - Verifies data integrity and requests retransmission of corrupted segments.

---

### Working of the Transport Layer
- Facilitates logical communication between applications running on separate hosts.
- Operates only on end systems (not implemented by intermediate routers).
- Utilizes TCP and UDP for various requirements:
  - **TCP**: Reliable, connection-oriented.
  - **UDP**: Lightweight, connectionless.
- Provides features like bandwidth guarantees and latency management for advanced needs.

---

### Transport Layer Protocols
1. **Transmission Control Protocol (TCP)**
   - Connection-oriented and reliable.
   - Performs handshaking before data transfer.
   - Includes error-checking, acknowledgments, and retransmissions.
   - Header size: Variable (20-60 bytes).

2. **User Datagram Protocol (UDP)**
   - Connectionless and lightweight.
   - Prioritizes speed and efficiency over reliability.
   - Minimal error-checking using checksums.
   - Header size: Fixed (8 bytes).

3. **Stream Control Transmission Protocol (SCTP)**
   - Combines features of TCP and UDP.
   - Supports multi-streaming and multi-homing.
   - Reliable and connection-oriented.

---

### Key Differences Between TCP and UDP
| Feature               | TCP                        | UDP                        |
|-----------------------|----------------------------|----------------------------|
| **Type**             | Connection-oriented        | Connectionless             |
| **Reliability**      | Reliable                   | Unreliable                 |
| **Error Checking**   | Extensive mechanisms       | Basic checksum             |
| **Acknowledgments**  | Yes                        | No                         |
| **Speed**            | Slower                     | Faster                     |
| **Retransmissions**  | Possible                   | Not supported              |
| **Header Size**      | 20-60 bytes (variable)     | 8 bytes (fixed)            |

---

### Additional Key Points and Lesser-Known Facts
1. **Advanced Protocols**
   - **DCCP (Datagram Congestion Control Protocol)**: Offers congestion control for UDP-like communication.
   - **RTP (Real-Time Transport Protocol)**: Used for real-time applications like VoIP and streaming.

2. **Flow Control Enhancements**
   - Techniques like **Selective Acknowledgment (SACK)** reduce retransmissions in TCP.

3. **Checksum Limitations**
   - Basic checksums may not detect all errors, especially in high-noise environments.

4. **Transport Layer Security (TLS)**
   - Operates above the transport layer but enhances data security for TCP connections.

5. **Multipath TCP (MPTCP)**
   - Allows simultaneous use of multiple paths for data transfer, improving redundancy and throughput.

6. **Port Ranges**
   - **0-1023**: Well-known ports (e.g., HTTP: 80, FTP: 21).
   - **1024-49151**: Registered ports.
   - **49152-65535**: Dynamic/private ports.

7. **Buffering Challenges**
   - Large buffers at the transport layer can introduce delays (bufferbloat).

---

### Conclusion
The transport layer is vital for enabling reliable, efficient, and organized communication across networks. By understanding its protocols, functions, and characteristics, one can appreciate its role in ensuring seamless data transfer in modern networked systems.



---

### **TCP vs UDP: Complete Notes**

#### **1. Introduction**
TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two most widely used transport layer protocols in computer networking. Both are used for data transmission over networks, but they have distinct characteristics and are suited for different use cases.

---

### **2. Features of TCP and UDP**

#### **TCP (Transmission Control Protocol)**
1. **Connection-Oriented**: Establishes a connection before data transfer (using a 3-way handshake).
2. **Reliable**: Ensures delivery of data using acknowledgments (ACKs) and retransmissions in case of packet loss.
3. **Error Checking**: Performs extensive error checking and correction.
4. **Flow Control**: Uses mechanisms like sliding windows to avoid overwhelming the receiver.
5. **Congestion Control**: Adjusts the transmission rate based on network conditions.
6. **Sequential Data Transfer**: Ensures data is delivered in the correct order.
7. **Heavy Overhead**: Due to acknowledgment, retransmission, and header fields.

#### **UDP (User Datagram Protocol)**
1. **Connectionless**: No handshake; data is sent directly without establishing a connection.
2. **Unreliable**: No guarantees of delivery, acknowledgment, or retransmission.
3. **Error Checking**: Minimal error detection using checksums; no correction.
4. **No Flow or Congestion Control**: Sends data at a constant rate regardless of network conditions.
5. **Fast and Lightweight**: Less overhead due to a simpler header structure.
6. **Order Not Guaranteed**: Packets may arrive out of order.

---

### **3. Use Cases**

#### **TCP Use Cases**
- **Web Browsing (HTTP/HTTPS)**: Reliable transmission is crucial for rendering web pages correctly.
- **Email (SMTP, IMAP, POP3)**: Ensures reliable delivery of messages.
- **File Transfer (FTP)**: Requires error-free and complete file delivery.
- **Remote Access (SSH, Telnet)**: Ensures secure and reliable communication.

#### **UDP Use Cases**
- **Streaming Media (VoIP, Video Streaming)**: Low latency is prioritized over reliability.
- **Online Gaming**: Real-time responsiveness is crucial; occasional packet loss is acceptable.
- **DNS Queries**: Fast and lightweight protocol for querying servers.
- **IoT Communication**: Limited overhead suits resource-constrained devices.

---

### **4. Header Structures**

#### **TCP Header**
The TCP header is complex due to the protocol’s features. It is **20 bytes minimum** and can extend with optional fields.

| **Field**            | **Size (Bits)** | **Description**                                                                 |
|-----------------------|-----------------|---------------------------------------------------------------------------------|
| Source Port          | 16             | Port number of the sending application.                                       |
| Destination Port     | 16             | Port number of the receiving application.                                     |
| Sequence Number      | 32             | Used to keep track of data segments.                                          |
| Acknowledgment Number| 32             | Used for confirming received segments.                                        |
| Data Offset          | 4              | Indicates the size of the TCP header.                                         |
| Reserved             | 3              | Reserved for future use (set to 0).                                           |
| Flags                | 9              | Control bits (e.g., SYN, ACK, FIN, etc.).                                     |
| Window Size          | 16             | Controls flow by specifying the size of the receive window.                   |
| Checksum             | 16             | Ensures integrity of the header and payload.                                  |
| Urgent Pointer       | 16             | Points to urgent data (used rarely).                                          |
| Options              | Variable       | Additional features (e.g., selective acknowledgment).                        |

#### **UDP Header**
The UDP header is simpler, with a fixed size of **8 bytes**.

| **Field**            | **Size (Bits)** | **Description**                                                                 |
|-----------------------|-----------------|---------------------------------------------------------------------------------|
| Source Port          | 16             | Port number of the sending application.                                       |
| Destination Port     | 16             | Port number of the receiving application.                                     |
| Length               | 16             | Length of the entire packet (header + data).                                  |
| Checksum             | 16             | Ensures the integrity of the header and data.                                 |

---

### **5. Comparison Table**

| **Feature**              | **TCP**                                   | **UDP**                              |
|---------------------------|-------------------------------------------|--------------------------------------|
| **Connection Type**      | Connection-oriented                      | Connectionless                      |
| **Reliability**          | Reliable (ACK, retransmission)           | Unreliable                          |
| **Order Guarantee**      | Ensures in-order delivery                | No guarantee of order               |
| **Error Handling**       | Extensive error detection and correction | Basic checksum                      |
| **Speed**                | Slower due to overhead                   | Faster due to minimal overhead      |
| **Header Size**          | 20-60 bytes                              | 8 bytes                             |
| **Use Cases**            | Web, email, file transfer, SSH           | Streaming, gaming, DNS, IoT         |

---

### **6. Key Points to Remember**
1. **TCP is suited for scenarios requiring reliability**, while **UDP is best for real-time, latency-sensitive applications**.
2. **TCP has mechanisms like windowing, acknowledgments, and congestion control**, which make it more robust but slower.
3. **UDP sacrifices reliability for speed** and is ideal for broadcast and multicast communications.
4. **UDP headers are fixed**, making it more efficient for high-speed data transfer with minimal processing.

---

### **Multiplexing and Demultiplexing in the Transport Layer: Complete Notes**

#### **1. Introduction**
The transport layer of the OSI and TCP/IP models provides essential services like **multiplexing** and **demultiplexing** to ensure efficient data transmission between multiple applications and devices over a network.

---

### **2. What is Multiplexing?**

#### **Definition**
- **Multiplexing** refers to the process of combining data from multiple applications at the sender’s side and transmitting it over a single channel or transport layer protocol (like TCP or UDP).
- Each data stream is uniquely identified using **port numbers**, ensuring that data from multiple sources can share the same network connection.

#### **How It Works**
1. Applications running on a system generate data streams.
2. The transport layer assigns a unique **source port number** to each stream.
3. These streams are then combined and sent over the network as segments.
4. The destination is identified by the combination of **IP address** and **port number**.

#### **Example**
- Multiple tabs in a web browser (e.g., YouTube, Gmail) send HTTP/HTTPS requests.
- The transport layer multiplexes these requests into TCP segments, uniquely identified by port numbers.

---

### **3. What is Demultiplexing?**

#### **Definition**
- **Demultiplexing** refers to the process of separating the incoming data streams at the receiver’s side and delivering them to the correct application.
- The transport layer uses **port numbers** to identify and direct each segment to the appropriate application.

#### **How It Works**
1. The network layer delivers incoming packets to the transport layer.
2. The transport layer examines the **destination port number** in each segment.
3. Based on the port number, the segment is directed to the corresponding application or process.

#### **Example**
- When a device receives data packets from a server, the transport layer demultiplexes the packets to deliver them to the correct applications, such as a web browser or email client.

---

### **4. Ports and Socket Identifiers**

- **Port Numbers**: Identify specific processes or applications on a device.
  - Ranges:
    - **0-1023**: Well-known ports (e.g., HTTP: 80, FTP: 21).
    - **1024-49151**: Registered ports (used by specific applications).
    - **49152-65535**: Dynamic or private ports (used temporarily).
- **Socket**: A unique identifier for a connection, defined by:
  - **IP Address** + **Transport Protocol** (TCP/UDP) + **Port Number**.

---

### **5. Role of Multiplexing and Demultiplexing in Transport Protocols**

#### **TCP (Transmission Control Protocol)**
- **Connection-Oriented**: TCP ensures that data streams from multiple applications are reliably multiplexed and delivered.
- **Unique Identification**: TCP uses **four-tuple identification**:
  - Source IP + Source Port + Destination IP + Destination Port.

#### **UDP (User Datagram Protocol)**
- **Connectionless**: UDP does not establish a connection and simply adds port numbers for multiplexing.
- **Fast Demultiplexing**: Lightweight mechanism with minimal overhead, often used for real-time applications.

---

### **6. Examples of Multiplexing and Demultiplexing in Action**

#### **Scenario 1: Web Browser**
- **Multiplexing**:
  - A browser opens multiple tabs, each accessing different websites.
  - Each tab’s data is multiplexed into TCP segments with unique source ports.
- **Demultiplexing**:
  - At the destination server, incoming packets are directed to the corresponding service (HTTP, HTTPS) using the port numbers.

#### **Scenario 2: Streaming and Gaming**
- **Multiplexing**:
  - A gaming application and a music streaming app send data simultaneously.
  - The transport layer assigns unique ports to each stream.
- **Demultiplexing**:
  - The receiving server uses port numbers to separate gaming data from music streaming data.

---

### **7. Key Differences Between Multiplexing and Demultiplexing**

| **Feature**            | **Multiplexing**                          | **Demultiplexing**                       |
|-------------------------|-------------------------------------------|------------------------------------------|
| **Definition**          | Combining multiple data streams into one | Separating a single stream into multiple |
| **Location**            | Sender’s side                            | Receiver’s side                          |
| **Purpose**             | Efficient use of network resources       | Correct delivery to applications         |
| **Use of Port Numbers** | Assigns source port numbers              | Uses destination port numbers            |

---

### **8. Advantages of Multiplexing and Demultiplexing**

#### **Multiplexing**
1. **Efficient Resource Utilization**: Multiple applications share the same transport channel.
2. **Scalability**: Supports simultaneous communication for numerous applications.
3. **Reduced Costs**: Optimizes network bandwidth and reduces transmission costs.

#### **Demultiplexing**
1. **Accurate Data Delivery**: Ensures data reaches the correct application.
2. **Application Separation**: Allows multiple services to run concurrently without interference.
3. **Simplified Communication**: Applications can communicate independently.

---

### **9. Protocol Headers for Multiplexing and Demultiplexing**

#### **TCP Header**
- **Source Port**: Identifies the sender’s application.
- **Destination Port**: Identifies the receiver’s application.
- **Sequence and Acknowledgment Numbers**: Ensure reliable data transfer.

#### **UDP Header**
- **Source Port**: Identifies the sending process.
- **Destination Port**: Identifies the receiving process.
- **Checksum**: Ensures data integrity.

---

### **10. Summary of Multiplexing and Demultiplexing**

| **Aspect**              | **Multiplexing**                                     | **Demultiplexing**                                  |
|--------------------------|-----------------------------------------------------|----------------------------------------------------|
| **Transport Protocols** | TCP, UDP                                            | TCP, UDP                                           |
| **Key Functionality**   | Combines multiple streams                           | Separates streams for delivery                    |
| **Identifiers Used**    | Source IP, Source Port, Protocol                    | Destination IP, Destination Port, Protocol        |
| **Real-World Use**      | Sending data from multiple applications             | Directing received data to appropriate applications |

---

### **Flow Control in TCP (Windowing Mechanism): Complete Notes**

#### **1. Introduction**
Flow control is a crucial mechanism in networking designed to manage the rate at which data is transmitted between a sender and receiver to avoid overwhelming the receiver. TCP (Transmission Control Protocol) implements **flow control** using the **TCP Windowing Mechanism**, which dynamically adjusts the transmission rate based on the receiver's capacity.

---

### **2. Objectives of Flow Control**
1. **Prevent Buffer Overflow**: Ensures the sender does not overwhelm the receiver's buffer space.
2. **Efficient Resource Utilization**: Matches the sender's transmission rate with the receiver's processing capacity.
3. **Reliable Data Transfer**: Guarantees that no data is lost due to an overloaded receiver.

---

### **3. The TCP Windowing Mechanism**
TCP flow control uses a **sliding window protocol** to regulate the flow of data. The window size determines how much data can be sent before the sender waits for an acknowledgment (ACK).

#### **3.1 Sliding Window Concept**
- The **window size** represents the amount of data (in bytes) the sender can transmit without receiving an ACK.
- The size of the window is determined by the receiver’s **advertised window** field in the TCP header.

#### **3.2 Components of the Sliding Window**
1. **Sent and Acknowledged Data**: Data that has been sent and acknowledged by the receiver.
2. **Sent but Not Acknowledged Data**: Data that has been sent but is awaiting an acknowledgment.
3. **Window Size (Unsent Data)**: Data that can be sent without exceeding the receiver’s buffer limit.
4. **Blocked Data**: Data that cannot be sent until the window size increases.

---

### **4. TCP Windowing Mechanism Steps**

#### **4.1 Sender and Receiver Coordination**
1. The receiver specifies its buffer capacity in the **"window size" field** of the TCP header.
2. The sender adjusts the amount of data sent based on this advertised window size.

#### **4.2 Data Transmission Process**
1. The sender transmits data up to the window size.
2. The receiver acknowledges received packets and updates the sender with the remaining buffer space.
3. The sender dynamically adjusts its transmission rate based on the updated window size.

#### **4.3 Example**
- **Initial Window Size**: Receiver advertises a window size of 10 KB.
- **Sender Sends 10 KB of Data**: After sending, it stops and waits for an acknowledgment.
- **Receiver Acknowledges 5 KB**: Receiver updates the window size to 5 KB.
- **Sender Sends the Next 5 KB**: Adjusts the rate based on the updated window size.

---

### **5. Window Size Adjustment**
The window size can increase or decrease dynamically:
1. **Window Expansion**: If the receiver processes data faster, it increases the window size to allow more data transmission.
2. **Window Reduction**: If the receiver’s buffer fills up, it decreases the window size, signaling the sender to slow down.

---

### **6. Zero Window Advertisement**
- If the receiver’s buffer is completely full, it advertises a **window size of 0**.
- The sender halts data transmission and periodically sends a **window probe** to check if the receiver has cleared space.

---

### **7. TCP Header Fields for Flow Control**
The following fields in the TCP header are critical for flow control:
1. **Sequence Number**: Indicates the byte number of the first data byte in the segment.
2. **Acknowledgment Number**: Specifies the next expected byte from the sender.
3. **Window Size**: Advertises the buffer space available on the receiver’s side.

---

### **8. Advantages of TCP Windowing Mechanism**
1. **Efficient Data Flow**: Matches the transmission rate with the receiver’s capacity.
2. **Dynamic Adjustment**: Adapts to varying network and receiver conditions.
3. **Prevents Congestion**: Avoids buffer overflow and packet drops.

---

### **9. Limitations of TCP Flow Control**
1. **Network Congestion**: TCP flow control does not address network congestion; this is managed by **congestion control**.
2. **Delay in Updates**: Delays in updating window size may lead to suboptimal data transmission rates.
3. **Dependency on Receiver Feedback**: Heavily reliant on accurate and timely acknowledgments from the receiver.

---

### **10. Key Terms and Concepts**
| **Term**               | **Definition**                                                                 |
|-------------------------|-------------------------------------------------------------------------------|
| **Sliding Window**      | Mechanism that regulates how much data can be sent before receiving an ACK.   |
| **Advertised Window**   | The size of the receiver's buffer available for data.                         |
| **Zero Window**         | Indicates the receiver's buffer is full, halting transmission temporarily.    |
| **Window Probe**        | A small packet sent by the sender to check if the receiver’s buffer has space.|
| **Dynamic Window Size** | Adjusts the window size based on buffer availability and processing speed.     |

---

### **11. Comparison with Congestion Control**

| **Feature**             | **Flow Control**                          | **Congestion Control**                     |
|--------------------------|-------------------------------------------|--------------------------------------------|
| **Purpose**             | Matches sender’s rate to receiver’s capacity.| Prevents overloading the network.         |
| **Mechanism**           | Uses sliding window protocol.             | Uses algorithms like AIMD (Additive Increase Multiplicative Decrease). |
| **Focus**               | Receiver buffer space.                    | Network capacity.                          |

---

### **12. TCP Window Scaling**
1. **Problem**: The maximum window size in standard TCP (16 bits) is 65,535 bytes, which is insufficient for high-speed, long-distance networks.
2. **Solution**: TCP window scaling (RFC 1323) introduces a scaling factor to expand the window size, supporting up to 1 GB of data.

---

### **13. Summary**
1. **Flow control** ensures the sender does not overwhelm the receiver, avoiding buffer overflows.
2. **TCP windowing mechanism** uses a sliding window protocol to regulate data flow.
3. It dynamically adjusts the transmission rate based on the receiver's available buffer space.
4. The combination of **window size adjustment** and **zero-window handling** makes TCP robust for reliable communication.

---

### **Port Numbers: Complete Notes**

#### **1. Introduction to Port Numbers**
A **port number** is a 16-bit numerical identifier used in networking to specify a particular process or service on a device. Port numbers work with **IP addresses** to distinguish between multiple applications or services running on the same system.

- **Purpose**: Enables the delivery of data to the correct application or service.
- **Range**: 0 to 65,535 (16 bits).

---

### **2. Role of Port Numbers**
- **Transport Layer Identification**: Ports are part of the transport layer in the **TCP/IP model** and help identify endpoints of communication.
- **Application Differentiation**: They allow multiple services (e.g., web servers, email servers) to run on the same device without conflict.
- **Endpoint Addressing**: A combination of **IP address + port number** forms a **socket**, uniquely identifying a network connection.

---

### **3. Port Number Assignment**
Port numbers are managed by the **Internet Assigned Numbers Authority (IANA)**, which divides them into three categories:

#### **3.1 Well-Known Ports**
- **Range**: 0–1,023
- **Purpose**: Reserved for standard services and protocols.
- **Examples**:
  - HTTP: Port 80
  - HTTPS: Port 443
  - FTP: Port 21
  - SSH: Port 22
  - DNS: Port 53

#### **3.2 Registered Ports**
- **Range**: 1,024–49,151
- **Purpose**: Assigned to specific applications or services by IANA upon request.
- **Examples**:
  - Microsoft SQL Server: Port 1433
  - PostgresSQL: Port 5432
  - Minecraft: Port 25565

#### **3.3 Dynamic/Private Ports**
- **Range**: 49,152–65,535
- **Purpose**: Used for temporary or ephemeral connections, often chosen by the operating system.
- **Examples**: When a browser initiates an HTTP request, it often uses a random port from this range for the client-side communication.

---

### **4. How Port Numbers Work**
1. **Client-Side Assignment**:
   - When a client initiates a connection, the operating system assigns a **dynamic port** from the ephemeral port range.
   - Example: A browser accessing a website uses a dynamic port for the client-side of the connection.

2. **Server-Side Assignment**:
   - Servers use well-known or registered ports to listen for incoming client connections.
   - Example: A web server listens on port 80 (HTTP) or 443 (HTTPS) for client requests.

3. **Communication Example**:
   - Client: Uses dynamic port 52,000.
   - Server: Uses port 80 for HTTP.
   - Data Exchange: Client IP:52,000 ↔ Server IP:80.

---

### **5. Port Number Fields in Protocols**
Port numbers are found in the transport layer protocols like **TCP** and **UDP**.

#### **5.1 TCP Header**
- **Source Port**: The port number of the sender.
- **Destination Port**: The port number of the receiver.
- Used for connection-oriented communication.

#### **5.2 UDP Header**
- Similar to TCP, but UDP is connectionless and does not establish a session.

---

### **6. Common Port Numbers**
| **Protocol**      | **Port Number** | **Purpose**                           |
|--------------------|-----------------|---------------------------------------|
| HTTP              | 80             | Web browsing (unsecured).             |
| HTTPS             | 443            | Secure web browsing (TLS/SSL).        |
| FTP               | 21             | File Transfer Protocol.               |
| SSH               | 22             | Secure Shell for remote login.        |
| DNS               | 53             | Domain Name System lookups.           |
| SMTP              | 25             | Sending emails.                       |
| POP3              | 110            | Receiving emails (Post Office Protocol). |
| IMAP              | 143            | Internet Message Access Protocol.     |

---

### **7. Port Number Security**
Port numbers can be exploited by attackers if not secured properly. Common security concerns include:
1. **Port Scanning**: Attackers scan open ports to find vulnerabilities.
2. **Exploitation of Open Ports**: Services on open ports can be targeted with malware or attacks.
3. **Best Practices**:
   - Close unused ports.
   - Use firewalls to filter traffic by port.
   - Implement port forwarding and Network Address Translation (NAT) to hide internal port usage.

---

### **8. Port Forwarding**
- A networking technique where a specific port on a public IP address is mapped to a port on a private IP address.
- Example: Allowing external access to a game server running on port 25565 in a local network.

---

### **9. Summary**
1. **Definition**: Port numbers are 16-bit identifiers for services or processes in networking.
2. **Categories**: Divided into well-known, registered, and dynamic/private ports.
3. **Usage**: Essential for enabling multiple applications and services to run on the same device.
4. **Security**: Proper configuration and monitoring are essential to protect against misuse.

Port numbers, along with IP addresses, form the backbone of the transport layer, enabling effective communication between devices and applications over the internet.


---
