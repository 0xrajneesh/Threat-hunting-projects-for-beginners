# Malicious PowerShell Script Detection using Sysmon

## Introduction
PowerShell is a powerful scripting language built into Windows operating systems, often used by attackers to execute malicious commands or scripts. Sysmon (System Monitor) is a Windows system service and device driver that logs system activity to the Windows event log, providing advanced visibility into the operating system. In this project, you will learn how to leverage Sysmon to detect and analyze malicious PowerShell scripts on Windows systems.

## Pre-requisites
- Basic understanding of PowerShell scripting language
- Familiarity with Windows operating system internals.
- Access to a Windows system (physical or virtual) for conducting exercises.
- Administrative privileges on the Windows system to install and configure Sysmon.

## Lab Set-up
- Windows System: Set up a Windows system (Windows 10 or Windows Server) for running PowerShell scripts and installing Sysmon.
- Sysmon: Download and install Sysmon from the official Microsoft Sysinternals website (https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon).
- PowerShell Scripts: Prepare a set of benign and malicious PowerShell scripts for testing purposes. You can create your own or obtain them from reliable sources for research purposes.

## Exercises: Detecting Malicious PowerShell Activity with Sysmon

Objective: Use Sysmon to detect and analyze malicious PowerShell activity on a Windows system.

Scenario: You suspect that an attacker has gained access to a Windows system and is executing malicious PowerShell scripts to further their objectives. Your task is to configure Sysmon to monitor PowerShell activity and detect any malicious behavior.

Step 1: Install and Configure Sysmon:

- Download Sysmon from the official Microsoft Sysinternals website.
- Extract the Sysmon ZIP file and copy the Sysmon.exe executable to a directory on the Windows system.
- Open a command prompt with administrative privileges and navigate to the directory containing Sysmon.exe.
- Run the following command to install Sysmon and configure it with a basic configuration:
```
sysmon.exe -accepteula -i -n
```

Step 2: Execute Malicious PowerShell Script:

- Use a simulated malicious PowerShell script (e.g., a script that downloads and executes a payload from a remote server) for testing purposes.
- Execute the malicious PowerShell script on the Windows system.

Step 3: Review Sysmon Event Logs:

- Open Event Viewer on the Windows system.
- Navigate to the Windows Event Logs and locate the Sysmon logs (Event ID 1).
- Look for events related to PowerShell activity, such as process creation (powershell.exe) and command line execution.

Step 4: Analyze Sysmon Events:

- Analyze the Sysmon events related to PowerShell activity.
- Look for suspicious or unusual command line parameters, execution arguments, and network connections initiated by PowerShell.
- Pay attention to processes spawned by PowerShell, file creations, registry modifications, and any other indicators of malicious behavior.

Step 5: Identify Malicious Activity:

- Identify any events that indicate malicious PowerShell activity, such as attempts to download and execute files from suspicious URLs, modifications to system settings, or unauthorized access to sensitive data.
- Correlate the Sysmon events with known indicators of compromise (IOCs) and threat intelligence sources for further analysis.

Expected Solution:

- If Sysmon logs indicate suspicious PowerShell activity, such as downloading and executing files from unknown or malicious URLs, it is likely indicative of malicious behavior. Take immediate action to investigate and remediate the threat.
- If Sysmon logs do not reveal any suspicious PowerShell activity or if the activity appears benign, continue monitoring the system for any further signs of compromise and consider additional security measures to enhance detection and prevention capabilities.


By completing this exercise, you'll gain practical experience in leveraging Sysmon to detect and analyze malicious PowerShell activity on Windows systems, strengthening your ability to defend against PowerShell-based attacks.
