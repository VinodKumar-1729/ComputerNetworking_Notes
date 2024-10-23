### Classless Inter-Domain Routing (CIDR) – Part 1

Classless Inter-Domain Routing (CIDR) is a method for allocating IP addresses and managing IP routing more efficiently than the older class-based addressing system. CIDR was introduced in 1993 by the Internet Engineering Task Force (IETF) as a solution to the rapid exhaustion of IPv4 addresses and to improve routing efficiency.

#### 1. **Background: Classful Addressing**
Before CIDR, IP addresses were divided into classes: 
- **Class A**: IPs from `0.0.0.0` to `127.255.255.255` with a default subnet mask of `255.0.0.0`, offering a huge range of host addresses.
- **Class B**: IPs from `128.0.0.0` to `191.255.255.255` with a default subnet mask of `255.255.0.0`, offering a medium-sized range.
- **Class C**: IPs from `192.0.0.0` to `223.255.255.255` with a default subnet mask of `255.255.255.0`, offering smaller address ranges.

Classful addressing was inefficient because networks were forced to adopt one of the predefined classes even if they didn’t need that many addresses. For example, an organization might only need 300 addresses, but if they used Class B, they would waste over 65,000 addresses.

#### 2. **CIDR Basics**
CIDR eliminates the rigid class structure of IP addressing, allowing for more flexible assignment of IP addresses. Instead of using default subnet masks based on address classes, CIDR uses **variable-length subnet masking (VLSM)**, which allows subnetting based on actual need.

A CIDR address consists of:
- **IP address** (e.g., `192.168.0.0`)
- **Slash notation** (e.g., `/24`), indicating the number of bits used for the network portion of the address.

For example, `192.168.0.0/24` means the first 24 bits are the network part, and the remaining 8 bits are used for hosts.

#### 3. **CIDR Notation**
CIDR uses **slash notation** to represent the subnet mask:
- An IP address is followed by a forward slash (`/`) and the number of bits that represent the network portion. 
- For example, `192.168.10.0/24` has a subnet mask of `255.255.255.0`, indicating that the first 24 bits are used for the network and the remaining 8 bits for host addresses.

| **CIDR Notation** | **Equivalent Subnet Mask** | **Number of Hosts** |
|-------------------|----------------------------|---------------------|
| /8                | 255.0.0.0                  | 16,777,214          |
| /16               | 255.255.0.0                | 65,534              |
| /24               | 255.255.255.0              | 254                 |
| /28               | 255.255.255.240            | 14                  |

#### 4. **Subnetting in CIDR**
CIDR allows networks to be divided into subnets based on requirements. With CIDR, network administrators can use any number of bits for the network prefix, leading to a more efficient use of IP addresses. 

For example, `192.168.1.0/24` can be divided into two subnets:
- `192.168.1.0/25` (Subnet 1) — First 25 bits for network, 7 bits for host addresses.
- `192.168.1.128/25` (Subnet 2) — First 25 bits for network, 7 bits for host addresses.

Each subnet can have 128 addresses, but only 126 are usable for hosts because two addresses are reserved (network and broadcast addresses).

---

### Classless Inter-Domain Routing (CIDR) – Part 2

#### 5. **Aggregation (Supernetting)**
CIDR also supports **route aggregation** or **supernetting**, which means multiple IP addresses (or networks) can be represented as a single route in the routing table, reducing the complexity of routing and saving memory and processing power.

For example, the following networks:
- `192.168.0.0/24`
- `192.168.1.0/24`
- `192.168.2.0/24`

Can be combined into a single aggregate route using CIDR as `192.168.0.0/22`. This encompasses the entire address range of `192.168.0.0` to `192.168.3.255`.

#### 6. **CIDR Example Calculation**
Let’s calculate the available IP addresses for a CIDR block.

Given the CIDR notation `192.168.10.0/26`:
- **/26** means that the first 26 bits are for the network and the remaining 6 bits are for hosts.
- The subnet mask for /26 is `255.255.255.192`.
- The number of host addresses is calculated as `2^(32 - 26) = 2^6 = 64`. But two addresses are reserved (network and broadcast), so the number of usable IP addresses is `64 - 2 = 62`.

This CIDR block can allocate IPs for 62 hosts, ranging from `192.168.10.1` to `192.168.10.62`.

#### 7. **Advantages of CIDR**
- **Efficient Address Allocation**: CIDR allows IP addresses to be allocated based on actual need, avoiding waste of addresses.
- **Scalable**: Networks can be split or aggregated easily.
- **Reduces Routing Table Size**: Route aggregation reduces the number of routes in the routing table, optimizing routing performance.
- **Better Utilization of IPv4**: CIDR delays IPv4 exhaustion by making more efficient use of available address space.

#### 8. **CIDR in IPv6**
CIDR is also applicable to **IPv6**, where the addresses are written in the same slash notation. For example, `2001:db8::/32` defines an IPv6 network with a 32-bit network prefix.

IPv6 has 128-bit addresses, so the flexibility offered by CIDR is critical in managing such large address spaces.

---

This concludes the detailed explanation of CIDR. The key takeaway is that CIDR enables flexible and efficient IP addressing and routing, making it a critical part of modern network design.
