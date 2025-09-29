# SIEM Implementation in Azure Cloud




## Description
This project demonstrates the end-to-end deployment and configuration of a Security Information and Event Management (SIEM) solution using Microsoft Sentinel in Azure Cloud. By leveraging the official Sentinel All-in-One solution, the implementation accelerates initial setup tasks such as data connectors, analytics rules, automation playbooks, and content hub solutions.


## Languages and Utilities Used
- **KQL**
- **ARM Templates**
- **Azure CLI & PowerShell**
- **JSON / YAML**



## Environments Used
- **Microsoft Azure Cloud**
  - Microsoft Sentinel
  - Azure Active Directory (AAD)
  - Microsoft 365 Defender Integration
  - Log Analytics Workspace


## Project Step-by-Step Descriptions

### 1. Deployment of Microsoft Sentinel
**Microsoft Sentinel is deployed in Azure using the Sentinel-All-in-One solution.** This approach streamlines initial setup by automatically provisioning a Log Analytics Workspace, enabling Microsoft Sentinel, and installing preconfigured Content Hub solutions (dashboards, detection rules, playbooks, and hunting queries). Key features of this deployment include: Data Connectors, Analytics Rules & Anomaly Detection, Health Diagnostics, and Retention Policies. This automated deployment delivers a ready-to-use cloud-native SIEM, significantly reducing manual effort while providing broad detection coverage; laying the foundation for advanced threat detection, incident response, and security automation.  

---

### 2. Resource Group & Log Analytics Configuration
**After deployment, Microsoft Sentinel creates hundreds of resources within the assigned resource group.** These include container instances, storage accounts, API connections, and numerous templates that represent prebuilt analytics rules and solutions from the Content Hub. A critical component of the deployment is the Log Analytics Workspace, which serves as the data repository for all ingested logs and telemetry. To ensure reliability and performance, diagnostic settings are configured on the workspace to capture all logs and metrics, storing them back into Sentinel for monitoring. This enables visibility into query performance, failures, and other potential issues that could affect security operations.  

---

### 3. Enabling UEBA & Automation Playbooks
**In this next stage, User and Entity Behavior Analytics (UEBA) is enabled to bring AI-driven insights into Sentinel.** UEBA leverages machine learning to detect and alert on unusual patterns of user or entity activity, adding an advanced layer of behavioral analysis to threat detection. By applying it to Azure Active Directory, Sentinel can enrich security monitoring with identity-based anomaly detection. Additionally, automation playbooks are configured by granting Sentinel the necessary permissions within the resource group. These playbooks allow for automated incident response workflows, reducing manual effort and ensuring faster remediation.  

---

### 4. Creating Watchlists
**Next, a watchlist is created in Microsoft Sentinel to track known Tor exit node IP addresses.** Watchlists allow analysts to centralize reference data (e.g., IPs, domains, or user lists) and reuse it across multiple analytics rules. Watchlists are KQL-queryable and easily modifiable, making them a flexible way to maintain dynamic threat intelligence feeds.  

---

### 5. Custom Analytics Rule Creation
**With the watchlist in place, the next step is creating a custom analytics rule in Sentinel to detect suspicious activity.** Using KQL, a rule is designed to identify successful sign-ins originating from Tor exit node IP addresses stored in the watchlist. The rule is enriched with key entities such as user accounts and IP addresses, allowing incidents to provide meaningful context during investigations. Severity levels and MITRE ATT&CK tactics are also assigned, aligning detections with standard threat categories.  

---

### 6. Simulated Attack – Creating a Test User
**To simulate real-world attack scenarios, a new Azure AD user account is created with intentionally unusual configurations.** Security defaults are first disabled to bypass strict baseline protections such as MFA enforcement and legacy authentication blocks, ensuring the account can be used for controlled testing. The account is provisioned with identifiable attributes and assigned both Security Reader and Contributor roles to mimic privileged access. This controlled setup provides a dedicated test identity for triggering and validating Microsoft Sentinel detections, incident creation, and investigation workflows in later stages.  

---

### 7. Simulated Compromise & Attacker Behavior
**This stage intentionally simulates an attacker compromising the test account to produce real telemetry for detection, investigation, and remediation exercises.** Actions include logging in via an anonymizing network, establishing persistence, and disabling or tampering with diagnostic settings. These behaviors are designed to trigger the custom watchlist-driven detections and scheduled analytics rules, generating incidents that trainees can triage. All these activities are performed in a controlled lab environment.  

---

### 8. Incident Management in Sentinel
**In this stage, the focus shifts to managing and investigating incidents generated by Microsoft Sentinel.** The incidents dashboard provides visibility into newly triggered alerts, each representing a potential security event requiring review. Analysts can navigate to the Incidents page to view details such as severity, creation time, and associated IP addresses or accounts. This step demonstrates Sentinel’s ability to transform raw detections into structured incidents, supporting a SOC workflow where alerts are triaged, assigned, and escalated efficiently. It also emphasizes the importance of refining analytic rules to enable effective correlation and reduce noise.  

---

### 9. Incident Investigation
**This phase focuses on the end-to-end investigation workflow for incidents in Microsoft Sentinel.** The incident window provides a structured view of critical details — including entities (users, IPs), related events, and supporting evidence. Analysts can drill into alerts, run queries, and validate findings using external intelligence sources. By correlating log data, external intelligence, and user activity patterns, analysts build a clear case for remediation. The investigation concludes with a decision to disable the compromised account, preventing further lateral movement and reducing the risk of escalation.  

---

### 10. Remediation Actions
**This stage focuses on how to take decisive remediation actions following an investigation in Microsoft Sentinel.** Once malicious activity is confirmed, the priority shifts to containing the threat, securing the environment, and documenting the response. Key steps include: Disabling the compromised account, Removing attacker-created resources, Re-enabling monitoring controls, and Closing & Classifying Incidents. This process highlights Sentinel’s role not only in detecting and investigating threats but also in guiding effective containment and recovery actions.  

---

## Project Summary
This project demonstrates the complete lifecycle of building and operating a cloud-native SIEM in Microsoft Azure using Microsoft Sentinel. Starting with deployment through the Sentinel All-in-One solution, the environment was configured with data connectors, analytics rules, watchlists, and automation playbooks to provide a strong foundation for threat detection and response. By simulating an end-to-end cyber attack and defense scenario, this project highlights Sentinel’s role as a powerful SIEM platform for monitoring, detection, investigation, and response. On top of that, it also provides hands-on experience in security operations and showcases essential skills for working in a modern SOC environment.
