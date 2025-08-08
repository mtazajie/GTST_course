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

---

Let me know if you want to turn this into a PDF or DOCX!
