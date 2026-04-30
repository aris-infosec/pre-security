# 002 — Network Fundamentals

> Part of [Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path](https://github.com/aris-infosec/aris-infosec)

This module covers how networks are built, addressed, and organised — from IP and MAC addresses to subnetting, ARP, DHCP, and the full OSI model.

---

## Table of Contents

- [What Is a Network?](#what-is-a-network)
- [IP Addresses](#ip-addresses)
- [MAC Addresses](#mac-addresses)
- [Ping & ICMP](#ping--icmp)
- [LAN Topologies](#lan-topologies)
- [Switches & Routers](#switches--routers)
- [Subnetting](#subnetting)
- [ARP](#arp)
- [DHCP](#dhcp)
- [The OSI Model](#the-osi-model)

---

## What Is a Network?

A network is a collection of connected devices that share resources. This can be as small as two devices or as large as billions — like the internet itself.

**Types:**
- **Private networks** — Small, internal networks (e.g., home or office)
- **Public networks** — Connect private networks together (i.e., the internet)

---

## IP Addresses

An IP (Internet Protocol) address identifies a device on a network. It is divided into four sections called **octets**, each ranging from 0 to 255.

**Types:**
- **Public** — Assigned by your ISP; visible on the internet
- **Private** — Used within local networks (e.g., 192.168.x.x)

Addresses can change between devices but cannot be active on the same network more than once simultaneously.

---

## MAC Addresses

Every network device has a physical network interface with a factory-assigned **MAC (Media Access Control) address**.

- Format: 12-character hexadecimal, written in pairs separated by colons — e.g., `a4:c3:f0:85:ac:2d`
- The **first six characters** identify the manufacturer
- The **last six characters** are a unique identifier for the specific device

> MAC addresses are permanent in hardware but can be *spoofed* in software.

---

## Ping & ICMP

**Ping** tests connectivity between devices using **ICMP (Internet Control Message Protocol)**. It sends *echo request* packets and waits for *echo reply* packets. The round-trip time tells you whether the connection exists and how reliable it is.

```
ping <IP address>
ping <website URL>
```

Pre-installed on both Linux and Windows.

---

## LAN Topologies

A **LAN (Local Area Network)** topology refers to the physical or logical layout of a network.

### Star Topology
Devices connect individually to a central switch or hub.
- ✅ Easy to expand; reliable under normal conditions
- ❌ Central device failure brings down the whole network; extra cabling cost

### Bus Topology
All devices share a single backbone cable.
- ✅ Cheap and simple to set up
- ❌ Bottlenecks under heavy traffic; a single cable failure stops everything

### Ring Topology
Devices form a circular loop; data travels through each device in turn.
- ✅ Less cabling than star; easier to troubleshoot
- ❌ One device or cable failure can affect the entire network

---

## Switches & Routers

### Switch
Connects multiple devices within the same network and directs data only to the intended recipient — unlike older hubs that broadcast to every port.
- Tracks which device is on which port
- Available in 4, 8, 16, 24, 32, or 64 port configurations

### Router
Connects different networks together and determines the best path for data to travel between them — a process called **routing**.
- Operates at Layer 3 (Network) of the OSI model
- Uses routing protocols and metrics to choose optimal paths

---

## Subnetting

Subnetting divides a larger network into smaller, more manageable sub-networks. It improves organisation, security, and efficiency.

A **subnet mask** defines which portion of an IP address refers to the network and which refers to individual hosts.

**The three address types in a subnet:**

| Type | Purpose | Example |
|------|---------|---------|
| **Network Address** | Identifies the network itself — not assignable to a device | `192.168.1.0` |
| **Host Address** | Assigned to individual devices | `192.168.1.100` |
| **Default Gateway** | Usually a router — forwards traffic destined for outside the local network | `192.168.1.254` |

**Benefits of subnetting:**
- Limits broadcast traffic
- Isolates network segments for security (e.g., staff vs. guest Wi-Fi)
- Granular control over traffic flow

---

## ARP

**ARP (Address Resolution Protocol)** links a device's IP address to its MAC address, allowing devices to communicate on a local network.

Every device maintains a local **ARP cache** — a table of known IP-to-MAC mappings.

**How it works:**
1. A device needs to communicate with an IP but has no MAC for it
2. It sends a **broadcast ARP Request** to the entire network
3. The device with that IP responds with an **ARP Reply** containing its MAC address
4. The requesting device stores this mapping in its ARP cache

---

## DHCP

**DHCP (Dynamic Host Configuration Protocol)** automatically assigns IP addresses to devices joining a network.

**The four-step process:**

| Step | Action |
|------|--------|
| **Discover** | The device broadcasts a request to find a DHCP server |
| **Offer** | The DHCP server responds with an available IP address |
| **Request** | The device accepts the offered IP |
| **ACK** | The server confirms the assignment — the device can now use the IP |

---

## The OSI Model

The **OSI (Open Systems Interconnection)** model defines how devices send, receive, and interpret data across a network. It enables interoperability between devices from different manufacturers.

As data moves *down* through the layers (sending), additional information is added at each step — **encapsulation**. The reverse process (receiving) is **decapsulation**.

| Layer | Name | Key Function | Key Protocols |
|-------|------|-------------|---------------|
| 7 | Application | User-facing network services | HTTP, HTTPS, DNS, FTP |
| 6 | Presentation | Data formatting, encryption/decryption | SSL/TLS, JPEG, ASCII |
| 5 | Session | Establishes, manages, and closes sessions | NetBIOS, RPC |
| 4 | Transport | End-to-end delivery; TCP vs UDP | TCP, UDP |
| 3 | Network | Routing and logical addressing | IP, OSPF, RIP |
| 2 | Data Link | MAC addressing; local delivery | Ethernet, Wi-Fi, ARP |
| 1 | Physical | Physical transmission of bits | Cables, switches, signals |

### Layer 4 in Detail — TCP vs UDP

**TCP (Transmission Control Protocol)**
- Connection-based — establishes a link before transmitting
- Guarantees delivery, ordering, and error checking
- Three-Way Handshake: SYN → SYN/ACK → ACK
- Used for web browsing, file transfers, email

**UDP (User Datagram Protocol)**
- Connectionless — sends data without setup
- No delivery guarantee or error checking
- Faster; used for video streaming, VoIP, online gaming

---

*[← Back to Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path Home](https://github.com/aris-infosec/aris-infosec)*
