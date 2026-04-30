# 004 — How the Web Works

> Part of [Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path](https://github.com/aris-infosec/aris-infosec)

This module covers the infrastructure and protocols that power the web — from DNS resolution and HTTP communication to how websites are built, served, and secured.

---

## Table of Contents

- [DNS](#dns)
- [HTTP & HTTPS](#http--https)
- [How Websites Are Built](#how-websites-are-built)
- [Web Infrastructure](#web-infrastructure)
- [Extending Your Network](#extending-your-network)

---

## DNS

**DNS (Domain Name System)** translates human-readable domain names into IP addresses. Without DNS, you would need to memorise numeric addresses instead of names.

**Analogy:** DNS is the internet's phonebook — names map to numbers.

### Domain Hierarchy

Domains are structured in levels, read right to left:

```
Root → TLD → Second-Level Domain → Subdomain
      .com  →      tryhackme      →   admin
```

| Level | Description | Example |
|-------|-------------|---------|
| TLD (Top-Level Domain) | Rightmost part of the domain | `.com`, `.org`, `.co.uk` |
| Second-Level Domain (SLD) | The main domain name | `tryhackme` in `tryhackme.com` |
| Subdomain | Appears left of the SLD | `admin.tryhackme.com` |

### DNS Record Types

| Record | Purpose |
|--------|---------|
| **A** | Maps a domain → IPv4 address |
| **AAAA** | Maps a domain → IPv6 address |
| **CNAME** | Points one domain → another domain name |
| **MX** | Defines mail servers for the domain (with priority values) |
| **TXT** | Stores text data — used for email security (SPF, DMARC) and domain verification |

### How a DNS Request Works

1. **Local cache** — Device checks its own DNS cache first
2. **Recursive DNS server** — If not cached, the request goes to your ISP's DNS resolver
3. **Root servers** — The resolver asks a root server, which directs it based on the TLD
4. **TLD server** — Points to the authoritative nameserver for that domain
5. **Authoritative nameserver** — Returns the actual DNS record
6. **Response returned** — The resolver caches the result and returns it to your device

**TTL (Time To Live)** — Every DNS response includes a TTL value (in seconds) that defines how long the result is cached before a fresh lookup is required.

---

## HTTP & HTTPS

**HTTP (HyperText Transfer Protocol)** is the protocol used to transfer web content between browsers and servers.

- **HTTP** — Fast but sends data in plain text (insecure)
- **HTTPS** — Encrypted version of HTTP; ensures confidentiality, integrity, and authenticity

### URL Structure

```
http://user:password@example.com:80/page?id=1#section
  |        |              |        |    |      |
Scheme  Credentials     Host    Port  Path  Fragment
```

### HTTP Methods

| Method | Action |
|--------|--------|
| **GET** | Retrieve data (read-only) |
| **POST** | Submit data to create a new record |
| **PUT** | Send data to update an existing record |
| **DELETE** | Remove a record |

### HTTP Status Codes

| Range | Category | Common Examples |
|-------|----------|----------------|
| 100–199 | Informational | Request received, processing |
| 200–299 | Success | `200 OK`, `201 Created` |
| 300–399 | Redirection | `301 Moved Permanently`, `302 Found` |
| 400–499 | Client Error | `400 Bad Request`, `401 Unauthorised`, `403 Forbidden`, `404 Not Found` |
| 500–599 | Server Error | `500 Internal Server Error`, `503 Service Unavailable` |

### HTTP Headers

**Request headers (client → server):**

| Header | Purpose |
|--------|---------|
| `Host` | Specifies which website on a shared server is being requested |
| `User-Agent` | Identifies the browser and version |
| `Content-Length` | Size of data in the request body |
| `Accept-Encoding` | Compression formats the client supports |
| `Cookie` | Sends stored session data to the server |

**Response headers (server → client):**

| Header | Purpose |
|--------|---------|
| `Set-Cookie` | Stores data in the browser for future requests |
| `Cache-Control` | How long content should be cached locally |
| `Content-Type` | Data type being returned (HTML, image, JSON, etc.) |
| `Content-Encoding` | How the response body is compressed |

### Cookies

Cookies solve a fundamental problem: HTTP is **stateless** — the server has no memory of previous requests. Cookies let websites simulate state.

**How cookies work:**
1. Server sends a `Set-Cookie` header
2. Browser stores the cookie locally
3. Browser includes the cookie in every subsequent request to that site
4. Server uses the cookie to identify the session or user

> Cookies typically store tokens (unique session identifiers), not passwords directly.

---

## How Websites Are Built

### Front End vs. Back End

- **Front End (Client-Side)** — What the browser renders and the user sees
- **Back End (Server-Side)** — The server that processes requests and generates responses

### HTML

HTML (HyperText Markup Language) defines the structure and content of a webpage.

Key concepts:
- Elements use opening and closing tags (e.g., `<h1>`, `</h1>`)
- **`id`** — unique identifier for a single element
- **`class`** — shared identifier across multiple elements

### JavaScript

JavaScript adds interactivity and dynamic behaviour to web pages.

**What JavaScript can do:**
- Update content in real time without reloading the page
- React to user actions (clicks, hovers, form input)
- Change styles and create animations

### Security Concepts

**Sensitive Data Exposure**
Occurs when a website includes sensitive information in front-end source code — visible to anyone who views the page source. Common examples: leaked credentials, private links, or API keys in HTML or JavaScript.

> Rule: Never include sensitive data in front-end code. Anything sent to the browser can be read by the user.

**HTML Injection**
A vulnerability where unsanitised user input is rendered directly on the page as HTML rather than plain text. If a user submits `<h1>Injected</h1>` and it is displayed without filtering, the browser renders it as actual HTML.

> Prevention: Always sanitise and escape user input before rendering it.

---

## Web Infrastructure

| Component | Role |
|-----------|------|
| **Web Server** | Serves files via HTTP/HTTPS (e.g., Apache, Nginx, Node.js) |
| **Load Balancer** | Distributes traffic across multiple servers; performs health checks |
| **CDN** | Delivers static content from geographically closer servers |
| **Database** | Stores and retrieves website data (MySQL, PostgreSQL, MongoDB) |
| **WAF** | Filters requests before they reach the server; blocks common attacks |

**Static vs. Dynamic Content:**
- **Static** — Fixed files (HTML, CSS, images) served as-is
- **Dynamic** — Generated per-request based on user input or database queries

---

## Extending Your Network

### Port Forwarding

Allows external internet users to reach services hosted inside a private network.

```
External request → Public IP : 80
Router maps it  → Internal server : 192.168.1.10:80
```

Configured on the router. Important distinction: port forwarding *opens a route* — a firewall still controls whether the traffic is *allowed*.

### Firewalls

Controls what network traffic is permitted to enter or leave a network based on rules.

**Decision factors:** Source IP, destination IP, port, protocol (TCP/UDP)

| Type | Behaviour |
|------|----------|
| **Stateful** | Monitors entire connections; makes dynamic decisions; more secure but resource-intensive |
| **Stateless** | Evaluates individual packets against fixed rules; faster but less intelligent |

### VPNs

A **VPN (Virtual Private Network)** creates an encrypted tunnel over the internet, allowing devices on different networks to communicate as if on the same private network.

**Key benefits:**
- Secure remote network access
- Privacy — encrypts traffic from intermediaries
- Anonymity — hides activity from ISPs (dependent on provider policy)

| Technology | Notes |
|-----------|-------|
| PPP | Handles authentication and encryption; not routable on its own |
| PPTP | Transports PPP data; easy to set up; weaker encryption |
| IPSec | Strong encryption at the IP level; widely supported; more complex to configure |

### VLANs

**VLAN (Virtual LAN)** — Logically segments a physical network into isolated groups. Devices share infrastructure but cannot communicate directly with devices on other VLANs. Improves security and traffic management.

---

*[← Back to Pre-Security Fundamentals](https://github.com/aris-infosec/pre-security) · [Learning Path Home](https://github.com/aris-infosec/aris-infosec)*
