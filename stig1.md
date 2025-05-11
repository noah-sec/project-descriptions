<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Automated Implementation of STIG WN10-AU-000500</h1>

<!-- INTRODUCTION -->
<p align=center><i>"Inadequate log size will cause the log to fill up quickly. This may prevent audit events from being <br>recorded properly and require frequent attention by administrative personnel." <br>- STIG ID: WN10-AU-000500</i></p>

<hr><br>

<!-- IMPLEMENTATION -->
<h3><b>Technical Implementation:</b></h3>

<p>
1. Scanned Windows 10 Azure VM with Tenable Nessus using DISA STIG compliance audit policy.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-scan.png">
2. Exported scan results to an <a href="https://github.com/noah-sec/projects/blob/main/assets/stig-report.pdf">audit report</a>.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig-report.png">
3. Examined the <a href="https://stigaview.com/products/win10/v3r1/WN10-AU-000500/">steps</a> to remediate vulnerability WN10-AU-000500.<br>
<img width=100% src="https://github.com/noah-sec/projects/blob/main/assets/stig1.png">
4. Developed a <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig1.ps1">PowerShell script</a> to automatically implement the STIG fix.<br>
  
```powershell
# Defining the registry path and registry value:
$registryPath = "HKLM:\SOFTWARE\Policies\Microsoft\Windows\EventLog\Application"
$valueName = "MaxSize"
$valueData = 32768

# Checking for registry path, if none then creating path:
if (-not (Test-Path $registryPath)) {
    New-Item -Path $registryPath -Force
}

# Setting value:
Set-ItemProperty -Path $registryPath -Name $valueName -Value $valueData -Type DWord

# Setting output message:
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

<p>Project code: <a href="https://github.com/noah-sec/powershell-toolbox/blob/main/stig1.ps1">stig1.ps1</a></p>
<p>This project was completed as part of an internship as a Cybersecurity Support Engineer.</p><br>

<hr>

<div align=center><a href="https://github.com/noah-sec">Return to STIG project activities</a></div><br>
<div align=center><a href="https://github.com/noah-sec">Return to main projects page</a></div>

<!-- ANIMATED BOTTOM BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=footer" alt="footer"/>
