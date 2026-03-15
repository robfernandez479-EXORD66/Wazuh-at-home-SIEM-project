# Playbook: Suspicious PowerShell EncodedCommand

**Detection ID:** WZ-DET-001  
**Rule ID (Wazuh):** 100010  
**MITRE ATT&CK:** T1059.001 – PowerShell  
**Severity:** High  

---

## 1. Trigger condition

This playbook is initiated when Wazuh generates an alert for:

- `powershell.exe` executed with the `-EncodedCommand` flag  
- Matched by Wazuh rule ID `100010`  

---

## 2. Initial triage

**2.1 Confirm the alert**

- Open Wazuh → Security Events  
- Filter by:
  - Rule ID: `100010`
  - Agent: affected Windows host
- Verify:
  - Process: `powershell.exe`
  - Command line contains: `EncodedCommand`

**2.2 Collect basic context**

- Identify:
  - **User account** running PowerShell  
  - **Host name** / IP  
  - **Time of execution**  
  - **Parent process** (if available via Sysmon)  

---

## 3. Investigation steps

**3.1 Decode the EncodedCommand**

- Extract the Base64 string from the command line
- Decode using PowerShell:

```powershell
[System.Text.Encoding]::Unicode.GetString([System.Convert]::FromBase64String("<Base64Here>"))

Review the decoded script:

Is it benign admin activity?

Is it downloading or executing payloads?

Is it modifying registry, services, or scheduled tasks?

3.2 Check for related activity

Look for:

Additional PowerShell executions around the same time

Network connections from the host to unknown IPs/domains

New services, scheduled tasks, or startup items

3.3 Review host history

Has this host generated prior alerts?

Is this user associated with admin or scripting tasks?

4. Containment actions
If activity appears malicious or highly suspicious:

Isolate the host from the network (if possible in your lab)

Terminate any suspicious PowerShell processes

Disable the affected user account (lab context: document this step)

5. Eradication & recovery
Remove any malicious scripts or tools identified

Revert unauthorized configuration changes

Consider restoring the system from a clean snapshot (lab)

6. Documentation
For each incident:

Capture:

Alert details (screenshot)

Decoded command content

Actions taken

Store related evidence in:

04-Data-Samples/

09-Screenshots/

10-Reports/ (full write-up)

7. Tuning opportunities
Add exclusions for known, legitimate admin scripts that use EncodedCommand

Combine with:

Parent process conditions

User context

Time-of-day patterns

8. Related artifacts
Detection: 06-Detections/powershell-encodedcommand.md

Sample alert: 04-Data-Samples/encodedcommand-alert.json

Screenshots: 09-Screenshots/encodedcommand_*.png

Report: 10-Reports/encodedcommand-incident-report.md
