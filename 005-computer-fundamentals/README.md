# 005 — Computer Fundamentals

> Part of [Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path](https://github.com/aris-infosec/aris-infosec)

You cannot effectively defend something you do not understand. Before learning to secure systems, you need to understand what a computer is, what its components do, and how they work together.

---

## Table of Contents

- [Inside a Computer System](#inside-a-computer-system)
- [The Boot Sequence](#the-boot-sequence)
- [Computer Types](#computer-types)
- [Client-Server Model](#client-server-model)
- [Virtualisation](#virtualisation)
- [Cloud Computing](#cloud-computing)

---

## Inside a Computer System

| Component | Role |
|-----------|------|
| **Motherboard** | The main circuit board connecting all components |
| **CPU (Processor)** | Executes instructions and processes data; multi-core CPUs handle parallel tasks |
| **RAM (Memory)** | Short-term, volatile memory for active tasks — fast but wiped when power is off |
| **Storage (SSD/HDD)** | Long-term data storage — SSDs are faster; HDDs offer larger capacity at lower cost |
| **Network Adapter** | Enables communication with other systems; wired or wireless |
| **PSU (Power Supply Unit)** | Converts wall electricity into usable power for all components |
| **GPU (Graphics Card)** | Handles visual processing and outputs to the display |
| **I/O** | Input: keyboard, mouse, microphone — Output: monitor, speakers, printer |

---

## The Boot Sequence

1. **Power button** — Signal sent to the PSU; electricity flows to components
2. **Firmware starts** — UEFI (modern) or BIOS (legacy) initialises hardware
3. **POST (Power-On Self Test)** — Checks that essential hardware is present and functional
4. **Boot device selection** — Firmware reads a priority list to choose where to load the OS from
5. **Bootloader** — A small program on the boot device begins loading the OS into RAM
6. **OS takes over** — The operating system starts and the computer becomes usable

---

## Computer Types

| Type | Characteristics | Examples |
|------|----------------|---------|
| **Laptop** | Portable; battery-powered; suited for everyday tasks | MacBook, Dell XPS, ThinkPad |
| **Desktop** | Stationary; wall-powered; better sustained performance | iMac, HP Pavilion, custom builds |
| **Workstation** | Desktop-form with specialised components for complex tasks (3D, simulations) | HP Z, Dell Precision |
| **Server** | Operates without a UI; runs continuously; serves multiple remote users | Web server, database server |
| **IoT Device** | Network-connected; single-purpose; sends/receives data or commands | Smart thermostat, camera, fitness tracker |
| **Embedded Computer** | May have no network; performs a dedicated internal task | Coffee maker controller, door sensor |

---

## Client-Server Model

Modern computing is built on the idea that some machines *provide* services and others *consume* them.

- **Client** — Initiates requests (e.g., your browser)
- **Server** — Receives requests and returns responses (e.g., a web server)

| Concept | Explanation |
|---------|-------------|
| **Request & Response** | The client asks; the server delivers — or returns an error |
| **Protocol** | Defines rules governing communication — commands, structure, error handling |
| **Port** | A numbered service access point; one server can offer multiple services via different ports |
| **DNS & IP** | The client uses DNS to translate a domain name into the server's IP address |

HTTP is stateless — each request is handled independently. State is simulated using **session IDs**, **cookies**, and **tokens**.

---

## Virtualisation

Virtualisation allows a single physical machine to run multiple independent virtual computers simultaneously.

### Core Components

**Hypervisor** — The software layer that creates and manages virtual machines; splits physical hardware into isolated virtual environments.

| Hypervisor Type | Description | Use Case |
|----------------|-------------|----------|
| **Type 1 (Bare-metal)** | Runs directly on hardware | Production servers, data centres |
| **Type 2 (Hosted)** | Runs on top of an existing OS | Home labs, malware testing, learning |

**Virtual Machines (VMs)** — Fully independent virtual computers, each with their own OS. Tools: VirtualBox, VMware.

**Containers** — Lightweight environments that share the host OS kernel. Package an application and its dependencies without a full OS. Faster and more resource-efficient than VMs but offer less isolation. Tool: Docker.

| Feature | VM | Container |
|---------|-----|-----------|
| OS included | Full OS per VM | Shares host kernel |
| Isolation | Strong | Moderate |
| Startup speed | Slower | Very fast |
| Resource use | Higher | Lower |
| Use case | Full isolation, mixed OS types | Scalable app deployment |

### Benefits
- Hardware consolidation and cost savings
- Safe, isolated environments for security testing
- Faster provisioning and deployment
- Easy scalability and centralised management

---

## Cloud Computing

Cloud computing moves infrastructure off local hardware onto internet-based systems managed by a cloud provider.

### Deployment Types

| Type | Description | Best For |
|------|-------------|---------|
| **Public Cloud** | Shared infrastructure over the internet | Most applications, startups |
| **Private Cloud** | Dedicated infrastructure for one organisation | Banks, healthcare, regulated industries |
| **Hybrid Cloud** | Mix of public and private | Sensitive data private + scalable workloads public |

### Service Models

| Model | You Manage | Provider Manages | Example |
|-------|-----------|-----------------|---------|
| **IaaS** | OS, apps, data | Hardware, networking | AWS EC2, Azure VMs |
| **PaaS** | Apps and data only | Infrastructure + OS | Heroku, Elastic Beanstalk |
| **SaaS** | Just the app | Everything | Gmail, Zoom, Office 365 |

### Major Cloud Providers

| Provider | Known For |
|----------|----------|
| AWS (Amazon) | Market leader; broadest service range |
| Microsoft Azure | Strong enterprise and hybrid integration |
| Google Cloud (GCP) | Data analytics and AI/ML capabilities |
| Alibaba Cloud | Dominant in Asia-Pacific |
| IBM Cloud | Hybrid cloud and AI solutions |

---

*[← Back to Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path Home](https://github.com/aris-infosec/aris-infosec)*
