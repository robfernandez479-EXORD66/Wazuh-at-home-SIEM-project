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
Today
how do you create folder layout inside github?
Here’s the clean, no‑nonsense truth: you don’t create a folder layout directly inside GitHub’s website. GitHub’s UI only lets you create one folder at a time, and only if that folder contains at least one file.

But the real way professionals do it — and the way you should do it for your SIEM portfolio — is this:

📁 How to Create a Folder Layout Properly in GitHub
⭐ Method 1 (Recommended): Create folders locally, then push to GitHub
This is the standard workflow used by developers.

1. Clone your repo locally
bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
2. Create your folder structure on your computer
You can do this using File Explorer/Finder or PowerShell:

powershell
mkdir docs, data_samples, spl, dashboards, configs, alerts, playbooks, scripts, screenshots
3. Stage, commit, and push
bash
git add .
git commit -m "Add folder layout"
git push
✔️ All folders now appear in GitHub
✔️ Fastest
✔️ Cleanest
✔️ Works with large structures (like your SIEM project)

⭐ Method 2: Create folders manually in GitHub (slow, not ideal)
GitHub requires each folder to contain at least one file.

Steps:
Go to your repo

Click Add file → Create new file

In the filename box, type something like:

Code
docs/README.md
GitHub will automatically create the docs folder

Repeat for every folder

⚠️ Painful
⚠️ Slow
⚠️ Not good for large structures
⚠️ You must create a file inside each folder

🧠 Which method should you use?
Given your workflow, your SIEM portfolio, and your preference for structured, reproducible steps:

👉 Use Method 1 — local folder creation + git push.  
It keeps your repo clean and lets you build your structure exactly the way you want.

If you want, I can generate a ready-to-run PowerShell script that builds your entire Splunk/Wazuh portfolio folder layout in one shot.

yeah that would be great
Absolutely — here’s a clean, professional, ready-to-run PowerShell script that builds a full SIEM‑portfolio folder layout. It’s structured, reproducible, and matches the way you like to organize your labs and documentation.

📁 PowerShell Script: Create SIEM Portfolio Folder Layout
powershell
# ================================
# SIEM Portfolio Folder Structure
# Author: Robert Fernandez
# ================================

$root = "C:\SIEM-Portfolio"

# Create root folder
New-Item -ItemType Directory -Path $root -Force | Out-Null

# Define folder structure
$folders = @(
    "01-Documentation",
    "02-Architecture",
    "03-Configs",
    "03-Configs\Wazuh-Manager",
    "03-Configs\Wazuh-Indexer",
    "03-Configs\Wazuh-Dashboard",
    "03-Configs\Agents-Windows",
    "03-Configs\Agents-Linux",
    "04-Data-Samples",
    "04-Data-Samples\Windows-Logs",
    "04-Data-Samples\Linux-Logs",
    "04-Data-Samples\Network",
    "05-Dashboards",
    "06-Detections",
    "06-Detections\Rules",
    "06-Detections\Decoders",
    "06-Detections\Sigma",
    "07-Playbooks",
    "08-Scripts",
    "09-Screenshots",
    "10-Reports",
    "99-Archive"
)

# Create folders
foreach ($folder in $folders) {
    New-Item -ItemType Directory -Path "$root\$folder" -Force | Out-Null
}

Write-Host "SIEM Portfolio folder structure created at $root" -ForegroundColor Green
🧩 What This Gives You
✔ A clean, numbered, professional layout
Perfect for GitHub, recruiters, and hiring managers.

✔ Mirrors real SOC workflows
Documentation → Architecture → Configs → Logs → Dashboards → Detections → Playbooks → Scripts → Reports.

✔ Ready for Splunk, Wazuh, Elastic, or hybrid SIEM labs
You can drop configs, screenshots, JSON exports, Sigma rules, and dashboards directly into the structure.

🚀 Want me to generate a GitHub‑ready README.md that explains this entire portfolio layout?
I can build a polished, recruiter‑ready README with:

Overview

Architecture diagram section

Lab workflow

Detection engineering examples

Screenshots placeholders

Professional formatting

Just say the word and I’ll assemble it.

yea
Perfect — I’ll build you a GitHub‑ready, professional README.md that matches the folder structure we created and presents your SIEM portfolio like a seasoned security engineer.

Here’s a polished version you can drop directly into your repo’s root.

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



