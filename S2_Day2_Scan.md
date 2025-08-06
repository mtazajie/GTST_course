# Day 2 – Scanning and Enumeration

## What is Scanning?

- It is the **second phase of ethical hacking**.
- Involves examining or testing a system based on previously gathered information.
- Focuses more on the **system** than on people.
- Scanning helps reveal:
  - Open ports
  - Operating system and service versions
  - Network topology
  - Specific vulnerabilities

## Why Do We Perform Scanning?

- To identify host systems
- To discover open ports
- To detect live systems

---

## Network Scanning

### What is Nmap?

- Nmap is a **network scanning tool**.
- Used for:
  - Network discovery
  - Port scanning
  - OS detection

### Ping Sweep

- Used to check if a system is **online** by sending ICMP packets.
- If a reply is received, the system is **up**.

#### TTL (Time To Live):

- **TTL=64** → Linux system
- **TTL=108** → Windows system

> **TTL Definition**: Specifies how long a packet can exist in a network before being discarded.

#### What does the time detail show?

- It indicates **connection stability**.

---

### Nmap Ping Sweep

```bash
nmap -sn <IP>
````

* For example:
  `nmap -sn 192.168.1.1-255`
* Also works with **CIDR notation**.

#### Important Notes:

* Ping sweep is an **active reconnaissance** method.
* Some admins block ICMP requests:

  * This makes hosts appear down when they are actually up.
* To bypass this:

  ```bash
  nmap -Pn <IP>
  ```

---

## Port Concepts

* Ports serve as **communication endpoints**.
* Two types of protocols:

  1. **TCP**
  2. **UDP**

### Common Ports:

| Port | Service | Description            |
| ---- | ------- | ---------------------- |
| 21   | FTP     | File Transfer Protocol |
| 22   | SSH     | Secure Shell           |
| 23   | Telnet  | Remote terminal        |
| 80   | HTTP    | Unsecured web port     |
| 443  | HTTPS   | Secured web port       |

---

### Port Status:

1. **Open** – Ready to accept requests.
2. **Closed** – Not accepting requests.

---

## Open Port Discovery

### Nmap Syntax Examples:

```bash
nmap <IP>
nmap -Pn <IP> -p <port>
nmap -Pn <IP> -p-
nmap -p 1000 google.com
```

### Suggested Port Scan (using Netcat):

```bash
nc -nv <IP> <port>
```

---

## Scan Methods

### 1. TCP Connect Scan (Default)

* Performs a full **three-way handshake**.

```bash
nmap -sT <IP>
```

### 2. Stealth Scan (SYN Scan)

* Sends **SYN** but doesn't complete handshake (no ACK).
* Less detectable than full TCP scan.

```bash
sudo nmap -sS <IP>
```

### 3. UDP Scan

* Scans using UDP protocol.

```bash
sudo nmap -sU <IP>
```

### 4. Xmas Scan

* Sends FIN, PSH, and URG flags instead of SYN.
* Results are **ambiguous** and often detected by firewalls or tools like Wireshark.

```bash
nmap -sX <IP>
```
## Operating System Detection

- Used to detect the operating system of the host.

### Syntax

```bash
sudo nmap -O [IP]         # OS detection
sudo nmap -A [IP]         # OS and version detection
````

---

## Banner Grabbing

* Retrieves text or metadata that a service sends when you connect to it.
* Useful for identifying service versions.

### Syntax

```bash
nmap -sV [IP]
```

---

## Scan Speeds

* Nmap timing template: `-T<0-5>`

  * Higher value = faster scan
  * Faster scans increase **detection** and reduce **accuracy**.

---

## Nmap Scripting Engine (NSE)

* Allows running scripts on detected ports/services.
* Uses **Lua programming language**.

### Examples

```bash
--script banner            # Banner grabbing
--script vuln              # Test if ports are vulnerable
-sC                       # Load default scripts
```

---

## Saving Nmap Outputs

| Option | Format             |
| ------ | ------------------ |
| `-oG`  | Greppable format   |
| `-oX`  | XML format         |
| `-oN`  | Normal text format |

### Example

```bash
nmap -oN output.txt [IP]
```

---

## Nmap Verbose Mode

* Displays more scan information.

### Syntax

```bash
-v     # Verbose
-vv    # More detail
-vvv   # Much more detail
```

---

## Nmap Firewall Evasion Techniques

1. **Decoy Scan**

   * Obscures the origin IP address.

   ```bash
   nmap -D RND:5 [IP]
   ```

2. **Fragment Scan**

   * Sends fragmented packets to evade detection.

   ```bash
   nmap -f -p21 [IP]
   ```

3. **MAC Address Spoofing**

   * Spoofs the MAC address.

   ```bash
   nmap --spoof-mac Apple [IP]
   nmap --spoof-mac [MAC_ADDRESS] [IP]
   ```

4. **Source Port Manipulation**

   * Changes the source port (e.g., port 21).

   ```bash
   nmap -g 21 -p21 [IP]
   ```

---

**Important**: Always use scanning tools with proper **authorization** and for ethical purposes only.



