

### Types of Computer Networks


#### 1. **Personal Area Network (PAN)**
   - **Purpose**: Connects devices within a short range, typically around a single user.
   - **Technology Used**: Bluetooth, Infrared (IrDA), Zigbee.
   - **Range**: ~1 to 100 meters.
   - **Transmission Speed**: High (variable based on technology).
   - **Applications**: Home, medical, offices, and educational sectors.
   - **Additional Point**: **Wireless PAN (WPAN)** is often implemented using Bluetooth, making it useful in wearable tech and IoT devices.

---

#### 2. **Local Area Network (LAN)**
   - **Purpose**: Connects computers and devices in a limited area like homes, schools, or offices.
   - **Technology Used**: Ethernet, Wi-Fi.
   - **Range**: Up to 2 km.
   - **Transmission Speed**: Very High (usually between 100 Mbps to several Gbps).
   - **Applications**: Office and home networking, computer labs, and libraries.
   - **Additional Point**: LANs are often enhanced with **Power over Ethernet (PoE)** technology, which reduces the need for separate power cables for network devices like IP cameras and VoIP phones.

---

#### 3. **Campus Area Network (CAN)**
   - **Purpose**: Connects multiple LANs across a campus or corporate buildings.
   - **Technology Used**: Ethernet, Fiber optics.
   - **Range**: Typically 1 – 5 km.
   - **Transmission Speed**: High; varies by deployment but generally fast within the campus.
   - **Applications**: University campuses, industrial areas, and large office buildings.
   - **Additional Point**: CANs benefit from a centralized network administration, which allows efficient monitoring and control of data flow within a confined area.

---

#### 4. **Metropolitan Area Network (MAN)**
   - **Purpose**: Connects LANs across a metropolitan area, typically a city.
   - **Technology Used**: Fiber Distributed Data Interface (FDDI), Synchronous Optical Network (SONET), ATM.
   - **Range**: 5 to 50 km.
   - **Transmission Speed**: Moderate to High.
   - **Applications**: City-wide networks, telecoms, internet providers.
   - **Correction**: Transmission speed and fault tolerance are medium, with redundancy often introduced via **dual-ring topologies** to enhance resilience.
   - **Additional Point**: A MAN can employ **ring-based redundancy** to provide better fault tolerance than many standard LANs.

---

#### 5. **Wide Area Network (WAN)**
   - **Purpose**: Connects computers and LANs across large geographic distances, often globally.
   - **Technology Used**: Leased Lines, MPLS, Satellite Links.
   - **Range**: Above 50 km, typically nationwide or global.
   - **Transmission Speed**: Variable (often lower than LANs or MANs due to distance and congestion).
   - **Applications**: The Internet, multinational organizations.
   - **Correction**: WANs, although slower in speed, are often built on **Multiprotocol Label Switching (MPLS)** for optimized routing.
   - **Additional Point**: **SD-WAN** (Software-Defined WAN) is increasingly used in WANs to manage and optimize bandwidth and routing flexibly over multiple network paths.

---

### Other Types of Computer Networks

1. **Wireless Local Area Network (WLAN)**
   - Acts like a LAN but uses wireless tech (Wi-Fi).
   - **Point**: WLANs are essential for portable devices and support multiple channels for concurrent connections.

2. **Storage Area Network (SAN)**
   - High-speed network of storage devices accessible by multiple servers.
   - **Point**: SANs use protocols like **Fibre Channel** and **iSCSI** for fast, block-level data access.

3. **Passive Optical Local Area Network (POLAN)**
   - A point-to-multipoint LAN using optical fibers, designed for scalability and low energy use.
   - **Point**: POLAN supports high bandwidth with minimal active components, ideal for hotels and high-density buildings.

4. **Enterprise Private Network (EPN)**
   - Used by businesses needing secure connectivity between multiple locations.
   - **Point**: EPNs often employ **virtual private LAN services (VPLS)** for secured, flexible connections.

5. **Virtual Private Network (VPN)**
   - Extends a private network across the internet, allowing secure remote access.
   - **Point**: **Split tunneling** in VPNs allows users to route some traffic via the VPN and the rest directly to the internet.

6. **Home Area Network (HAN)**
   - LAN within a home for connecting personal devices.
   - **Point**: HANs are increasingly IoT-enabled, allowing control of appliances and security systems.
