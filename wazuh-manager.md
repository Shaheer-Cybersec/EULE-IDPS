# Wazuh Manager Installation

**Date:** April 21, 2026

## Environment
- **OS:** Ubuntu 22.04 LTS (64-bit)
- **RAM:** 4GB
- **Disk:** 50GB
- **Network:** 
  - VMnet8 (NAT): 192.168.17.128 - Internet access
  - VMnet1 (Host-Only): 192.168.248.128 - Internal IDPS network

## Installation Method
All-in-One installation using official Wazuh installer v4.7

## Installation Commands

### 1. System Update
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Download Installer
```bash
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
```

### 3. Execute Installation
```bash
sudo bash ./wazuh-install.sh -a
```

Installation duration: ~12 minutes

### 4. Extract Credentials Backup
```bash
sudo tar -xvf wazuh-install-files.tar
```

## Access Information

**Dashboard URL:** https://192.168.248.128  
**Username:** admin  
**Password:** [Stored securely in wazuh-install-files.tar]

## Installed Components

- **Wazuh Indexer** - Elasticsearch-based log storage and search
- **Wazuh Server** - SIEM engine and manager
- **Wazuh Dashboard** - Web interface (port 443)
- **Filebeat** - Log shipper to indexer

## Post-Installation Status

✅ Dashboard accessible via browser  
✅ All services running  
✅ 283 baseline alerts detected (manager self-monitoring)  
✅ Ready for agent deployment

## Dashboard Features Available

- Endpoint Security (Configuration Assessment, Malware Detection, File Integrity)
- Threat Intelligence (Threat Hunting, Vulnerability Detection, MITRE ATT&CK)
- Security Operations (IT Hygiene, PCI DSS, GDPR, HIPAA compliance)
- Cloud Security (Docker, AWS, Google Cloud, GitHub monitoring)

## Next Steps
- Deploy Wazuh agent to Windows 10 VM (192.168.248.129)
- Configure custom detection rules
- Integrate Snort IDS
- Test attack scenarios

## Screenshots
- `2026-04-21_wazuh-login.png` - Login page
- `2026-04-21_wazuh-dashboard.png` - Main dashboard overview
- `2026-04-21_ubuntu-install.png` - Installation completion

