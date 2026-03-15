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
