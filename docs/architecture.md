# EULE-IDPS Architecture

## System Design

### Overview
EULE-IDPS is a distributed intrusion detection and prevention system designed to monitor, detect, and automatically respond to security threats in real-time.

### Components

**1. Wazuh Manager (Ubuntu 22.04)**
- Centralized SIEM platform
- Log aggregation and analysis
- Alert generation engine
- Active response orchestration

**2. Wazuh Agent (Windows 10)**
- Endpoint monitoring
- Log forwarding to manager
- Local security scanning
- Response action execution

**3. Attacker System (Kali Linux)**
- Red team simulation platform
- Attack vector testing
- Penetration testing tools

### Network Architecture
All systems operate on isolated VMware virtual network (NAT/Host-Only) to ensure attack traffic doesn't affect production environment.

## Detection Flow
1. Agent monitors system activity
2. Logs forwarded to Wazuh Manager
3. Manager analyzes logs against detection rules
4. Alerts generated for suspicious activity
5. Active response triggered if threshold met

## Prevention Flow
1. Alert triggers active response script
2. Python automation evaluates threat severity
3. Prevention action selected (block IP, kill process, etc.)
4. Action executed on target system
5. Confirmation logged and reported

*Detailed implementation to be added during build phase*
