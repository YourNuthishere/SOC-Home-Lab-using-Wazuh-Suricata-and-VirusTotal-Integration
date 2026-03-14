Step 1. Get the VirusTotal API from your VirusTotal account 

Step 2. Insert these command with in the Wazuh Manager 

nano /var/ossec/etc/ossec.conf 

<integration>
    <name>virustotal</name>
    <api_key>.....................................</api_key> <!-- Replace with your VirusTotal API key -->
    <group>syscheck_entry_added</group>
    <alert_format>json</alert_format>
  </integration>    

Step 3.Ensure the integration is success

-Restart first 
sudo systemctl restart wazuh-manager
sudo systemctl status wazuh-manager

-Check the Integration Logs
sudo cat /var/ossec/logs/ossec.log | grep -i virustotal

-What to look for in the output:
Success: You should see a line saying: ossec-integratord: INFO: Remote integration connection allowed for: virustotal.
Error: If you see Error: Invalid API key or Connection Refused, double-check your API key and internet connectivity.

Step 4: Live Trigger Test : 

-Trigger a "File Integrity Monitoring" (FIM) event:

On the Windows 10 Target: Create a new file or move a known malicious hash (like an EICAR test file) into a folder monitored by syscheck.

-On the Wazuh Dashboard: * Navigate to Modules -> Integrity Monitoring.
Look for an event where the "VirusTotal" field is populated.
Alternatively, go to Discover and search for integration: virustotal



"To trigger the virustotal alert : You have to temporary disable the window defender"
 