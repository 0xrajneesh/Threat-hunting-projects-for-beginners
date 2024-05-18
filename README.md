# Threat hunting projects for beginners

## Network Traffic Analysis for Malicious Activity

Objective: Identify and analyze suspicious network traffic patterns indicative of malware or unauthorized access.
Tasks: Capture network traffic using tools like Wireshark, analyze unusual traffic spikes, identify communication with known malicious IP addresses, and correlate findings with threat intelligence sources.

## Detecting unauthorized processes using Wazuh EDR

Objective: Use EDR tools to detect and investigate potential threats on endpoints.
Tasks: Deploy an EDR solution like CrowdStrike or Carbon Black, monitor for suspicious activities such as unusual process executions, analyze endpoint logs, and respond to detected threats by isolating affected systems.

## Email Phishing Detection and Analysis

Objective: Identify phishing emails and analyze them to understand phishing tactics.
Tasks: Collect and review email logs, identify phishing indicators (e.g., suspicious URLs, attachments), analyze email headers for spoofing attempts, and use sandbox environments to safely open and analyze attachments.

## Malicious PowerShell Script Detection

Objective: Detect and analyze the use of malicious PowerShell scripts within a network.
Tasks: Monitor PowerShell command logs using tools like Sysmon, identify unusual or obfuscated commands, analyze scripts for malicious intent, and create alerts for detected suspicious activities.

## Analyzing Failed Login Attempts for Brute Force Attacks

Objective: Detect and analyze failed login attempts to identify brute force attacks.
Tasks: Collect and analyze authentication logs from various sources (e.g., Windows Event Logs, Linux auth logs), identify patterns of repeated failed attempts, map IP addresses to geographical locations, and correlate with known attack signatures to confirm a brute force attempt.

These projects help beginners develop practical threat hunting skills by analyzing different types of data and using various tools to detect and respond to potential security threats.
