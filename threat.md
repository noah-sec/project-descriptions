<!-- ANIMATED TOP BANNER -->
<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=450a0a&height=120&section=header" alt="header"/>

<!-- TITLE -->
<h1 align=center>Threat Hunt Report (File Exfiltration with Tailscale)</h1>

<!-- INTRODUCTION -->
<p align=center><i><b>Detection of unauthorized Tailscale installation, file sharing, and file exfiltration.</b></i></p>
<p align=center><a href="https://github.com/noah-sec/projects/blob/main/threat-scenario.md">Threat Hunt Scenario</a></p>

<hr>

<!-- TECHNOLOGIES -->
<h3><b>Technologies:</b></h3>

- <b>Microsoft Azure</b> (cloud platform)
- <b>Microsoft Defender</b> (XDR)
- <b>Microsoft Sentinel</b> (SIEM)
- <b>Tenable Nessus</b> (vulnerability scanner)
- <b>Windows 10 Pro</b> (virtual machine)
- <b>Tailscale</b> (mesh overlay network, fileserver)
- <b>KQL</b> (SIEM query language)
- <b>YARA</b> (detection rule language)

<hr>

<!-- SCENARIO -->
<h3><b>Scenario:</b></h3>

Management suspects a data breach after observing unusual network traffic originating from an employee's workstation: persistent, encrypted connections to IP addresses in the 100.64.0.0/10 range, indicative of unauthorized Tailscale usage bypassing standard security controls. This activity coincides with a spike in outbound data from the workstation and follows anonymous reports of the employee seeking ways to transfer files undetected. The goal is to confirm the use of Tailscale, determine what sensitive data was exfiltrated via this covert tunnel, and secure the network against similar future incidents.

<hr>

<!-- OVERVIEW -->
<h3><b>Overview of IoC Discovery Plan:</b></h3>

1. Check ```DeviceFileEvents``` for any ```tailscale.exe``` file events
2. Check ```DeviceProcessEvents``` for any signs of installation or usage
3. Check ```DeviceNetworkEvents``` for any signs of outgoing connections over Tailscale port

<hr>

<!-- IMPLEMENTATION -->
<h3><b>Technical Implementation:</b></h3>

#### 1. Searched the `DeviceFileEvents` Table:

Searched for any file that had the string "secret" in the filename and discovered that the user "windows-admin" created a file called `secrets.txt` on the desktop.

**Query used to locate events:**

```kql
DeviceFileEvents 
| where DeviceName == "noah-windows10"  
| where InitiatingProcessAccountName == "windows-admin"  
| where FileName contains "secret"  
| order by Timestamp desc  
| project Timestamp, DeviceName, ActionType, FileName, FolderPath, SHA256, Account = InitiatingProcessAccountName
``` 

<br>

#### 2. Searched the `DeviceFileEvents` Table:

Searched for any file that had the string "tailscale" in it and discovered that the user "windows-admin" downloaded a Tailscale installer `tailscale-setup-1.82.5.exe`.

**Query used to locate events:**

```kql
DeviceFileEvents 
| where DeviceName == "noah-windows10"  
| where InitiatingProcessAccountName == "windows-admin"  
| where FileName contains "tailscale"  
| order by Timestamp desc  
| project Timestamp, DeviceName, ActionType, FileName, FolderPath, SHA256, Account = InitiatingProcessAccountName
``` 

<br>

#### 3. Searched the `DeviceProcessEvents` Table:

Searched for any `ProcessCommandLine` that contained the string "tor-browser-windows-x86_64-portable-14.0.1.exe". Based on the logs returned, an employee on the "noah-windows10" device ran the file `tailscale-setup-1.82.5.exe` from their Downloads folder, using a command that triggered a silent installation.

**Query used to locate events:**

```kql
DeviceProcessEvents  
| where DeviceName == "noah-windows10"  
| where ProcessCommandLine contains "tailscale-setup-1.82.5.exe"  
| project Timestamp, DeviceName, AccountName, ActionType, FileName, FolderPath, SHA256, ProcessCommandLine
```

<br>

#### 4. Searched the `DeviceProcessEvents` Table:

Searched for any indication that user "windows-admin" actually started the Tailscale service. There was evidence that the user executed the application. There was an instance of `tailscale.exe`.

**Query used to locate events:**

```kql
DeviceProcessEvents  
| where DeviceName == "noah-windows10"  
| where FileName has_any ("tailscale.exe")  
| project Timestamp, DeviceName, AccountName, ActionType, FileName, FolderPath, SHA256, ProcessCommandLine  
| order by Timestamp desc
```

<br>

#### 5. Searched the `DeviceNetworkEvents` Table:

Searched for indication that the Tailscale service was used to establish a connection using the known Tailscale port. It was found that an employee on the "noah-windows10" device successfully established a connection to the remote IP address `176.198.129.43` on port `41641`. The connection was initiated by the process `tailscale.exe`.

**Query used to locate events:**

```kql
DeviceNetworkEvents  
| where DeviceName == "noah-windows10"  
| where InitiatingProcessAccountName != "system"  
| where InitiatingProcessFileName in ("tailscale.exe")  
| where RemotePort in ("41641")  
| project Timestamp, DeviceName, InitiatingProcessAccountName, ActionType, RemoteIP, RemotePort, RemoteUrl, InitiatingProcessFileName, InitiatingProcessFolderPath  
| order by Timestamp desc
```

<hr>

<!-- TIMELINE -->
<h3><b>Event Timeline:</b></h3>

#### 1. File Creation - `secrets.txt` File:

- **Timestamp:** `2025-05-10T03:21:05.8251167Z`
- **Event:** The user "windows-admin" created a file named `secrets.txt` on the desktop, potentially indicating a list or notes with credentials or company intellectual property.
- **Action:** File creation detected.
- **File Path:** `C:\Users\windows-admin\Desktop\secrets.txt`

<br>

#### 2. File Download - `tailscale-setup-1.82.5.exe` File:

- **Timestamp:** `2025-05-10T03:23:33.6542989Z`
- **Event:** The user "windows-admin" downloaded a file named `tailscale-setup-1.82.5.exe` to the Downloads folder.
- **Action:** File download detected.
- **File Path:** `C:\Users\windows-admin\Downloads\tailscale-setup-1.82.5.exe`

<br>

#### 3. Process Execution - `tailscale-setup-1.82.5.exe` File:

- **Timestamp:** `2025-05-10T03:24:18.2165227Z`
- **Event:** The user "windows-admin" executed the file `tailscale-setup-1.82.5.exe` in silent mode, initiating a background installation of the Tailscale service.
- **Action:** Process creation detected.
- **Command:** `tailscale-setup-1.82.5.exe /S`
- **File Path:** `C:\Users\windows-admin\Downloads\tailscale-setup-1.82.5.exe`

<br>

#### 4. Process Execution - `tailscale.exe` File:

- **Timestamp:** `2025-05-10T03:26:59.7339123Z`
- **Event:** The user "windows-admin" executed the file `tailscale.exe` using the "serve" option, initiating a fileserver using the Tailscale service.
- **Action:** Process creation detected.
- **Command:** `tailscale serve C:\Users\windows-admin\Desktop\secrets.txt`
- **File Path:** `C:\Users\windows-admin\Downloads\tailscale-setup-1.82.5.exe`

<br>

#### 5. Network Connection - Tailscale Network:

- **Timestamp:** `2025-05-10T03:27:07.1147931Z`
- **Event:** A network connection to IP `176.198.129.43` on port `41641` by user "windows-admin" was established using `tailscale.exe`, confirming Tailscale network activity.
- **Action:** Connection success.
- **Process:** `tailscale.exe`
- **File Path:** `c:\Program Files\Tailscale\tailscale.exe`

<hr>

<!-- SUMMARY -->
<h3><b>Summary:</b></h3>

The user "windows-admin" on the "noah-windows10" device initiated and completed the installation of the Tailscale service. They created a file related to company secrets, `secrets.txt` on their desktop. They proceeded to launch the service with a fileserve option, and establish connections within the Tailscale network. This sequence of activities indicates that the user actively installed, configured, and used the Tailscale service, likely for file exfiltration purposes, with possible documentation in the form of the "secrets" file.

<hr>

<!-- RESPONSE -->
<h3><b>Response:</b></h3>

#### 1. Isolation:

Tailscale usage was confirmed on the endpoint "noah-windows10" by the user "windows-admin". The device was isolated.


#### 2. Notification:

Tailscale usage was confirmed on the endpoint "noah-windows10" by the user "windows-admin". The user's direct manager was notified.


#### 2. Detection Engineering:

Created YARA rules to import into Tenable Nessus vulnerability scanner for detection of the `tailscale.exe` process. <br>Detection rules YARA file: <a href="https://github.com/noah-sec/yara-toolbox/blob/main/tailscale.yar">tailscale.yar</a>

**Detection Rules:**

```yara
import "filepath"
// Rule to detect Tailscale executable files by path. This is set to critical severity because Tailscale can be used for file exfiltration.
rule Tailscale_Executable_Paths
{
    meta:
        description = "Detects Tailscale executable files in common installation paths"
         autora = "Noah Grayson"
        date = "2025-05-13"
        severity = "Critical"
    strings:
        $path1 = "C:\\Program Files\\Tailscale\\tailscale.exe" ascii wide
        $path2 = "C:\\Program Files\\Tailscale\\tailscaled.exe" ascii wide
    condition:
        any of them
}

// Rule to detect running Tailscale processes by name. This is set to critical severity because Tailscale can be used for file exfiltration.
rule Tailscale_Running_Process
{
    meta:
        description = "Detects running Tailscale processes"
        autora = "Noah Grayson"
        date = "2025-05-13"
        severity = "Critical"
    strings:
        $proc1 = "tailscale.exe" ascii wide
        $proc2 = "tailscaled.exe" ascii wide
    condition:
        for any $str in ($proc1, $proc2) : ( filepath contains $str or proc.name == $str ) // Syntax should be valid in modern YARA implementations.
}
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
