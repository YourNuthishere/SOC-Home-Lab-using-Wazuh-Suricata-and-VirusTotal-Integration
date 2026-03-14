# SOC Home Lab – Wazuh + Suricata + VirusTotal

## Overview
This is a personal Security Operations Center (SOC) Home Lab designed to simulate real-world network monitoring and endpoint security scenarios. The lab integrates **Wazuh**, **Suricata**, and **VirusTotal** to detect and analyze security events in a controlled environment.

The goal of this lab is to practice monitoring network activity, analyzing logs, and testing threat detection techniques.

---

## Objectives
- Deploy Wazuh SIEM and agents on Windows and Ubuntu machines  
- Configure Suricata on the agent to forward network logs (`eve.json`) to the Wazuh dashboard  
- Monitor endpoint logs and network events  
- Test connectivity (ICMP Ping) and discover open ports using Nmap  
- Integrate VirusTotal for threat intelligence and malware detection  
- Simulate downloading malicious files to test detection and alerting  
- Collect, analyze, and visualize security events centrally  

---

## Lab Architecture
The lab consists of the following components:

- **Attacker Machine:** Kali Linux (used for Nmap scanning and ICMP ping testing)  
- **Victim Machine:** Windows 10 with Wazuh Agent and Suricata configured  
- **SIEM Server:** Ubuntu running Wazuh Manager  
- **Threat Intelligence:** VirusTotal for checking file hashes and detecting malicious files  
