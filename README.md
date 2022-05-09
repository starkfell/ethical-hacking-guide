# Ethical Hacking in 6 hours

The goal is to shrink this - https://www.youtube.com/watch?v=fNzpcB7ODxQ into a 6 hour video. All Killer, No Filler!

<br/>

## A Day in the Life of an Ethical Hacker

Let's not even do this. This is just the presentation masturbation.

</br>

## Effective Notekeeping

Sample effective notekeeping tools

- Pen/Paper
- OneNote
- Private GitHub Repo

</br>

### Install a screenshot tool

```powershell
choco install greenshot
```

</br>

### Use Windows Snippet Tool

If using Windows 10 or higher, you can also use snippet (Windows Key + Shift + Alt)

</br>

## Important Tools

Incorporated into the section above.

</br>

## Networking Refresher: Introduction

</br>

### IP Address

Bullet Points:

- A Number used to identify a Host (PC, Laptop, Mobile Device) on a network.
- The Number can be **Public** which would identify the Host's Geographical Location on a **Public Network**.
- The Number can be **Private** which would identify the Host's Physical Location in a **Private Network** which are typically in an Office, Building or Home.

</br>

How do I find my Private IP Address?

Windows:

Click on Start and type in ```cmd``` and then type in ```ipconfig```. The Private IP Address of the Computer you are using will be displayed.

Linux:

From a terminal, type in ```ifconfig```.

<br/>

How do I find my Public IP Address?

Open a web browser and go to https://whatismyip.com. Notice that the Geographical Location where you are visting from will be displayed.

</br>

### MAC Address

The Media Access Control (MAC) address is a binary number used to identify a Hosts Network Adapters computer network adapters. These are embedded in the network hardware during the manufacturing process or stored in firmware and designed not to be modified. MAC Addresses were designed to remain fixed for a devices hardware whereas IP Addresses can be changed depending on what network the adapter associated with. 

An easy way to demonstrate this is to check your IP Address at home as compared to at work or school and you'll notice that the IP Address has probably changed whereas your MAC Address has not.

</br>

### TCP, UDP, Three-Way Handshake

TCP (Transmission Control Protocol)
- requires a connection to be established before data can be sent.
- Uses: World Wide Web, email, file transfers, remote administration
- Common Application Layer Protocols: DNS, FTP, HTTP, HTTPS, IMAP, POP3, SFTP, SMB, SMTP, SSH, Telnet

UDP (User Datagram Protocol) 
- doesn't require an existing connection does not setup a dedicated end-to-end connection.
- Uses: Network Discovery, Voice over IP, online video games, streaming media
- Common Application Layer Protocols: DHCP, DNS, IPTV, NTP, SNMP, TFTP

Three-Way Handshake
- Used to establish a standard TCP Connection.
- Step 1: a SYN message with a sequence value of (x) is sent from Point A to B.
- Step 2: Point B replies to A with a SYN-ACK message with a sequence number (y) and an acknowledgement number (x + 1).
- Step 3: Point A replies to B with an ACK message with an acknowledgement number (y + 1).
- Point A and B do not use a default sequence number (such as 0) to ensure that the connection doesn't reuse the same sequence number too soon.
- 
</br>

### Wireshark Filters

```text
# All Traffic except from 192.168.73.202 and Destination not 192.168.73.208
ip.addr != 192.168.73.202 && ip.dst != 192.168.73.180

#

#
```

### Common Ports and Protocols

TCP: DNS, FTP, HTTP, HTTPS, IMAP, POP3, SFTP, SMB, SMTP, SSH, Telnet

| Name     | Port      | Description |
|----------|-----------|-------------|
| DNS      | 53        |             |
| FTP      | 21        |             |
| HTTP     | 80        |             |
| HTTPS    | 443       |             |
| IMAP     | 143       |             |
| POP3     | 110       |             |
| SFTP     | 22        |             |
| SMB      | 139 + 445 |             |
| SMTP     | 25        |             |
| SSH      | 22        |             |
| Telnet   | 23        |             |

UDP: , , , , , 

| Name     | Port      | Description |
|----------|-----------|-------------|
| DHCP     | 67, 68    |             |
| DNS      | 53        |             |
| IPTV     | 80        |             |
| NTP      | 123       |             |
| SNMP     | 161       |             |
| TFTP     | 69        |             |


## How-To Install Kali Linux on Windows 10 (Developer Mode Enabled)

The instructions below have been tested on a Windows 10 Clean Install and fully patched with Developer Mode Enabled.

```powershell
# Copy/Paste everything below this line to install Chocolatey and Virtual Box.
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iwr https://chocolatey.org/install.ps1 -UseBasicParsing | iex
choco feature enable -n=allowGlobalConfirmation
choco install virtualbox
```

## Disable Windows 10 Updates

```powershell
wget https://github.com/WereDev/Wu10Man/releases/download/v4.4.0/Wu10Man_Installer.msi

```

```powershell
add-type -typedefinition "using System;`n using System.Runtime.InteropServices;`n public class PInvoke { [DllImport(`"user32.dll`")] public static extern bool SetSysColors(int cElements, int[] lpaElements, int[] lpaRgbValues); }";`n [PInvoke]::SetSysColors(1, @(1), @(0x000000))
Reg Add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\VisualEffects" /v "VisualFXSetting" /t REG_DWORD /d 2 /f

```

```powershell
$script = $(wget https://gist.githubusercontent.com/starkfell/9915cdd83c2b4af13aa18fa186d5acd5/raw/1bc3dace8d28abe27c77e59be013e14d2f872228/win10.custom.ps1 -UseBasicParsing).Content ; Invoke-Expression $script

```
