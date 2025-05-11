<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Automated Implementation of STIG WN10-00-000031</h1>

<!-- INTRODUCTION -->
<p align=center><i>"Windows 10 systems must use a BitLocker PIN for pre-boot authentication." <br>- STIG ID: WN10-00-000031</i></p>

<hr><br>

<!-- IMPLEMENTATION -->
<h3><b>Business Impact:</b></h3>

<p>
"If data at rest is unencrypted, it is vulnerable to disclosure. Even if the operating system enforces permissions on data access, an adversary can remove non-volatile memory and read it directly, thereby circumventing operating system controls. Encrypting the data ensures that confidentiality is protected even when the operating system is not running. Pre-boot authentication prevents unauthorized users from accessing encrypted drives." - STIG ID: WN10-00-000031
</p>


<!-- IMPLEMENTATION -->
<h3><b>Technical Implementation:</b></h3>

<p>
1. Scanned Windows 10 Azure VM with Tenable Nessus using DISA STIG compliance audit policy.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-scan.png">
2. Exported scan results to an <a href="https://github.com/noah-sec/projects/blob/main/assets/stig-report.pdf">audit report</a>.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-report.png">
3. Examined the <a href="https://stigaview.com/products/win10/v3r1/WN10-00-000031/">steps</a> to remediate vulnerability WN10-00-000031.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig3.png">
4. Developed a <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig3.ps1">PowerShell script</a> to automatically implement the STIG fix.<br>
  
```powershell
# Defining the common registry path:
$registryPath = "HKLM:\SOFTWARE\Policies\Microsoft\FVE"

# Configuring advanced startup (to use Bitlocker without TPM):
$valueName1 = "UseAdvancedStartup"
$valueData1 = 1

# Configuring startup PIN with TPM:
$valueName2 = "UseTPMPIN"
$valueData2 = 1

# Checking for registry path, if none then creating path:
if (-not (Test-Path $registryPath)) {
    Write-Host "Registry path '$registryPath' not found. Creating it now."
    New-Item -Path $registryPath -Force
} else {
    Write-Host "Registry path '$registryPath' already exists."
}

# Setting value for UseAdvancedStartup:
Set-ItemProperty -Path $registryPath -Name $valueName1 -Value $valueData1 -Type DWord -Force
# Setting output message:
Write-Host "Registry value '$valueName1' set to '$valueData1' at '$registryPath'."

# Setting value for UseTPMPIN:
Set-ItemProperty -Path $registryPath -Name $valueName2 -Value $valueData2 -Type DWord -Force
# Setting output message:
Write-Host "Registry value '$valueName2' set to '$valueData2' at '$registryPath'."
Write-Host "Script complete."
```
<br>
5. Ran the script and tested that the STIG fix was implemented.
</p><br>

<!-- TESTING 
### Testing and Validation-->

<!-- LESSONS 
### Lessons Learned-->

<!-- IMPROVEMENTS 
### Future Improvements-->

<!-- REFERENCES -->
<h3><b>References:</b></h3>

<p>Project code: <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig3.ps1">stig3.ps1</a></p>
<p>This project was completed as part of an internship as a Cybersecurity Support Engineer.</p><br>

<hr>

<div align=center><a href="https://github.com/noah-sec/projects/blob/main/vuln.md">Return to STIG project activities</a></div><br>
<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>

<!-- ANIMATED BOTTOM BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=footer" alt="footer"/>
