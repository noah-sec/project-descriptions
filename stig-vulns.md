<!-- TITLE -->
<h1 align=center>Cloud Endpoint Security Management, Compliance, <br>Hardening, and Automation</h1>

<!-- INTRODUCTION -->
<p align=center><b><i>Developed a Microsoft Windows 10 Enterprise virtual machine endpoint golden image in Microsoft Azure cloud platform. Ran DISA STIG compliance audit scan with Tenable Nessus vulnerability scanner. Automated implementation of audit findings with PowerShell scripts.</i></b></p><hr>

<h3><b>Technologies:</b></h3>

<p>
  
- <b>Microsoft Azure</b>: enterprise cloud computing platform (for resilient IaaS)
- <b>Microsoft Windows 10 Enterprise</b>: enterprise virtual machine operating system (for golden image in Azure hypervisor)
- <b>Tenable Nessus</b>: enterprise vulnerability scanner (for configuration and compliance auditing)
- <b>STIGs</b>: DISA configuration management guidelines (for USDOD system security regulatory compliance)
- <b>PowerShell</b>: Microsoft script interpreter and CLI/shell (for automation and configuration management)
- <b>Microsoft Intune Configuration Manager</b>: systems deployment and management (for running scripts on managed endpoints)
- <b>Azure Virtual Desktop:</b> cloud virtual DaaS (for desktop service delivery standardization and security)

<i>IaaS: infrastructure-as-a-service</i><br>
<i>STIG: Security Technical Implementation Guide</i><br>
<i>DISA: Defense Information Systems Agency</i><br>
<i>USDOD: United States Department of Defense</i><br>
<i>CLI: command-line interpreter</i>
<i>DaaS: desktop-as-a-service</i>
</p>
<hr>

<h3><b>Skills:</b></h3>

<p>

- <b>Cloud Security Management and Administration</b>
- <b>Systems Security Management and Administration</b>
- <b>Endpoint/Desktop Security Management and Administration</b>
- <b>USDOD Regulatory Compliance for IA-enabled Systems</b>
- <b>DISA STIG Configuration and Compliance Auditing</b>
- <b>Vulnerability Management</b>
- <b>Configuration Management</b>
- <b>Scripting and Automation</b>

<i>IA: Information Assurance</i>
<hr>

<h3><b>Business Impact:</b></h3>

<p>This project enabled an organization to deploy a desktop service for its users where the base desktop image was compliant with defense industry regulations based on information systems security guidelines. Using an enterprise cloud platform enabled the organization to scale resources quickly and efficiently with lower latency across wide geographic service areas, without investing in physical infrastructure. Infrastructure as a service (IaaS) enabled the organization to create virtual resources like servers and networks in the cloud rather than on premises. An enterprise operating system is more functional when integrated into an enterprise internal network.<br>

Using a virtual machine enabled the organization to allocate compute and storage irrespective of physical hardware, and to snapshot and template the underlying operating system and machine. A golden image enabled the organization to create a known secure, compatable, and tested machine state to be used as a base image for other machines to copy as a template. An enterprise vulnerability scanner enabled the organization to assess its assets for configuration or patching issues, and to audit its assets for compliance. DISA STIGs are best practices for securing specific systems, required by some USDOD policies (see DODD 8500.1 and DODD 8500.2) to be implemented in IA-enabled environments. Hardening systems at the endpoint level is a first line of defense that makes initial access and exploitation more difficult for criminals and makes it easier for defenders to detect security events.<br>

Script automation enabled the organization to repeat the same work quickly across many endpoints. The scripts contributed individually were 1/6 of the total team effort for automating the process of creating a compliant golden image as the base for the desktop service. Microsoft Intune enabled the organization to centrally manage and rapidly apply changes to multiple endpoints simultaneously. Configuration Manager, part of Microsoft Intune, enabled the organization to execute configuration automation scripts on endpoints. Desktop as a service (DaaS) enabled the organization to securely deliver a desktop experience to users over the cloud, allowing for both flexibility and standardization of the end user experience (UX). Azure Virtual Desktop enabled the organization to deliver cloud DaaS to users, with virtual desktop images derived from virtual machine snapshots. The Azure Marketplace has premade STIG compliant Windows images, but the organization required the ability to apply STIG security hardening granularly with individual scripts for each audit scan finding.
</p>
<hr>

<h3><b>Technical Implementation:</b></h3>

<p>1. A Windows 10 Enterprise virtual machine was created in Azure cloud to be the basis of a golden image for future desktop deployments.</p>
<p>2. Performed a DISA STIG compliance audit scan on the endpoint with Nessus vulnerabilty scanner.</p>
<p>3. Reviewed audit scan findings and determined the steps required to implement DISA STIGs.</p>
<p>4. Developed scripts to automate the implementation of the STIGs from the audit scan findings.

- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000500.md">Automated Implementation of STIG WN10-AU-000500</a>: <br>The Application event log size must be configured to 32768 KB or greater.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000090.md">Automated Implementation of STIG WN10-00-000090</a>: <br>Accounts must be configured to require password expiration.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000031.md">Automated Implementation of STIG WN10-00-000031</a>: <br>Windows 10 systems must use a BitLocker PIN for pre-boot authentication.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000032.md">Automated Implementation of STIG WN10-00-000032</a>: <br>Windows 10 systems must use a BitLocker PIN with a minimum length of six digits for pre-boot authentication.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000107.md">Automated Implementation of STIG WN10-00-000107</a>: <br>Copilot in Windows must be disabled for Windows 10.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000145.md">Automated Implementation of STIG WN10-00-000145</a>: <br>Data Execution Prevention (DEP) must be configured to at least OptOut.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000155.md">Automated Implementation of STIG WN10-00-000155</a>: <br>The Windows PowerShell 2.0 feature must be disabled on the system.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-00-000175.md">Automated Implementation of STIG WN10-00-000175</a>: <br>The Secondary Logon service must be disabled on Windows 10.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AC-000005.md">Automated Implementation of STIG WN10-AC-000005</a>: <br>Windows 10 account lockout duration must be configured to 15 minutes or greater.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AC-000010.md">Automated Implementation of STIG WN10-AC-000010</a>: <br>The number of allowed bad logon attempts must be configured to 3 or less.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AC-000015.md">Automated Implementation of STIG WN10-AC-000015</a>: <br>The period of time before the bad logon counter is reset must be configured to 15 minutes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AC-000030.md">Automated Implementation of STIG WN10-AC-000030</a>: <br>The minimum password age must be configured to at least 1 day.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AC-000035.md">Automated Implementation of STIG WN10-AC-000035</a>: <br>Passwords must, at a minimum, be 14 characters.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000005.md">Automated Implementation of STIG WN10-AU-000005</a>: <br>The system must be configured to audit Account Logon - Credential Validation failures.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000010.md">Automated Implementation of STIG WN10-AU-000010</a>: <br>The system must be configured to audit Account Logon - Credential Validation successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000035.md">Automated Implementation of STIG WN10-AU-000035</a>: <br>The system must be configured to audit Account Management - User Account Management failures.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000045.md">Automated Implementation of STIG WN10-AU-000045</a>: <br>The system must be configured to audit Detailed Tracking - PNP Activity successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000050.md">Automated Implementation of STIG WN10-AU-000050</a>: <br>The system must be configured to audit Detailed Tracking - Process Creation successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000054.md">Automated Implementation of STIG WN10-AU-000054</a>: <br>The system must be configured to audit Logon/Logoff - Account Lockout failures.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000060.md">Automated Implementation of STIG WN10-AU-000060</a>: <br>The system must be configured to audit Logon/Logoff - Group Membership successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000081.md">Automated Implementation of STIG WN10-AU-000081</a>: <br>Windows 10 must be configured to audit Object Access - File Share failures.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000082.md">Automated Implementation of STIG WN10-AU-000082</a>: <br>Windows 10 must be configured to audit Object Access - File Share successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000083.md">Automated Implementation of STIG WN10-AU-000083</a>: <br>Windows 10 must be configured to audit Object Access - Other Object Access Events successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000084.md">Automated Implementation of STIG WN10-AU-000084</a>: <br>Windows 10 must be configured to audit Object Access - Other Object Access Events failures.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000085.md">Automated Implementation of STIG WN10-AU-000085</a>: <br>The system must be configured to audit Object Access - Removable Storage failures.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000090.md">Automated Implementation of STIG WN10-AU-000090</a>: <br>The system must be configured to audit Object Access - Removable Storage successes.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000505.md">Automated Implementation of STIG WN10-AU-000505</a>: <br>The Security event log size must be configured to 1024000 KB or greater.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-AU-000510.md">Automated Implementation of STIG WN10-AU-000510</a>: <br>The System event log size must be configured to 32768 KB or greater.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-CC-000005.md">Automated Implementation of STIG WN10-CC-000005</a>: <br>Camera access from the lock screen must be disabled.<br>
- <a href="https://github.com/noah-sec/project-descriptions/blob/main/WN10-CC-000007.md">Automated Implementation of STIG WN10-CC-000007</a>: <br>Windows 10 must cover or disable the built-in or attached camera when not in use.
</p>
<p>5. Executed the scripts on the endpoint with Configuration Manager (scripts from team resolved all 180 audit findings).</p>
<p>6. Saved a snapshot of the virtual machine.</p>
<p>7. Generalized the virtual machine with sysprep.</p>
<p>8. Deployed the golden image in Azure Virtual Desktop as a standalone managed image.</p>
<hr>

<h3><b>References:</b></h3>

<p>Microsoft <a href="https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-golden-image">guide</a> to creating an Azure Virtual Desktop golden image from a virtual machine.</p>
<p>Tenable Nessus compliance audit scan <a href="https://docs.tenable.com/nessus/Content/Compliance.htm">documentation</a>.</p>
<p><a href="https://www.disa.mil/~/media/files/disa/news/conference/cif/briefing/ia_stig_scap_and_data_metrics.pdf">Explanation</a> of DISA STIGs, USDOD requirements for implementation of DISA STIGs, and the STIG development cycle.</p>
<p>Microsoft <a href="https://learn.microsoft.com/en-us/intune/configmgr/apps/deploy-use/create-deploy-scripts">guide</a> to running scripts on endpoints using Configuration Manager in Microsoft Intune.</p>
<p>This project was completed as part of an internship as a Cloud Security Engineer.</p><hr>

<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>
