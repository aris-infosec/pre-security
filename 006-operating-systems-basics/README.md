# 006 — Operating Systems Basics

> Part of [Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path](https://github.com/aris-infosec/aris-infosec)

Every device runs an operating system underneath everything else. This module covers what an OS is, what it does, how you interact with it, and why understanding it matters for security.

---

## Table of Contents

- [What Is an Operating System?](#what-is-an-operating-system)
- [Core OS Duties](#core-os-duties)
- [OS Security Functions](#os-security-functions)
- [Interacting with the OS](#interacting-with-the-os)
- [The OS Landscape](#the-os-landscape)
- [Summary Glossary](#summary-glossary)

---

## What Is an Operating System?

An **operating system (OS)** is the core software layer that manages a computer's hardware, applications, and resources. It acts as the bridge between users, applications, and physical hardware — ensuring everything can work together without conflict.

**Analogy:**
- Hardware = runways, radar, aircraft
- Applications = airlines and passengers
- Operating System = air traffic control — coordinating everything so nothing collides

### Privilege Layers

| Layer | Description |
|-------|-------------|
| **Kernel Space** | The core of the OS — has unrestricted access to hardware and system resources |
| **User Space** | Where applications run — limited permissions; must request kernel services to interact with hardware |

---

## Core OS Duties

| Function | What It Does | Real Example |
|----------|-------------|-------------|
| **Process Management** | Schedules and prioritises programs running simultaneously | Running a browser and music player at the same time |
| **Memory Management** | Allocates RAM to applications; keeps them isolated from each other | Multiple apps open without one overwriting another's memory |
| **File Management** | Organises files in a hierarchy; manages paths and access permissions | Saving a document; setting a file to read-only |
| **User Management** | Handles user accounts, authentication, and permissions | Login screen; different users with different access levels |
| **Device Management** | Loads drivers so applications can use hardware | Plugging in a USB device and having it recognised automatically |

---

## OS Security Functions

The OS is the first and most fundamental layer of system security.

| Security Feature | How It Works |
|-----------------|-------------|
| **Authentication** | Verifies identity before granting access (password, PIN, biometrics) |
| **Permissions** | Controls what users and processes can read, write, or execute |
| **Isolation** | Keeps processes separated — user space cannot directly access kernel space |
| **System Protection** | Prevents unauthorised modification of core system files |

> A compromised OS means everything running on top of it is compromised too. This is why OS-level exploits are so valuable to attackers.

---

## Interacting with the OS

### GUI (Graphical User Interface)
- Uses visual elements: icons, windows, menus
- Intuitive for everyday users
- Best for general tasks and ease of use
- **Analogy:** Using a navigation app — tap a destination, get directions automatically

### CLI (Command-Line Interface)
- Text-based: you type commands directly
- Requires knowing syntax and command names
- Faster, more precise, and more powerful for advanced tasks, scripting, and automation
- **Analogy:** Entering exact GPS coordinates manually

Both can perform the same actions — the difference is control and efficiency:
- GUI → click through folders to find a file
- CLI → run a single command to list all files instantly

---

## The OS Landscape

| Category | Purpose | Examples |
|----------|---------|---------|
| **Desktop OS** | Personal computing, productivity, gaming | Windows, macOS, Ubuntu, Fedora |
| **Server OS** | Hosting websites, databases, cloud services — often headless (no GUI) | Windows Server, Ubuntu Server, Debian, RHEL |
| **Mobile OS** | Smartphones and tablets — touch-based, power-efficient | Android, iOS |
| **Embedded OS** | IoT devices, appliances, vehicles — lightweight, task-specific | Embedded Linux, FreeRTOS, QNX |
| **Virtual/Cloud OS** | Virtual machines, containers, data centre workloads | Ubuntu LTS, Amazon Linux, Alpine Linux |

---

## Summary Glossary

| Term | Definition |
|------|------------|
| **Operating System** | Core software managing hardware, applications, and system resources |
| **Kernel Space** | Privileged OS area with direct hardware access |
| **User Space** | Where applications run, with limited permissions |
| **GUI** | Visual interface using windows, icons, and menus |
| **CLI** | Text-based interface where commands are typed directly |
| **Process Management** | OS function scheduling and prioritising running programs |
| **Memory Management** | OS function allocating and isolating RAM between processes |
| **Authentication** | Verifying a user's or process's identity |
| **Permissions** | Rules controlling what can be read, written, or executed |

---

*[← Back to Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path Home](https://github.com/aris-infosec/aris-infosec)*
