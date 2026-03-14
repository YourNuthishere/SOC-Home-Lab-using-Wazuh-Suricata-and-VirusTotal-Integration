ON THE WAZUH AGENT (WINDOW )

1. Prerequisites
Suricata requires a driver to "sniff" network packets on Windows.

Download Npcap: Go to  and download the installer.

Install Npcap: During installation, ensure you check the box for "Install Npcap in WinPcap API-compatible mode".

2. Installation
Download the Suricata MSI installer from the .

Run the .msi and follow the defaults. By default, it installs to:

C:\Program Files\Suricata

3. Configuration (suricata.yaml)
Open Notepad++ (as Administrator) and edit C:\Program Files\Suricata\suricata.yaml.

Set Home Network: HOME_NET: "[192.168.1.0/24]" (Replace with your lab's subnet).

Select Interface: Run ipconfig /all in Command Prompt to find your interface name (e.g., "Ethernet"). Update the pcap section:

Enable EVE JSON: Ensure the eve-log is enabled (it usually is by default) so Wazuh can read the output.


🔗 Connecting Windows Suricata to Wazuh Agent

-Open the Wazuh agent configuration file:

C:\Program Files (x86)\ossec-agent\ossec.conf

Add a <localfile> entry to read Suricata’s eve.json:

<localfile>
  <log_format>json</log_format>
  <location>C:\Path\To\suricata\eve.json</location>
</localfile>

-Save the file and restart the Wazuh agent:
net stop wazuh-agent
net start wazuh-agent

ON THE WAZUH MANAGER (UBUNTU )


  <localfile>
    <log_format>json</log_format>
    <location>/var/log/suricata/eve.json</location>
  </localfile>

-Verify Wazuh is receiving logs 
sudo tail -f /var/ossec/logs/alerts/alerts.json

