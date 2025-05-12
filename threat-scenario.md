<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Threat Scenario (File Exfiltration with Tailscale)</h1>

<!-- INTRODUCTION -->
<p align=center><i><b>Unauthorized Tailscale installation, file sharing, and file exfiltration.</b></i></p>

<hr>

<!-- STEPS TAKEN -->
<h3><b>Steps Taken to Create IoCs:</b></h3>

1. Download Tailscale (assuming the existance of a previously setup Tailscale tailnet): https://tailscale.com/download
2. Install it silently: ```tailscale-setup-1.82.5.exe /S```
3. Authenticate to the tailnet using browser or auth key.
4. Create a file on the desktop called ```secrets.txt``` and fill it with (fake) secrets like credentials.
5. Serve the file using ```tailscale serve /{PATH TO DESKTOP}/secrets.txt```
6. Download the file to another machine on the same tailnet.
7. Delete the file.

<hr>

<!-- TABLES -->
<h3><b>Tables Used to Detect IoCs:</b></h3>

| **Parameter**       | **Description**                                                              |
|---------------------|------------------------------------------------------------------------------|
| **Name**| DeviceFileEvents|
| **Info**|https://learn.microsoft.com/en-us/defender-xdr/advanced-hunting-deviceinfo-table|
| **Purpose**| Used for detecting Tailscale download and installation, and the secrets.txt file creation and deletion. |

| **Parameter**       | **Description**                                                              |
|---------------------|------------------------------------------------------------------------------|
| **Name**| DeviceProcessEvents|
| **Info**|https://learn.microsoft.com/en-us/defender-xdr/advanced-hunting-deviceinfo-table|
| **Purpose**| Used to detect the silent installation of Tailscale and the Tailscale service launching.|

| **Parameter**       | **Description**                                                              |
|---------------------|------------------------------------------------------------------------------|
| **Name**| DeviceNetworkEvents|
| **Info**|https://learn.microsoft.com/en-us/defender-xdr/advanced-hunting-devicenetworkevents-table|
| **Purpose**| Used to detect Tailscale network activity, especially related to tailscale.exe and port 41641.|

<hr>

<h3><b>Related KQL Queries:</b></h3>

```kql
// Installer name == tailscale-setup-1.82.5.exe
// Detect the installer being downloaded
DeviceFileEvents
| where FileName startswith "tailscale"

// Tailscale being silently installed
// Take note of two spaces before the /S
DeviceProcessEvents
| where ProcessCommandLine contains "tailscale-setup-1.82.5.exe  /S"
| project Timestamp, DeviceName, ActionType, FileName, ProcessCommandLine

// Tailscale service was successfully installed and is present on the disk
DeviceFileEvents
| where FileName has_any ("tailscale.exe", "tailscaled.exe")
| project  Timestamp, DeviceName, RequestAccountName, ActionType, InitiatingProcessCommandLine

// Tailscale service was launched
DeviceProcessEvents
| where ProcessCommandLine has_any("tailscale.exe", "tailscaled.exe")
| project  Timestamp, DeviceName, AccountName, ActionType, ProcessCommandLine

// Tailscale service is being used and is actively creating network connections
DeviceNetworkEvents
| where InitiatingProcessFileName in~ ("tailscale.exe", "tailscaled.exe")
| where RemotePort in (41641)
| project Timestamp, DeviceName, InitiatingProcessAccountName, InitiatingProcessFileName, RemoteIP, RemotePort, RemoteUrl
| order by Timestamp desc

// secrets.txt file was created and, changed, or deleted
DeviceFileEvents
| where FileName contains "secrets.txt"
```
<hr>
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
