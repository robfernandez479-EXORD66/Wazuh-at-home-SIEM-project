PowerShell EncodedCommand Detection
Detection ID: 100010
Platform: Windows
Data Source: Sysmon (Event ID 1 – Process Creation)
Author: Robert Fernandez
Project: Wazuh‑at‑Home SIEM Lab

Purpose of This Detection
Attackers frequently use PowerShell’s -EncodedCommand flag to execute malicious payloads while avoiding plain‑text command logging. This detection identifies any PowerShell process that includes the EncodedCommand argument, which is a strong behavioral indicator of:

Execution of obfuscated payloads

Initial access scripts

Persistence mechanisms

Credential harvesting or lateral movement tooling

This rule is designed to alert analysts early in the attack chain.

📡 Log Source & Requirements
Sysmon Configuration
This detection relies on Sysmon Event ID 1 – Process Creation, specifically capturing:

Image

CommandLine

ParentImage

User

IntegrityLevel

Your Sysmon config already includes full command‑line logging, which is required for this rule to function.

Wazuh Custom Rule (ID 100010)
<rule id="100010" level="10">
  <if_group>sysmon_event1</if_group>
  <match>EncodedCommand</match>
  <description>PowerShell EncodedCommand detected</description>
  <mitre>
    <id>T1059.001</id>
  </mitre>
</rule>

Why Level 10?
High‑confidence malicious behavior

No legitimate business use of EncodedCommand in home lab

Ensures visibility in dashboards and alerting pipelines

Test Procedure
To validate the rule, the following command was executed on the Windows endpoint:
powershell.exe -EncodedCommand SQBFAFgA

This intentionally uses a harmless Base64 payload to trigger the detection.

Expected Behavior
Sysmon logs Event ID 1 with the encoded command

Wazuh decodes and matches the keyword EncodedCommand

Rule 100010 fires

Alert appears in Wazuh Dashboard

Actual Behavior
 Alert successfully generated
 Correct rule ID triggered
 JSON alert captured
 Screenshots saved to repo

Evidence & Artifacts
Screenshots
Located in:
09-Screenshots/

encodedcommand_alert_01.png

encodedcommand_alert_02.png (if applicable)

Raw Alert JSON
Located in:
04-Data-Samples/JSON Encoded Command/

encodedcommand_alert.json

These artifacts demonstrate the full detection lifecycle for recruiters and hiring managers.

 MITRE ATT&CK Mapping

Technique	ID	Description
PowerShell	T1059.001	Adversaries may abuse PowerShell to execute malicious commands, scripts, or payloads.

Analyst Interpretation
This alert indicates that PowerShell executed with the EncodedCommand flag. While not inherently malicious, this behavior is strongly associated with:

Obfuscated execution

Fileless malware

Living‑off‑the‑land attacks

Initial access scripts (phishing payloads)

C2 frameworks (Empire, Covenant, Metasploit)

In a production SOC, this would be treated as high‑severity and investigated immediately.

 Recommended Analyst Actions
Review the decoded Base64 payload

Identify the parent process (phishing? scheduled task?)

Check for follow‑on PowerShell activity

Review network connections from the same PID

Validate user account legitimacy

Summary
This detection provides strong visibility into obfuscated PowerShell execution, a common tactic in modern attacks. The rule is simple, high‑signal, and easy to demonstrate in a portfolio — making it an excellent addition to your Wazuh SIEM project.
