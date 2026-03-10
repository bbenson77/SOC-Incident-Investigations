# Phishing Unfolding – SOC Investigation

This investigation documents the analysis of a simulated phishing attack within a corporate environment using the TryHackMe SOC Simulator.

The scenario replicates a real SOC workflow where a phishing email leads to malicious activity on a corporate endpoint.

The investigation involves:

• Alert triage  
• SIEM log investigation  
• Endpoint analysis  
• DNS activity analysis  
• Indicator of Compromise identification  
• Attack timeline reconstruction  

The objective is to determine how the attacker gained access, what actions were performed on the system, and whether data exfiltration or command and control activity occurred.

---

# Investigation Environment

Platform
TryHackMe SOC Simulator

SIEM
Splunk

Endpoint
Windows Workstation

Available Investigation Tools

• SIEM log search
• Endpoint virtual machine
• Network telemetry
• Threat intelligence lookups

---

# SOC Investigation Workflow

This investigation follows a structured SOC workflow:

1. Alert Detection  
2. Alert Triage  
3. Log Investigation  
4. Pivot Analysis  
5. Indicator Identification  
6. Attack Timeline Reconstruction  
7. MITRE ATT&CK Mapping  
8. Incident Reporting

---

# Evidence Collection

Screenshots and investigation evidence are stored inside the screenshots folder.

Evidence includes:

• Alert queue screenshots  
• SIEM queries  
• Log evidence  
• Endpoint investigation results  
• Attack timeline reconstruction  
