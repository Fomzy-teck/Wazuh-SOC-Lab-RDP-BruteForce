# Home SOC Lab: RDP Brute-Force Detection & Analysis

## Project Overview
This project demonstrates the deployment of a home Security Operations Center (SOC) lab utilizing the **Wazuh SIEM platform**. The objective was to generate live threat telemetry by simulating an automated Remote Desktop Protocol (RDP) brute-force attack against a target Windows Server endpoint and performing full incident triage, log analysis, and defensive engineering recommendations.

📊 **[Click Here to Read the Full 9-Page Incident Response Report](./Incident_Response_Report_RDP_Brute_Force.pdf)**

---

## Lab Architecture & Components
* **SIEM Manager:** Wazuh SIEM Server (Centralized Log Ingestion & Alerts)
* **Target Endpoint:** Windows Server (Configured with Wazuh Agent & Logging Enabled)
* **Attacking Machine:** Kali Linux (Utilizing automated credential testing utilities)

---

## Threat Simulation & Triage Workflow
1. **The Attack:** Executed a high-velocity password guessing campaign using **Hydra** targeting the default local `Administrator` account on the Windows host.
2. **Log Ingestion:** Captured Windows Security Logs natively and piped them directly into the Wazuh telemetry stream.
3. **Correlation & Analysis:** Investigated the chronological sequence of events spanning two phases:
   * **Phase 1 (03:17:18 UTC):** High-density flood of 14+ authentication failures (**Windows Event ID 4625** / Wazuh Rule 60122).
   * **Phase 2 (03:17:21 UTC):** Successful credential breach and network logon (**Windows Event ID 4624** / Wazuh Rule 92657).

---

## Key Skills Demonstrated
* **SIEM Engineering:** Log parsing, rule correlation, and dashboard analysis within Wazuh.
* **Incident Triage:** Forensic timeline construction, telemetry tracking, and event mapping.
* **Defensive Hardening:** Implementation plans for Wazuh Active Response, Network Level Authentication (NLA), Group Policy account lockout policies, and Sysmon process integration.

---

## Detailed Documentation
The complete, boardroom-ready technical documentation includes raw telemetry payloads, evidence mapping tables, and deep MITRE ATT&CK tactical alignments. 

👉 View the comprehensive documentation here: **[Incident_Response_Report_RDP_Brute_Force.pdf](./Incident_Response_Report_RDP_Brute_Force.pdf)**
