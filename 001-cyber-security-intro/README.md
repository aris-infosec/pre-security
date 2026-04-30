# 001 — Cyber Security Introduction

> Part of [Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path](https://github.com/aris-infosec/aris-infosec)

This module covers the two core disciplines of cybersecurity, the teams and roles within them, and the specialised functions that make up a modern security operation.

---

## Table of Contents

- [Offensive Security](#offensive-security)
- [Defensive Security](#defensive-security)
- [Security Operations Center (SOC)](#security-operations-center-soc)
- [Threat Intelligence](#threat-intelligence)
- [Digital Forensics & Incident Response (DFIR)](#digital-forensics--incident-response-dfir)
- [Malware Analysis](#malware-analysis)
- [Roles Overview](#roles-overview)

---

## Offensive Security

Offensive security is about thinking like an attacker — finding weaknesses before malicious actors do.

The goal is to break into systems, exploit software vulnerabilities, and discover loopholes in applications in a controlled, authorised manner. The insights gained are then used to strengthen defences.

**Key Roles:**

| Role | Description |
|------|-------------|
| Penetration Tester | Tests technology products by actively searching for exploitable vulnerabilities |
| Red Teamer | Simulates a real adversary — attacks an organisation and reports findings from the attacker's perspective |
| Security Engineer | Designs, monitors, and maintains security controls, networks, and systems to prevent attacks |

---

## Defensive Security

Defensive security focuses on two primary goals:

1. **Preventing** intrusions from occurring in the first place
2. **Detecting and responding** to intrusions when they do happen

**Core Tasks:**

- **User awareness training** — Teaching users to recognise social engineering and phishing reduces the human attack surface
- **Asset management** — Maintaining an inventory of all systems and devices you are responsible for protecting
- **Patching and updates** — Keeping all devices current to eliminate known vulnerabilities
- **Preventative controls** — Deploying firewalls and Intrusion Prevention Systems (IPS) to block malicious traffic
- **Logging and monitoring** — Capturing network activity so unauthorised devices or suspicious behaviour can be detected

---

## Security Operations Center (SOC)

A SOC is a dedicated team that monitors an organisation's environment around the clock. Their work covers four main areas:

**Vulnerabilities**
When a weakness is discovered, the priority is to patch it. If no patch exists, compensating controls should be implemented to reduce exploitation risk.

**Policy Violations**
Security policies define acceptable behaviour. Violations — such as uploading confidential data to unauthorised cloud services — must be detected and addressed.

**Unauthorised Activity**
If a user's credentials are stolen and used by an attacker, the SOC must detect and block that access as quickly as possible to limit damage.

**Network Intrusions**
No matter how strong the defences, intrusions can still happen. The SOC's goal is to detect and contain them before they escalate.

---

## Threat Intelligence

Threat intelligence is information about current or potential attackers that helps an organisation build a stronger, more targeted defence.

**Why it matters:**
Adversaries vary widely. Nation-state groups may have political goals, ransomware groups are financially motivated, and some attackers target specific industries. Knowing *who* is likely to target you — and *how* — shapes how you defend.

**Data Sources:**
- Internal: network logs, endpoint telemetry, incident reports
- External: open-source intelligence (OSINT), dark web forums, industry threat feeds

**The Process:**
Raw data is collected → processed into a usable format → analysed to extract actionable insights.

**Output:**
- Identification of threat actors and their motivations
- Understanding of their Tactics, Techniques, and Procedures (TTPs)
- Predictions of likely attacker behaviour
- Recommended defensive and response strategies

---

## Digital Forensics & Incident Response (DFIR)

### Digital Forensics

Digital forensics applies scientific methods to investigate cybercrime and establish facts based on digital evidence. Used in cases involving attacks, intellectual property theft, espionage, and other forms of system misuse.

**Key Evidence Sources:**

| Source | What It Contains |
|--------|-----------------|
| Disk Images | Copies of storage devices — files, deleted data, installed programs, remnants |
| Memory (RAM) | In-memory malware and running processes captured at acquisition time |
| System Logs | Host activity records — traces often remain even if an attacker tries to cover their tracks |
| Network Logs | Traffic data revealing communication patterns and the timeline of an attack |

### Incident Response

A structured process for handling cyber incidents. The goal is to minimise damage and restore normal operations as quickly as possible.

**The Four Phases:**

| Phase | What Happens |
|-------|-------------|
| **Preparation** | Train response teams, deploy tools, implement preventative controls |
| **Detection & Analysis** | Identify that an incident has occurred; assess scope and severity |
| **Containment, Eradication & Recovery** | Stop the spread → remove the threat → restore affected systems |
| **Post-Incident Activity** | Document findings, report to stakeholders, apply lessons learned |

---

## Malware Analysis

The study of malicious software to understand what it does, how it works, and what it targets — so defenders can detect and stop it.

**Common Malware Types:**

| Type | Behaviour |
|------|----------|
| Virus | Attaches to legitimate files or programs; spreads when they are executed |
| Trojan | Disguises itself as a legitimate application but performs malicious actions in the background |
| Ransomware | Encrypts the victim's files and demands payment for the decryption key |

**Analysis Approaches:**

| Method | Description |
|--------|-------------|
| **Static Analysis** | Examines the malware without executing it — reviews code structure, strings, imports, and file metadata |
| **Dynamic Analysis** | Runs the malware in a controlled sandbox and observes its behaviour in real time |

---

## Roles Overview

| Role | Core Responsibility |
|------|-------------------|
| Security Analyst | Monitors the environment, assesses risk, recommends improvements |
| Security Engineer | Builds, tests, and maintains security systems and controls |
| Incident Responder | Detects and responds to active attacks; contains and recovers from incidents |
| Digital Forensics Examiner | Investigates incidents using disk images, memory captures, logs, and network data |
| Malware Analyst | Studies malicious software using static and dynamic techniques |
| Penetration Tester | Ethically simulates attacks to find and report exploitable vulnerabilities |
| Red Teamer | Conducts full-scale adversary simulations to test detection and overall security posture |

---

*[← Back to Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path Home](https://github.com/aris-infosec/aris-infosec)*
