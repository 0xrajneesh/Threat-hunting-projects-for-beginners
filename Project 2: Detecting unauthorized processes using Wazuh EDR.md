# Detecting unauthorized processes using Wazuh EDR
## Introduction
Endpoint Detection and Response (EDR) is a cybersecurity approach focusing on detecting and investigating suspicious activities on endpoints. EDR solutions provide continuous monitoring and analysis, enabling prompt detection and response to security incidents. In this project, you will use Wazuh, an open-source security monitoring tool, to investigate a simulated security incident on an endpoint.

## Pre-requisites
- Basic understanding of endpoint security and incident response.
- Familiarity with Linux and Windows operating systems.
- Basic knowledge of cybersecurity concepts and tools.
## Lab Set-up
1. Operating System:
- A Linux server (e.g., Ubuntu) for Wazuh server installation.
- A Windows virtual machine for the endpoint.
2. Tools:
- Wazuh: For endpoint detection and response.
- VirtualBox or VMware: For creating virtual machines.
3. Network:
- Ensure the Windows VM can communicate with the Wazuh server.

## Exercises
Step 1: Add the following configuration block to the Wazuh agent /var/ossec/etc/ossec.conf file. This allows to periodically get a list of running processes:
```
<ossec_config>
  <localfile>
    <log_format>full_command</log_format>
    <alias>process list</alias>
    <command>ps -e -o pid,uname,command</command>
    <frequency>30</frequency>
  </localfile>
</ossec_config>
```

Step2: Restart the Wazuh agent to apply the changes:
```
sudo systemctl restart wazuh-agent
```
Step 3: Install Netcat and the required dependencies:
```
sudo apt install ncat nmap -y
```

Step 4: Add the following rules to the /var/ossec/etc/rules/local_rules.xml file on the Wazuh server
```
<group name="ossec,">
  <rule id="100050" level="0">
    <if_sid>530</if_sid>
    <match>^ossec: output: 'process list'</match>
    <description>List of running processes.</description>
    <group>process_monitor,</group>
  </rule>

  <rule id="100051" level="7" ignore="900">
    <if_sid>100050</if_sid>
    <match>nc -l</match>
    <description>netcat listening for incoming connections.</description>
    <group>process_monitor,</group>
  </rule>
</group>
```
Step 5: Restart the Wazuh manager to apply the changes:
```
sudo systemctl restart wazuh-manager
```

Visualize the Alert
You can visualize the alert data in the Wazuh dashboard. To do this, go to the Security events module and add the filters in the search bar to query the alerts.
![image](https://github.com/0xrajneesh/Threat-hunting-projects-for-beginners/assets/40385860/30510d00-fe98-4e42-8f9b-1b68c46c3ff2)









