<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Automated Implementation of STIG WN10-00-000107</h1>

<!-- INTRODUCTION -->
<p align=center><i>"Copilot in Windows must be disabled for Windows 10." <br>- STIG ID: WN10-00-000107</i></p>

<hr><br>

<!-- IMPLEMENTATION -->
<h3><b>Business Impact:</b></h3>

<p>
"Some features may communicate with the vendor, sending system information or downloading data or components for the feature. Turning off this capability will prevent potentially sensitive information from being sent outside the enterprise and uncontrolled updates to the system." - STIG ID: WN10-00-000107
</p><br>


<!-- IMPLEMENTATION -->
<h3><b>Technical Implementation:</b></h3>

<p>
1. Scanned Windows 10 Azure VM with Tenable Nessus using DISA STIG compliance audit policy.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-scan.png">
2. Exported scan results to an <a href="https://github.com/noah-sec/projects/blob/main/assets/stig-report.pdf">audit report</a>.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-report.png">
3. Examined the <a href="https://app.xylok.io/reference/benchmark/ms_windows_10_stig/check/19ae6a92-49ad-420b-b34c-b970951e67e1/?version=1b7985f3-177c-4283-a3cf-bcc484600224">steps</a> to remediate vulnerability WN10-00-000107.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig5.png">
4. Developed a <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig5.ps1">PowerShell script</a> to automatically implement the STIG fix.<br>
  
```powershell
# Defining the common registry path:
$registryPath = "HKLM:\Software\Policies\Microsoft\Windows\WindowsCopilot"

# Defining the registry value name, data, and type:
$valueName = "TurnOffWindowsCopilot"
$valueData = 1
$valueType = "DWord"

# Checking for registry path, if none then creating path:
if (-not (Test-Path $registryPath)) {
    Write-Host "Registry path '$registryPath' not found. Creating it now."
    New-Item -Path $registryPath -Force
} else {
    Write-Host "Registry path '$registryPath' already exists."
}

# Setting the "MinimumPIN" registry value:
Set-ItemProperty -Path $registryPath -Name $valueName -Value $valueData -Type $valueType -Force
Write-Host "Registry value '$valueName' set to '$valueData' at '$registryPath'."
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

<p>Project code: <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig5.ps1">stig5.ps1</a></p>
<p>This project was completed as part of an internship as a Cybersecurity Support Engineer.</p><br>

<hr>

<div align=center><a href="https://github.com/noah-sec/projects/blob/main/vuln.md">Return to STIG project activities</a></div><br>
<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>

<!-- ANIMATED BOTTOM BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=footer" alt="footer"/>
