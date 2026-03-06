# 🔐 SIEM Portfolio — Robert Fernandez  
A hands-on, end‑to‑end security monitoring and detection engineering portfolio built using **Wazuh**, **Splunk**, and real-world log data.  
This repository demonstrates my ability to design, deploy, configure, and operate SIEM components while producing actionable detections, dashboards, and incident response playbooks.

---

## 📁 Repository Structure
01-Documentation/        → Project notes, lab guides, architecture explanations
02-Architecture/         → Diagrams, topology, data flow, threat models
03-Configs/              → Wazuh Manager, Indexer, Dashboard, Agent configs
04-Data-Samples/         → Windows, Linux, and network log samples
05-Dashboards/           → JSON exports, screenshots, dashboard designs
06-Detections/           → Rules, decoders, Sigma, correlation logic
07-Playbooks/            → Incident response workflows
08-Scripts/              → Automation, parsing, enrichment scripts
09-Screenshots/          → Evidence of lab work, dashboards, alerts
10-Reports/              → Final write-ups, case studies, incident reports
99-Archive/              → Deprecated or older versions


---

## 🧩 Project Overview

This portfolio showcases:
- **SIEM deployment & configuration** (Wazuh Manager, Indexer, Dashboard)
- **Log ingestion pipelines** for Windows, Linux, and network telemetry  
- **Detection engineering** using Wazuh rules, decoders, and Sigma  
- **Dashboard creation** for threat visibility and SOC workflows  
- **Incident response playbooks** aligned with NIST 800‑61  
- **Automation scripts** for enrichment, parsing, and log validation  
- **Documentation & reporting** for SOC‑style investigations  

---

## 🏗️ Architecture
This lab environment simulates a small SOC environment:

- Wazuh Manager (Ubuntu)
- Wazuh Indexer cluster (single-node for lab)
- Wazuh Dashboard
- Windows 10/11 endpoints
- Ubuntu endpoints
- Optional: Splunk Forwarder + Splunk Free for comparison

**Architecture diagrams** are located in:  
`02-Architecture/`

---

## 🔍 Detection Engineering

All detections are stored in:
06-Detections/
├── Rules/
├── Decoders/
├── Sigma/
└── Correlation/


Each detection includes:
- Purpose  
- Log source  
- MITRE ATT&CK mapping  
- Test data  
- Expected alert behavior  
- Screenshots of triggered alerts  

---

## 📊 Dashboards
Dashboards are exported as JSON and stored in:


📘 README.md — SIEM Portfolio (Wazuh + Splunk + Detection Engineering)
markdown
# 🔐 SIEM Portfolio — Robert Fernandez  
A hands-on, end‑to‑end security monitoring and detection engineering portfolio built using **Wazuh**, **Splunk**, and real-world log data.  
This repository demonstrates my ability to design, deploy, configure, and operate SIEM components while producing actionable detections, dashboards, and incident response playbooks.

---

## 📁 Repository Structure

01-Documentation/        → Project notes, lab guides, architecture explanations
02-Architecture/         → Diagrams, topology, data flow, threat models
03-Configs/              → Wazuh Manager, Indexer, Dashboard, Agent configs
04-Data-Samples/         → Windows, Linux, and network log samples
05-Dashboards/           → JSON exports, screenshots, dashboard designs
06-Detections/           → Rules, decoders, Sigma, correlation logic
07-Playbooks/            → Incident response workflows
08-Scripts/              → Automation, parsing, enrichment scripts
09-Screenshots/          → Evidence of lab work, dashboards, alerts
10-Reports/              → Final write-ups, case studies, incident reports
99-Archive/              → Deprecated or older versions

Code

---

## 🧩 Project Overview

This portfolio showcases:

- **SIEM deployment & configuration** (Wazuh Manager, Indexer, Dashboard)
- **Log ingestion pipelines** for Windows, Linux, and network telemetry  
- **Detection engineering** using Wazuh rules, decoders, and Sigma  
- **Dashboard creation** for threat visibility and SOC workflows  
- **Incident response playbooks** aligned with NIST 800‑61  
- **Automation scripts** for enrichment, parsing, and log validation  
- **Documentation & reporting** for SOC‑style investigations  

---

## 🏗️ Architecture

This lab environment simulates a small SOC environment:

- Wazuh Manager (Ubuntu)
- Wazuh Indexer cluster (single-node for lab)
- Wazuh Dashboard
- Windows 10/11 endpoints
- Ubuntu endpoints
- Optional: Splunk Forwarder + Splunk Free for comparison

**Architecture diagrams** are located in:  
`02-Architecture/`

---

## 🔍 Detection Engineering

All detections are stored in:

06-Detections/
├── Rules/
├── Decoders/
├── Sigma/
└── Correlation/

Code

Each detection includes:

- Purpose  
- Log source  
- MITRE ATT&CK mapping  
- Test data  
- Expected alert behavior  
- Screenshots of triggered alerts  

---

## 📊 Dashboards

Dashboards are exported as JSON and stored in:

05-Dashboards/

Each dashboard includes:

- Use case  
- Data sources  
- Visualizations  
- SOC value  
- Screenshots  

---

## 🛠️ Configurations

All Wazuh and agent configurations are stored in:

03-Configs/

This includes:

- `ossec.conf`  
- Agent enrollment configs  
- Indexer + Dashboard configs  
- Custom rulesets  

---

## 🧪 Sample Logs

To demonstrate detection coverage, sample logs are stored in:

04-Data-Samples/

Examples:

- Windows Security Event Logs  
- Sysmon logs  
- Linux auth logs  
- Network logs (Zeek, Suricata optional)  

---

## 🚨 Incident Response Playbooks

Located in:

07-Playbooks/

Each playbook includes:

- Trigger condition  
- Containment steps  
- Eradication  
- Recovery  
- Evidence collection  
- Reporting  

---

## 📄 Reports & Case Studies

Located in:
10-Reports/


Includes:

- Incident write-ups  
- Threat analysis  
- Lessons learned  
- Executive summaries  

---

## 📌 About This Portfolio

This project reflects my commitment to:

- Continuous learning  
- Real-world security engineering  
- Clear documentation  
- Repeatable, professional workflows  

---

## 📬 Contact

**Robert Fernandez**  
System Support Technician → Transitioning to Cybersecurity  
Austin, TX  



