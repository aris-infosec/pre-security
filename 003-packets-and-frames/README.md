# 003 — Packets & Frames

> Part of [Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path](https://github.com/aris-infosec/aris-infosec)

This module covers how data is broken down and transmitted across networks — including the structure of packets and frames, TCP and UDP in depth, and how ports route data to the right application.

---

## Table of Contents

- [Packets vs. Frames](#packets-vs-frames)
- [TCP](#tcp)
- [UDP](#udp)
- [TCP vs. UDP Summary](#tcp-vs-udp-summary)
- [Ports](#ports)

---

## Packets vs. Frames

When data is transmitted across a network, it is not sent as one continuous stream. It is broken into smaller units — which reduces congestion and allows for efficient, parallel transmission.

**The two main data units:**

| Unit | OSI Layer | What It Contains |
|------|-----------|-----------------|
| **Packet** | Layer 3 — Network | IP header + payload |
| **Frame** | Layer 2 — Data Link | Encapsulates the packet; adds MAC addresses |

**Analogy:** A frame is the envelope; the packet is the letter inside. When the envelope is removed, you are left with the packet.

**Key IP packet headers:**

| Header | Purpose |
|--------|---------|
| **Time to Live (TTL)** | Limits the packet's lifespan to prevent it circulating indefinitely |
| **Checksum** | Detects data corruption during transmission |
| **Source Address** | The IP address of the sender |
| **Destination Address** | The IP address of the intended recipient |

---

## TCP

**TCP (Transmission Control Protocol)** is the reliable, connection-based protocol used when accurate data delivery matters more than raw speed.

### Key Characteristics
- Requires a connection to be established before data transfer begins
- Guarantees delivery and correct ordering via acknowledgements and sequencing
- More reliable but slower than connectionless protocols due to overhead

### TCP Packet Headers

| Header | Description |
|--------|-------------|
| Source Port | Randomly chosen sending port (0–65535) |
| Destination Port | Service port on the receiver (e.g., port 80 for HTTP) |
| Sequence Number | Orders data chunks for correct reassembly |
| Acknowledgement Number | Confirms receipt (sequence number + 1) |
| Checksum | Detects data corruption |
| Flags | Control connection state (SYN, ACK, FIN, RST, etc.) |
| Data | The actual payload being transmitted |

### The Three-Way Handshake

Before any data is transferred, TCP establishes a connection:

```
Client → Server : SYN        (connection request + initial sequence number)
Server → Client : SYN/ACK    (acknowledges client + sends server's sequence number)
Client → Server : ACK         (confirms — connection established)
```

Data transfer begins after the handshake completes.

### Closing a TCP Connection

```
Device A → Device B : FIN
Device B → Device A : ACK
Device B → Device A : FIN
Device A → Device B : ACK   (connection closed)
```

> TCP reserves system resources — connections should be closed as soon as transfer is complete.

---

## UDP

**UDP (User Datagram Protocol)** is the speed-focused, connectionless alternative to TCP.

### Key Characteristics
- **Stateless** — no persistent connection, no handshake
- Data is sent immediately without setup
- No guarantee of delivery, ordering, or error correction
- Designed for applications where some data loss is acceptable

### UDP Packet Headers

| Header | Description |
|--------|-------------|
| Time to Live (TTL) | Prevents packets from circulating indefinitely |
| Source / Destination IP | Sender and receiver addresses |
| Source Port | Randomly chosen sending port |
| Destination Port | Target service port |
| Data | The payload being transmitted |

---

## TCP vs. UDP Summary

| Feature | TCP | UDP |
|---------|-----|-----|
| Connection | Required (handshake) | None |
| Delivery guarantee | Yes | No |
| Ordering | Yes | No |
| Error checking | Yes | No |
| Speed | Slower | Faster |
| Use case | File transfers, web, email | Streaming, gaming, VoIP |

---

## Ports

Ports are numbered entry and exit points on a device that direct traffic to the correct application. Without ports, a device receiving multiple types of traffic would have no way to route it correctly.

**Port range:** 0–65535 (65,536 total)
- **Ports 0–1023** — Well-known ports reserved for standard services
- **Ports 1024–65535** — Available for custom or dynamic applications

### Common Ports to Know

| Protocol | Port | Purpose |
|----------|------|---------|
| FTP | 21 | File transfer between client and server |
| SSH | 22 | Secure remote terminal access |
| HTTP | 80 | Standard web traffic (unencrypted) |
| HTTPS | 443 | Secure web traffic (encrypted) |
| SMB | 445 | File and device sharing (e.g., printers) |
| RDP | 3389 | Remote graphical desktop access |

> These are conventions, not strict requirements. A service can run on a non-standard port, but it must then be specified explicitly (e.g., `192.168.1.1:8080`).

---

*[← Back to Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path Home](https://github.com/aris-infosec/aris-infosec)*
