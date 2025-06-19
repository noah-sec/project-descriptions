<!-- TITLE -->
<h1 align=center>Enterprise Vulnerability Management Program Implementation</h1>

<!-- INTRODUCTION -->
<p align=center><i><b>Designed a draft vulnerability management policy, secured stakeholder support, and implemented the final approved policy. Vulnerability Analysis and Resolution Capability</b></i></p><hr>

<h3><b>Technologies:</b></h3>

<hr>

<h3><b>Skills:</b></h3>

<hr>


<h3><b>Business Impact:</b></h3>
using industry standards, building security program and risk management maturity, building maturity in the right order of prioritization, asset management, patch management, configuration management, vulnerabilities, vuln mgmt, vuln mgmt capability component of security program, enterprise vulnerability scanning, 
<hr>

<h3><b>Industry Standards and Best Practices:</b></h3>

The organization required the vulnerability management capability component to align with the same standards used to design and implement the rest of the overall security program. These best practices weren't all hard requirements to be implemented entirely, but rather were used collectively to guide and justify security program design decisions.<br><br>

<h4><a href="https://www.nist.gov/cyberframework">1. NIST Cybersecurity Framework (CSF):</a></h4>
<i>A taxonomy of high-level cybersecurity outcomes for a risk management program.</i><br><br>

<b>Risk Governance:</b>
- <b>Govern (GV):</b> The organization’s cybersecurity risk management strategy, expectations, and policy are established, communicated, and monitored.

<b>Risk Management:</b>
- <b>Identify (ID):</b> The organization’s current cybersecurity risks are understood.
- <b>Protect (PR):</b> Safeguards to manage the organization’s cybersecurity risks are used.
- <b>Detect (DE):</b> Possible cybersecurity attacks and compromises are found and analyzed.
- <b>Respond (RS):</b> Actions regarding a detected cybersecurity incident are taken.
- <b>Recover (RC):</b> Assets and operations affected by a cybersecurity incident are restored.

The vulnerability management capability component of a security program plays a part in achieving each of the CSF cybersecurity outcomes, focused mainly around ID and PR. The design and approval of the plan for the vulnerability management capability component is part of GV.<br><br>

<h4><a href="https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final">2. NIST SP 800-53 Security and Privacy Controls for Information Systems and Organizations:</a></h4>
<i>A catalog of security and privacy controls to manage cybersecurity risk.</i><br><br>

<b>Control Categories:</b>
- <b>Access Control</b>
- <b>Awareness and Training</b>
- <b>Audit and Accountability</b>
- <b>Assessment, Authorization, and Monitoring</b>
- <b>Configuration Management</b>
- <b>Contingency Planning</b>
- <b>Identification and Authentication</b>
- <b>Incident Response</b>
- <b>Maintenance</b>
- <b>Media Protection</b>
- <b>Physical and Environmental Protection</b>
- <b>Planning</b>
- <b>Program Management</b>
- <b>Personnel Security</b>
- <b>Personally Identifiable Information Processing and Transparency</b>
- <b>Risk Assessment</b>
- <b>System and Services Acquisition</b>
- <b>System and Communications Protection</b>
- <b>System and Information Integrity</b>
- <b>Supply Chain Risk Management</b>

The vulnerability management capability component of a security program is classified in NIST SP 800-53 under the category of Risk Assessment as Control RA-5 - Vulnerability Monitoring and Scanning.

<b>Control RA-5 - Vulnerability Monitoring and Scanning:</b>
- Monitor and scan for vulnerabilities in the system and hosted applications (Assignment:
organization-defined frequency and/or randomly in accordance with organization-defined
process) and when new vulnerabilities potentially affecting the system are identified and
reported;
- Employ vulnerability monitoring tools and techniques that facilitate interoperability among
tools and automate parts of the vulnerability management process by using standards for:
  - Enumerating platforms, software flaws, and improper configurations;
  - Formatting checklists and test procedures; and
  - Measuring vulnerability impact;
- Analyze vulnerability scan reports and results from vulnerability monitoring;
- Remediate legitimate vulnerabilities (Assignment: organization-defined response times) in
accordance with an organizational assessment of risk;
- Share information obtained from the vulnerability monitoring process and control
assessments with (Assignment: organization-defined personnel or roles) to help eliminate
similar vulnerabilities in other systems; and
- Employ vulnerability monitoring tools that include the capability to readily update the
vulnerabilities to be scanned.<br><br>

<h4><a href="https://csrc.nist.gov/projects/risk-management/about-rmf">3. NIST Risk Management Framework (RMF):</a></h4>
<i>A process that integrates security, privacy, and cyber supply chain risk management activities into the system development life cycle.</i><br><br>

<b>RMF Steps:</b>
- <b>Prepare:</b> Carry out essential activities to help prepare all levels of the organization to manage its security and privacy risks using the RMF.
- <b>Categorize:</b> Inform organizational risk management processes and tasks by determining the adverse impact with respect to the loss of confidentiality, integrity, and availability of systems and the information processed, stored, and transmitted by those systems
- <b>Select:</b> Select, tailor, and document the controls necessary to protect the system and organization commensurate with risk.
- <b>Implement:</b> Implement the controls in the security and privacy plans for the system and organization.
- <b>Assess:</b> Determine if the controls are implemented correctly, operating as intended, and producing the desired outcome with respect to meeting the security and privacy requirements for the system and the organization.
- <b>Authorize:</b> Provide  accountability by requiring a senior official to determine if the security and privacy risk based on the operation of a system or the use of common controls, is acceptable.
- <b>Monitor:</b> Maintain ongoing situational awareness about the security and privacy posture of the system and organization to support risk management decisions.

The vulnerability management capability component of a security program is a security control that was identified as part of the Select RMF step after completing the Categorize step.<br><br>

<h4><a href="https://www.cisecurity.org/controls/v8-1">4. CIS Critical Security Controls:</a></h4>
<i>Guide for prioritizing implementation of security controls and security program components.</i><br><br>

<b>CIS Controls:</b>
- <b>Control 1 - Inventory and Control of Enterprise Assets</b>
- <b>Control 2 - Inventory and Control of Software Assets</b>
- <b>Control 3 - Data Protection</b>
- <b>Control 4 - Secure Configuration of Enterprise Assets and Software</b>
- <b>Control 5 - Account Management</b>
- <b>Control 6 - Access Control Management</b>
- <b>Control 7 - Continuous Vulnerability Management</b>
- <b>Control 8 - Audit Log Management</b>
- <b>Control 9 - Email and Web Browser Protections</b>
- <b>Control 10 - Malware Defenses</b>
- <b>Control 11 - Data Recovery</b>
- <b>Control 12 - Network Infrastructure Management</b>
- <b>Control 13 - Network Monitoring and Defense</b>
- <b>Control 14 - Security Awareness and Skills Training</b>
- <b>Control 15 - Service Provider Management</b>
- <b>Control 16 - Application Software Security</b>
- <b>Control 17 - Incident Response Management</b>
- <b>Control 18 - Penetration Testing</b>

The vulnerability management capability component of a security program is classified in the CIS Controls as Control 7 - Continuous Vulnerabilty Management. The security program already created capability components for each of the preceding controls (1-6).<br>

<b>Control 7 - Continuous Vulnerabilty Management:</b> Develop a plan to continuously assess and track vulnerabilities on all enterprise assets within the enterprise's infrastructure, in order to remediate, and minimize, the window of opportunity for attackers. Monitor public and private industry sources for new threat and vulnerability information.
- <b>CIS Safeguards for Control 7:</b>
  - <b>Safeguard 7.1 - Establish and Maintain a Vulnerability Management Process:</b> Establish and maintain a documented vulnerability management process for enterprise assets. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard.
    - <b>NIST CSF Function:</b> Govern (GV)
  - <b>Safeguard 7.2 - Establish and Maintain a Remediation Process:</b> Establish and maintain a risk-based remediation strategy documented in a remediation process, with monthly, or more frequent, reviews.
    - <b>NIST CSF Function:</b> Govern (GV)
  - <b>Safeguard 7.3 - Perform Automated Operating System Patch Management:</b> Perform operating system updates on enterprise assets through automated patch management on a monthly, or more frequent, basis.
    - <b>NIST CSF Function:</b> Protect (PR)
  - <b>Safeguard 7.4 - Perform Automated Application Patch Management:</b> Perform application updates on enterprise assets through automated patch management on a monthly, or more frequent, basis.
    - <b>NIST CSF Function:</b> Protect (PR)
  - <b>Safeguard 7.5 - Perform Automated Vulnerability Scans of Internal Enterprise Assets:</b> Perform automated vulnerability scans of internal enterprise assets on a quarterly, or more frequent, basis. Conduct both authenticated and unauthenticated scans.
    - <b>NIST CSF Function:</b> Identify (ID)
  - <b>Safeguard 7.6 - Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets:</b> Perform automated vulnerability scans of externally-exposed enterprise assets. Perform scans on a monthly, or more frequent, basis.
    - <b>NIST CSF Function:</b> Identify (ID)
  - <b>Safeguard 7.7 - Remediate Detected Vulnerabilities:</b> Remediate detected vulnerabilities in software through processes and tooling on a monthly, or more frequent, basis, based on the remediation process.
    - <b>NIST CSF Function:</b> Respond (RS)
<br><br>

<h4><a href="https://www.cisecurity.org/controls/v8-1">5. DOE Cybersecurity Program Maturity Model (C2M2):
A guide to developing and measuring maturity of individual program capability components.<br><br>

DOD Cybersecurity Maturity Model Certification (CMMC):
guide timeline and degree of standards implementation depending on type and sensitivity of controlled information

NIST SP 800-171 Protecting Controlled Unclassified Information in Nonfederal Systems and Organizations:
recommended security requirements for protecting the confidentiality of controlled information

NIST SP 800-171A Assessing Security Requirements for Controlled Unclassified Information:
assessment procedures and a methodology that can be used to conduct assessments of the
security requirements in NIST SP 800-171

NIST SP 1800-5 IT Asset Management:
example solution to guide tracking of location and configuration of assets

NIST SP 800-40 Guide to Enterprise Patch Management Planning:
guide to improve enterprise patch management planning to strengthen risk management

NIST SP 800-128 Guide for Security-Focused Configuration Management of Information Systems:
guide to implementation of the information system security aspects of configuration management

Microsoft Cloud Security Benchmarks (MCSB):
prescriptive best practices and recommendations to help improve the security of workloads, data, and services on Azure and multi-cloud environment

CIS Benchmarks:
prescriptive configuration recommendations to help protect systems against threats

DISA Security Technical Implementation Guides (STIGs):
best practices and regulatory compliance, bridges the gap between NIST SP 800-53 and NIST RMF

<h4><a href="https://insights.sei.cmu.edu/library/cert-resilience-management-model-cert-rmm-version-12/">CERT Resilience Management Model (CERT-RMM):</a></h4>
<i>Defines the essential organizational practices that are necessary to manage operational resilience.</i><br><br>

<b>Vulnerability Analysis and Resolution (VAR) Goals and Practices:</b>
- <b>Prepare for Vulnerability Analysis and Resolution:</b> Preparation for vulnerability analysis and resolution activities is conducted.
  - <b>Establish Scope:</b> The assets and operational environments that must be examined for vulnerabilities are identified.
  - <b>Establish a Vulnerability Analysis and Resolution Strategy:</b> An operational vulnerability analysis and resolution strategy is established and maintained.
- <b>Identify and Analyze Vulnerabilities:</b> A process for identifying and analyzing vulnerabilities is established and maintained.
  - <b>Identify Sources of Vulnerability Information:</b> The sources of vulnerability information are identified.
  - <b>Discover Vulnerabilities:</b> A process is established to actively discover vulnerabilities.
  - <b>Analyze Vulnerabilities:</b> Vulnerabilities are analyzed to determine whether they have to be reduced or eliminated.
- <b>Manage Exposure to Vulnerabilities:</b> Strategies are developed to manage exposure to identified vulnerabilities.
  - <b>Manage Exposure to Vulnerabilities:</b> Strategies are developed and implemented to manage exposure to identified vulnerabilities.
- <b>Identify Root Causes:</b> The root causes of vulnerabilities are examined to improve vulnerability analysis and resolution and reduce organizational exposure.
  - <b>Perform Root-Cause Analysis:</b> A review of identified vulnerabilities is performed to determine and address underlying causes.

The vulnerability management capability component of the security program was designed and planned referencing these goals and practices.<br><br>

CISA Cyber Resilience Review (CRR) Supplemental Resource Guides, Volume 4 Vulnerability Management:
A guide to set up a vulnerability management program that aligns to CERT-RMM goals and practices.

NIST SP 800-181 Workforce Framework for Cybersecurity (NICE Framework):
guide to the job role around vulnerability analysis

MITRE Common Vulnerabilities and Exposures (CVE):
identify, define, and catalog publicly disclosed cybersecurity vulnerabilities

MITRE Common Weakness Enumeration (CWE):
list of common software and hardware weakness types that could have security ramifications
(a “weakness” is a condition in a software, firmware, hardware, or service component that, under certain circumstances, could contribute to the introduction of vulnerabilities)

NIST National Vulnerability Database (NVD):
performs enrichment on CVEs that have been published to the CVE List

Common Vulnerability Scoring System (CVSS):
provides a way to capture the principal characteristics of a vulnerability and produce a numerical score reflecting its severity

<hr>

<h3><b>Technical Implementation:</b></h3>

1. [Vulnerability Management Policy Draft Creation](#vulnerability-management-policy-draft-creation)
2. [Mock Meeting with Stakeholders - Policy Buy-In](#step-2-mock-meeting-policy-buy-in-stakeholders)
3. [Policy Finalization and Senior Leadership Sign-Off](#step-3-policy-finalization-and-senior-leadership-sign-off)
4. [Mock Meeting with Server Team - Initial Scan Permission](#step-4-mock-meeting-initial-scan-permission-server-team)
5. [Initial Scan of Server Team Assets](#step-5-initial-scan-of-server-team-assets)
6. [Vulnerability Assessment and Prioritization](#step-6-vulnerability-assessment-and-prioritization)
7. [Distributing Remediations to Remediation Teams](#step-7-distributing-remediations-to-remediation-teams)
8. [Mock Meeting with Server Team - Post-Initial Discovery Scan](#step-8-mock-meeting-post-initial-discovery-scan-server-team)
9. [Mock Meeting with CAB - Implementing Remediations](#step-9-mock-cab-meeting-implementing-remediations)
10. [Remediation Round 1: Outdated Wireshark Removal](#remediation-round-1-outdated-wireshark-removal)
11. [Remediation Round 2: Insecure Protocols & Ciphers](#remediation-round-2-insecure-protocols--ciphers)
12. [Remediation Round 3: Guest Account Group Membership](#remediation-round-3-guest-account-group-membership)
13. [Remediation Round 4: Windows OS Updates](#remediation-round-4-windows-os-updates)
14. [First Cycle Remediation Effort Summary](#first-cycle-remediation-effort-summary)
15. [Ongoing Vulnerability Management (Maintenance Mode)](#first-cycle-remediation-effort-summary)

<hr>

<!-- ... -->
<h3><b>1. Vulnerability Management Policy Draft Creation:</b></h3>
This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.<br>
<a href="https://docs.google.com/document/d/1kJI5_rl7T6AwItJe2nWGbp30LVWOsFcM6tBttlOdUII/edit?usp=sharing">Draft Policy</a>
<hr>

<!-- GET SUBTITLES INTO TRANSCRIPT https://youtu.be/8g6uafc6LjE -->
<h3><b>2. Mock Meeting with Stakeholders - Policy Buy-In:</b></h3>
In this phase, a meeting with the server team introduces the draft Vulnerability Management Policy and assesses their capability to meet remediation timelines. Feedback leads to adjustments, like extending the critical remediation window from 48 hours to one week, ensuring collaborative implementation.
<hr>

<!-- ... -->
<h3><b>3. Policy Finalization and Senior Leadership Sign-Off:</b></h3>
After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.
<a href="https://docs.google.com/document/d/1kx6HUXyCtTHubbG1EeybOmJUSXmvobX731_JExJRTLw/edit?usp=sharing">Finalized Policy</a>
<hr>

<!-- GET SUBTITLES INTO TRANSCRIPT https://youtu.be/lg068WA4SKM -->
<h3><b>4. Mock Meeting with Server Team - Initial Scan Permission:</b></h3>
The team collaborates with the server team to initiate scheduled credential scans. A compromise is reached to scan a single server first, monitoring resource impact, and using just-in-time Active Directory credentials for secure, controlled access.
<hr>

<!-- ... -->
<h3><b>5. Initial Scan of Server Team Assets:</b></h3>
In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.
<a href="https://github.com/noah-sec/projects/blob/main/assets/stig-report.pdf">Initial Scan</a>
<hr>

<!-- ... -->
<h3><b>6. Vulnerability Assessment and Prioritization:</b></h3>
We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Wireshark)
2. Windows OS Secure Configuration (Protocols & Ciphers)
3. Windows OS Secure Configuration (Guest Account Group Membership)
4. Windows OS Updates

<hr>

<!-- ... -->
<h3><b>7. Distributing Remediations to Remediation Teams:</b></h3>
The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.
<a href="https://github.com/noah-sec/projects/blob/main/remediation-email.md">Remediation Email</a>
<hr>

<!-- GET SUBTITLES INTO TRANSCRIPT https://youtu.be/0tjjFewxSNw -->
<h3><b>8. Mock Meeting with Server Team - Post-Initial Discovery Scan:</b></h3>
The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB).
<hr>

<!-- GET SUBTITLES INTO TRANSCRIPT https://youtu.be/zOFPkTa9kY8 -->
<h3><b>9. Mock Meeting with CAB - Implementing Remediations:</b></h3>
The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.
<hr>

<!-- ... -->
<h3><b>10. Remediation Effort (Round 1):</b></h3>
The server team used a PowerShell script to remove outdated Wireshark. A follow-up scan confirmed successful remediation.
<a href="https://github.com/noah-sec/powershell-toolbox/">PowerShell Script</a>
<img width="634" alt="image" src="https://github.com/user-attachments/assets/7b4f9ab2-d230-4458-ac0f-c0ff070ae79a">
<hr>

<!-- ... -->
<h3><b>11. Remediation Effort (Round 2):</b></h3>
The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.
<a href="https://github.com/noah-sec/powershell-toolbox/">PowerShell Script</a>
<img width="630" alt="image" src="https://github.com/user-attachments/assets/0e96120d-8ec9-4f76-8e42-79c752200010">
<hr>

<!-- ... -->
<h3><b>12. Remediation Effort (Round 3):</b></h3>
The server team removed the guest account from the administrator group. A new scan confirmed remediation, and the results were exported for comparison.
<img width="627" alt="image" src="https://github.com/user-attachments/assets/870a3eac-3398-44fe-91c0-96f3c2578df4">
<a href="https://github.com/noah-sec/powershell-toolbox/">PowerShell Script</a>
<hr>

<!-- ... -->
<h3><b>13. Remediation Effort (Round 4):</b></h3>
Windows updates were re-enabled and applied until the system was fully up to date. A final scan verified the changes
<img width="627" alt="image" src="https://github.com/user-attachments/assets/870a3eac-3398-44fe-91c0-96f3c2578df4">
<a href="https://github.com/noah-sec/powershell-toolbox/">PowerShell Script</a>
<hr>

<!-- ... -->
<h3><b>14. First Cycle Remediation Effort Summary:</b></h3>
The remediation process reduced total vulnerabilities by 80%, from 30 to 6. Critical vulnerabilities were resolved by the second scan (100%), and high vulnerabilities dropped by 90%. Mediums were reduced by 76%. In an actual production environment, asset criticality would further guide future remediation efforts.
<hr>

<!-- ... -->
<h3><b>15. Ongoing Vulnerability Management (Maintenance Mode):</b></h3>

After completing the initial remediation cycle, the vulnerability management program transitions into **Maintenance Mode**. This phase ensures that vulnerabilities continue to be managed proactively, keeping systems secure over time. Regular scans, continuous monitoring, and timely remediation are crucial components of this phase. (See [Finalized Policy](https://docs.google.com/document/d/1kx6HUXyCtTHubbG1EeybOmJUSXmvobX731_JExJRTLw/edit?usp=sharing) for scanning and remediation cadence requirements.)

Key activities in Maintenance Mode include:
- **Scheduled Vulnerability Scans**: Perform regular scans (e.g., weekly or monthly) to detect new vulnerabilities as systems evolve.
- **Patch Management**: Continuously apply security patches and updates, ensuring no critical vulnerabilities remain unpatched.
- **Remediation Follow-ups**: Address newly identified vulnerabilities promptly, prioritizing based on risk and impact.
- **Policy Review and Updates**: Periodically review the Vulnerability Management Policy to ensure it aligns with the latest security best practices and organizational needs.
- **Audit and Compliance**: Conduct internal audits to ensure compliance with the vulnerability management policy and external regulations.
- **Ongoing Communication with Stakeholders**: Maintain open communication with teams responsible for remediation, ensuring efficient coordination.

By maintaining an active vulnerability management process, organizations can stay ahead of emerging threats and ensure long-term security resilience.

<hr>

<h3><b>References:</b></h3>

<p>This project was completed as part of an internship as a Cloud Security Engineer.</p><hr>

<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>
