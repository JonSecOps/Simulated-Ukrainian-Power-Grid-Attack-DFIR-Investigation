# Simulated Ukrainian Power Grid Attack & DFIR Investigation

**Project Summary:**

Conducted an end-to-end digital forensics and incident response (DFIR) investigation into a simulated Industrial Control System (ICS) / SCADA cyber-physical intrusion modeled after real-world critical infrastructure attacks. Utilizing an isolated virtual testbed, executed multi-stage threat emulation involving Apache Tomcat exploitation (CVE-2007-2447 Samba privilege escalation) leading to unauthorized manipulation of a 330kV substation circuit breaker.

Performed rigorous live network telemetry capture (tcpdump), volatile RAM acquisition, and dead-box forensic disk imaging of an 8.0GB raw disk image. Maintained strict chain of custody using SHA-256 and MD5 cryptographic hashing (hashdeep). Analyzed evidence via Wireshark and Autopsy, overcoming LVM partition barriers through CLI data carving (strings and grep) to isolate local OS logs (SCADA_ACTUATION_EVENT). Mathematically corroborated a verified 19.20-second cyber-physical grid outage window, delivering a complete PICERL-aligned incident response report.


**Learning Points:**
1. **ICS/SCADA Cyber-Physical Impact Analysis:** Investigated the direct operational consequences of IT compromise bleeding into OT environments, establishing precise timestamps for a 19.20-second unauthorized circuit breaker disruption window.
2. **Dual-Verification Forensic Methodology:** Corroborated network-based intrusion evidence (Wireshark UTC packet arrivals on TCP streams 1111/1112) with host-based dead-box artifacts via advanced CLI data carving (strings on LVM partitions).
3. **Chain of Custody & Cryptographic Integrity:** Enforced enterprise-grade forensic standards by generating, recording, and verifying MD5/SHA-256 cryptographic hashes via hashdeep and Autopsy across every phase of evidence handling.
4. **Network Telemetry & Packet Forensics:** Captured and filtered high-volume live traffic using tcpdump, isolating multi-stage exploitation vectors including HTTP credential decoding in CyberChef and SMB command injection payload inspection.
5. **Host-Based Triage & Filesystem Forensics:** Configured and deployed Autopsy Forensic Browser and dead-box analysis workflows to inspect Linux partition mounts, investigate timeline events, and extract system logs.
6. **Adversary Tactics & Privilege Escalation (MITRE ATT&CK):** Traced an end-to-end attack lifecycle from initial perimeter compromise via weak Apache Tomcat credentials (tomcat:tomcat) to root-level privilege escalation via Samba (CVE-2007-2447).
7. **PICERL Incident Response & Remediation:** Authored structured remediation frameworks covering immediate credential rotation and patch management, alongside strategic long-term hardening like ICS network segmentation and centralized SIEM log forwarding.

**References:**
1. **Analysis of the Cyber Attack on the Ukrainian Power Grid** - https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf
2. **DarkNet Project Initiative** - https://www.youtube.com/watch?v=Yho3ab_-ukI
3. **Oak Ridge National Laboratory Pilot Demonstration of an Attestation and Anomaly Detection Framework using Distributed Ledger Technology for Power Grid Infrastructure** - https://info.ornl.gov/sites/publications/Files/Pub180482.pdf

![image](https://github.com/user-attachments/assets/0b3ec4dd-843a-440e-aff6-c55f1fe94cd5)
