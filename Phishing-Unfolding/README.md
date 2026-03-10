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

---

# Initial Alert

The investigation began with an alert triggered in the SOC dashboard related to suspicious email activity.

Alert Name:
Suspicious Attachment Found in Email

Severity:
Low

Alert Type:
Phishing

The alert indicated that an email containing an attachment was delivered internally within the organisation.

The attachment file identified in the alert was:

forceupdate.ps1

PowerShell script attachments are highly suspicious because they can execute commands directly on a Windows system.

---

# Alert Investigation

The alert was assigned and investigated through the SIEM platform.

Using the Splunk interface, logs were reviewed to identify the origin of the email and associated activity on the endpoint.

Relevant log data included:

Email metadata  
Sender address  
Recipient address  
Attachment name  
Associated endpoint events

The email metadata revealed the following:

Sender:
yani.zubair@tryhatme.com

Recipient:
michelle.smith@tryhatme.com

Attachment:
forceupdate.ps1

The subject line indicated the script was presented as a legitimate update.

Subject:
Force update fix

This is a common phishing technique where attackers disguise malicious scripts as internal updates.

---

# Log Analysis

Log events were analysed using Splunk to identify any activity associated with the attachment.

Logs confirmed that the attachment was delivered but no execution of the PowerShell script was observed in the available telemetry.

No malicious child processes or command execution events were triggered.

This indicates the script was not executed on the endpoint.

---

# Alert Classification

After reviewing the available logs and system activity, the alert was classified as a True Positive phishing attempt.

The attachment was confirmed to be suspicious due to the PowerShell script format.

However, no evidence was found indicating that the script executed on the endpoint.

The threat was therefore contained before execution.

---

# Indicators of Compromise

Email Sender

yani.zubair@tryhatme.com

Attachment

forceupdate.ps1

---

# Impact Assessment

The phishing email successfully reached the recipient mailbox.

However, there is no evidence that the malicious attachment was executed.

No endpoint compromise or lateral movement was observed.

The risk was therefore limited to attempted phishing delivery.

---

# MITRE ATT&CK Mapping

Technique

T1566 – Phishing

Sub Technique

T1566.001 – Spearphishing Attachment

---

# Conclusion

This investigation identified a phishing attempt involving a PowerShell script attachment delivered via email.

The script did not execute on the endpoint and no additional malicious activity was detected.

The alert was therefore closed as a confirmed phishing attempt with no system compromise.
