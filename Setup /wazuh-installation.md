1. Set up the Wazuh through this :

https://documentation.wazuh.com/current/quickstart.html

2. Make sure all three component of the wazuh is running 

 -systemctl status Wazuh-manager
 -systemctl status Wazuh-indexer 
 -systemctl status Wazuh-dashboard

if not restart it using these command 

 -systemctl restart Wazuh-manager
 -systemctl restart Wazuh-indexer 
 -systemctl restart Wazuh-dashboard

3. Access to dashbaord with the https://<ip of manager>
   access with the given username and credential that provided after the installation 

