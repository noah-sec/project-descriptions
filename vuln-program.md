<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Enterprise Vulnerability Management Program Implementation</h1>

<!-- INTRODUCTION -->
<p align=center><i><b>Drafted a formal policy, secured stakeholder buy-in, and developed vulnerability management practices for a medium-sized business.</b></i></p>

<hr>

<!-- TECHNOLOGIES -->
<h3><b>Technologies:</b></h3>

- <b>Microsoft Azure</b> (cloud platform)
- <b>Tenable Nessus</b> (vulnerability management platform)
- <b>Windows 10 Pro</b> (virtual machines)
- <b>PowerShell</b> (scripting language)

<hr>

<!-- IMPACT -->
<h3><b>Business Impact:</b></h3>

This project simulates the implementation of a comprehensive enterprise vulnerability management program, from inception to completion.

_**Inception State:**_ the organization has no existing policy or vulnerability management practices in place.

_**Completion State:**_ a formal policy is enacted, stakeholder buy-in is secured, and a full cycle of organization-wide vulnerability remediation is successfully completed.

<hr>

<!-- CONTENTS -->
<h3><b>Contents:</b></h3>

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

<!-- IMPACT 
<h3><b>Business Impact:</b></h3>

<p>This project documentation is currently under construction.</p>
<hr>-->

<!-- ARCHITECTURE 
<h3><b>Technical Architecture:</b></h3>

<p>This project documentation is currently under construction.</p>
<hr>-->

<!-- IMPLEMENTATION 
<h3><b>Technical Implementation:</b></h3>

<p>
</p>
<hr>-->

<!-- TESTING 
### Testing and Validation-->

<!-- LESSONS 
### Lessons Learned-->

<!-- IMPROVEMENTS 
### Future Improvements-->

<!-- REFERENCES -->
<h3><b>References:</b></h3>

<p>This project was completed as part of an internship as a Cybersecurity Support Engineer.</p>

<hr>

<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>

<!-- ANIMATED BOTTOM BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=footer" alt="footer"/>
