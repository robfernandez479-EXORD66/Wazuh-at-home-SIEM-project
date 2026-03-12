# Incident Response Playbooks

This folder contains SOC-style playbooks for responding to alerts generated in the Wazuh-at-home SIEM environment.

---

## 1. Purpose of This Folder

To document repeatable, structured workflows for:

- Alert triage  
- Investigation steps  
- Containment and remediation  
- Evidence collection  

---

## 2. Typical Playbooks

| Playbook | Description |
|----------|-------------|
| `powershell-encodedcommand.md` | Steps to investigate suspicious PowerShell activity |
| `ssh-bruteforce.md` | Workflow for handling repeated SSH authentication failures |
| `fim-alert.md` | Response steps for unauthorized file changes |

---

## 3. Playbook Structure

Each playbook includes:

- Alert summary  
- MITRE technique  
- Required logs  
- Investigation steps  
- Analyst decision points  
- Containment actions  
- Recovery steps  

---

## 4. Related Folders

- `06-Detections/` — Alerts that trigger these playbooks  
- `10-Reports/` — Case studies based on these workflows  
