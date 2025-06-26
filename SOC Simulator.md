# TryHackMe: SOC Simulator

### Overview:
Simulated a real-world Security Operations Center (SOC) environment to practice incident response and threat detection. Used Splunk to investigate a range of alerts, analyze malicious activity, and apply the MITRE ATT&CK framework to map adversary behavior.
Key Skills Demonstrated: 
SIEM Analysis (Splunk): Queried and filtered logs to identify indicators of compromise (IOCs) and trace attacker activity.

Incident Response: Conducted step-by-step investigations of suspicious events such as phishing, privilege escalation, and lateral movement.

Threat Intelligence: Correlated evidence with MITRE ATT&CK tactics and techniques to determine adversary behavior patterns.

Analytical Thinking: Made data-driven decisions and documented findings in investigation reports.

Hands-on Blue Team Experience: Simulated responsibilities of a Tier 1 SOC Analyst, triaging alerts and escalating incidents when appropriate.

---
### Process:

I used the introduction to phishing room for this project. The objectives are to monitor and analyze alerts, identify and document susipcious emails and attachments, and lastly create a detailed case report based on my observations on each alert to help the team understand the full scope of the threat. 
Each case report will also clarify if the alert is a true positive or a false positive, if it is found to be true positive then I will clarify and give reasoning as to whether the incident requires esculation or not.

---
### Alert 1: Inbound Email Containing Suspicious External Link
![yhgf](https://github.com/user-attachments/assets/d4747d08-9601-49d3-8c99-44eb5a462569)

The alert was triggered by a link within the email body, I can use the playbook provided to me to see what the next steps would be to analyze the alert.
![ghtb](https://github.com/user-attachments/assets/0fadcd24-bf62-477c-bb30-1dc160156b87)

The first step for phishing email analysis is to search up the sender's domain on TryDetectThis to detect if the domain is safe or malicious. TryDetectThis is an application much like VirusTotal or URLvoid.com.
![788766](https://github.com/user-attachments/assets/a5c405ff-77df-4f78-89f5-3f755b3b5cb1)

TryDetectThis has found this URL to be safe. The next step in the phishing playbook is to see if the sender has communicated with any other recipient and search logs to see if the firewall allowed or blocked access if the recipient clicked on the link.
![prog](https://github.com/user-attachments/assets/20b85835-9cd7-4b31-bf3f-95fc3680103f)

The sender has only communicated with J. Garcia on two seperate occasions, this shows signs that the sender's intentions are not malicious.
![uut](https://github.com/user-attachments/assets/50268f75-1ad8-4bab-a167-111b4da91b91)

There is no log that shows record of the firewall allowing or blocking access so it is assumed J. Garcia did not click on the link. I can put all the information I gathered a write a case report on a false positive alert.
![85969](https://github.com/user-attachments/assets/a521a433-f683-4c9d-b325-3a5b658057b2)

---
### Alert 2: Access to Blacklisted External URL Blocked By Firewall
Normally we would take care of the highest severity alerts first however this alert did not come up before starting the previous one.
![tghg](https://github.com/user-attachments/assets/35fde93f-13e1-4900-ae4c-9dbc6bacf352)

