# EULE-IDPS v2.0

**Intrusion Detection and Prevention System**

Enterprise-grade IDPS combining Wazuh SIEM, Snort IDS, and Python automation to detect and automatically prevent security threats in real-time.

---

## 🏗️ Architecture

┌─────────────────────────────────────────────────────────────┐
│ VMware Virtual Network │
│ (192.168.x.0/24) │
│ │
│ ┌─────────────┐ ┌─────────────┐ ┌────────────┐ │
│ │ Ubuntu │ │ Windows 10 │ │ Kali │ │
│ │ 22.04 │ │ Agent │ │ Linux │ │
│ │ │ │ │ │ │ │
│ │ 192.168.x.10│◄─────┤192.168.x.20 │◄─────┤192.168.x.30│ │
│ │ │ Logs │ │Attack│ │ │
│ │ Wazuh SIEM │ │ Wazuh Agent │ │Attack Tools│ │
│ │ Snort IDS │ │ │ │ │ │
│ │ Python │ │ │ │ │ │
│ └─────────────┘ └─────────────┘ └────────────┘ │
│ ▲ │
│ │ │
│ └──── Active Response (Block/Kill/Disable) │
└─────────────────────────────────────────────────────────────┘

---

## 🛠️ Tech Stack

| Component          | Technology         | Version   |
| ------------------ | ------------------ | --------- |
| **SIEM**           | Wazuh              | 4.7       |
| **IDS**            | Snort              | 3.x       |
| **Automation**     | Python             | 3.10+     |
| **Virtualization** | VMware Workstation | 17.x      |
| **Manager OS**     | Ubuntu Server      | 22.04 LTS |
| **Target OS**      | Windows            | 10 Pro    |
| **Attacker OS**    | Kali Linux         | 2024.x    |

---

## 🛡️ Prevention Capabilities

### Automated Response Actions

- ✅ **IP Blocking** - Firewall rules auto-added for detected attackers
- ✅ **Process Termination** - Malicious processes killed immediately
- ✅ **Account Lockout** - Compromised accounts disabled automatically
- ✅ **Service Isolation** - Suspicious services quarantined

### Detection Rules

- Port scan detection (nmap, masscan)
- Brute-force login attempts
- Lateral movement patterns
- Suspicious process execution
- Unauthorized file access

---

## 📋 Project Phases

### Phase 1: Foundation Setup ⏳

- [x] VMware shared folder configuration
- [x] Git repository initialization
- [x] Project structure creation
- [ ] Ubuntu VM deployment (Wazuh Manager)
- [ ] Windows 10 VM deployment (Agent)
- [ ] Kali VM deployment (Attacker)
- [ ] Network connectivity verification

### Phase 2: Detection Layer 📡

- [ ] Wazuh Manager installation
- [ ] Wazuh Agent deployment to Windows 10
- [ ] Snort IDS integration
- [ ] Custom detection rules configuration
- [ ] Alert generation testing
- [ ] Log flow verification

### Phase 3: Prevention Layer 🚫

- [ ] Wazuh Active Response configuration
- [ ] Firewall automation (iptables/Windows Firewall)
- [ ] Python response orchestration scripts
- [ ] Automated blocking validation
- [ ] Response action testing

### Phase 4: Attack Scenarios 🎯

- [ ] **Scenario 1:** Port Scan Detection → Auto IP Block
- [ ] **Scenario 2:** Brute-Force Attack → Auto Account Lockout
- [ ] **Scenario 3:** Lateral Movement → Auto Service Isolation
- [ ] Evidence collection (logs, screenshots)
- [ ] Results documentation

### Phase 5: Documentation 📝

- [ ] Architecture diagrams
- [ ] Installation step-by-step guides
- [ ] Attack methodology documentation
- [ ] Response playbooks
- [ ] Final project report

---

## 📁 Repository Structure

EULE-IDPS/
│
├── docs/ # Architecture & design documentation
│ ├── architecture.md # System design details
│ └── response-playbooks.md # Incident response procedures
│
├── screenshots/ # Evidence & visual documentation
│ ├── wazuh-dashboard.png
│ ├── agent-connected.png
│ └── attack-blocked.png
│
├── configs/ # Sanitized configuration files
│ ├── ossec.conf # Wazuh manager config
│ ├── local_rules.xml # Custom detection rules
│ └── snort.conf # Snort IDS config
│
├── attack-scenarios/ # Attack documentation
│ ├── port-scan.md # Port scan methodology
│ ├── brute-force.md # Brute-force attack
│ └── lateral-movement.md # Lateral movement simulation
│
├── automation/ # Python response scripts
│ ├── alert_parser.py # Parse Wazuh alerts
│ ├── auto_response.py # Trigger prevention actions
│ ├── ip_blocker.py # Automated IP blocking
│ └── requirements.txt # Python dependencies
│
└── installation/ # Setup guides
├── wazuh-manager.md # Manager installation
├── agent-deployment.md # Agent setup
└── network-setup.md # Network configuration

---

## 🎯 Attack Detection & Prevention Examples

### Example 1: Port Scan Attack

**Attacker Action:** `nmap -sS 192.168.x.20`  
**Detection:** Snort detects scan pattern  
**Prevention:** Wazuh triggers `firewall-drop` → IP blocked  
**Result:** Attacker cannot reach network

### Example 2: Brute-Force Login

**Attacker Action:** `hydra -l admin -P passwords.txt rdp://192.168.x.20`  
**Detection:** Wazuh detects 5+ failed logins in 60s  
**Prevention:** Account locked via active response  
**Result:** Attack stopped, account secured

### Example 3: Malicious Process

**Attacker Action:** Executes `mimikatz.exe` on compromised system  
**Detection:** Wazuh detects suspicious process signature  
**Prevention:** Python script kills process immediately  
**Result:** Credential theft prevented

---

## 🚀 Current Status

**Phase:** 1 - Foundation Setup  
**Progress:** In Development  
**Last Updated:** April 2026

---

## 👨‍💻 About

**Shaheer Hussain**  
Cybersecurity Analyst & Penetration Tester  
Rawalpindi, Pakistan

Security-focused analyst with hands-on experience in Web Application Pentesting, SIEM monitoring, ISO 27001 audits, and network security. Skilled with industry tools like Burp Suite, Nmap, Snort, and Metasploit. Passionate about offensive security and incident response.

### Connect

- 🔗 **LinkedIn:** [linkedin.com/in/shaheer-hussain-cybersec](https://www.linkedin.com/in/shaheer-hussain-cybersec/)
- 💻 **GitHub:** [@Shaheer-Cybersec](https://github.com/Shaheer-Cybersec)
- 🎯 **TryHackMe:** [Cicada664 - Top 6% Globally](https://tryhackme.com/p/Cicada664)
- 📧 **Email:** shaheerch6@gmail.com

---

## 📄 License

This project is for educational and portfolio purposes.

EOF
