<h1>SIEM Implementation in Azure Cloud (Microsoft Sentinel)</h1>


<h2>Description</h2>
</b>This project demonstrates the end-to-end deployment and configuration of a Security Information and Event Management (SIEM) solution using Microsoft Sentinel in Azure Cloud. By leveraging the official Sentinel All-in-One solution, the implementation accelerates initial setup tasks such as data connectors, analytics rules, automation playbooks, and content hub solutions.</b>
<br />


<h2>Languages and Utilities Used</h2>

- <b>KQL</b> 
- <b>ARM Templates</b>
- <b>Azure CLI & PowerShell<b>
- <b>JSON / YAML

<h2>Environments Used </h2>

- <b>Microsoft Azure Cloud</b>
  - <b>Microsoft Sentinel<b>
  - <b>Azure Active Directory (AAD)<b>
  - <b>Microsoft 365 Defender Integration<b>
  - <b>Log Analytics Workspace<b>

<h2>Project walk-through:</h2>
</b>Microsoft Sentinel is deployed in Azure using the Sentinel-All-in-One solution. This approach streamlines initial setup by automatically provisioning a Log Analytics Workspace, enabling Microsoft Sentinel, and installing preconfigured Content Hub solutions (dashboards, detection rules, playbooks, and hunting queries). Key features of this deployment include: Data Connectors, Analytics Rules & Anomaly Detection, Health Diagnostics, and Retention Policies. This automated deployment delivers a ready-to-use cloud-native SIEM, significantly reducing manual effort while providing broad detection coverage; laying the foundation for advanced threat detection, incident response, and security automation.</b>
<br><br>

<b>After deployment, Microsoft Sentinel creates hundreds of resources within the assigned resource group. These include container instances, storage accounts, API connections, and numerous templates that represent prebuilt analytics rules and solutions from the Content Hub. A critical component of the deployment is the Log Analytics Workspace, which serves as the data repository for all ingested logs and telemetry. To ensure reliability and performance, diagnostic settings are configured on the workspace to capture all logs and metrics, storing them back into Sentinel for monitoring. This enables visibility into query performance, failures, and other potential issues that could affect security operations.<b>
<br><br>

<b>In this next stage, User and Entity Behavior Analytics (UEBA) is enabled to bring AI-driven insights into Sentinel. UEBA leverages machine learning to detect and alert on unusual patterns of user or entity activity, adding an advanced layer of behavioral analysis to threat detection. By applying it to Azure Active Directory, Sentinel can enrich security monitoring with identity-based anomaly detection. Additionally, automation playbooks are configured by granting Sentinel the necessary permissions within the resource group. These playbooks allow for automated incident response workflows, reducing manual effort and ensuring faster remediation.<b>
<br><br>

<b>In this stage, a watchlist is created in Microsoft Sentinel to track known Tor exit node IP addresses. Watchlists allow analysts to centralize reference data (e.g., IPs, domains, or user lists) and reuse it across multiple analytics rules. Watchlists are KQL-queryable and easily modifiable, making them a flexible way to maintain dynamic threat intelligence feeds.<b>


